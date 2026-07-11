# ARCHITECTURE — the materialize contract

Companion to [`BRAIN.md`](./BRAIN.md). This is the "how it works"
for humans. When you touch anything under `friday/` on disk from
code, read this first.

---

## The contract

**Disk is a materialized view.** DB owns row facts. S3 owns blob
bytes. Trunk on disk is regenerated from those two sources on
demand. Every visible file under `friday/<project_id>/…` — every
folder, every PDF, every intel JSON — reaches disk through exactly
one function.

```
DB rows  ┐
         ├──► materializeProject(project_idx) ──► friday/<project_id>/…
S3 bytes ┘
```

Nothing else writes there. No hooks. No per-mutation mirrors. No
"partial resync" paths. Every drift heals on the next materialize.

---

## The writer

`server_a1/services/brain/materialize.ts`.

Signature:

```ts
materializeProject(project_idx: number, opts?: {
  reason?: string;    // for the commit message + logs
  force?: boolean;    // bypass "no changes" short-circuit
}): Promise<MaterializeReport>;
```

What it does, in order:

1. **Load DB state, single transaction.** Reads `projects` row for
   the project_id, then `app_projects`, `jobs`, `job_definitions`
   (recursive on `parent_job_definition_id`), `project_folders`
   (scopes `documents` and `media`), `documents`, `media`,
   `file_link`, `media_link`.
2. **Compose target tree in memory.** Turns the rows into an
   in-memory representation of the desired disk layout. See
   [`DATA_MODEL.md`](./DATA_MODEL.md) for the row→path rules.
3. **Preserve intel + artifact leaves.** Reads existing intel JSONs
   (`facts.json`, `rules.json`, `beliefs.json`), foundation prose
   (`CLAUDE.md`), and artifact folders at every entity node — those
   are trunk-native, never regenerated from DB. Kept in-place through
   the wipe/rebuild.
4. **Wipe the project subtree.** `rm -rf friday/<project_id>/*`
   except `.git`. Yes, everything else. Intel + artifacts are
   restored from the in-memory snapshot in step 6.
5. **Rebuild the folder tree.** Every entity folder + every
   `project_folders` row gets a directory. Intel JSONs stubbed to
   `{}` at fresh entity folders.
6. **Restore preserved leaves.** Intel + artifacts written back into
   their new folder positions.
7. **Materialize blob bytes.** For each `documents` / `media` row,
   compute target path from folder ancestry, resolve the file via
   content-addressed cache (below), hardlink or copy into place.
8. **Write `data.json` at every entity node.** Load referenced
   customers, employees, and documents once. Compose the entity's
   typed columns + resolved FKs + parsed `profile` JSON per the
   contract in [`DATA_MODEL.md`](./DATA_MODEL.md#datajson-shape).
   Not preserved — regenerated on every materialize.
9. **Commit or skip.** `git status --porcelain` → if empty, exit
   with `report.no_changes = true`. Otherwise
   `git add -A && git commit -m "materialize project_idx=N ({reason})"`.

Returns a `MaterializeReport` with counts (folders_created,
documents_materialized, bytes_downloaded_from_s3, commit_sha, ms_elapsed).

---

## The cache

Blob download from S3 is expensive. We do it once per blob, ever.

`server_a1/services/brain/cache.ts`:

- Root: `~/.friday-cache/` (configurable via
  `FRIDAY_CACHE_ROOT` env).
- Key: `sha256(s3_key)` — deterministic per (bucket, key) pair.
- Layout: `~/.friday-cache/<hash>.<ext>` where ext is derived from
  the DB row's `original_name` or `mime_type`.
- Reads: `ensureCached(project_idx, s3_key, ext)` — returns the
  local absolute path. If not present, downloads via
  `getS3Client(project_idx)` (same resolver every other block uses)
  and writes.
- Writes into the trunk: `hardlinkOrCopy(cache_path, target_path)`.
  Prefer hardlink so the trunk is essentially free disk space; fall
  back to copy if hardlink fails (cross-device or filesystem
  refusal).

Cache invalidation: none needed. `s3_key` is content-addressed by
convention (see the block's `buildS3Key` — uuid per upload). If a
doc's bytes change, its `s3_key` changes → new cache entry, old one
stays around until the periodic sweeper removes it.

Periodic sweeper (small daemon or cron): removes cache entries with
no corresponding `documents.s3_key` or `media.url`. Not blocking for
correctness — just disk hygiene.

---

## The trigger surface

Three ways materialize gets called:

### 1. Debounced, from any DB write in dev-cms

`packages/blocks/brain/server/materializeQueue.ts` exposes
`enqueueMaterialize(project_idx, reason)`:

- Module-level `Map<project_idx, { timer, reason }>`.
- Debounce window: 5s from the last call for that project.
- On fire: `POST /api/brain/materialize { project_idx, reason }` to
  server_a1. Fire-and-forget.
- Coalescing: repeated calls within the window bump the timer and
  concatenate reasons; the actual materialize runs once per burst.

Callsites replace every prior `triggerReconcile(project_idx)`:
- `projects` insert/update
- `app_projects` insert/update/delete
- `jobs` insert/update/delete
- `job_definitions` insert/update/delete
- `project_folders` insert/rename/move/delete
- `documents` insert/upload-complete/rename/delete/update-from-html
- `media` insert/delete (same pattern once we sweep media)

### 2. Synchronous, before Claude Code intelligence runs

`server_a1`'s brain dispatcher wraps every job dispatch in
`await materializeProject(project_idx)`. This is the only case where
we block on materialize — the intelligence layer must never see a
stale tree.

### 3. Manual, via CLI or HTTP

- CLI: `npx tsx server_a1/scripts/brain-materialize.ts <project_idx>`
- HTTP: `POST /api/brain/materialize { project_idx }` — synchronous,
  returns the full `MaterializeReport` as JSON.

Both bypass the debounce and force a full run. Useful during
development or after schema changes.

---

## The git model

The trunk is one repo, single main branch. Every materialize either:
- makes no changes → no commit (nothing to record)
- makes changes → one commit, subject
  `materialize project_idx=N ({reason})`

Commits are linear on `main`. No branches, no merges — this is a
materialized view, not a collaborative surface.

Intelligence leaves (`facts.json`, `rules.json`, `beliefs.json`)
authored by humans or by the intel-rebuild agent commit through the
same materialize path: the agent writes to disk, the next
materialize picks the change up and commits it with a
`materialize project_idx=N (agent write)` reason. This means intel
commits go through the same pipeline as data-driven commits — one
history to audit.

---

## Per-entity `CLAUDE.md` — foundation prose

Every entity node (project, app_project, job, job_definition) may
have a `CLAUDE.md` file. Free-form markdown authored by Boss (or,
later, the intelligence layer with strict review). Purpose: the
foundational context the AI needs at that scope — company philosophy,
job-type-specific rules, edge cases, decision heuristics.

**Contract:**
- **Trunk-native.** Never derived from DB, never regenerated. Human-
  or agent-authored at rest.
- **Preserved through wipe.** Same class as intel JSONs. Materialize
  step 3 reads them into memory before the wipe; step 6 writes them
  back before the git commit.
- **Read automatically by Claude CLI.** When the intelligence layer
  spawns `claude` in a subprocess scoped to a specific entity folder,
  claude-code picks up `CLAUDE.md` at that scope AND every ancestor
  scope (project-level context inherits down). Zero plumbing.
- **Optional at every scope.** Only exists where it's genuinely
  useful. Empty scopes have no CLAUDE.md; materialize doesn't create
  stubs.
- **Version-controlled.** Every edit is a git commit. History of the
  company's own thinking about itself.

**Typical locations:**
- `friday/<project_id>/CLAUDE.md` — the tenant's philosophy, policies,
  operating context. This is the highest-leverage one to write.
- `friday/<project_id>/job_definitions/<jdef_id>/CLAUDE.md` — job-type
  defaults, must-do checkpoints, canonical durations.
- `friday/<project_id>/app_projects/<ap_id>/CLAUDE.md` — only when this
  specific project has unusual constraints (site access, HOA rules,
  etc.). Usually empty.
- `friday/<project_id>/app_projects/<ap_id>/jobs/<job_id>/CLAUDE.md` —
  rarely needed. Only when this one job has a truly unique wrinkle.

**Distinction from the `profile` JSON column:**
- `profile` is structured, typed, zod-validated. For fields other
  systems query directly (working_hours, service_area).
- `CLAUDE.md` is free-form prose. For philosophy, heuristics, the
  onboarding-doc-for-a-new-hire kind of context.
- No overlap conflict. Different homes for different consumers.

## The change-log

`friday/<project_id>/.change-log.jsonl` — one line per materialize
event, append-only, git-committed, preserved through wipe. The
semantic index over the git commit history.

**Purpose.** Git already carries every commit, timestamp, and diff.
That's the raw truth. But `git log -p` is expensive and noisy for
an agent that just wants to know "what changed to which entity
recently." The change-log is a compact, structured feed Claude
Code can grep in one call. Full field-level detail is still one
`git show <sha>` away when needed.

**Line format** (JSON per line):

```json
{
  "ts": "2026-07-11T01:47:18.920Z",
  "reason": "customer_id changed on APPPROJ-01KKR…",
  "actor": "user",
  "entities": [
    { "kind": "app_project", "id": "APPPROJ-…", "action": "update" }
  ]
}
```

Fields:
- `ts` — ISO timestamp at commit time (millisecond precision).
- `reason` — the semantically loaded string passed to `enqueueMaterialize`.
- `actor` — `"user"`, `"agent"`, `"boot"`, `"cli"`. Materialize infers
  from context; when unclear, defaults to `"user"`.
- `entities` — compact array of touched entity references. Not
  field-level; per-entity granularity only. Detected by diffing the
  pre-wipe DB snapshot against the post-wipe rebuilt state.

Sha is deliberately NOT included in the line. The line and the
data changes it describes land in ONE commit — the ts uniquely
identifies the commit. If a consumer needs the sha, one command
gets it: `git log --format="%H %ai" -- friday/<project>/.change-log.jsonl`
grepped by ts.

**What lives in the log vs git:**

| Question | Answer via |
|---|---|
| "What changed today?" | grep `.change-log.jsonl` for recent lines |
| "What was the state before X changed?" | git show `<sha>~1:friday/<project>/…/data.json` |
| "Which entities have been most-modified this week?" | count entity ids across log lines |
| "Show me the exact bytes that changed" | `git show <sha>` — full diff |
| "When did belief B start being wrong?" | `git log --since=<derived_at>` on relevant paths |

**Preservation.** The change-log lives in the preserved-leaves set.
Materialize's wipe (step 4) reads it into memory before removing
the project subtree; restore (step 6) writes it back before the
new commit. Cannot be recovered from DB — the log encodes semantic
history the DB rows don't retain.

**Append-only.** Materialize appends one line per successful
commit. Never rewrites existing lines. Never truncates. If the log
grows large, we can add pruning later (e.g. rotate to
`.change-log.YYYY-MM.jsonl` monthly); today, one line per
materialize burst is tiny.

## Failure modes

1. **S3 unreachable during materialize.** Blob download fails.
   Materialize returns partial success with the failing keys listed.
   The tree ends in a mid-write state. Next materialize retries and
   converges. UI reads the tree as-is; no crashes.
2. **DB unreachable.** Materialize aborts with a clear error; disk
   unchanged. Nothing to converge — you can't materialize without a
   source.
3. **Concurrent materialize call for the same project.** In-flight
   flag per project_idx; second call awaits the first. No two
   materializes run in parallel for one project.
4. **Concurrent materializes for different projects.** Parallel is
   fine — separate subtrees, separate git commits (git supports
   linear appends from concurrent writers if we serialize the commit
   phase — see `git.ts` for the process-mutex we already have).
5. **Cache corruption / partial writes.** `ensureCached` writes to
   a temp file + atomic rename. Partial writes crash before rename
   → no bad file, next call re-downloads.
6. **Intel leaf lost during wipe.** Cannot happen: step 3 preserves
   intel + artifacts in memory before step 4 wipes. If we ever ship
   a bug where an intel file is lost, git history has it — recover
   with `git checkout <last_good_sha> -- <path>`.

---

## Single-user assumption

Every design decision above assumes one human writing at a time.
Multi-user scenarios (two PMs editing the same project's rules
simultaneously, or one writing via the UI while another materializes
via CLI) are out of scope. When we're ready to open that door, the
materialize function is the natural home for CRDT-style merges — it
already reads all state, composes a target, and writes. That's the
extension point.

Do not add lock files, mutex tables, or "who wrote last" tracking
now. Anything that pretends to solve multi-user without actually
solving it is bandaid two.

---

## What NOT to do

- **Don't** add a hook that mirrors "just this one DB change" to
  disk. If materialize is too slow for your use case, make it
  faster — don't split the writer.
- **Don't** edit `data.json` on disk. It's derived — the next
  materialize wipes it. Changes belong in the DB or in the
  `profile` JSON column. Zod validates the profile shape at the
  API boundary.
- **Don't** write intel JSON from DB. Intel + artifacts are
  trunk-native; the DB has no opinion on them.
- **Don't** delete `.git/` under any project when materializing.
  History is the audit trail — losing it is losing the ability to
  recover from bugs.
- **Don't** put a database row for "brain trunk state" — the trunk
  IS the state, always regeneratable from DB + S3. A row would
  become the next drift surface.
- **Don't** materialize on every keystroke. The 5s debounce is
  intentional. If a user wants immediate reflection they can trigger
  it manually.
