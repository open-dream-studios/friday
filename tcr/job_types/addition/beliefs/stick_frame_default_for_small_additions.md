---
id: stick_frame_default_for_small_additions
scope: job_type
job_type: addition
job_id: null
confidence: 0.92
supports:
  - _company/knowledge/_examples/wills_voice.md
  - _company/knowledge/308_evergreen_wills_audit_transcript.md
source_signature: sha256:placeholder_until_harness_computes_this
recorded_at: 2026-06-22T14:00:00Z
recorded_by: agent
supersedes: null
stale: false
tags: [framing, roof, additions]
---

For addition jobs under ~800 sqft with a roof span < 24 ft, TCR defaults
to stick-framing the roof rather than ordering trusses. Lumber arrives
just-in-time with the framing crew; no `procurement.trusses` task
needed.

**How to apply.** Override the default only when scope explicitly says
"trusses" OR the PM Interview confirms a span over 24 ft / footprint
over 800 sqft.

**Note.** Promoted from `_company/beliefs/_examples/` because this is
actually job-type-specific (not all TCR work is additions). The
canonical example file remains in `_company/beliefs/_examples/` as
documentation of the belief frontmatter shape.
