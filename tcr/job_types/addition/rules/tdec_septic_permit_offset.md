---
id: tdec_septic_permit_offset
title: TDEC septic permit must be anchored at start of pre-construction
scope: job_type
job_type: addition
job_id: null
severity: hard
authored_by: will
authored_at: 2026-06-22T14:00:00Z
supersedes: null
tags: [tdec, septic, pre_construction, addition]
---

For any addition that adds a bedroom, bathroom, or other TDEC-counted
fixture AND the home is on septic, the `permit.tdec_septic` task MUST
have `pre_construction_offset_working_days: 30`.

**Rationale.** Without the offset, CPM backward-schedules TDEC from
its consumer (`excavation.dig`, which lands ~7 working days into
on-site after the demo phase) and TDEC's start drifts to ~4 weeks
before on-site instead of the full 6 weeks. PMs file TDEC at the START
of pre-construction, not as-late-as-possible — the offset anchors it
correctly.

**Shape.** `permit.tdec_septic`, `kind: lead_time`,
`lead_time_days: 42` (calendar, ~6 weeks),
`pre_construction_offset_working_days: 30`, gates `excavation.dig` via FS.

**Skip when.** Home is on city sewer.
