---
id: retrofit_tie_in_discovery
title: Retrofit additions require a framing tie-in discovery buffer
scope: job_type
job_type: addition
job_id: null
severity: hard
authored_by: friday
authored_at: 2026-07-01T12:00:00Z
supersedes: null
tags: [framing, retrofit, discovery, risk_gate, addition]
---

Any addition that ties into existing framing, roofing, or MEP (i.e. NOT
a standalone new structure) MUST include a `framing.tie_in_discovery`
task that runs SS (start-to-start) with the tie-in framing task and
exposes concealed conditions before sheathing goes on.

**Task shape.**

```
framing.tie_in_discovery:
  duration_days: 1
  crew: 2
  trade: framing (lead + carpenter)
  relationship_to_framing: SS
  purpose: |
    Expose concealed conditions at the tie-in seam:
      - chimney flashing pockets
      - non-plumb existing walls
      - hidden MEP runs behind kick plates
      - roof pitch transitions (existing 6/12 → new 3/12 valley)
      - existing rot / termite / rodent damage
    If discovery finds change-order-worthy conditions, PM triggers a
    review BEFORE sheathing goes on.
```

**Why.** Run #137's task_graph_v2 added this on its own for 308 Evergreen
(T33 `framing.roof_tie_in_discovery`) as a hedge on the 3/12→6/12 tie-in
plus the existing chimney. That was the RIGHT call and shouldn't depend
on the agent re-inferring it every run. Codifying it here makes it
guaranteed for every addition that meets the retrofit trigger.

**Trigger condition.** Any of:
  * `manifest.subtype == "addition_tie_in"`, OR
  * Extracted plans note relocated windows/doors, OR
  * Extracted plans note existing chimney or plumbing runs at the
    addition boundary, OR
  * Scope narrative uses phrases like "tie into existing," "retrofit,"
    "match existing," or "removed existing wall."

**Skip condition.** Fully detached new construction (ADU, garage on a
new pad with no shared wall to the existing home) does not need this
task.
