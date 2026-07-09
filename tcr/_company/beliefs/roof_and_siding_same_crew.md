---
id: roof_and_siding_same_crew
scope: company
job_type: null
job_id: null
confidence: 0.90
supports:
  - _company/knowledge/308_evergreen_wills_audit_transcript.md
source_signature: sha256:placeholder_until_harness_computes_this
recorded_at: 2026-07-01T12:00:00Z
recorded_by: friday
supersedes: null
stale: false
tags: [staffing, roofing, siding, sequencing, defeasible]
---

TCR's default staffing pattern: the SAME 2–3 person crew handles roofing
(sheathing → underlayment → shingles → fascia/soffit/gutters) AND siding.
This is TCR's shop preference, not an industry-wide truth — a developer-
scale outfit would run separate specialty crews.

**Implication for the schedule.** Even though the sequencing rule
`siding_starts_at_underlayment` (job_type addition, rank 200) ALLOWS
siding to overlap roofing steps via `can_overlap_with`, the real wall-
clock schedule for TCR typically SERIALIZES roof and siding because
the same hands do both. The schedule engine should default to a
serial rendering unless the PM signals a two-crew job.

**Task-graph representation.**

```
siding.install:
  # dependencies remain as siding_starts_at_underlayment specifies
  soft_serialize_with: [roofing.shingles, roofing.fascia_soffit_gutters]
  # engine treats these as "prefer serial by same crew" unless
  # PM overrides with a two_crew: true flag
```

**Why.** Will's audit V1 (2026-06-22): *"I'm not the type of company
that brings in a siding guy, and that brings in a roofer, and that
brings in — no, I don't do that, preferably, whenever I can. I just
bring in the guy that can do all of it."*

**When to override.** PM knows a specialty siding crew is available AND
the roof job is large enough to justify their day rate. Sets a
`two_crew: true` flag on the job manifest, which unlocks the parallel
rendering.

**Interaction with `siding_starts_at_underlayment`.** The dependency
rule says WHEN siding CAN start. This belief says WHEN it typically
DOES start on a TCR job. Both truths coexist and the engine respects
both.
