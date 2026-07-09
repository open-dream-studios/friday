---
generation_kind: risk_review_v1
depends_on:
  - _projects/9921-emmerson-ln-garage_APPPROJ-01KVV3710873M9AW2MH6STQWZB/jobs/9921-emmerson-ln-garage_JOB-01KVV371088TPDJ532ZF8FFJ28/inputs/scope.md
  - _projects/9921-emmerson-ln-garage_APPPROJ-01KVV3710873M9AW2MH6STQWZB/jobs/9921-emmerson-ln-garage_JOB-01KVV371088TPDJ532ZF8FFJ28/manifest.json
  - _projects/9921-emmerson-ln-garage_APPPROJ-01KVV3710873M9AW2MH6STQWZB/jobs/9921-emmerson-ln-garage_JOB-01KVV371088TPDJ532ZF8FFJ28/generations/baseline.md
  - _company/rules/_examples/plumbing_rough_min_duration.md
  - _company/knowledge/_examples/wills_voice.md
  - _company/knowledge/308_evergreen_wills_audit_transcript.md
last_verified_at: "2026-06-23T20:59:08.726Z"

---

# Risk register — 9921 Emmerson Ln

- **Job:** JOB-01KVV371088TPDJ532ZF8FFJ28
- **AppProject:** APPPROJ-01KVV3710873M9AW2MH6STQWZB
- **Generated against:** `generations/baseline.md` (which itself is built against `inputs/scope.md` while flagging the manifest/scope conflict)

Every entry below cites the trunk file that justifies it. Items without a citable source are excluded.

---

## Top 5 risks

### R1 — Manifest vs. scope describe two different jobs
**Severity: HIGH** (blocking; nothing else is reliable until resolved)

- **Trigger:** Anyone treats this job as planned without first reconciling the inputs.
- **Sources:** `manifest.json` (`job_type: addition`, `summary: "Garage Addition"`, `tags: [addition]`, folder slug `9921-emmerson-ln-garage`) vs. `inputs/scope.md` ("Master bath full gut. New tile shower, vanity, fixtures. ~6 weeks target."). Conflict already flagged in `generations/baseline.md` ("⚠ Input conflict").
- **Impact:** If the real job is the garage addition, the entire baseline (cost-floor, runway logic, on-site sequence) is for the wrong scope. A garage addition pulls in TDEC, footings/slab, framing inspection, exterior envelope — none of which the current baseline plans. Conversely, if the bath remodel is correct, the manifest's `job_type: addition` will mis-route any downstream automation that branches on job type.
- **Mitigation:**
  1. Stop further generation against this job until the PM (or Will) confirms which file is truth.
  2. Whichever wins, correct the loser in the same commit: either rewrite `inputs/scope.md` against a real addition scope, or fix `manifest.json` (`job_type`, `summary`, `tags`) and rename the folder slug to match.
  3. Re-run `baseline_estimate_v1` after reconciliation so this risk doc and the baseline reference the same job.

### R2 — No cost baseline; the question this job exists to answer is currently unanswerable
**Severity: HIGH**

- **Trigger:** Customer or PM asks for the customer-vs-direct gap before a breakdown or actuals exist.
- **Sources:** `generations/baseline.md` ("Cost baseline — Direct cost subtotal: not derivable from current inputs"); job tree shows no `inputs/breakdown.json`, no `inputs/notes.md`; `_company/actuals/README.md` explicitly says "**P9 territory.** This folder is empty during P1–P8."; transcript lines 47–69 show the breakdown-CSV ingestion flow Will demonstrated on 308 Evergreen.
- **Impact:** Estimate gets locked to a gut-feel number with no traceable derivation. Future learning loop (actuals → baseline) breaks because there's no anchor to compare against on closeout.
- **Mitigation:**
  1. Request PM Buildertrend export → `inputs/breakdown.csv` and run it through the same path the 308 transcript demonstrates.
  2. Until a breakdown lands, do not publish a dollar figure outward — the only sourced number is the 4-day × 2-crew plumbing-rough labor floor from `_company/rules/_examples/plumbing_rough_min_duration.md`.
  3. On closeout, harvest this job into `_company/actuals/` so the next master-bath baseline has an anchor (per `_company/actuals/README.md`).

### R3 — Scope is one sentence; every silent line item is a change-order vector
**Severity: HIGH**

- **Trigger:** Construction starts on a scope of "New tile shower, vanity, fixtures" without dimensions, fixture counts, plumbing-reroute language, electrical work, HVAC work, or substrate spec.
- **Sources:** `inputs/scope.md` (full text is one line). Risk catalog in `generations/baseline.md` § "Risks #2" + § "Open questions" enumerates the silent dimensions.
- **Impact:** Each undeclared dimension becomes a mid-job CO or a margin leak. Tile spec alone (subway vs. mosaic, niche, bench, substrate Schluter vs. hot-mop) swings the on-site long pole from 4 days to 6+ — see baseline § "On-site execution" line 9.
- **Mitigation:**
  1. Before signature, get answers to the seven Open Questions in `baseline.md` § "Open questions" (job-type reconciliation, selections-runway start, plumbing reroutes, HVAC, electrical, tile spec, breakdown).
  2. Codify the answers in `inputs/scope.md` and `inputs/notes.md` rather than as verbal commitments. Re-run baseline against the revised scope.

### R4 — Customer "~6 weeks" target is ambiguous and probably misaligned
**Severity: MEDIUM**

- **Trigger:** Customer signs against an expectation of "done in 6 weeks" without clarifying whether that's on-site or signed-to-keys.
- **Sources:** `inputs/scope.md` ("~6 weeks target"); `generations/baseline.md` § "Duration baseline" computes 4–6 weeks on-site + 3-week selection runway = 7–9 weeks signed-to-closeout. Selections floor sourced to transcript line 220 ("two or three weeks before the project starts").
- **Impact:** If customer means signed-to-keys and selections aren't already underway, TCR is automatically 1–3 weeks late at signature. Late-delivery posture from day one damages the relationship and biases the rest of the project toward concession.
- **Mitigation:**
  1. Confirm in writing which clock the 6 weeks counts — on-site or signed-to-keys.
  2. If signed-to-keys: either renegotiate the target to 7–9 weeks, or get selections locked before signature so the 3-week runway shrinks to zero.
  3. Make the selections-locked checkpoint a precondition for signature, not a phase-1 task.

### R5 — Plumbing rough hard-floor (4d × 2 crew) constrains any "compress the bath" instinct
**Severity: MEDIUM**

- **Trigger:** Anyone tries to compress the on-site schedule by collapsing plumbing rough below 4 working days × 2 crew, e.g. to hit the customer 6-week target.
- **Sources:** `_company/rules/_examples/plumbing_rough_min_duration.md` (severity: hard) — applies to any job that includes a master bath. Will's source line: transcript line 484 ("four days for two guys… that's fine for this kind of job"), echoed in `_company/knowledge/_examples/wills_voice.md` § "Plumbing rough".
- **Impact:** Compressing plumbing rough violates a hard rule and historically produces callbacks (the rationale in the rule file). If the validator gets wired (per `CONVENTIONS.md` § "Validator promise"), generations that under-budget plumbing will be rejected.
- **Mitigation:**
  1. Lock plumbing rough at ≥4d × 2 in any schedule generation for this job.
  2. If compression pressure appears, look elsewhere on the critical path — tile long pole and drywall (3–5d) are softer numbers in the baseline.
  3. If the job is truly powder-room-grade plumbing rather than master-bath (it isn't, per scope), override at job level — never weaken the company rule.

---

## Watch list (lower priority but live)

| # | Item | Source | Why it's on watch, not in top 5 |
|---|---|---|---|
| W1 | MEP-before-framing inspection sequencing | Transcript lines 398–404 (Will: "framing inspection can't happen until after MEP inspections") | Code reality, not unique to this job. Catches teams that haven't run a remodel before; routine for any seasoned PM. Schedule generation must encode it. |
| W2 | Drywall tie-in cracks Year 1 | `_company/knowledge/_examples/wills_voice.md` § "Drywall warranty" | Will calls it expected, not a defect. Risk is mis-categorizing the return visit as a callback (margin hit) instead of budgeting it as warranty (planned cost). |
| W3 | Tile shower is the on-site long pole | `generations/baseline.md` § "On-site execution" row 9 (4–6 days) + § "Critical-path gates" #5 | Already flagged on the critical path; lives here because the day-count tightens the moment tile spec is answered (see R3). |
| W4 | Finish-material delivery timing | Transcript lines 220, 232–234 (Will: "two or three weeks before" / "week or two prior to when we need them"); for a bath remodel install is Day 1 of finish | Procurement slip directly slips the long pole. PM order calendar handles this; track it. |
| W5 | Permit "walk in, walk out" is 90%, not 100% | Transcript lines 132–136 | One-week buffer per baseline § "Pre-construction runway" covers the 10% case. Risk only if PM assumes 100%. |
| W6 | Dumpster + equipment day-before delivery | Transcript lines 261–268, 272 | Standard PM checklist item. Belongs in schedule generation; not a project-killer if missed by a day. |
| W7 | HVAC scope undeclared (mini-split tie-in vs. existing vent) | `inputs/scope.md` is silent; transcript lines 476, 482, 494 size the work at ~½ day if mini-split | Half-day swing. Real risk is downstream automation assuming "no HVAC" and missing a permit/inspection lane. |
| W8 | Electrical scope undeclared (new circuits vs. fixture swap) | `inputs/scope.md` silent; transcript line 474 sizes panel/circuit work at one person × one day | Same shape as W7 — small day-count, but undeclared scope risks a missed inspection or undersized estimate. |
| W9 | Inspector-day PM presence | Transcript lines 516–527 (Will: "the project manager should really walk through it with the inspector") | Operational hygiene. Risk is PM no-shows the inspection day and chases a vague report for a week. |
| W10 | Post-inspection punch buffer (2–4 days, nothing scheduled) | Transcript lines 530–532 | Already encoded in baseline § "On-site execution" row 11. Watch in case schedule generation drops it under compression pressure (see R5). |

---

## How to use this register

- R1 must be closed before any other risk is actionable; the whole document is conditional on which scope is real.
- R2 and R3 are the levers that turn this baseline from a thin first-cut into a defensible estimate. Both are unblocked by PM input, not by more agent reasoning.
- R4 is a pre-signature conversation, not a construction risk. Handle it before the contract, not after.
- R5 and the watch list are operating constraints — they shape the schedule generation and the PM checklist, they don't block the estimate.
