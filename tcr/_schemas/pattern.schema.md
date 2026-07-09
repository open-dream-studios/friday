# Pattern file schema

Last created: 2026-07-08. Patterns are the third category of the
intelligence layer, alongside rules and beliefs. See
[`friday/BRAIN.md`](../../BRAIN.md#layer-2--intelligence-derived-understanding).

A pattern is a `.md` file with YAML frontmatter + a markdown body.
One observation per file.

**How patterns differ from beliefs:**
- Beliefs answer "what should we assume by default?" — inferred
  from limited evidence, often a single input, with confidence.
- Patterns answer "what has been observed across many work units?"
  — aggregate observations extracted from historical data. Every
  pattern cites the specific work units that support it.

Examples of patterns:
- "TCR's addition jobs are stick-framed 11 of the last 12 times."
- "Customer Smith has signed 0 change orders across 4 completed
  jobs."
- "Rough plumbing inspections in Church Hill pass on the first
  attempt 82% of the time (32 of 39 jobs)."

Patterns NEVER auto-approve. They enter the review queue and
require PM sign-off before landing `status: active`.

## Frontmatter contract

```yaml
id: string                  # MUST equal filename without `.md`.
scope: tenant | category | context | work_unit
category: string | null
context_id: string | null
work_unit_id: string | null

kind: pattern
observation_type:           # what kind of aggregate is this
  frequency | ratio | threshold_crossing | temporal_trend |
  correlation | absence
confidence: number          # 0.0–1.0 based on sample size + variance.

# ── Evidence — the aggregation source ─────────────────────────────
evidence_from:              # MUST be non-empty. The work units this pattern was derived from.
  - _projects/<ctx-id>/jobs/<wu-id>
  - _projects/<ctx-id>/jobs/<wu-id>
sample_size: integer        # number of work units in evidence_from
observation_window:         # timespan the evidence spans
  start: ISO8601
  end: ISO8601

# ── Lifecycle (mandatory) ─────────────────────────────────────────
status: proposed | active | deprecated
recorded_at: ISO8601
recorded_by: string         # "agent" or human user_id.
last_verified_at: ISO8601   # updated when a re-extraction confirms the pattern still holds
verified_by_run_ids: [int]  # brain_job_run ids that re-verified this pattern

supersedes: string | null   # id of a prior pattern this replaces
superseded_by: string | null

stale: boolean              # true when new evidence would materially change the pattern
                            # (e.g. sample size doubled, or ratio drifted >10%)
decay_window_days: integer  # default 180 — patterns decay slower than beliefs

tags: [string]
```

## Body

- **Lead** with the observation in one sentence.
- **Evidence table or list** — link to each work unit contributing
  to this pattern, with the specific observation from that unit.
- **How / when this pattern is used** — which generators should
  consider this? What does it change downstream?
- **Confidence rationale** — how sample size + variance justify the
  confidence number.

## Extraction

Patterns are produced by a `pattern_extract_v1` generator (Sprint 4)
that walks the historical work units in scope and derives
observations. Each extraction run:
1. Reads the current active patterns
2. Walks work units under scope
3. Proposes new patterns OR re-verifies existing ones
4. Queues proposals for PM review

Human authors may also write patterns directly for high-level
observations that aren't derivable from work-unit walks.

## Auto-approval

Patterns do NOT auto-approve. Even a `confidence: 1.0` pattern must
be PM-reviewed because patterns describe cross-context reality that
downstream generators will treat as ground truth.

## Hard rules

- `evidence_from[]` is non-empty. A pattern without cited work units
  is speculation, not observation. Validator rejects.
- `sample_size` matches `len(evidence_from)`.
- Only `status: active` patterns get cited by generators.
- Staleness sweep re-runs the extraction periodically. If the ratio
  or frequency has drifted materially, `stale: true` and a
  supersession proposal enters the queue.
- When PM disagrees with a pattern (rejects it or supersedes with a
  human-authored version), the original stays in the trunk as
  `deprecated` — never deleted. Audit trail intact.

See `_company/patterns/_examples/` (populated in Sprint 4) for
canonical examples.
