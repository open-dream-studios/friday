# Brain Events — real-time WebSocket bus

Server-pushed events replace polling for every brain-related status
indicator in the UI. This doc is the pattern reference for new
surfaces.

## Why

Before: the Context tab had 8+ `useQuery` hooks polling every 5-30
seconds (`useJobBrain`, `runsQ`, `proposalsQ`, `useInterviewStatus`,
`useIntelRunsForJob`, `useBrainSchedule`, etc.). "Stale → Refreshing
→ Idle" pill transitions lagged by up to 30 seconds. Perceived UI
slowness was mostly polling latency, not real work.

After: server_a1 emits typed events at every state transition;
dev-cms broadcasts them on a single WebSocket; clients subscribe with
one hook and invalidate React Query cache keys. UI updates within
~10ms of the actual server-side change.

## Architecture

```
server_a1                       dev-cms server                  browser
────────                        ──────────────                  ───────
markJobRunCompleted()  ──POST──▶  /api/_internal/brain-events
     emitBrainEvent()             (x-agent-secret verify)
                                        │
                                        ▼
                                  broadcastBrainEvent()
                                        │
                                  Set<WebSocket>
                                        │
                                        ▼  (WS frame per client)
                                  /brain-events              ──▶  BrainEventsProvider
                                  (Firebase token auth)             ├─ useBrainEvent
                                                                    └─ useBrainEventsConnection
```

Three trust boundaries:

1. **server_a1 → dev-cms**: shared secret `x-agent-secret` (same
   envelope as the existing `/api/image-queue/agent-notify`). Fire-
   and-forget; missing config or network error → event silently
   drops, polling fallback catches within 60s.
2. **dev-cms broadcast**: in-process `Set<ConnectionMeta>` iterated
   per event. Zero persistence — an offline browser tab does not see
   events it missed, but its next `refetchInterval` fires within 60s.
3. **browser → dev-cms WS**: Firebase ID token in `?token=` query
   string, verified on upgrade. 401 → refused; token expires after
   50 min → client force-reconnects with a fresh token.

## Event catalog

Defined in `packages/blocks/brain/shared/events.ts`. Discriminated
union — no registry, no codegen. To add an event: append a member,
emit it from the relevant server_a1 service, subscribe in the
relevant hook.

| kind                    | emitted by                              | typical UI reaction                                                       |
| ----------------------- | --------------------------------------- | ------------------------------------------------------------------------- |
| `job_run.queued`        | `jobRunRepository.enqueueJobRun`        | invalidate runs list; button switches to "queued"                         |
| `job_run.started`       | `jobRunRepository.claimNextQueuedJobRun`| lock InFlightRoundCard start time; Pipeline row shows live counter        |
| `job_run.completed`     | `jobRunRepository.markJobRunCompleted/Failed/Cancelled` | invalidate runs list; wall_ms lands in the row |
| `proposal.created`      | `proposalRepository.createProposal`     | invalidate proposals list; Pipeline row flips to `pending_review`         |
| `proposal.merged`       | `proposalRepository.markProposalMerged` | invalidate proposals + every `generations/*` read-file query              |
| `proposal.rejected`     | `proposalRepository.rejectProposal`     | invalidate proposals list                                                 |
| `queue.processed`       | `hydrationConsumer.drainOnce`           | invalidate any surface that watches the hydration queue                   |
| `intelligence.updated`  | `proposalRepository.markProposalMerged` (when intelligence/* files landed) | invalidate questions/facts/confirmed/manifest reads |
| `schedule.derived`      | `scheduleDeriver.deriveScheduleForJob`  | invalidate schedule.json read; Schedule tab unlocks                       |

Every event carries `company` + `event_ts` (ISO); most carry
`job_path` for cheap client-side filtering.

## Client pattern

Mounted once in `src/layouts/appLayout.tsx`:

```tsx
<QueryProvider>
  <BrainEventsProvider>
    <App />
  </BrainEventsProvider>
</QueryProvider>
```

Subscribing anywhere below:

```tsx
import {
  useBrainEvent,
  useBrainEventsConnection,
} from "@open-dream/packages/blocks/brain/project";

function MyComponent({ company, jobPath }) {
  const queryClient = useQueryClient();
  const { ready: wsReady } = useBrainEventsConnection();

  // Reactive invalidation — fires within ms of the server transition.
  const onEvent = useCallback(() => {
    void queryClient.invalidateQueries({ queryKey: ["my-key"] });
  }, [queryClient]);
  useBrainEvent({ kind: "job_run.completed", company, job_path: jobPath }, onEvent);

  // Polling as safety net — 60s when WS is up, tighter when down.
  const { data } = useQuery({
    queryKey: ["my-key"],
    queryFn: () => fetchMyThing(),
    refetchInterval: wsReady ? 60_000 : 5_000,
  });
  ...
}
```

### Filter semantics

`{ kind, company?, job_path? }` — subscriber fires only when ALL
specified fields match. Omit `company` to receive events for every
company (rare — usually you want your own scope).

## Connection state

`useBrainEventsConnection()` returns `{ ready, reconnecting }`. The
LeftBar's `BrainEventsConnectionDot` uses this — green when ready,
amber when reconnecting, gray when offline. Any component can read
this and adjust polling cadence (`wsReady ? 60_000 : 5_000` pattern
above).

Reconnect: exponential backoff 1s → 30s cap, resets on successful
open. Token refresh: forced disconnect + reconnect every 50 min so
Firebase's 60-min ID-token expiry never surfaces as an error.

## Adding a new event

1. **Define** — append a member to the `BrainEvent` union in
   `packages/blocks/brain/shared/events.ts`. Add the kind string to
   the `KNOWN_KINDS` array in
   `packages/blocks/brain/server/eventIngest.ts` (validator).
2. **Emit** — from the relevant server_a1 service, call
   `emitBrainEvent({ kind, company, event_ts: ..., ... })`. `event_ts`
   should be the transition moment, not network time.
3. **Subscribe** — in the client hook or component that renders the
   affected state, call `useBrainEvent({ kind, company, job_path? },
   handler)`. Handler typically invalidates a React Query key.
4. **Fallback** — keep or add a `refetchInterval` on the underlying
   query, gated by `wsReady`. This is the safety net for a
   disconnected client.

## Files

- `packages/blocks/brain/shared/events.ts` — the union + matcher +
  envelope
- `packages/blocks/brain/server/eventBus.ts` — in-process broadcaster
- `packages/blocks/brain/server/eventIngest.ts` — HTTP ingest handler
- `packages/blocks/brain/server/eventWsUpgrade.ts` — WS upgrade + auth
- `packages/blocks/brain/project/eventsClient.ts` — provider + hooks
- `server_a1/services/brain/eventEmitter.ts` — server_a1 outbound POST
- `server/index.ts` — WS route + ingest mount

## Gotchas

- **`event_ts` vs network time**: emitters set `event_ts` at the
  moment of the DB write / file commit. Clients that display
  "N ago" durations should use `event_ts`, not `Date.now()`, so
  cross-client clock skew doesn't matter.
- **Naive UTC timestamps from server_a1**: some `started_at` /
  `completed_at` values are MySQL `DATETIME` (no timezone marker).
  Parse them with `parseServerTs()` from
  `src/modules/AppProjectsModule/_util/formatElapsed.ts` — it
  appends `Z` when no tz marker exists so Chrome doesn't interpret
  them as local time.
- **Missed events**: no replay buffer. Every client is best-effort.
  If you need durable guarantees, the underlying query's
  `refetchInterval` is the fallback; make sure it's set.
- **Cross-tab**: multiple browser tabs each hold their own socket.
  Broadcast fans out to all of them — no manual coordination needed.
- **HMR / dev**: modifying the `eventBus` module hot-reloads the
  broadcaster but drops the socket set. Client auto-reconnects
  within 1-2s. Not visible to the PM.
