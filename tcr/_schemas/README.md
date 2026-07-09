# `_schemas/` — frontmatter + JSON contracts

Last revised: 2026-07-08. Added `pattern.schema.md`.

The canonical shape of every typed file in this trunk. Changes here
are **breaking changes** — they invalidate existing files and require
migration. Developer-only.

## Files in this folder

- `rule.schema.md` — frontmatter contract for rule files
  (`_company/rules/`, `job_types/*/rules/`,
  `_projects/*/jobs/*/rules/`).
- `belief.schema.md` — frontmatter contract for belief files.
  Includes the belief lifecycle (proposed → active → deprecated,
  `last_verified_at`, `verified_by_run_ids[]`,
  `decay_window_days`).
- `pattern.schema.md` — frontmatter contract for pattern files.
  The third intelligence category. Aggregate observations across
  many work units. Never auto-approves.
- `events.schema.md` — line shape for per-work-unit
  `events.jsonl` audit logs, with the catalog of event kinds.
- `ref.schema.md` — `.ref.json` pointer shape for S3-backed
  binaries.
- `task_graph.schema.md` — canonical shape for the task_graph
  artifact (a construction-specific generator's output; kept in
  this folder because it's a schema contract, but domain-scoped).
- `pep.schema.md` — canonical shape for the PEP artifact
  (construction-specific).

## Layer taxonomy

Read [`friday/BRAIN.md`](../../BRAIN.md#the-3-layer-taxonomy) for the
full architecture. Schemas map to the taxonomy as:

| Schema | Layer |
|---|---|
| `rule.schema.md` | Intelligence |
| `belief.schema.md` | Intelligence |
| `pattern.schema.md` | Intelligence |
| `ref.schema.md` | Data (pointer) |
| `events.schema.md` | Data (audit log) |
| `task_graph.schema.md` | Artifact |
| `pep.schema.md` | Artifact |

## How these schemas are used

- **Humans** read them when editing trunk files by hand.
- **Agents** read them as part of the toolset context so they know
  the shape they must write.
- **Validators** enforce them mechanically on every proposal branch
  before merge. (Enforcement lands in Sprint 4 alongside the
  proposals queue.)

## Canonical examples

Each schema keeps one canonical example committed at the matching
slot:

- `_company/rules/_examples/plumbing_rough_min_duration.md`
- `_company/beliefs/_examples/stick_frame_default_for_small_additions.md`
- `_company/patterns/_examples/` (populated in Sprint 4)
- `_company/knowledge/_examples/wills_voice.md`

Examples sit in `_examples/` subfolders so they don't get loaded as
real intelligence by the agent.

## Domain scoping note

`task_graph.schema.md` and `pep.schema.md` describe
construction-specific artifacts. In a multi-domain future they move
under `_domains/construction/schemas/`. For now they live here
because construction is the only tenant.
