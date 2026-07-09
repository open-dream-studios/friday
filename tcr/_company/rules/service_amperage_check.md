---
id: service_amperage_check
title: Service amperage must be verified before electrical rough
scope: company
job_type: null
job_id: null
severity: hard
authored_by: friday
authored_at: 2026-07-01T12:00:00Z
supersedes: null
tags: [electrical, pre_construction, checkpoint, risk_gate]
---

Every job that adds electrical load (new subpanel, ≥4 new circuits,
mini-split, HVAC replacement, EV charger, tankless WH, elevator) MUST
include a `prep.amperage_check` task during pre-construction, scheduled
BEFORE `procurement.panel.order` and BEFORE `electrical.rough`.

**Task shape.**

```
prep.amperage_check:
  duration_days: 0.5
  crew: 1
  trade: electrical (senior / licensed)
  pre_construction_offset_working_days: 10
  predecessor_of: [procurement.panel.order, electrical.rough]
```

**What it does.** Senior electrician visits the site, checks the meter
and existing panel, calculates the added load, and confirms the service
can carry it. If not, PM is on notice to file for a utility upgrade
BEFORE the job breaks ground.

**Why.** V11 had this discipline; Run #137 dropped it. Real cost of
skipping: crew shows up to install a 100A subpanel on a service that
can't support it, mid-project. Blocks rough. Utility upgrade typically
adds 2–4 weeks + $1,500–5,000 in coordination cost. Cheaper to catch
before procurement lands.

**Exempt jobs.** Cosmetic-only remodels with zero circuit additions may
skip this. Everything else: mandatory.
