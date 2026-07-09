---
generation_kind: intelligence_interview_v2
interview_status: needs_more
round: 2
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWD458DXBEREH8PWBJTFEADS/jobs/308-evergreen-street-addition_JOB-01KWD49ZCC89C3TCH1MZVJEV2P/intelligence/confirmed.md
  - _projects/308-evergreen-street_APPPROJ-01KWD458DXBEREH8PWBJTFEADS/jobs/308-evergreen-street-addition_JOB-01KWD49ZCC89C3TCH1MZVJEV2P/intelligence/facts.md
  - _projects/308-evergreen-street_APPPROJ-01KWD458DXBEREH8PWBJTFEADS/jobs/308-evergreen-street-addition_JOB-01KWD49ZCC89C3TCH1MZVJEV2P/intelligence/applicable_rules.json
  - _projects/308-evergreen-street_APPPROJ-01KWD458DXBEREH8PWBJTFEADS/jobs/308-evergreen-street-addition_JOB-01KWD49ZCC89C3TCH1MZVJEV2P/interview/round-1.md
  - job_types/addition/rules/addition_rules.md
---

# Open questions — round 2

> Cut log: 3 candidates → 1 final. Round 1 closed all 8 critical scope/sequencing
> gaps cleanly. Only one PM answer opened a meaningfully new structural question
> (engineer-stamped LVL sizing status). Dropped: `q.windows_lead_bound`
> (PM said "4-6 wk" + single PO — defaulting to 42 cal-d upper bound is the
> correct read, no decision left); `q.elevator_shaft_floor_penetration`
> (PM deferred to drawings; the framing crew handles vertical penetration
> from the stamped set — not a scheduling-critical input for the task graph).

### q.structural_engineer_status

**Question:** Is the structural engineer's stamp for the LVL beam (and any other load paths the new addition introduces) already in hand, or pending?

**Category:** structural / pre-construction

**Hint:** Round 1 (q.lvl_load_bearing) confirmed the LVL bears actual new floor + roof load and "engineer-stamped sizing required." If the stamp is still pending, we need to emit `prep.structural_engineer_signoff` as a pre-construction checkpoint and gate `order.lvl` on it — otherwise we risk ordering the wrong beam spec. If the stamp is already in hand, no checkpoint is needed and `order.lvl` can fire at structural sign-off.

**Choices:**
- Stamp already in hand — no pre-con engineering task needed
- Pending — engineer engaged, expect ≤ 2 weeks
- Pending — engineer not yet engaged, expect 3–4 weeks
- Unsure — PM to confirm with engineer

**Why:** Determines whether a structural-engineering checkpoint sits ahead of LVL procurement and whether pre-construction has a hidden ~2-week lead the schedule must absorb. Wrong answer either pads the schedule unnecessarily or ships the LVL order before the spec is final.
