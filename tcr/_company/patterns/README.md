# `_company/patterns/` — tenant-scoped aggregate observations

Patterns are **descriptive with evidence**. They describe what has
been observed across many work units. Distinct from beliefs
(single-source inferences) and rules (prescriptive policy).

Full lifecycle + frontmatter contract: `_schemas/pattern.schema.md`.

## What lives here

Cross-work-unit observations that apply tenant-wide:
- Frequencies ("11 of 12 TCR additions have been stick-framed")
- Ratios ("Rough plumbing inspections in Church Hill pass first
  attempt 82% of the time")
- Absences ("Zero TCR jobs have used trusses under 800 sqft")
- Temporal trends ("Q1 addition durations trended 8% shorter than
  Q3")
- Customer-specific patterns ("Customer Smith has signed zero
  change orders across 4 jobs")

## What does NOT belong here

- **Single-source claims** → those are **beliefs**. A pattern
  requires `sample_size >= 2` in evidence_from[].
- **Prescriptive policy** ("addition plumbing MUST be ≥ 4d") →
  those are **rules**.
- **Raw source data** → those are **knowledge** or work-unit
  inputs.

## How patterns are produced

1. **Agent extraction** (default). A `pattern_extract_v1` generator
   walks work units in scope, aggregates observations, proposes
   patterns via the review queue. Runs periodically or on-demand.
2. **Human authoring** (for high-level observations that aren't
   derivable from a work-unit walk). Same schema, same review flow.

Patterns NEVER auto-approve regardless of confidence. Downstream
generators treat active patterns as ground truth — the human review
gate is what keeps that safe.

## Rules of the road

- Every pattern MUST cite ≥2 work units in `evidence_from[]`.
- `sample_size` must match `len(evidence_from)`.
- Confidence reflects sample size + variance, not the extractor's
  gut feeling.
- Staleness (`stale: true`) triggers a re-extraction. If the ratio
  drifts materially, a supersession proposal enters the queue.
- Never delete a superseded pattern. Set `superseded_by`; keep for
  audit.

## `_examples/`

Canonical examples ship in Sprint 4 alongside the extraction
generator. This slot is intentionally empty for now — real patterns
come from real work-unit walks.
