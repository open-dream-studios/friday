# ROADMAP — the 6-series master plan

Last revised: 2026-07-08.

**Read [`BRAIN.md`](./BRAIN.md) first** for the architecture. This
file is the operational plan: 6 series, each with phases (labeled
Alpha, Bravo, Charlie, …), each phase with sweeps (labeled
Alpha.1, Alpha.2, …). Sweeps are single Claude Code loop
iterations, typically 3–8 per phase.

**This file is the living plan.** When the plan changes, edit
here. Do NOT append — rewrite the affected section.

**Companion docs:**
- [`SPRINT_TRACKER.md`](./SPRINT_TRACKER.md) — where we are.
- [`OBSERVABILITY.md`](./OBSERVABILITY.md) — UI design principles.

**Vocabulary:**
- **Series** — top-level chunk. 6 total (Series 1 through Series 6).
- **Phase** — subdivision of a series. Military lettering
  (Alpha, Bravo, Charlie, Delta, Echo, Foxtrot, Golf, Hotel, India).
- **Sweep** — a single Claude Code loop iteration. Labeled
  `<Phase>.<n>` (e.g. Alpha.3).

**Ship rules:**
- Series ship sequentially. Do not start Series N+1 until Series N
  is done.
- Every series' last phase is tests. Tests are built into that
  series' UI as a Test Panel. Results write to
  `friday/_tests/results/series-<n>-<phase>-<sweep>-<ts>.json`
  where Friday can Read them directly.
- Every UI ships with the series that needs it, not as a separate
  observability push.

---

# Series 1 — Data Trunk Foundation

Layer 1 of the brain rebuilt from scratch. Authoritative facts that
cannot be regenerated. This series makes the DB↔trunk mirror
airtight, formalizes the S3 pointer contract, gets extractions
deterministic, and gives Boss the two UIs that make raw data
visible: the Data Trunk Browser (files as they are) and the Sync
Health Monitor (drift detection). Nothing about intelligence yet —
this is about the facts layer. Every subsequent series presumes
this layer is solid.

## Phase Alpha — Manifest schema lockdown

Every field that lives in a work-unit `manifest.json` gets a Zod
schema, tenant-agnostic. This is the contract downstream consumers
depend on. Fields cover identity, scope dimensions, temporal
(start/end dates), status, and mirror bookkeeping. Naming stays
generic — no construction-specific terms in the schema itself;
tenants alias generic terms via their domain manifest.

- **Alpha.1** — Design the manifest field taxonomy (identity /
  scope / temporal / status / mirror bookkeeping). Draft the Zod
  schema at `packages/blocks/brain/shared/manifest.schema.ts`.
  Focus: no domain-specific field names; tenants pick their aliases.
- **Alpha.2** — Codegen TypeScript types from the Zod schema; wire
  them into `jobCatalog.ts`, `deriveJob.ts`, dispatcher, and every
  reader. Replace ad-hoc typing with generated types. Focus: no
  runtime behavior change, just type safety.
- **Alpha.3** — Add per-field mirror bookkeeping
  (`last_mirrored_at`, `source_hash`, `mirror_hash`) to the schema.
  Focus: the Sync Health Monitor (Phase Foxtrot) reads these to
  decide sync state.
- **Alpha.4** — Backfill script that walks every existing manifest,
  validates against the new schema, stamps missing bookkeeping
  fields with defaults. Focus: idempotent; dry-run first, then
  `--write`.

## Phase Bravo — DB↔trunk mirror rewrite

Replace the current ad-hoc write-through path with an idempotent,
per-field, hash-checked mirror. Every mirror write logs an event.
The mirror refuses silent overwrites when trunk-side content
drifted from what we expected. This closes the class of bugs where
a DB field never propagated (the `scheduled_start_date` bug lived
here).

- **Bravo.1** — Define the mirror contract:
  `mirrorField(work_unit, field, source_hash, value) →
  { written | skipped_unchanged | rejected_drift }`. Focus:
  idempotent by hash; refuse silent overwrites.
- **Bravo.2** — Rewrite `deriveJob.ts`, `brainAutoBootstrap.ts`,
  `jobRefresh.ts` to route every manifest write through the new
  API. Focus: no direct manifest mutations bypass the mirror.
- **Bravo.3** — Emit `mirror_write` / `mirror_skip` / `mirror_drift`
  events to per-WU `events.jsonl`. Focus: every mutation
  observable in the audit log.
- **Bravo.4** — Add a mirror-audit DB table (or periodic snapshot
  job) that Sync Health reads from. Focus: this is the source of
  truth for the UI badges.
- **Bravo.5** — Delete the legacy `notifyBrainTrunkOfJobChange` and
  all bypass paths. Focus: no dead code, no double-write surface.

## Phase Charlie — S3 pointer contract

Every uploaded binary produces a canonical `.ref.json` at upload
time containing content hash, size, DB row link, S3 key,
extraction status. Downstream agents + hydration consumers +
extraction pipeline read only the pointer; the binary is fetched
on demand and cached outside git. This is the single-source-of-
truth tying trunk slot ↔ S3 blob ↔ DB row.

- **Charlie.1** — Formalize + tighten the `.ref.json` schema
  against `_schemas/ref.schema.md`. Mandatory `content_hash`,
  `db.table`, `db.id`, `s3.bucket`, `s3.key`. Focus: reject any
  ref-write missing these.
- **Charlie.2** — Rewrite the document-upload path so `.ref.json`
  is atomic with the S3 upload-complete signal. Focus: no orphan
  S3 objects and no orphan pointers.
- **Charlie.3** — Add a periodic reconciler that walks every
  `.ref.json`, HEADs S3 to verify presence, and files a `note`
  event for any orphan. Focus: self-healing sanity check.

## Phase Delta — Extraction pipeline

Deterministic, content-hash-cached PDF/CSV/DOCX → text extraction.
Same input bytes never re-extract. Extracted `.txt` is a
first-class committed artifact next to its `.ref.json`. The
pipeline handles retries, tracks extraction failures, and emits
`extraction_completed` events for observability.

- **Delta.1** — Wrap the hydration consumer in a hash-gate: given a
  `.ref.json`, if `content_hash` matches an entry in the
  extraction cache table, copy the cached `.txt` instead of
  re-extracting. Focus: identical bytes never burn CPU twice.
- **Delta.2** — Add extraction status field to `.ref.json`
  (`extracted | failed | pending | unextractable`) + a `note`
  field for failure reasons. Focus: downstream code stops guessing
  why a `.txt` is missing.
- **Delta.3** — Emit `extraction_completed` / `extraction_failed`
  events. Focus: postmortem tooling can trace extraction latency
  + failure rates.
- **Delta.4** — Add a "reprocess extraction" admin endpoint (used
  by Sync Health UI later) that clears a hash from the cache and
  re-triggers extraction. Focus: recovery path when we ship an
  extractor fix.

## Phase Echo — Data Trunk Browser UI

Tree view of the trunk. Boss can navigate any tenant/context/WU
folder, preview file contents inline, see per-file metadata
(mirror source, hash, last written, ref pointer if binary), and
grep across the whole tree. Every file cross-links to its per-WU
events.jsonl and (for `.ref.json`) to the DB row.

- **Echo.1** — Build the tree API in dev-cms:
  `GET /api/trunk/tree?path=...` returns nested folder+file JSON.
  Focus: mirrors the filesystem exactly; no filtering.
- **Echo.2** — Build the file-read endpoint:
  `GET /api/trunk/file?path=...` returns content + metadata
  (mtime, size, hash, ref-linked-row if `.ref.json`). Focus: no
  size limit for text; blobs served as pointer info only.
- **Echo.3** — Build the tree view component (expand/collapse per
  folder, file-type icons, metadata sidecar on file click). Focus:
  fast, no re-fetch on expand.
- **Echo.4** — Build the inline text preview (renders `.md`,
  `.txt`, `.json`, `.jsonl`). Focus: syntax-highlight JSON,
  render markdown, tail JSONL newest-first.
- **Echo.5** — Build trunk grep: `POST /api/trunk/grep
  { pattern, path_prefix, case_sensitive }` → hits with 3-line
  context. Focus: ripgrep under the hood on server_a1.
- **Echo.6** — Add cross-links: `.ref.json` → DB row (opens admin);
  any file → per-WU events.jsonl. Focus: this is what makes the
  browser a debugger, not just a viewer.

## Phase Foxtrot — Sync Health Monitor UI

Per-work-unit table showing every mirrored field's status:
in-sync (green), drift (amber), never-mirrored (grey), rejected
(red). Timestamp of last check. Click any field to see mirror-audit
event history. A tenant-level rollup shows total drift count and
last-check.

- **Foxtrot.1** — API: `GET /api/trunk/sync-health?tenant=&work_
  unit=` returns per-field status rows read from the mirror-audit
  table. Focus: no live re-check unless requested.
- **Foxtrot.2** — API: `POST /api/trunk/sync-health/recheck
  { tenant, work_unit }` triggers on-demand hash re-computation +
  drift comparison. Focus: results land in the same audit table.
- **Foxtrot.3** — Build the per-WU health table (color-coded status
  badges + timestamps). Focus: sortable + filterable.
- **Foxtrot.4** — Build the tenant-level rollup card (drift count,
  last-full-check, alert level). Focus: this is what Boss glances
  at daily.
- **Foxtrot.5** — Add per-field event-history drawer: click a row,
  see the last N mirror events for that field. Focus: this is where
  "who changed this and when" lives.

## Phase Golf — Tests + test panel

Test Panel component embedded in the Sync Health UI. Each button
triggers an integrity test; each writes a JSON result to
`friday/_tests/results/series-1-<phase>-<sweep>-<ts>.json`. Tests
cover the entire series' load-bearing paths.

- **Golf.1** — Define the shared test-result JSON schema
  (test_id, tenant, work_unit, timestamp, pass/fail, actual,
  expected, notes). Focus: schema shared across all series' tests.
- **Golf.2** — Build the reusable Test Panel component (list of
  tests, "Run" button per test, last-run status + result
  preview). Focus: reused across every series' UI.
- **Golf.3** — Test: "Mirror integrity" — for a chosen WU, verify
  every manifest field's trunk value matches DB source. Focus:
  this is the golden path — if it fails after Bravo, something's
  broken.
- **Golf.4** — Test: "Extraction idempotency" — for a chosen
  `.ref.json`, force re-hydration, verify no new commit was
  produced (cached hit). Focus: proves Delta.1.
- **Golf.5** — Test: "Drift detection" — deliberately corrupt a
  mirrored field, verify Sync Health flips to `drift` on next
  check. Focus: end-to-end proof that monitoring works.
- **Golf.6** — Test: "Orphan reconciler" — plant a fake `.ref.json`
  pointing at a non-existent S3 key, verify reconciler catches it
  and files a note. Focus: proves Charlie.3.

---

# Series 2 — Intelligence Primitives

Layer 2 gets first-class treatment: rules, beliefs, and patterns
as entities with lifecycle (proposed → active → deprecated), full
provenance, review gates, staleness decay, and supersession
chains. Every AI-derived intelligence flows through the proposals
queue — no silent additions. Explorer and Proposals Queue are the
daily-use UIs. This is where the brain stops being static
markdown and starts being a living, self-updating system.

## Phase Alpha — Schema unification

One Zod schema per intelligence category (rule, belief, pattern)
covering all lifecycle states. Schemas shared across every scope
tier. Codegen'd TS types replace ad-hoc typing. Every existing
intelligence entry migrates via a backfill.

- **Alpha.1** — Formalize `rule.schema.md` into Zod; codegen
  types. Focus: unify with the doc that already exists.
- **Alpha.2** — Formalize `belief.schema.md` with lifecycle fields
  (status, verified_by_run_ids, decay_window_days). Focus: match
  the current belief schema doc.
- **Alpha.3** — Formalize `pattern.schema.md` into Zod; codegen
  types. Focus: patterns are new — schema must be clean from day
  one.
- **Alpha.4** — Backfill script reads every existing intelligence
  file, validates against the new Zod schema, patches missing
  fields with defaults. Focus: idempotent, dry-run first.

## Phase Bravo — Provenance graph

Every intelligence entry's `supports[]` becomes a queryable graph.
"Show me every belief that traces back to Will's audit
transcript." Nodes typed (rule, belief, pattern, source doc, prior
run). Edges typed (supports, contradicts, supersedes).

- **Bravo.1** — Design the provenance graph representation (JSON
  at `_index/provenance.json`, refreshed on any intelligence
  write). Focus: static index, cheap to load.
- **Bravo.2** — Build the index-refresh job that walks all
  intelligence entries, resolves `supports[]` targets, writes the
  graph. Focus: runs on every accept event.
- **Bravo.3** — Build the graph query API:
  `GET /api/intelligence/provenance?entry_id=...` returns
  forward + backward chains. Focus: powers the Explorer's
  "cited by / traces to" panels.

## Phase Charlie — Review-gate infrastructure

Proposal branches, queue rows, accept/reject/edit-then-accept
mutations, event-log emissions. Everything an agent proposes goes
through this gate. Human-authored entries can bypass via explicit
flag; agent-authored never can.

- **Charlie.1** — Formalize proposal branch naming per
  `CONVENTIONS.md` (already documented; enforce in code). Focus:
  reject non-conforming branches at the accept endpoint.
- **Charlie.2** — Add a `proposals` DB table (tenant, scope, kind,
  entry_id, branch, status, proposer, proposed_at, decided_by,
  decided_at, decision). Focus: this is the queue's source of
  truth.
- **Charlie.3** — API: `POST /api/proposals/accept
  { proposal_id, editor_notes? }` — merges branch, updates row,
  emits `<kind>_accepted`, refreshes provenance index. Focus:
  atomic.
- **Charlie.4** — API: `POST /api/proposals/reject { proposal_id,
  reason }` — deletes branch, updates row, emits `<kind>_rejected`.
  Focus: atomic.
- **Charlie.5** — API: `POST /api/proposals/edit-then-accept
  { proposal_id, edited_content }` — writes edit on branch,
  merges, emits `<kind>_edited` + `<kind>_accepted`. Focus:
  preserve the diff between proposal and edit for audit.

## Phase Delta — Auto-approval rules

Beliefs meeting `confidence ≥ 0.85` AND no contradiction
auto-approve. Rules and patterns NEVER auto-approve regardless of
confidence. Auto-approvals still emit events; PM can retroactively
reject via the queue.

- **Delta.1** — Build the auto-approval evaluator: given a
  proposal, walk contradictions (any active rule, any active
  same-scope-or-more-specific belief), return
  `{ approve: bool, reason }`. Focus: pure function, testable.
- **Delta.2** — Wire evaluator into `POST /api/proposals` so agent
  submissions get evaluated on write. Focus: no manual accept
  needed for high-confidence beliefs.
- **Delta.3** — Emit `belief_auto_approved` events with the
  evaluator's reason recorded. Focus: audit trail for automated
  decisions.

## Phase Echo — Staleness sweeps

Periodic job walks intelligence entries, recomputes
`source_signature` from current `supports[]` file contents, flips
`stale: true` on drift. Also flips stale when
`last_verified_at + decay_window_days` has elapsed with no
citation. Stale entries badge in the Explorer.

- **Echo.1** — Build the staleness evaluator (pure function on
  entry + current source hashes). Focus: testable, no side
  effects.
- **Echo.2** — Build the periodic sweep job (server_a1 cron, runs
  nightly). Focus: idempotent, safe to re-run.
- **Echo.3** — On stale flip, emit `<kind>_marked_stale` with the
  reason (source drift vs decay). Focus: distinguish the two
  causes.

## Phase Foxtrot — Supersession chains

New entries superseding old auto-maintain the chain.
`supersedes` on the new entry triggers `superseded_by` back-
pointer + status flip to `deprecated` on the old entry. History
preserved forever.

- **Foxtrot.1** — On proposal accept where `supersedes` is set,
  auto-write `superseded_by` on the old entry, flip old status to
  `deprecated`. Focus: atomic with the accept.
- **Foxtrot.2** — Explorer renders the supersession chain as a
  horizontal timeline. Click any entry in the chain to jump to
  its detail.

## Phase Golf — Intelligence Explorer UI

Tree of all rules/beliefs/patterns layered by scope. Search +
filter (dimension, tag, confidence, staleness, status). Per-entry
detail panel with content, provenance, cited-by, staleness signal,
supersession chain, in-place propose-edit.

- **Golf.1** — API:
  `GET /api/intelligence/list?tenant=&scope=&kind=` returns entries
  with lifecycle metadata (paginated, no full-body payload).
  Focus: fast list load.
- **Golf.2** — API: `GET /api/intelligence/entry?id=...` returns
  full entry + provenance + cited-by list. Focus: detail-panel
  payload.
- **Golf.3** — Build the tree view (scope tiers as expandable
  folders, entries as leaves). Focus: match Data Trunk Browser
  feel.
- **Golf.4** — Build the search + filter bar (fuzzy match on
  id/title/tags; filter chips for status/staleness/confidence).
  Focus: fast interactive filtering.
- **Golf.5** — Build the detail panel (content, provenance sub-
  panel, cited-by sub-panel, staleness badge, supersession
  timeline). Focus: dense but readable.
- **Golf.6** — Build the in-place "Propose Edit" button opening a
  diff editor, saving as a proposal branch. Focus: proposal flow
  triggered from UI, not just API.
- **Golf.7** — Cross-links: to Data Trunk Browser (`supports[]`
  source), to Run Postmortem (a cited run).

## Phase Hotel — Proposals Queue UI

Unified inbox of pending rule + belief + pattern + generation
proposals. Side-by-side diff. Evidence citations with click-
through. Batch operations for high-confidence multi-accept.

- **Hotel.1** — API: `GET /api/proposals?tenant=&status=pending`
  returns queue rows (sortable + filterable). Focus: light payload
  for fast list.
- **Hotel.2** — Build the queue list view (one row per proposal
  with kind icon, scope, proposer, evidence-count, proposed-at).
  Focus: scannable at a glance.
- **Hotel.3** — Build the diff viewer (proposed content vs current
  active version, or new-entry mode). Focus: syntax-highlight,
  per-line accept where feasible.
- **Hotel.4** — Build the batch-accept panel: select N proposals,
  one-click accept with a note. Focus: for high-confidence
  beliefs where PM just glances.

## Phase India — Tests + test panel

Explorer buttons trigger lifecycle tests. Results →
`friday/_tests/results/series-2-<ts>.json`.

- **India.1** — Test: "Full belief lifecycle" — seed a test
  belief, verify auto-approval decision, verify events land.
- **India.2** — Test: "Contradiction blocks auto-approve" — seed
  belief contradicting an active rule, verify NOT auto-approved.
- **India.3** — Test: "Staleness sweep flips" — drift a source
  file, run sweep, verify `stale: true`.
- **India.4** — Test: "Supersession chain" — accept a proposal
  that supersedes an existing entry, verify chain + status
  transitions.
- **India.5** — Test: "Provenance graph query" — accept a belief
  citing a specific source, verify forward + backward query
  returns correct nodes.

---

# Series 3 — Generic Scope Selector

Replace the hardcoded 100/200/300/400 priority ranks with a
dimensional scope-match engine declared per domain via a manifest.
This is where the brain stops being TCR-specific and becomes
swappable across any business. UI: Scope Match Inspector — the
debugging surface for "why did this rule match?"

## Phase Alpha — Domain manifest schema

Every domain declares its own dimensions, human labels, aliases in
`_domains/<name>/domain.json`. Zod schema for the manifest itself.

- **Alpha.1** — Design the domain manifest Zod schema (ordered
  dimensions list, per-dimension label + description + optional
  data-schema-ref). Focus: extensible.
- **Alpha.2** — Author `_domains/construction/domain.json`
  describing TCR (tenant, category, context, work_unit with
  construction aliases). Focus: reference implementation.
- **Alpha.3** — Server_a1 loader reads domain manifest on startup +
  on trunk change. Focus: hot-reload safe.

## Phase Bravo — Scope selector engine

Given a WU dimensional context + intelligence entries, walk
dimensions broad-to-specific, return matches sorted by specificity
+ explicit priority.

- **Bravo.1** — Design the engine's input/output types (context
  object, entries array, match trace output). Focus: match trace
  is the audit output.
- **Bravo.2** — Implement the matcher: for each entry, walk its
  scope tier, check dimensional predicates, compute specificity
  score, return sorted matches with trace. Focus: pure function,
  side-effect free, testable.
- **Bravo.3** — Handle explicit priority overrides (a rule can pin
  priority higher than its natural scope). Focus: rare but real
  edge case.
- **Bravo.4** — Add tie-breaking: same specificity + priority →
  by `authored_at` desc. Focus: deterministic.

## Phase Charlie — Trace-carrying match output

`applicable_rules.json` now includes the dimensional trace for
every matched entry. Downstream tooling can inspect why an entry
matched.

- **Charlie.1** — Update `applicable_rules.json` schema in
  `_schemas/` to include trace fields per entry. Focus: backward-
  compatible (add fields, don't remove).
- **Charlie.2** — Update intel_rebuild stage-A "applicable_rules"
  to emit the new format via the selector engine. Focus: no agent
  behavior change.

## Phase Delta — Parallel-verify vs legacy

During transition, every match runs through BOTH the old rank
engine and the new dimensional engine. Diverging results log a
warning; investigate every divergence before removing legacy.

- **Delta.1** — Wire legacy rank code and new selector into a
  comparison harness. Focus: run both, diff outputs, log
  divergences.
- **Delta.2** — Run for a week; investigate every divergence.
  Focus: fix root causes; no shipping until divergences drop to
  zero.
- **Delta.3** — Delete legacy rank code once clean. Focus: no
  dead code.

## Phase Echo — Scope Match Inspector UI

Pick a WU context, see every intelligence entry the selector
considered, matched or not, with the dimensional reason.

- **Echo.1** — API: `POST /api/intelligence/scope-match { tenant,
  context, entries? }` runs the selector, returns full trace.
  Focus: no side effects.
- **Echo.2** — Build the picker UI (tenant + dimensional context
  drop-downs populated from the domain manifest). Focus: works
  for any domain.
- **Echo.3** — Build the match-trace table (one row per candidate
  entry, columns for each dimension showing match/skip with
  reason). Focus: this is the debugging surface.

## Phase Foxtrot — Tests + test panel

Inspector buttons trigger match tests. Results →
`friday/_tests/results/series-3-<ts>.json`.

- **Foxtrot.1** — Test: "Construction match golden set" — 10 known
  WU contexts, assert expected entries with expected trace.
- **Foxtrot.2** — Test: "Fake secondary domain" — author
  `_domains/_test-hr/domain.json`, seed test entries, verify
  selector adapts.
- **Foxtrot.3** — Test: "Priority override" — seed entry with
  explicit priority > natural scope, verify respected.
- **Foxtrot.4** — Test: "Tie-breaking" — two entries with
  identical specificity + priority, verify `authored_at` desc
  breaks tie.

---

# Series 4 — Context Assembly & Handoff API

The brain's job is done when a workflow gets perfect context.
Given "prepare context for workflow W on work unit U," the brain
assembles the WU's data slice + intelligence slice + prior-
artifacts slice, snapshots for reproducibility, hands off. UI:
Context Preview — Boss sees exactly what a workflow would receive
before it fires. This is where the brain graduates from "storage"
to "context service."

## Phase Alpha — Handoff contract schema

JSON shape the workflow receives. Data / intelligence / prior-
artifacts / metadata sections. Zod schema. Version field for
future evolution.

- **Alpha.1** — Design the top-level shape (data, intelligence,
  prior_artifacts, metadata, snapshot_hash, version). Focus:
  extensible for domain-specific extras.
- **Alpha.2** — Data section: manifest fields + interview rounds +
  inputs list (paths + hashes). Focus: no raw file contents
  (workflow reads on demand).
- **Alpha.3** — Intelligence section: selected rules/beliefs/
  patterns with full text + trace. Focus: this is the biggest
  payload.
- **Alpha.4** — Prior-artifacts section: list of prior generations
  for this WU with metadata. Focus: workflow decides whether to
  read them.
- **Alpha.5** — Metadata section: tenant, WU id, workflow name,
  requested_at, snapshot_hash of the entire handoff. Focus:
  enables replay.

## Phase Bravo — Context assembler service

Server function `assembleContext(tenant, work_unit, workflow_spec)
→ HandoffContract`. Pure orchestration; no writes.

- **Bravo.1** — Implement the assembler (reads manifest, calls
  scope-selector, reads interview rounds + prior artifacts).
  Focus: no side effects.
- **Bravo.2** — Add per-workflow filters: some workflows want all
  patterns, some only rules. Workflow spec declares its filter.
  Focus: extensible.
- **Bravo.3** — Compute `snapshot_hash` from concatenated content
  of the entire handoff. Focus: deterministic; identical inputs
  → identical hashes.

## Phase Charlie — Cost estimator

Given a handoff contract, estimate token count and dollar cost per
model choice.

- **Charlie.1** — Build the token estimator (tiktoken-style
  approximation + correction factor per content type). Focus:
  within ±10% of actual.
- **Charlie.2** — Multiply by posted model rates (Sonnet, Opus)
  for input + output estimates using a config, not hardcoded
  values. Focus: rates update easily.
- **Charlie.3** — Include cost estimate in the handoff metadata.
  Focus: workflow can decide whether to run based on cost.

## Phase Delta — Snapshot + reproducibility

Every handoff snapshotted to a per-WU history file. Later replays
load the snapshot exactly.

- **Delta.1** — On assemble, write handoff to
  `<wu>/handoffs/<workflow>-<snapshot_hash>.json`. Focus: keyed
  by content hash so identical assembles don't duplicate.
- **Delta.2** — Add `getHandoffBySnapshot(hash)` reader. Focus:
  replay path.
- **Delta.3** — Periodic pruner for old handoffs (older than N
  days, unreferenced by any run). Focus: bounded growth.

## Phase Echo — Context Preview UI

Pick a WU + workflow name, see the full handoff contract, token
count, cost estimate.

- **Echo.1** — API: `POST /api/context/preview { tenant, work_
  unit, workflow }` returns the assembled contract. Focus: no
  side effects, no snapshot write on preview.
- **Echo.2** — Build the picker: tenant → WU → workflow (workflow
  list from the domain's generator catalog). Focus: works for
  any domain.
- **Echo.3** — Build the contract viewer (collapsible sections for
  data/intelligence/prior-artifacts, token count + cost
  prominent). Focus: dense but readable.
- **Echo.4** — Add "Copy JSON" and "Compare to last snapshot"
  buttons. Focus: debugging aids.

## Phase Foxtrot — Tests + test panel

Preview buttons trigger golden-context tests. Results →
`friday/_tests/results/series-4-<ts>.json`.

- **Foxtrot.1** — Test: "Golden handoff" — for a known WU +
  workflow, assert handoff matches expected snapshot byte-for-
  byte.
- **Foxtrot.2** — Test: "Snapshot determinism" — assemble twice,
  assert identical snapshot_hash.
- **Foxtrot.3** — Test: "Cost estimate ±10%" — assemble, estimate,
  run the actual workflow, compare estimate to actual.
- **Foxtrot.4** — Test: "Replay from snapshot" — load an old
  snapshot, verify contract matches file, verify workflow can
  run against it.

---

# Series 5 — Freshness, Efficiency, Cost Discipline

Brain does no pointless work. DB writes mark affected intelligence
dirty; refresh happens lazily on demand. Every generator is
diff-aware. Prompt cache preserved across generators of the same
WU. Budget gates block runs over budget. UIs: Cost + Capacity
Monitor + Freshness Dashboard. This series turns cost + latency
from firefighting into a monitored discipline.

## Phase Alpha — Dirty flag propagation

DB writes emit a "which WU intelligence is now stale" signal.
Downstream consumers respect it.

- **Alpha.1** — Add `intelligence_dirty` flag to WU intel manifest
  (bool + list of dirty categories: data, rules, beliefs,
  patterns). Focus: set on any relevant DB write.
- **Alpha.2** — On mirror write, evaluate whether the mirrored
  field affects intelligence; if so, flip dirty. Focus: define
  the "which fields matter" rule set.
- **Alpha.3** — On dirty-flag-consumer read (e.g., a workflow
  about to fire), if dirty, trigger a refresh before proceeding.
  Focus: lazy invalidation.

## Phase Bravo — Content-hash skip on every generator

Every generator (not just intel_rebuild) checks input hashes and
skips stages whose inputs are unchanged.

- **Bravo.1** — Extend intel_rebuild's manifest input-hash pattern
  to every other generator. Focus: standardize.
- **Bravo.2** — Add a `force` flag on every generator API to
  bypass the skip. Focus: manual override for debugging.
- **Bravo.3** — Log skip decisions to events.jsonl. Focus:
  observable.

## Phase Charlie — Prompt cache preservation

Same rendered context across sub-agents of the same WU whenever
possible. Byte-identical bytes cache-hit reliably.

- **Charlie.1** — Audit which generators produce identical
  rendered context but currently diverge. Focus: identify fix
  targets.
- **Charlie.2** — Refactor context assembly (from Series 4) to
  produce canonical bytes. Focus: byte-identical for cache.
- **Charlie.3** — Measure cache-read tokens per run; log to Cost
  Monitor. Focus: observability.

## Phase Delta — Cheap classifier gate

Small pre-flight call before expensive generators: "material
change since last successful run? If no, skip."

- **Delta.1** — Design the classifier prompt (Sonnet, ~2K tokens,
  structured JSON output). Focus: cheap, definitive.
- **Delta.2** — Wire before every expensive generator. Focus:
  skip when classifier says no.
- **Delta.3** — Log verdict + downstream skip/run to Cost Monitor.
  Focus: verify hit rate.

## Phase Echo — Budget gates + alerts

Per-tenant weekly budget. Block runs when exceeded. Alert on
approach.

- **Echo.1** — Add per-tenant weekly budget field to tenant
  manifest. Focus: configurable.
- **Echo.2** — Middleware on every generator dispatch compares
  current week spend to budget, blocks if over. Focus: hard stop.
- **Echo.3** — Alerts at 75% / 90% / 100% (event log + optional
  email). Focus: PM aware before block.

## Phase Foxtrot — Cost + Capacity Monitor UI

Per-week cost, cache-hit ratios, slowest runs, budget usage, per-
generator breakdown.

- **Foxtrot.1** — API: `GET /api/cost/report?tenant=&window=`
  aggregates brain_job_run + estimated cost + cache metrics.
  Focus: fast, cacheable.
- **Foxtrot.2** — Build the week-over-week cost view (bar chart +
  total). Focus: readable at a glance.
- **Foxtrot.3** — Build the per-generator breakdown. Focus:
  prioritization aid.
- **Foxtrot.4** — Build the budget gauge. Focus: prominent,
  action-triggering.

## Phase Golf — Freshness Dashboard UI

Per-WU "what's dirty" view with age-since-dirty and last-refresh
signals.

- **Golf.1** — API: `GET /api/freshness?tenant=` returns per-WU
  dirty status + last-refresh timestamps. Focus: aggregated.
- **Golf.2** — Build the WU list sorted by dirtiest first. Focus:
  PM sees where attention is needed.
- **Golf.3** — Add per-WU "refresh now" button. Focus: manual
  trigger.

## Phase Hotel — Tests + test panel

Monitor buttons trigger discipline tests. Results →
`friday/_tests/results/series-5-<ts>.json`.

- **Hotel.1** — Test: "Skip on unchanged inputs" — trigger a
  redundant generator run, assert skip decision + no new commit.
- **Hotel.2** — Test: "Budget gate blocks" — set tenant budget
  to $0, attempt a run, assert blocked with correct error.
- **Hotel.3** — Test: "Dirty flag propagates" — poison an input,
  assert intel manifest dirty flag flips.
- **Hotel.4** — Test: "Classifier skip rate" — run 10 redundant
  fires, assert classifier catches ≥8.
- **Hotel.5** — Test: "Prompt cache preserved" — run workflow
  twice quickly, assert second run has high cache_read ratio.

---

# Series 6 — Multi-Tenant Proof

Add a real second tenant in a non-construction vertical. Prove
tenant isolation. Prove the scope engine adapts. Discover meta-
patterns emerging across tenants. If the abstraction doesn't hold
here, everything before this needs revising. UIs: Tenant Manager
+ Cross-tenant Meta Explorer. This is the graduation exercise.

## Phase Alpha — Tenant provisioning flow

Creating a new tenant — declares dimensions, seeds starter rules,
live in one PM session.

- **Alpha.1** — Build `POST /api/tenants { name, domain_manifest }`
  — validates domain manifest, creates trunk folder, initializes
  tenant manifest. Focus: idempotent.
- **Alpha.2** — Provisioning wizard UI (step 1: name + domain,
  step 2: dimensions review, step 3: starter rules paste). Focus:
  end-to-end in one session.
- **Alpha.3** — Post-provision verification: run Series-1 golden
  tests against the new tenant. Focus: catch broken abstractions
  early.

## Phase Bravo — Isolation guarantees

Hard rule: no generator on Tenant A can read Tenant B's trunk or
DB.

- **Bravo.1** — Audit every filesystem tool the agent uses; add
  tenant-root guard rejecting paths outside the current tenant.
  Focus: server_a1 level.
- **Bravo.2** — Add tenant scoping to every DB query the harness
  makes on behalf of an agent run. Focus: no leaks.
- **Bravo.3** — Periodic isolation-audit job samples handoff
  contracts, verifies no cross-tenant paths appear. Focus:
  continuous verification.

## Phase Charlie — Second-tenant seed

Real starter rules + beliefs for the chosen domain. One working
workflow that consumes the handoff.

- **Charlie.1** — Boss picks the second domain (candidates: ops
  incident review, HR onboarding, legal case triage). Focus:
  real business need, not synthetic.
- **Charlie.2** — Author `_domains/<chosen>/domain.json` with
  dimensions matching natural business hierarchy.
- **Charlie.3** — Seed 5–10 starter rules + 2–3 beliefs. Focus:
  enough for a first workflow.
- **Charlie.4** — Wire one simple workflow analogous to
  task_graph_v2 but for the new domain that consumes the
  handoff. Focus: proves end-to-end.

## Phase Delta — Cross-tenant meta-patterns

Meta-layer above tenants: observations about the brain
infrastructure itself.

- **Delta.1** — Design the meta-pattern extraction generator
  (walks all tenants' brain_job_run + proposals rows, aggregates).
  Focus: no reading of tenant content, only brain-metadata.
- **Delta.2** — First meta-pattern: "auto-approval rate per tenant
  per belief-confidence-bucket." Focus: proves the pipeline.
- **Delta.3** — Second meta-pattern: "average time between
  proposal and PM decision, per kind." Focus: measures PM
  engagement.

## Phase Echo — Tenant Manager UI

List of tenants, per-tenant health/cost/status, provision-new-
tenant flow.

- **Echo.1** — API: `GET /api/tenants` returns list with rollup
  metrics (WU count, weekly cost, active proposals, drift count).
  Focus: aggregated.
- **Echo.2** — Build the tenant list view. Focus: click a tenant
  to drill into scope-specific UIs.
- **Echo.3** — Wire the provisioning wizard as "New Tenant"
  button. Focus: one entry point.

## Phase Foxtrot — Cross-tenant Meta Explorer UI

Same shape as Intelligence Explorer, scoped to meta-patterns.

- **Foxtrot.1** — API: `GET /api/meta/patterns` returns brain-
  infrastructure meta-patterns. Focus: separate from tenant
  intelligence.
- **Foxtrot.2** — Build the meta explorer view (list of meta-
  patterns, each with content + supporting stats). Focus:
  observability of the brain itself.

## Phase Golf — Tests + test panel

Tenant Manager buttons trigger multi-tenant tests. Results →
`friday/_tests/results/series-6-<ts>.json`.

- **Golf.1** — Test: "Cross-tenant read blocked" — attempt to read
  Tenant A's manifest from an agent run on Tenant B, assert
  rejection.
- **Golf.2** — Test: "Dimensional match on Tenant B" — run
  Series-3 match golden set adapted for Tenant B's domain.
- **Golf.3** — Test: "Meta-pattern extraction non-trivial" — run
  extractor, assert ≥1 pattern surfaces.
- **Golf.4** — Test: "Tenant provisioning end-to-end" — provision
  a synthetic tenant, run all Series-1 tests against it, tear
  down.

---

## Change log

- **2026-07-08** — Initial 6-series plan committed. Series 7
  (Production Hardening) removed as out of scope. Series >
  Phase (military lettering) > Sweep vocabulary locked. Test
  Panel is the last phase of every series.
