---
id: scope_vs_csv_total_reconciliation
title: Scope-total vs CSV-total mismatch ≥5% must surface as an interview question
scope: company
job_type: null
job_id: null
severity: hard
authored_by: friday
authored_at: 2026-07-01T12:00:00Z
supersedes: null
tags: [intel_rebuild, breakdown, scope, interview, reconciliation, risk_gate]
---

During `intelligence_rebuild_v2` stage-A `extract_breakdown`, the agent
MUST compare the CSV grand total against the "Total Investment" (or
equivalent contract-total figure) in `inputs/scope.md`. If the two
differ by ≥5%, an interview question MUST be emitted in
`<job_path>/intelligence/questions.md` asking the PM to reconcile the
gap.

**Question schema (agent emits this into questions.md).**

```
### q.scope_vs_csv_total_reconciliation
**Question:** The scope quotes a total of $<SCOPE_TOTAL> but the CSV
grand total is $<CSV_TOTAL> — a gap of $<DELTA> (<PCT>%). How should
we treat this?
**Category:** scope
**Hint:** Rule scope_vs_csv_total_reconciliation flagged this gap.
Change-order paperwork? CSV omissions to add? Scope inflation to trim?
**Choices:**
- Signed change order — CSV total is authoritative
- CSV is missing line items — add and reprice
- Scope figure includes contingency / soft costs not in CSV
- Other (specify in text)
**Why:** Without reconciling, procurement runs on the wrong budget and
downstream billing schedules break.
```

**Gate.** If this question is emitted, the run MUST set
`interview_status: needs_more` in `intelligence/manifest.json`. The
interview cannot be marked `complete` until this question has a PM
answer in an interview round.

**Why.** Run #135 caught this ($73k gap on 308 Evergreen: $173,850 scope
vs $100,778 CSV). Run #137 lost it — the model didn't happen to notice
on that particular pass. Codifying makes it deterministic. No future run
can silently swallow a 5%+ arithmetic gap between scope and breakdown
totals.

**Edge cases.**
  * CSV totals only labor+material (no soft costs) while scope includes
    contingency: PM answer clarifies; agent updates
    `intelligence/facts.md` on next rebuild.
  * Scope has no explicit total: skip this rule. Question isn't emitted.
  * CSV total not resolvable (missing grand-total row, malformed file):
    emit a `data_quality` category question instead asking PM to
    confirm the CSV grand total.
