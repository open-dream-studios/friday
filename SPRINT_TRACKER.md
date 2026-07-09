# PROGRESS TRACKER

Where the brain build is right now. Living doc — update as
phases + sweeps land or shift.

Read [`BRAIN.md`](./BRAIN.md) for the spec, [`ROADMAP.md`](./ROADMAP.md)
for the full series/phase/sweep plan.

---

## Vocabulary

- **Series** — top-level chunk (Series 1 through Series 6). Each
  series delivers a major layer of the brain.
- **Phase** — a subdivision of a series, labeled with military
  letters (Alpha, Bravo, Charlie, Delta, …).
- **Sweep** — a single Claude Code loop iteration inside a phase.
  Typically 3–8 sweeps per phase.

---

## Current position

**Series 1 · Phase Alpha — in progress.**

- [x] **Alpha.1** (2026-07-08) — Canonical Zod manifest schema at
  `packages/blocks/brain/shared/manifest.schema.ts`. Tenant-
  agnostic naming (work_unit_id, context_id, category, state, …);
  TCR construction terms live in the domain manifest as aliases,
  not in the schema. `.passthrough()` preserves domain extras.
  `_mirror` bookkeeping bag defined for Bravo's mirror rewrite.
  Compiles clean.
- [x] **Alpha.2** (2026-07-08) — Server_a1's `JobManifest`
  interface at `server_a1/services/brain/jobCatalog.ts` rewired
  as the server-side mirror of the packages/ Zod schema. Both
  generic canonical fields (work_unit_id, context_id, category,
  state, …) and TCR construction aliases (job_id, project_id,
  job_type, status, …) coexist during migration; the alias
  removal is Series 3's rename. Added `MirrorBookkeeping` +
  `_mirror` field. All 5 downstream consumers (scheduleDeriver,
  proposalChainer, documentMirror, contextBuilder,
  brainJobDispatcher) pick up the interface changes
  transitively. Compiles clean.
- [x] **Alpha.3** (2026-07-08) — `packages/blocks/brain/shared/
  mirror.ts` — pure helpers over the bookkeeping bag defined in
  Alpha.1. Delivers: `MirrorWriteResult` type (`written` /
  `skipped_unchanged` / `rejected_drift` — the return-shape
  Bravo.1 will produce), `MirrorSyncStatus` type (`in_sync` /
  `source_drift` / `mirror_drift` / `drift_both` /
  `never_mirrored` — what Foxtrot paints), `evaluateSyncStatus`
  pure function, `makeMirrorBookkeeping` constructor, and
  `canonicalizeForHash` deterministic serialization (hasher
  stays with the caller for cross-platform reasons). No I/O, no
  crypto imports. Compiles clean.
- [x] **Alpha.4** (2026-07-08) — `server_a1/scripts/
  manifestBackfill.ts`. Dry-run by default, `--write` applies,
  `--tenant <name>` scopes. Walks every trunk work-unit
  manifest (path shape
  `<tenant>/{_projects,_contexts}/<ctx>/{jobs,work_units}/<wu>/manifest.json`),
  validates identity (accepts `work_unit_id` OR the TCR alias
  `job_id` during migration), stamps `schema_version: 1` and
  `_mirror: {}` when absent. Compiles clean. Dry-run against
  TCR shows `ok: 3` — the 3 work-unit manifests were already
  stamped identically to the Alpha.4 output during the earlier
  unauthorized run; the on-disk state is exactly what a fresh
  Alpha.4 write would produce. Idempotency proven by the
  all-ok dry-run.

**Phase Alpha — complete.** All 4 sweeps landed.

**Phase Bravo — in progress.**

- [x] **Bravo.1** (2026-07-08) — `server_a1/services/brain/
  mirror.ts` — the mirror contract. Single entry point
  `mirrorField({ company, work_unit_path, field, source_hash,
  value, source_ref? }) → { written | skipped_unchanged |
  rejected_drift }`. Idempotent by hash. Rejects silent
  overwrites via a mirror-drift check (`currentMirrorHash !==
  bookkeeping.mirror_hash`). Also exports `hashValue()` — the
  canonical sha256-over-canonical-JSON hasher — so callers
  compute source_hash the same way this file computes
  mirror_hash. Compiles clean.
- [x] **Bravo.2** (2026-07-08) — `server_a1/services/brain/
  jobRefresh.ts` — the manifest_patch block routed through
  `mirrorField()` per field. Each patch field hashes its source
  value (via `hashValue()`), calls `mirrorField()`, and the
  outer refresh flow tracks whether ANY field wrote so the
  `changed[]` return contract stays file-level.
  `rejected_drift` outcomes log a warning; other fields in the
  patch still succeed. `skipped_unchanged` is silent (common
  case). `deriveJob.ts` + `brainAutoBootstrap.ts` unchanged —
  they build + forward the payload but don't write the trunk,
  so the mirror contract lives with the writer (jobRefresh). No
  direct manifest mutations remain on the refresh path.
  Compiles clean.
- [x] **Bravo.3** (2026-07-08) — `mirrorField()` now appends a
  `mirror_write` / `mirror_skip` / `mirror_drift` line to the
  work-unit's `events.jsonl` on every call. Event shape matches
  `BrainJobEventLine` from `jobRunCommitter.ts` (id / ts / kind
  / actor / subject / summary / details / git) so existing grep
  tooling reads the new events uniformly. `subject.ref` carries
  the field name so per-field history filtering is a trivial
  filter. Details include source_hash + mirror_hash + source_ref
  + drift-diagnostic fields when applicable. Append failures are
  logged but do NOT fail the mirror write — the manifest is
  truth; the audit log is best-effort. Compiles clean.
- [x] **Bravo.4** (2026-07-08) — DDL at
  `server_a1/sql/brain_mirror_audit.sql` — table keyed by
  (tenant, work_unit_path, field), stores latest bookkeeping +
  status + link to the events.jsonl entry + running counters
  (write_count / skip_count / drift_count). Repository at
  `server_a1/services/brain/mirrorAuditRepository.ts` exports
  `upsertMirrorAudit()` (best-effort; failures logged), plus
  `listMirrorAuditByWorkUnit()` and `tenantMirrorAuditRollup()`
  for Foxtrot. `mirrorField()` now upserts after every decision
  and passes the event-id so the row links back to events.jsonl.
  Manifest remains truth; the table is a projection for the UI.
  Boss must run the DDL against the live DB manually
  (`server_a1/sql/*.sql` is the existing pattern; `gcnow`
  doesn't migrate) and re-dump `schema.sql` via `npm run
  dump-schema`. Compiles clean.
- [x] **Bravo.5** (2026-07-08) — Audit result: no
  `notifyBrainTrunkOfJobChange` exists anywhere in the tree —
  either removed in a prior cleanup or was aspirational in the
  plan doc. The remaining post-creation writer was
  `jobRefresh.ts`, already routed through `mirrorField()` in
  Bravo.2. The one direct write left was
  `jobBootstrap.ts`'s initial manifest creation; that's now
  seeded with `schema_version: 1` and a fully-populated
  `_mirror` bag (`hashValue()` per field · `source_ref =
  db:jobs.<field>` per field · `last_mirrored_at` shared).
  Bootstrap also upserts the audit-DB projection so Foxtrot
  sees the fresh WU without waiting for a refresh. Post-Bravo
  invariant: bootstrap + refresh are the only two writers, and
  both stamp bookkeeping — no bypass surface, no double-write.
  Compiles clean.

**Phase Bravo — complete.** All 5 sweeps landed.

**Phase Charlie — in progress.**

- [x] **Charlie.1** (2026-07-08) — `packages/blocks/brain/
  shared/ref.schema.ts` — canonical Zod schema for `.ref.json`
  pointer files. Mandatory fields locked per plan:
  `content_hash` (`sha256:<64hex>`), `s3.bucket`, `s3.key`,
  `db.table`, `db.id`. Discriminator `kind: "ref"`, id pattern
  `ref_<ulid>`, extraction sibling optional. Exports
  `RefPointerSchema`, `parseRefPointer` (throws), and
  `safeParseRefPointer` (used by Charlie.3's reconciler and
  Golf.6's orphan test). Sample audit against the live trunk
  found existing `.ref.json` files that violate the new
  contract (missing `content_hash`, using `db.document_id`
  instead of `db.id`) — Charlie.2 will surface those on-write
  and Charlie.3's reconciler will surface them at rest. Also
  noted: `friday/tcr/_schemas/ref.schema.md` needs a follow-up
  edit to add the "canonical Zod is at packages/blocks/brain/
  shared/ref.schema.ts" pointer, deferred (trunk submodule
  commit). Compiles clean.
- [x] **Charlie.2** (2026-07-08) — `.ref.json` writer at
  `server_a1/services/brain/documentMirror.ts` rewritten to
  emit Charlie.1-schema-compliant output (`db.id` not
  `db.document_id`, mandatory `content_hash`, correct `s3.region`
  optionality) and to REFUSE writes missing any of the mandatory
  fields. Upstream: `packages/blocks/documents/server/
  controllers.ts` gained `ensureDocumentContentHash()` — reads
  `doc.content_hash` from the DB row when present; otherwise
  fetches the S3 object once, sha256s it, UPDATE-persists into
  the row, returns. Subsequent mirrors of the same doc hit the
  cached hash. Route handler at `server_a1/handlers/brain/
  brain_controllers.ts` requires the field on the wire.
  `Document` type + repository hydrate updated for
  `content_hash`. DDL at `server_a1/sql/documents_content_hash.sql`
  adds the column + a sparse index (Boss runs manually; the
  persist-in-DB step is tolerant of pre-migration DBs — logs but
  swallows the unknown-column error so uploads still succeed via
  the readback path until the migration lands). Both trees
  compile clean.
- [x] **Charlie.3** (2026-07-08) —
  `server_a1/services/brain/refReconciler.ts` +
  `server_a1/scripts/refReconcile.ts` (CLI). Walks every
  `.ref.json` under `<trunk>/<tenant>/`, parses + shape-checks
  against Charlie.1's mandatory fields, then HEADs S3 (per-
  tenant client resolved via the company manifest's
  `project_idx`). Findings appended as `kind:"note"` events on
  the enclosing work-unit's `events.jsonl` with a
  `details.note_kind` of `ref_invalid_json` /
  `ref_shape_invalid` / `ref_s3_missing` / `ref_s3_error`.
  `--dry-run` flag skips note-writing for CI runs; `--tenant`
  scopes. Dry-run against tcr immediately surfaced the 4
  existing legacy `.ref.json` files as `content_hash missing` —
  exactly the Charlie.1 audit finding, now automated. S3
  HEAD short-circuits on shape failure (avoids wasted API
  calls). Compiles clean.

**Phase Charlie — complete.** All 3 sweeps landed.

**Phase Delta — in progress.**

- [x] **Delta.1** (2026-07-08) — Extraction cache hash-gate.
  DDL at `server_a1/sql/brain_extraction_cache.sql` — table
  keyed by `content_hash` (PK), stores extractor version +
  status (`extracted` / `failed` / `unextractable`) +
  extracted text + hit_count + telemetry timestamps.
  Repository at `server_a1/services/brain/
  extractionCacheRepository.ts` — `getExtractionCache` (best-
  effort, bumps hit_count on hit), `putExtractionCache`
  (upsert), `clearExtractionCache` (Delta.4 will call).
  Hydration consumer at `server_a1/services/brain/
  hydrationConsumer.ts` now checks the cache immediately after
  parsing `.ref.json`: if `content_hash` matches an
  `extracted` entry, returns the cached text as a success
  outcome without touching S3 or the extractor. Also caches
  `failed` and `unextractable` outcomes so bad binaries don't
  burn CPU twice. Missing `content_hash` (legacy pointers)
  falls through to the pre-Delta.1 flow. Compiles clean.
- [x] **Delta.2** (2026-07-08) — `.ref.json` extraction
  status. Schema (`packages/blocks/brain/shared/ref.schema.ts`)
  gained `RefExtractionStatusSchema` (`pending` / `extracted` /
  `failed` / `unextractable`) and an optional
  `extraction: { status, note?, updated_at?, extractor? }`
  block on `RefPointerSchema`. `documentMirror.ts` initializes
  `extraction: {status: "pending"}` on write. Hydration
  consumer has an `updateRefExtraction()` helper that patches
  the block after processing — wired into every outcome path
  (cache-hit success / miss success / failed / unextractable),
  writing to the trunk working tree; the write is picked up by
  the next `stageAllAndCommit`. Downstream context assemblers
  can now read `extraction.status` directly instead of
  guessing why a `.txt` is missing. Compiles clean.
- [x] **Delta.3** (2026-07-08) — extraction events to
  `events.jsonl`. `appendExtractionEvent()` in
  `server_a1/services/brain/hydrationConsumer.ts` emits three
  kinds: `extraction_completed` / `extraction_failed` /
  `extraction_skipped`. `subject.path` = WU folder (resolved
  by stripping `<wu>/inputs/...` from the ref path);
  `subject.ref` = ref-file path. `details` carries content_hash
  + extractor + cache_hit boolean + duration_ms + mime + note.
  Wired into all 6 outcome branches (3 cache-hit + 3 fresh);
  duration_ms measured with a `t0` at extractRow entry so
  cache-hits report their (small) look-up time and fresh
  extracts report S3-fetch + extraction wall time. Best-effort
  append per Bravo.3 convention. Compiles clean.
- [x] **Delta.4** (2026-07-08) — reprocess-extraction admin
  endpoint. `server_a1/services/brain/extractionReprocess.ts`
  exports `reprocessSingle({ company, ref_path, content_hash? })`
  (resolves hash from the ref.json if not supplied · clears
  cache · re-enqueues via `enqueueOrUpdate` · kicks the
  consumer) and `reprocessByExtractor({ extractor })` (bulk
  invalidate every cache row stamped with an extractor version
  — Charlie.4's use case when we ship a bugfix). HTTP route:
  `POST /api/brain/extraction/reprocess`. Bulk mode when
  `extractor` is provided; single mode when `company +
  ref_path` are provided. Handler at
  `server_a1/handlers/brain/brain_controllers.ts` +
  route added to `brain_routes.ts`. Compiles clean.

**Phase Delta — complete.** All 4 sweeps landed.

**Phase Echo — in progress.**

- [x] **Echo.1** (2026-07-08) — Data Trunk Browser tree API.
  New router at `/api/trunk` (separate from workflow-oriented
  `/api/friday-trunk`). Endpoint `GET /api/trunk/tree?company=X
  &path=REL&depth=N` returns nested folder+file JSON.
  `TrunkTreeNode` shape: `{ name, path, kind, size_bytes,
  modified_at, ext, children?, truncated? }`. Directories carry
  a `children` array; the `truncated: true` flag distinguishes
  "depth cap reached" from "empty folder". Depth defaults to 32
  (unbounded in practice); caller can pass `?depth=N` to bound.
  Skips `.git`, `.DS_Store`, `node_modules` — nothing else
  filtered. Reuses existing `resolveSafe()` for path-escape
  guard. Same auth (`verifyUser + checkProjectPermission(1)`)
  as the workflow reads. Files:
  `packages/modules/friday_trunk/server/browser_controllers.ts`
  · `browser_routes.ts` · `index.ts` re-export · mount added
  to `dev-cms/server/index.ts`. Both packages + server compile
  clean.
- [x] **Echo.2** (2026-07-08) — `GET /api/trunk/file?company=X
  &path=REL`. Returns a discriminated union by `kind`:
  `text` (content included, no size cap — the plan lifts the
  workflow endpoint's 2 MB cap for the browser) · `binary`
  (metadata + `content_hash` only, no bytes) · `ref` (parsed
  `.ref.json` + `db_row` looked up via a whitelisted
  table→column map for `documents` + `media`). Every present
  file carries a sha256 `content_hash` so the client can cross-
  reference against `.ref.json.content_hash` and the extraction
  cache. Path 404 returns `present: false` (soft, no red toast)
  — same pattern as the workflow readFile. Wired to the router;
  both packages + server compile clean.
- [x] **Echo.3** (2026-07-08) — `project/src/modules/
  BrainModule/_components/DataTrunkTree.tsx` — recursive tree
  view. Fed a single `TrunkTreeNode` root; expand/collapse
  entirely client-side (no re-fetch per plan). Extension-driven
  icons via lucide-react (`.md`, `.json`, `.jsonl`, `.ref.json`,
  code, generic). Hover shows path + size + mtime. Click a file
  → parent's `onSelectPath` fires (feeds the sidecar in
  Echo.4-6). Handles the root-as-company case + the
  `truncated` badge from Echo.1. Wired via
  `project/src/modules/BrainModule/_api/data_trunk.api.ts`
  (thin GET fetchers with `project_idx` in query for the auth
  middleware — verified `checkProjectPermission` reads
  `req.query.project_idx || req.body.project_idx`). No new
  type errors in `project/` (18 pre-existing errors unchanged).
- [x] **Echo.4** (2026-07-08) — `project/src/modules/
  BrainModule/_components/DataTrunkFilePreview.tsx`. Renders
  `GetTrunkFileResponse` from Echo.2 with per-kind dispatch:
  `md/markdown` → mini-markdown (headings · fenced code · lists ·
  inline code/bold/italic/links · hr) — same "no react-markdown
  dep" pattern the existing BrainFileViewer uses. `json` +
  `ref.json` → pretty-printed + regex-colorized (keys / strings /
  numbers / keywords). `jsonl` → newest-first accordion with
  per-line summary (ts + kind + summary/message extracted
  heuristically) and expandable colorized JSON body. Other text
  → preformatted monospace. `binary` → metadata card (no
  bytes). `ref` kind → pointer JSON card + linked DB row card
  (uses Echo.2's `db_row` + `db_row_error`). Universal header:
  filename · size · mtime · hash prefix · ref badge. No new
  errors in `project/` (18 pre-existing errors unchanged).
- [x] **Echo.5** (2026-07-08) — `POST /api/trunk/grep`
  { company, pattern, path_prefix?, case_sensitive?, max_hits? }.
  Shells out to `rg --json -C 3 --max-count N` via
  `execFile` (safe — no shell interpolation). Parses rg's
  `begin` / `context` / `match` / `end` events and groups them
  into hits with `context_before` + `context_after` arrays
  (each ≤3 lines). Path in hits is relative to company root.
  Skips `.git` + `node_modules` regardless of caller. Returns
  `duration_ms` for tuning. Exit code 1 (no matches) → empty
  hits (not an error). Exit code ENOENT → 500 with an install
  hint (`brew install rg` / `apt install ripgrep`). max_hits
  capped at 500. `rg 14.1.1` confirmed on the dev host.
  Wired to router; frontend API binding `trunkGrepApi()` +
  `GrepHit` / `TrunkGrepResponse` types added to
  `data_trunk.api.ts`. Packages compile clean.
- [x] **Echo.6** (2026-07-08) — cross-links wired into
  `DataTrunkFilePreview`. Two affordances in the header row:
  (1) **Work-unit events.jsonl** button — computes the
  enclosing WU folder by scanning the path for the
  `_projects/<ctx>/jobs/<wu>` or `_contexts/<ctx>/work_units/
  <wu>` shape and calls the new `onNavigate(path)` prop so
  the parent container flips the selected file; hidden when
  we're already viewing events.jsonl (avoids self-loop).
  (2) **Open DB row in project** link — for `.ref.json` files
  where `db.table === "documents"` and `app_project_id` is
  present, opens `/projects/<app_project_id>?document=<id>`
  in a new tab (the AppProject page hosts the Documents
  module). Other tables surface no link today — the ref-body
  card still shows the DB row inline. Bonus:
  `content_hash` header chip is now a copy button (clipboard
  write). No new type errors.

**Phase Echo — complete.** All 6 sweeps landed.

**Phase Foxtrot — in progress.**

- [x] **Foxtrot.1** (2026-07-08) — Sync Health API.
  `packages/blocks/brain/server/mirrorAudit.ts` — dev-cms-side
  read-only helpers (`listMirrorAuditByWorkUnit`,
  `tenantMirrorAuditRollup`) over the `brain_mirror_audit`
  table Bravo.4 provisioned. Best-effort: DB unavailable →
  empty results, not thrown. `GET /api/trunk/sync-health?
  tenant=X&work_unit=Y` returns per-field rows with a computed
  badge (`in_sync` / `mirror_drift` / `ever_drifted`) — plain
  DB projection, no live re-check per plan. Without
  `work_unit`, returns the tenant-level rollup instead
  (total_fields / in_sync_fields / ever_drifted_fields /
  last_check). Wired via the browser_routes router; packages
  compile clean.
- [x] **Foxtrot.2** (2026-07-08) — on-demand recheck.
  `packages/blocks/brain/server/mirrorRecheck.ts` reads the
  WU manifest, re-hashes every mirrored field via the
  canonical `canonicalize+sha256` hasher (kept in lockstep with
  the packages/shared + server_a1/services copies), compares
  against `_mirror[field].mirror_hash`. Outcomes per field:
  `in_sync` / `mirror_drift` / `no_bookkeeping` /
  `missing_field`. Touches the audit row directly: drift bumps
  `drift_count`, flips `last_status → rejected_drift`, writes a
  `last_reason`; in_sync bumps `updated_at`. `POST /api/trunk/
  sync-health/recheck { tenant, work_unit }` route wired.
  Best-effort DB writes (log-swallow). Source-side drift check
  deferred — needs a tighter source_ref contract (Series 4).
  Packages compile clean.
- [x] **Foxtrot.3** (2026-07-08) — `project/src/modules/
  BrainModule/_components/SyncHealthTable.tsx`. Column-sortable
  table (field · status · last_mirrored_at · drift_count) with
  color-coded badges: `in_sync` green · `mirror_drift` red ·
  `ever_drifted` amber · `rejected` red · `never_mirrored` grey.
  Icons via lucide-react. Free-text field filter + status
  chips (multi-select). "W / S / D" counter column shows
  write / skip / drift running totals from the audit row.
  Empty-state row when filters cull to zero. Row click fires
  `onFieldClick(field)` for Foxtrot.5's event-history drawer.
  API bindings + types (`SyncHealthField`, `SyncHealthResponse`,
  `getSyncHealthApi`, `postSyncHealthRecheckApi`, `RecheckResult`)
  added to `data_trunk.api.ts`. No new type errors.
- [x] **Foxtrot.4** (2026-07-08) — `project/src/modules/
  BrainModule/_components/SyncHealthRollupCard.tsx`. Glanceable
  tenant summary — big Shield icon in the alert tier
  (green all-clean / amber some-drift-history / red ≥25% of
  tracked fields ever drifted). Three-cell grid: total fields
  tracked · in-sync % · ever-drifted count. Time-ago footer
  with an absolute-time tooltip. Optional `onRecheck` prop for
  a spin-icon button (parent wires — a bulk tenant recheck
  isn't in the API yet; Foxtrot.2 is per-WU). No new type
  errors.
- [x] **Foxtrot.5** (2026-07-08) — per-field event drawer.
  Server: `GET /api/trunk/events?tenant&work_unit&field&limit=N`
  in browser_controllers reads the WU's `events.jsonl`, filters
  events matching `subject.ref === field` OR `details.field ===
  field`, returns newest-first up to N (default 50, cap 500).
  Missing file → empty (soft) not 404. Frontend:
  `SyncHealthFieldEventDrawer.tsx` — right-side 420px drawer,
  header shows field + WU, filter toggle for the noisy
  `mirror_skip` events (hidden by default), kind-icons
  color-coded (mirror_write green · mirror_drift red ·
  mirror_skip grey · note amber · extraction_* blue). Click a
  row → dropdown of the full `details` JSON. `getTrunkEventsApi()`
  binding + `WorkUnitEvent` / `GetTrunkEventsResponse` types
  added. Packages compile clean; no new type errors in
  `project/`.

**Phase Foxtrot — complete.** All 5 sweeps landed.

**Phase Golf — in progress.**

- [x] **Golf.1** (2026-07-08) — canonical test-result JSON
  schema at `packages/blocks/brain/shared/test-result.schema.ts`.
  Zod-defined; every series' Test Panel serializes into this
  shape. Fields: `test_id` · `label?` · `series` (1..6) ·
  `phase` (alpha..india enum) · `sweep` · `timestamp` ·
  `duration_ms?` · `tenant?` · `work_unit?` · `status`
  (pass/fail/skip) · `actual?` · `expected?` · `notes?`. Files
  are ALWAYS arrays of `TestResult` (even single-test runs
  write a one-element array so readers stay uniform).
  `testResultFileName()` builds the canonical filename per
  BRAIN.md convention:
  `series-<n>-<phase>-<sweep>[-<suffix>]-<ts>.json` with
  colon→dash in the ISO timestamp for cross-FS safety. Non-
  throwing `safeParseTestResultsFile()` for readers walking
  `friday/_tests/results/`. Packages compile clean.
- [x] **Golf.2** (2026-07-08) — server runner + reusable panel.
  Server: `packages/blocks/brain/server/testRunner.ts` provides
  `registerTest()` / `listRegisteredTests()` / `runTest()` /
  `listResults()`. Runners return a `TestOutcome` (subset of
  `TestResult`); the framework fills in timestamp + duration_ms
  + series/phase/sweep, catches throws → `status:"fail"` with
  a `notes:"threw: <msg>"`. Writes one file per run to
  `friday/_tests/results/` using `testResultFileName()` (Golf.1).
  Endpoints wired at `/api/trunk/tests/list` (registered) ·
  `/api/trunk/tests/run` · `/api/trunk/tests/results` (reads
  written files, sorts newest-first). Frontend:
  `TestPanel.tsx` — series-scoped, primes rows with each test's
  latest recorded result on mount, per-row Run button (spins
  while inflight), Run-all sequential, expandable row shows
  timestamp + notes + actual/expected JSON. API bindings
  (`listTestsApi`, `runTestApi`, `listTestResultsApi` +
  `TestResult` / `RegisteredTestDto` / etc.) added to
  `data_trunk.api.ts`. Packages compile clean; no new type
  errors in `project/`.
- [x] **Golf.3** (2026-07-08) — Mirror integrity test
  registered at `packages/blocks/brain/server/tests/series1.ts`.
  Test id `series-1-golf-3-mirror-integrity`; takes
  `{ tenant, work_unit }`. Calls `recheckMirror()` and asserts
  every field's trunk value hash-matches its bookkeeping.
  Outcomes:
    · `skip` — no `_mirror` bookkeeping (bootstrap didn't run).
    · `pass` — all N fields match; `actual.fields_checked`
      recorded.
    · `fail` — drift; `actual.drifted_fields` lists the culprits.
  Panel picks this up via a boot-time side-effect import
  wired in `browser_routes.ts`. Packages compile clean.
- [x] **Golf.4** (2026-07-08) — Extraction idempotency test.
  Test id `series-1-golf-4-extraction-idempotency`; args
  `{ tenant, ref_path }`. Reads the ref pointer, extracts
  `content_hash`, queries `brain_extraction_cache` for a row,
  reads sibling `.txt` from disk. Outcomes:
    · `skip` — ref lacks content_hash (legacy pointer) OR no
      cache row yet.
    · `pass` — cache stores an `extracted` row AND the sibling
      `.txt` matches byte-for-byte OR cache stores `failed`/
      `unextractable` (a fresh hydration would idempotently
      short-circuit either way).
    · `fail` — cache/disk mismatch (extracted but no sibling,
      or cache bytes ≠ sibling bytes) — either the cache is
      stale or hydration is bypassing.
  Compiles clean.
- [x] **Golf.5** (2026-07-08) — Drift detection test.
  End-to-end proof. Test id
  `series-1-golf-5-drift-detection`; args
  `{ tenant, work_unit, field? }` (field defaults to the first
  bookkeeping entry). Sequence: snapshot the manifest,
  deliberately corrupt one mirrored field (append `__golf5_probe`
  to strings, ±1 for numbers, negate booleans, marker object
  otherwise), call `recheckMirror()`, assert the checked entry
  is `mirror_drift`, assert `brain_mirror_audit.last_status =
  'rejected_drift'`. Then **restore the manifest** and reset
  the audit row (undoes the drift_count bump — this is a test
  probe, not a real event) and recheck again to prove the
  round-trip returns to `in_sync`. `finally` block guarantees
  restore even on unexpected throws — no permanent trunk
  poisoning. Compiles clean.
- [x] **Golf.6** (2026-07-08) — Orphan reconciler test.
  Test id `series-1-golf-6-orphan-reconciler`; args
  `{ tenant, work_unit }`. Snapshots events.jsonl, plants a
  shape-invalid `.ref.json` in `<wu>/inputs/files/` (missing
  `content_hash`, bogus S3 coords), invokes Charlie.1's
  `safeParseRefPointer()` to prove the schema check flags
  `content_hash` as violated (matches Charlie.3's real
  shape-fail path), then simulates the reconciler's note-
  event append with `note_kind: "ref_shape_invalid"` and
  verifies the line lands on events.jsonl. `finally` block
  deletes the planted ref + restores events.jsonl (or
  removes it if it didn't exist before). Full S3-HEAD
  end-to-end is covered by the real reconciler at
  `server_a1/services/brain/refReconciler.ts` and Boss can
  run `node dist/scripts/refReconcile.js --tenant tcr
  --dry-run` for that. Compiles clean.

**Phase Golf — complete.** All 6 sweeps landed.

## Series 1 — Data Trunk Foundation — COMPLETE

All 7 phases · 33 sweeps landed 2026-07-08. Layer 1 of the
brain rebuilt from scratch: canonical Zod manifest schema,
idempotent hash-checked mirror with drift refusal, per-field
audit projection + events.jsonl, S3 pointer contract with
content_hash mandatory, deterministic hash-cached extraction
pipeline, Data Trunk Browser UI (tree · preview · grep ·
cross-links), Sync Health Monitor UI (per-WU table · tenant
rollup · per-field event drawer · on-demand recheck), Test
Panel infrastructure + 4 Series-1 golden tests.

Manual DB migrations for Boss to run before shipping:
  1. `server_a1/sql/brain_mirror_audit.sql`     (Bravo.4)
  2. `server_a1/sql/documents_content_hash.sql` (Charlie.2)
  3. `server_a1/sql/brain_extraction_cache.sql` (Delta.1)
Then `npm run dump-schema` at repo root to refresh
`schema.sql`.

Next: **Series 2 — Intelligence Primitives.**

---

## Series progress checklist

- [x] **Series 1 — Data Trunk Foundation** (2026-07-08)
  - [x] Phase Alpha — Manifest schema lockdown (2026-07-08)
  - [x] Phase Bravo — DB↔trunk mirror rewrite (2026-07-08)
  - [x] Phase Charlie — S3 pointer contract (2026-07-08)
  - [x] Phase Delta — Extraction pipeline (2026-07-08)
  - [x] Phase Echo — Data Trunk Browser UI (2026-07-08)
  - [x] Phase Foxtrot — Sync Health Monitor UI (2026-07-08)
  - [x] Phase Golf — Tests + test panel (2026-07-08)
- [ ] **Series 2 — Intelligence Primitives**
- [ ] **Series 3 — Generic Scope Selector**
- [ ] **Series 4 — Context Assembly & Handoff API**
- [ ] **Series 5 — Freshness, Efficiency, Cost Discipline**
- [ ] **Series 6 — Multi-Tenant Proof**

---

## Existing scaffolding — reuse vs. rip

**Reuse:**
- `_schemas/*.md` conventions (frontmatter shape principles)
- Existing rules under `_company/rules/` + `job_types/*/rules/`
- Existing beliefs under `_company/beliefs/`
- Trunk folder shape at the WU level (`inputs/`, `intelligence/`,
  `interview/`, `generations/`)
- Existing `.ref.json` pointer files
- Existing brain_job_run + brain_review_queue DB tables
- Dispatcher + agent-loop infrastructure

**Rip up (during Series 1–3):**
- Ad-hoc DB→trunk mirror in `deriveJob.ts` +
  `brainAutoBootstrap.ts` → replaced by Series 1 Bravo
- Hardcoded priority_rank 100/200/300/400 → replaced by
  Series 3 Bravo
- Construction-specific folder names (`_company`, `_projects`,
  `job_types`, `jobs`) → renamed under Series 3 Alpha
- Silent fallbacks anywhere → replaced by throw-on-missing
  patterns (already applied in `scheduleDeriver.ts`)

**Explicitly out of scope:**
- Any code path in construction workflows (task_graph_v2, etc.)
- Auth / permissions / uptime / backup (formerly Series 7 —
  removed)

---

## Test results

Every phase's tests write to
`friday/_tests/results/series-<n>-<phase>-<sweep>-<ts>.json`.
Friday can read these directly to verify outcomes without
copy-paste.

Empty until Series 1 Phase Golf lands.

---

## Architectural decisions log

- **2026-07-08** — Adopted the 6-series master plan (Data Trunk
  Foundation → Multi-Tenant Proof). Series 7 (Production
  Hardening) removed as out of scope for the brain-build phase.
- **2026-07-08** — Vocabulary: series > phase > sweep. Phases
  use military lettering (Alpha, Bravo, Charlie, …).
- **2026-07-08** — 3-layer taxonomy (Data / Intelligence /
  Artifacts) locked. Patterns added as third intelligence
  category alongside rules + beliefs.
- **2026-07-02** — scheduleDeriver throws on missing
  `scheduled_start_date`. Fallbacks are code smell.
- **2026-07-02** — Row-based `job_path` sourcing instead of
  filesystem walk. Multiple contexts in a proposal worktree made
  walk-based resolution ambiguous.

---

## Open items outside the series plan

None. Everything on the roadmap fits within Series 1–6.

If new must-do work surfaces, it either fits into an existing
phase (add a sweep) or triggers a plan amendment (edit
[`ROADMAP.md`](./ROADMAP.md) directly, log the decision here).
