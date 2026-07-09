# Belief file schema

Last revised: 2026-07-08. Adds lifecycle fields.

A belief is a `.md` file with YAML frontmatter + a markdown body.
One claim per file. Filename = `<id>.md` matching the frontmatter
`id`.

Beliefs are **descriptive with confidence + provenance**. They say
what the brain currently understands to be true, sourced from
something specific. Agent writes freely on proposal branches; entry
lands `status: active` only when either (a) auto-approved (high
confidence + no contradictions) or (b) PM-approved via the review
queue.

## Frontmatter contract

```yaml
id: string                  # MUST equal filename without `.md`.
scope: tenant | category | context | work_unit
                            # matches the file's folder location.
                            # Aliases in TCR: company | job_type | project | job.
category: string | null     # set when scope=category (e.g. "addition").
context_id: string | null   # set when scope=context (the APPPROJ-... id).
work_unit_id: string | null # set when scope=work_unit (the JOB-... id).

confidence: number          # 0.0–1.0. Humans default to 1.0. Agent picks.
supports:                   # MUST be non-empty. The provenance trail.
  - path/relative/to/trunk/root.md
  - path/to/another/source.txt#section-anchor-optional
source_signature: string    # sha256:<hex>. Hash of concatenated supports' content at write-time.

# ── Lifecycle (mandatory) ─────────────────────────────────────────
status: proposed | active | deprecated
                            # proposed = queued for review (never cited by generators)
                            # active   = live; visible to generators
                            # deprecated = superseded or PM-rejected; kept for audit
recorded_at: ISO8601
recorded_by: string         # "agent" or human user_id.
authored_by: string         # who wrote the FIRST version of this belief (may equal recorded_by)
last_verified_at: ISO8601   # updated when a run cites this belief AND the observation still holds
verified_by_run_ids: [int]  # brain_job_run ids that cited AND confirmed this belief
supersedes: string | null   # id of a prior belief this replaces.
superseded_by: string | null # id of a newer belief that replaces this (auto-set when a successor lands)
stale: boolean              # default false. Flipped true when a `supports` file's hash changes
                            # OR when `last_verified_at + decay_window_days` has passed.
decay_window_days: integer  # how long without re-verification before auto-stale. Default 90.
tags: [string]
```

## Body

- **Lead** with the claim in plain language.
- **How / when to apply** — short note on the boundary or trigger.
- Optional **alternatives considered** or **caveats**.

## Auto-approval rules

Beliefs proposed by the agent auto-approve to `status: active`
IF ALL are true:
- `confidence >= 0.85`
- No `active` rule contradicts this belief
- No `active` belief with `scope` equal-or-more-specific
  contradicts this belief
- No prior PM-confirmed answer (in interview rounds) contradicts
  this belief

Otherwise → `status: proposed` and queued for PM review.

Rules NEVER auto-approve; patterns NEVER auto-approve.

## Hard rules

- `supports[]` is non-empty. A belief without provenance is
  unverifiable.
- `source_signature` is sha256 of `supports`' file contents
  concatenated in declared order. Recomputed on staleness sweeps.
- `supersedes` chains history. Never delete; supersede.
- Only `status: active` beliefs get cited by generators.
- `last_verified_at` MUST be updated when a run cites the belief
  and the observation still holds. `verified_by_run_ids` appended.
- When a belief gets stable enough to enforce, a human promotes it
  to a rule. The rule's frontmatter notes `supersedes: <belief_id>`.
  Belief flips to `deprecated`.

See `_company/beliefs/_examples/` for a canonical example.
