---
id: stick_frame_default_for_small_additions
scope: company
job_type: null
job_id: null
confidence: 0.92
supports:
  - _company/knowledge/_examples/wills_voice.md
  - _company/rules/_examples/plumbing_rough_min_duration.md
source_signature: sha256:placeholder_until_harness_computes_this
recorded_at: 2026-06-22T14:00:00Z
recorded_by: agent
supersedes: null
stale: false
tags: [framing, roof, additions]
---

For additions under ~800 sqft with a roof span < 24 ft, TCR defaults to
stick-framing the roof rather than ordering trusses. Lumber arrives
just-in-time with the framing crew; no `procurement.trusses` task
needed.

**How to apply.** Override the default only when scope explicitly says
"trusses" OR the PM Interview confirms a span over 24 ft / footprint
over 800 sqft.

**Alternatives considered.** Trusses are cheaper labor on the roof
itself but add 4-6 weeks of supplier lead time. For small additions
that lead time dominates total project length; stick-framing wins on
calendar even when materials cost slightly more.
