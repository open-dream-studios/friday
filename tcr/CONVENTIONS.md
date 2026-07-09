# Naming + git conventions

Last revised: 2026-07-08. Adds `pattern` and proposal-review kinds.

Lock these so the agent doesn't have to guess. Apply to every file
and every branch in this trunk.

## Slugs (lowercase_with_underscores)

Every `id` field and every filename slug uses
**lowercase_with_underscores**.

```
✅  plumbing_rough_min_duration
✅  stick_frame_default_for_small_additions
❌  PlumbingRoughMinDuration
❌  plumbing-rough-min-duration   (dashes reserved for the id-suffix
                                  separator in context/work-unit folder names)
```

The `id` field in frontmatter MUST equal the filename without the
extension.

## Context + work-unit folder names

`<readable-slug>_<canonical-id>`. Slug is dashed for readability;
the `_` separator splits slug from id. Canonical id stays
unchanged from the DB row.

```
_projects/308-evergreen-street_APPPROJ-01KKRDKBGY5E38A036W0NCQ3AF/
  jobs/
    308-evergreen-street-addition_JOB-01KV94MXDGHRSP8BRZ3HTMC6XN/
```

- Slug = dashed-lowercase, ≤ 40 chars. Human-comfort.
- Id suffix = the canonical `APPPROJ-…` or `JOB-…` ULID from DB.
  Never edit by hand. The id is the key.
- If the slug ever needs to change, only the slug half moves; the
  id half is forever.

## Timestamps

ISO 8601 UTC everywhere. `2026-07-08T14:00:00Z`. Frontmatter,
events, branch names — all the same shape.

Filename-embedded dates (e.g. an actuals dump): `YYYY-MM-DD`
prefix. Example: `2026-06-22_addition_durations.json`.

## Branch names

`main` = canonical state. Anything else is a proposal awaiting
review.

Proposal-branch pattern:

```
proposal/<work-unit-or-trunk-scope>/<kind>/<isoshort>-<short-summary>

proposal/wu_JOB-01KV94.../belief/20260708T1400-stick_frame_default
proposal/wu_JOB-01KV94.../pattern/20260708T1600-additions_stick_frame_ratio
proposal/wu_JOB-01KV94.../generation/20260708T1545-task_graph
proposal/trunk/rule/20260708T1700-plumbing_rough_min_duration
```

Field rules:

- `kind` is one of: `rule`, `belief`, `pattern`, `generation`,
  `knowledge`, `note`.
- `isoshort` = `YYYYMMDDTHHMM` (compact, sortable).
- `short-summary` = 1-4 word slug. lowercase_with_underscores.
- Trunk-scope branches use `trunk`; work-unit-scope branches use
  `wu_<JOB-id>`.

## Commit messages

One-line subject, optional body. Subject starts with the proposal
kind in brackets:

```
[rule] propose plumbing_rough_min_duration
[belief] propose stick_frame_default_for_small_additions
[pattern] propose tcr_additions_stick_frame_ratio (sample=12)
[generation] task_graph v3 for 308 evergreen
[accept] proposal/wu_JOB-.../belief/20260708T1400-stick_frame_default
[reject] proposal/trunk/rule/... — see notes on PR
[note] PM confirmed mini-split HVAC
[archive] context APPPROJ-... superseded 2026-06-25
```

Brackets keep `git log --oneline` scannable and let downstream
tooling filter by kind.

## File extensions

| Extension          | Use for                                           |
| ------------------ | ------------------------------------------------- |
| `.md` w/ frontmatter | Rules, beliefs, patterns.                       |
| `.md` plain          | Knowledge, generation prose (PEPs).             |
| `.json`              | Structured generations (task_graph, schedule).  |
| `.ref.json`          | S3-binary pointers (see `_schemas/ref.schema.md`). |
| `.txt`              | Extracted text from binaries.                    |
| `.jsonl`             | Append-only logs (events.jsonl).                |
| `.gitkeep`           | Empty-folder marker.                            |

## `_examples/` subfolders

Anything under `*/_examples/` is documentation, NOT live data. The
agent's read tools filter it out. Put canonical-shape examples
here.

## What the agent must never do

- Edit `main` directly. Everything goes through a proposal branch
  and the review queue.
- Edit `_schemas/`. Schema changes are developer-only events.
- Edit a file's `id` without simultaneously renaming the file.
  They MUST stay in lockstep.
- Write a file outside the trunk root (`friday/tcr/`).
- Promote a belief to a rule without an explicit human accept. That
  is the load-bearing gate on the whole self-improving system.
- Auto-approve a pattern of any confidence. Patterns describe
  cross-context reality that downstream generators treat as ground
  truth — human review is mandatory.

## Validator

The proposal-review validator lands in Sprint 4 alongside the
Unified Proposals Queue (see
[`friday/OBSERVABILITY.md`](../OBSERVABILITY.md#5-unified-proposals-queue)).
Until then: enforcement is discipline plus the manual review flow.
