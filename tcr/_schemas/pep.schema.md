# PEP (Project Execution Plan) file schema

A PEP is a `.md` file with YAML frontmatter + a markdown body. **One
PEP per job.** Lives at `<job>/generations/pep.md`. Filename is fixed.

A PEP is the canonical, customer-facing "this is what we're committing
to" document for the job. It consolidates the upstream artifacts
(baseline → risks → task_graph → daily_schedule) into a single signed
plan. The PEP is what the PM walks the customer through; everything
else in `generations/` is the brain's working memory behind it.

## Frontmatter contract

```yaml
generation_kind: pep_v1   # required, per P10 convention
depends_on:               # required, per P10 convention
  - <job>/generations/baseline.md
  - <job>/generations/risks.md
  - <job>/generations/task_graph.md
  - <job>/generations/daily_schedule.md
  - <job>/manifest.json
  - <job>/inputs/scope.md
last_verified_at: ISO8601 # set by the committer; agent may overwrite

# ── Commitment block ──────────────────────────────────────────────
version: integer          # bumped on every PEP regeneration
supersedes: string | null # commit_sha of the prior PEP version, or null
status: draft             # draft | proposed | signed | superseded
                          # draft  = brain just produced it; not customer-facing yet
                          # proposed = sent to customer for review
                          # signed = customer signed; this is the contract
                          # superseded = a newer PEP version replaces this one

customer_price_usd: number | null    # locked customer total; null when scope undefined
direct_cost_usd: number | null       # PM-side cost (labor+materials+equipment)
margin_pct: number | null            # (customer − direct) / customer

# Schedule
on_site_start_target: ISO8601 | null
on_site_completion_target: ISO8601 | null
duration_working_days: integer | null
duration_calendar_weeks: integer | null

# Sign-off
pm_signed_by: string | null    # user_id when locked
pm_signed_at: ISO8601 | null
customer_signed_by: string | null
customer_signed_at: ISO8601 | null

# ── Plan structure ─────────────────────────────────────────────────
milestones:                # ordered list of named gates
  - id: string             # short slug, e.g. "tdec_permit_in_hand"
    name: string           # human-readable
    target_day: integer    # working-day index from T-0 (negative = pre-con)
    gate_kind: inspection | delivery | customer_decision | permit | trade_start | other
    blocks: [string]       # task_graph task ids this milestone gates
    notes: string

critical_path:             # task_graph task ids in execution order
  - T1
  - T2
  # ...

open_commitments:          # things the PM owes the customer / themselves
  - description: string
    owner: string          # pm | customer | trade name
    due: ISO8601 | null

contingencies:             # planned-for deviations
  - trigger: string        # the condition that activates this
    response: string       # what we do when it activates
    cost_impact_usd: number | null
    schedule_impact_days: number | null
```

## Body

The body is the human-readable narrative. Sections, in order:

1. **Executive summary** — one paragraph the customer reads first.
2. **Scope locked** — bullet list of what is + isn't included.
3. **Schedule narrative** — prose explanation of the timeline and the
   key sequencing constraints (LVL chain, MEP-before-framing-inspection,
   trade-stacking caps). References milestone ids.
4. **Risk allocation** — who carries which risk (customer change order
   vs. PM contingency vs. shared). References `risks.md` entries.
5. **Open items** — what's not yet decided + decision-by dates.
6. **Sign-off** — a checklist for PM and customer.

## Hard rules

1. **One PEP per job.** Filename is `pep.md`, fixed. The brain
   regenerates the file in place; version + supersedes track history.
2. **PEP `status: signed` is a contract.** The brain MUST NOT
   regenerate a signed PEP — re-runs against a signed PEP land in the
   review queue requiring explicit human approval to supersede.
3. **Frontmatter `depends_on` lists all upstream artifacts.** This
   wires the PEP into the staleness checker (P7) — if any upstream
   moves, the PEP goes stale and prompts a regenerate.
4. **`customer_price_usd` MUST trace to `inputs/scope.md`.** If scope
   has no number, leave `customer_price_usd: null` and explain in
   the body. Don't fabricate.
5. **`milestones[].target_day` is anchored to T-0** (on-site start).
   Pre-con milestones use negative working-day indices. Calendar dates
   are derived; the canonical form is the working-day offset.
6. **`critical_path` references task_graph task ids verbatim.** If the
   task graph regenerates, the critical_path entries must still
   resolve — drift means the PEP needs regenerating.
