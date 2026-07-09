# applicable_rules.json schema

Series 3 · Phase Charlie · Sweep Charlie.1 — the canonical shape
of `intelligence/applicable_rules.json`. Written by stage-A of
the intel rebuild pipeline. Consumed by Layer-2 synthesis + by
downstream workflows that need the rules index without a full
selector walk.

## Shape

Backward-compatible with the pre-Series-3 file — every legacy
field is still there. New fields are additive:

- `domain` (new) — the domain manifest `name` that owned the
  selector run.
- `context` (new) — the WU context object the selector ran
  against, dimension-key → value.
- `rules[].tier` (new) — generic tier (`tenant | category |
  context | work_unit`). Renames the legacy `layer` field but
  keeps `layer` populated for any consumer still keyed off it.
- `rules[].applies_to` (new) — the dimensional predicate map
  the selector evaluated.
- `rules[].specificity` (new) — non-negative int; higher = more
  specific.
- `rules[].explicit_priority` (new) — the `priority` override on
  the entry, `null` if none was declared.
- `rules[].score` (new) — sort key (`specificity +
  explicit_priority`).
- `rules[].trace` (new) — per-dimension outcome table:
  `[{ key, tier, expected, actual, matched, reason }]`.
- `rules[].tie_breaker` (new) — `authored_at` used to break ties
  when two entries share a score.

The legacy `priority_rank` field is still populated for backward
compatibility, mapped from `score` for consumers that key off
integers. New consumers SHOULD read `score` + `trace` instead.

## Example (partial)

```json
{
  "schema_version": 2,
  "generated_at": "2026-07-09T14:00:00Z",
  "domain": "construction",
  "context": {
    "job_type": "bathroom_remodel",
    "structure_type": "stick_frame",
    "region": "franklin_county_wa",
    "phase": "rough_in",
    "trade": "plumbing"
  },
  "layers": {
    "company":  { "priority_rank": 100 },
    "job_type": { "priority_rank": 200 },
    "project":  { "priority_rank": 300 },
    "job":      { "priority_rank": 400 }
  },
  "rules": [
    {
      "path": "job_types/bathroom_remodel/rules/plumbing_rough_min_duration.md",
      "kind": "rule",
      "tier": "category",
      "layer": "job_type",
      "applies_to": { "job_type": "bathroom_remodel", "trade": "plumbing" },
      "specificity": 4,
      "explicit_priority": 0,
      "score": 4,
      "priority_rank": 200,
      "trace": [
        {
          "key": "job_type",
          "tier": "category",
          "expected": "bathroom_remodel",
          "actual": "bathroom_remodel",
          "matched": true,
          "reason": "value_ok"
        },
        {
          "key": "trade",
          "tier": "work_unit",
          "expected": "plumbing",
          "actual": "plumbing",
          "matched": true,
          "reason": "value_ok"
        }
      ],
      "tie_breaker": "2026-05-14T09:12:00Z",
      "one_line_why": "Plumbing rough-in minimums for TCR bathroom scopes."
    }
  ],
  "derived_from": [
    {
      "path": "job_types/bathroom_remodel/rules/plumbing_rough_min_duration.md",
      "sha256": "sha256:…"
    }
  ]
}
```

## Layer → tier mapping

`layer` retains its legacy vocabulary for backward compatibility:

| `tier`      | `layer`      |
|-------------|--------------|
| `tenant`    | `company`    |
| `category`  | `job_type`   |
| `context`   | `project`    |
| `work_unit` | `job`        |

Non-construction domains that adopt the new tier vocabulary
should treat `layer` as vestigial.
