# `_company/` — tenant-scoped knowledge

Last revised: 2026-07-08.

**Generic term:** *tenant scope* (see
[`friday/BRAIN.md`](../../BRAIN.md#the-generic-scoping-model)). In
TCR's construction domain this is labeled "company." Applies to
**every work unit at TCR** unless a more-specific layer
(`job_types/` or the work unit itself) overrides it.

## Subfolders

- **`rules/`** — prescriptive, human-authored. "Plumbing rough ≥ 4d
  × 2 crew for any master bath." Slow-changing. Agent can *propose*
  a rule but never auto-merges.
- **`beliefs/`** — descriptive with confidence + provenance. "Will
  defaults to stick-frame for additions under 800 sqft." Faster-
  changing than rules. Agent proposes; auto-merges when confidence
  ≥ 0.85 and no contradictions. Otherwise queued for PM review.
  Full lifecycle in `_schemas/belief.schema.md`.
- **`patterns/`** — aggregate observations across many work units.
  "TCR's addition jobs are stick-framed 11 of the last 12 times."
  Extracted periodically by a `pattern_extract_v1` generator. Never
  auto-approve. Full lifecycle in `_schemas/pattern.schema.md`.
- **`knowledge/`** — raw, unstructured business context (Data
  layer, not Intelligence). Will's playbook, meeting transcripts,
  scope templates. No schema, just markdown.
- **`actuals/`** — legacy slot for harvested cross-work-unit
  outcome data. Being subsumed by `patterns/` — patterns are the
  active category going forward. Kept for archival reads.

## Taxonomy mapping

Read [`friday/BRAIN.md`](../../BRAIN.md#the-3-layer-taxonomy) for
the 3-layer taxonomy. Files here map as:

| Subfolder | Layer |
|---|---|
| `rules/` | Intelligence — rules |
| `beliefs/` | Intelligence — beliefs |
| `patterns/` | Intelligence — patterns |
| `knowledge/` | Data — unstructured reference |
| `actuals/` | Data — legacy structured (superseded by patterns) |

## Examples this scope expects

| Slot         | Filename example                | Body                                           |
| ------------ | ------------------------------- | ---------------------------------------------- |
| `rules/`     | `plumbing_rough_min_duration.md` | "Master bath plumbing rough is ≥ 4d × 2 crew." |
| `beliefs/`   | `stick_frame_default_for_small_additions.md` | "Stick-frame is the default for <800 sqft additions." |
| `patterns/`  | `tcr_additions_stick_frame_ratio.md` | "11 of 12 TCR additions have been stick-framed." |
| `knowledge/` | `wills_playbook.md`              | Free-form notes from Will.                     |
