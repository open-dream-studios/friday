---
id: siding_starts_at_underlayment
title: Siding can start when underlayment is on (parallel with roofing finish)
scope: job_type
job_type: addition
job_id: null
severity: soft
authored_by: friday
authored_at: 2026-07-01T12:00:00Z
supersedes: null
tags: [siding, roofing, sequencing, addition, exterior]
---

Once the roof underlayment is installed on an addition tie-in, siding
install MAY start in parallel with fascia, soffit, gutters, and shingles.
Windows and doors MUST be in first — the WRB (weather-resistive barrier)
is not intact without them, and siding attached over an incomplete WRB
is a leak risk.

Do NOT chain `siding.install` after `roofing.fascia_soffit_gutters` or
`roofing.shingles` as a hard predecessor. Those are `can_overlap_with`
relationships, not FS dependencies.

**Why.** V1 chained siding after full roofing completion. Will's audit
transcript (308 Evergreen, 2026-06-22): *"You can install siding as soon
as the underlayment is done. It does not have to wait."* On a small shop
where roof + siding share a crew, real wall-clock will still serialize
(see belief `roof_and_siding_same_crew`), but the DEPENDENCY should
allow parallelism so a two-crew job doesn't waste 2–4 days waiting.

**Task-graph shape.**

```
siding.install:
  depends_on: [windows.install, roofing.underlayment]
  can_overlap_with:
    - roofing.shingles
    - roofing.fascia_soffit_gutters
    - mep.rough_*
```

**Precedence.** This rule (rank 200 job_type) beats any older company-
level rule that hard-chained siding to full roof completion.
