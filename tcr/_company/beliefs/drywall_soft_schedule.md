---
id: drywall_soft_schedule
scope: company
job_type: null
job_id: null
confidence: 0.85
supports:
  - _company/knowledge/308_evergreen_wills_audit_transcript.md
source_signature: sha256:placeholder_until_harness_computes_this
recorded_at: 2026-07-01T12:00:00Z
recorded_by: friday
supersedes: null
stale: false
tags: [drywall, scheduling, communication, defeasible]
---

The drywall crew's start date is the least reliable date on the calendar.
It's gated by three inspection passes (rough MEPs → punch cycle → insulation
inspection), each of which has an unpredictable punch tail. TCR's practice:
**pencil in the drywall crew based on the nominal schedule, but do NOT
commit them until the first insulation inspection date is set.**

**Task-graph representation.**

```
drywall.hang_finish:
  depends_on: [inspect.insulation]
  soft_start: true       # engine treats this as slidable
  communication_note: "PM confirms crew 5-7 days out, once insulation
                       inspection is calendared."
```

The `soft_start: true` flag tells the schedule engine that a slip in
`inspect.insulation` does NOT cascade a full re-calc downstream — the
drywall block absorbs the slip via the punch buffer.

**Why.** Will's audit V1 (2026-06-22): *"I would call my drywall crew
when I've scheduled the first insulation inspection."* Hard-linking
drywall to insulation is not wrong — it just falsifies the schedule's
"crew committed" signal. Preserves flexibility without lying about it.

**When to override.** If PM has a drywall crew on retainer or a booked
slot, this belief loses to a PM-set hard-start. Belief, not rule.
