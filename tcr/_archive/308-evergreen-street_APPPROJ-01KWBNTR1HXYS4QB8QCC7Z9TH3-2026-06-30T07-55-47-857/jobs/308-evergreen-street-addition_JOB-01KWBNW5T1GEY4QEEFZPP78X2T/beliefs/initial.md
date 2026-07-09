---
generation_kind: intel_questions_v1
interview_status: complete
round: 8
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWBNTR1HXYS4QB8QCC7Z9TH3/jobs/308-evergreen-street-addition_JOB-01KWBNW5T1GEY4QEEFZPP78X2T/generations/_pre/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KWBNTR1HXYS4QB8QCC7Z9TH3/jobs/308-evergreen-street-addition_JOB-01KWBNW5T1GEY4QEEFZPP78X2T/generations/_pre/breakdown.md
  - _projects/308-evergreen-street_APPPROJ-01KWBNTR1HXYS4QB8QCC7Z9TH3/jobs/308-evergreen-street-addition_JOB-01KWBNW5T1GEY4QEEFZPP78X2T/generations/_pre/plans.md
  - _projects/308-evergreen-street_APPPROJ-01KWBNTR1HXYS4QB8QCC7Z9TH3/jobs/308-evergreen-street-addition_JOB-01KWBNW5T1GEY4QEEFZPP78X2T/generations/_pre/rules_index.json
  - _projects/308-evergreen-street_APPPROJ-01KWBNTR1HXYS4QB8QCC7Z9TH3/jobs/308-evergreen-street-addition_JOB-01KWBNW5T1GEY4QEEFZPP78X2T/manifest.json
  - _projects/308-evergreen-street_APPPROJ-01KWBNTR1HXYS4QB8QCC7Z9TH3/jobs/308-evergreen-street-addition_JOB-01KWBNW5T1GEY4QEEFZPP78X2T/beliefs/interview-2026-06-30T07-21-33-548.md
  - _projects/308-evergreen-street_APPPROJ-01KWBNTR1HXYS4QB8QCC7Z9TH3/jobs/308-evergreen-street-addition_JOB-01KWBNW5T1GEY4QEEFZPP78X2T/beliefs/interview-2026-06-30T07-21-47-983.md
  - _projects/308-evergreen-street_APPPROJ-01KWBNTR1HXYS4QB8QCC7Z9TH3/jobs/308-evergreen-street-addition_JOB-01KWBNW5T1GEY4QEEFZPP78X2T/beliefs/interview-2026-06-30T07-22-03-577.md
  - _projects/308-evergreen-street_APPPROJ-01KWBNTR1HXYS4QB8QCC7Z9TH3/jobs/308-evergreen-street-addition_JOB-01KWBNW5T1GEY4QEEFZPP78X2T/beliefs/interview-2026-06-30T07-22-16-145.md
  - _projects/308-evergreen-street_APPPROJ-01KWBNTR1HXYS4QB8QCC7Z9TH3/jobs/308-evergreen-street-addition_JOB-01KWBNW5T1GEY4QEEFZPP78X2T/beliefs/interview-2026-06-30T07-22-27-127.md
  - _projects/308-evergreen-street_APPPROJ-01KWBNTR1HXYS4QB8QCC7Z9TH3/jobs/308-evergreen-street-addition_JOB-01KWBNW5T1GEY4QEEFZPP78X2T/beliefs/interview-2026-06-30T07-27-28-794.md
  - _projects/308-evergreen-street_APPPROJ-01KWBNTR1HXYS4QB8QCC7Z9TH3/jobs/308-evergreen-street-addition_JOB-01KWBNW5T1GEY4QEEFZPP78X2T/beliefs/interview-2026-06-30T07-27-43-777.md
last_verified_at: "2026-06-30T07:29:27.333Z"
---

# Intel Questions — 308 Evergreen Street Addition (Round 8 — COMPLETE)

All round-1 (8 questions) and the three round-6 follow-ups have been answered by
the PM. The interview is now **complete**: every CRITICAL trigger is resolved,
every HIGH trigger is resolved or logged as a confirmed risk, and no remaining
follow-up would measurably change the eventual task graph. The facts below fold
in every confirmed answer.

## What we know

### Customer & Job
- Customer is **308 Evergreen Street**; job type is **addition** (manifest.json). Field/drawings address is 647 AA Deakins Rd, Jonesborough TN 37659 — project/plans address mismatch flagged in `_pre/plans.md` Discrepancy 5 (verify the drawing set is the correct one for this job before construction).
- **Two-story addition** (basement + first floor), **30ʼ × 10ʼ, ~590 sqft total**, plus a primary bedroom remodel (`_pre/scope.md` Footprint).

### Scope (new construction objective)
- Objective areas: **new primary bedroom suite** (bedroom, master bath ~7ʼ×4ʼ custom tile shower w/ niche + return bench, his/hers walk-in closets, linen), **basement storage addition**, and an **elevator shaft (frame only, 4ʼ×4ʼ, 30A rough-in)** (`_pre/scope.md`; `_pre/plans.md` Structural).
- Foundation is **monolithic slab** (12" footings + 4" slab, no CMU/foundation wall) — monolithic pour default applies (`_pre/scope.md` Foundation; rule: company:`_company/rules/editor_rules.md`, rank 100).
- One **3-ply 14" LVL beam** (~15ʼ-6" span) opens an existing load-bearing wall; temporary shoring required. **PM-CONFIRMED:** the addition's floor system above **loads on this beam** — the new floor framing IS load-bearing on the LVL location, so LVL install must precede that floor framing (`_pre/scope.md` Framing; `_pre/plans.md` Structural). Standard 3-ply engineered LVL (presumed standard order, 7–14 day lead).

### Trades
- HVAC is a **ductless mini-split** ($2,500 budget) — MEP rough order is plumbing → electrical → mini-split line set; rough = 0.5d/1, install = 1d/1 (`_pre/scope.md` HVAC; rule: company:`_company/rules/editor_rules.md`, rank 100).
- **PM-CONFIRMED (round 6): tankless water heater IS in scope.** Customer signed off on the $6,500 option. Add a **tankless procurement task (~10 day standard lead)**; the **tankless install replaces the tank-set task**, and the **gas line + vent extension to the new roof location stays**. Because a tankless (not a tank) is being set, the **Rule 4H tank-set-FIRST sequence is skipped entirely** — plumbing rough-in does not gate on a `plumbing.tank_set` predecessor (rule: company:`_company/rules/dev_rules.md` 4H, rank 100).
- Plumbing includes a **master bath (2 lav + toilet + custom shower), W/D relocation, and vent stacks through roof** — hits the 4-day × 2-crew rough-in floor (`_pre/scope.md` Plumbing; rule: company:`_company/rules/editor_rules.md`, rank 100).
- Electrical includes a **new 100A subpanel**. **PM-CONFIRMED:** existing main service capacity is **unverified** — plan a pre-construction **amperage-check task** and budget a **service-upgrade contingency** (200A main panel swap), surfaced as a contingency line, NOT baked into base contract.

### Sequencing / Retrofit (all PM-CONFIRMED)
- **Customer early item:** hall bath **acrylic shower swap** — customer wants it done BEFORE main demo so they keep a working shower throughout construction. Gets `early.<name>` task in `site_prep / customer_early_items`, Day 1, off the critical path (rule: company:`_company/rules/dev_rules.md` 4V, rank 100).
- **Hall bath (BTH. 2) is full retrofit** of the existing house (acrylic shower swap + window infill + drywall patch + repaint) → its own `hall_bath_mod` Component running parallel to main scope. The acrylic swap two-buckets: early item in site_prep, the rest in interior_finishes (rule: company:`_company/rules/editor_rules.md` two-bucket, rank 100).
- **Primary bedroom remodel is retrofit** in the EXISTING house (framing mods, drywall, LVT, trim, paint) — distinct from the new addition's master bedroom. **Two bedroom buckets, not one** → own retrofit Component.
- **Existing-house mods are all retrofit, bundled into one existing-house Component:** window relocations (×2), dryer-vent reroute, door relocation. Run parallel with main addition; gated only by their own physical deps (not new-construction framing/foundation).
- Roof is a **complex tie-in**: new 3/12 gable into existing 6/12, valley cuts at two points, "verify existing slopes/soffit before construction" drawing flag, plus an existing chimney near the tie-in zone — concealed-condition risk (`_pre/plans.md` Structural, Roof tie-in, Retrofit indicator 6).
- **PM-CONFIRMED (round 6): the concealed roof tie-in discovery buffer is ACCEPTED.** Bake in a **2–3 day concealed-conditions discovery buffer** at the 3/12 → 6/12 tie-in as **non-negotiable schedule float** (NOT a CO contingency). Framing sub on call day 1 of the dried-in window to verify existing rafter conditions; if off-spec, the buffer absorbs it without slipping downstream MEPs. Carry a chimney-flashing allowance at the valley.

### Procurement (PM-CONFIRMED)
- **Roof framing is stick-framed** — 590 sqft / ~10ʼ span, well under the 24ʼ truss threshold. **No `procurement.trusses` task** (rule: job_type:`job_types/addition/rules/addition_rules.md`, rank 200; belief: stick_frame_default_for_small_additions).
- **Septic — TCR handles the TDEC permit.** Adding a bathroom triggers a soil/field review. **Plan a ~6-week pre-construction window** for TDEC; it gates the realistic start date (rule: job_type:`job_types/addition/rules/tdec_septic_permit_offset.md`, rank 200 — `permit.tdec_septic` carries `pre_construction_offset_working_days: 30`).
- **Windows — PM-CONFIRMED (round 6): defer to the drawing schedule** (drawings are the latest authoritative source; scope's window line is stale). **Final count: 2 windows — 1 transom + 1 36"×36" double-hung. Stock vinyl, standard ~14 day supplier lead.** Drop ~$1,200 from the scope window line as a scope correction. This sets `wait.windows` lead time at ~14 calendar days and the install duration accordingly (resolves `_pre/plans.md` Discrepancies 2, 4).
- **Brick veneer IS in scope** (lower level: brick below, lap siding above) — drawings are correct, the cost breakdown missed the brick line. **Add a masonry sub + brick procurement (~2-week lead)**; revise the siding line to vinyl lap. Flag as a likely materials change-order. Masonry becomes an exterior-sequence trade gating siding above it (`_pre/plans.md` Discrepancy 1).
- **Tankless procurement (~10 day standard lead)** added per the round-6 tankless confirmation above.

### Cost / scope corrections (not task-graph-blocking, logged for downstream)
- Negative material credit (-$4,199 on the Existing Hall Bath / Bedroom / Closeout line) is a buyback/credit, not work to expand (`_pre/breakdown.md` Note 1).
- HVAC material (~$5,140) running >2× the $2,500 mini-split budget is now explained by the confirmed tankless inclusion partially priced into that line (`_pre/breakdown.md` Note 4).

## What we're uncertain about

None. All CRITICAL and HIGH triggers from the curated question bar have been
answered or accepted as logged risk. The remaining open items (brick change-order
pricing, window-line credit, negative material credit) are cost/scope-correction
items the PM handles administratively — they do not block a high-quality task
graph. **Interview complete; no further questions.**

## Open commitments

- Tankless WH ($6,500 option) signed off by customer — included in contract.
- Concealed roof tie-in 2–3 day discovery buffer accepted as fixed schedule float (not a CO).
- Service-upgrade (200A) treated as a contingency line, NOT base contract.
- Brick veneer + ~$1,200 window-line drop flagged as a likely materials change-order to reconcile with the customer.
