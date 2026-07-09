---
generation_kind: intel_questions_v1
interview_status: needs_more
round: 1
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWBK10XGZAZRZH36BEG30TGJ/jobs/308-evergreen-street-addition_JOB-01KWBK1Y38CDJ808X76SSAKKEP/generations/_pre/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KWBK10XGZAZRZH36BEG30TGJ/jobs/308-evergreen-street-addition_JOB-01KWBK1Y38CDJ808X76SSAKKEP/generations/_pre/breakdown.md
  - _projects/308-evergreen-street_APPPROJ-01KWBK10XGZAZRZH36BEG30TGJ/jobs/308-evergreen-street-addition_JOB-01KWBK1Y38CDJ808X76SSAKKEP/generations/_pre/plans.md
  - _projects/308-evergreen-street_APPPROJ-01KWBK10XGZAZRZH36BEG30TGJ/jobs/308-evergreen-street-addition_JOB-01KWBK1Y38CDJ808X76SSAKKEP/generations/_pre/rules_index.json
  - _projects/308-evergreen-street_APPPROJ-01KWBK10XGZAZRZH36BEG30TGJ/jobs/308-evergreen-street-addition_JOB-01KWBK1Y38CDJ808X76SSAKKEP/manifest.json
last_verified_at: "2026-06-30T06:47:47.188Z"
---

## What we know

### Customer & job

- **Customer 308 Evergreen Street; job type = addition** (manifest.json). Two-story addition (~30' × 10' per floor) with basement storage, primary bedroom expansion, master bathroom, walk-in closet, and a 4'×4' future elevator shaft rough-in (`_pre/scope.md` Customer & Job, Footprint).
- **Addition footprint ~590 sqft** (295 basement + 295 first floor), confirmed against the plans (`_pre/plans.md` Structural decisions). Under the 800 sqft small-addition threshold.

### Scope (objective areas where new construction is presumed)

- **Named new-construction areas:** basement storage, 1st-floor primary bedroom/master bath/walk-in closet suite, elevator shaft. These are the ONLY presumed-new areas; everything else is retrofit-suspect (`_pre/scope.md`; `_pre/plans.md` Retrofit indicators).
- **Master bath is full wet area:** 7'×4' custom tile shower (waterproofing, niche, bench, mosaic floor), 72" double vanity, two faucets, commode (`_pre/scope.md` Plumbing/Interior Finishes). This triggers the 4-day × 2-crew plumbing rough-in floor (rule: company:`_company/rules/editor_rules.md`, rank 100).

### Trades & sequencing

- **HVAC is a ductless mini-split** ($2,500 budget), explicitly stated in scope (`_pre/scope.md` HVAC). MEP rough order is therefore plumbing → electrical → mini-split line set; not asking q.hvac_type (rule: company:`_company/rules/editor_rules.md`, rank 100).
- **Roof framing is stick-frame by default:** addition <800 sqft, ~10' span, plans (sheet 04-A) show ridges/valleys consistent with rafter framing and no truss grid — but scope literally says "truss or rafter, determined during design phase" (`_pre/scope.md` Framing; `_pre/plans.md` Discrepancy 3). Confirming below to lock procurement (rule: job_type:`job_types/addition/rules/addition_rules.md`, rank 200 > company default).
- **LVL beam in scope:** one 3-ply 14" LVL spanning ~15'-6" to open an existing load-bearing wall; temporary shoring required before demo of that wall (`_pre/scope.md` Framing; `_pre/plans.md` Structural decisions).
- **Roof tie-in is non-trivial:** new 3:12 ties into existing 6:12 at multiple valleys, with a chimney near the footprint and a "CONTRACTOR TO VERIFY EXISTING ROOF SLOPES" note (`_pre/plans.md` Structural decisions, Discrepancies 1/6).

### Site & procurement

- **Septic vs sewer is unresolved:** scope requires septic inspection and excludes relocation/grinder pump (TBD via change order); for an addition adding a bathroom, septic handling drives a long-lead TDEC permit (`_pre/scope.md` Special Features; rule: job_type:`job_types/addition/rules/tdec_septic_permit_offset.md`, rank 200).
- **100A subpanel in scope; existing main service assumed adequate but unverified** (`_pre/scope.md` Electrical). Breakdown also flags electrical labor as possibly under-budgeted (`_pre/breakdown.md` Anomaly 3).
- **Tankless water heater is an OPTIONAL $6,500 allowance not cleanly costed** — CSV title says "Incl. Tankless WH Option" but the breakdown doesn't carry the full allowance (`_pre/breakdown.md` Silent omission 4, Anomaly 7). Whether a new WH is installed determines if the tank_set-first sequence applies (rule: company:`_company/rules/editor_rules.md`, rank 100). Scope also lists a water-heater vent extension through the new roof (`_pre/scope.md` Demolition).
- **Heat pump / electrical disconnect relocation is in scope** and must precede demo (`_pre/scope.md` Demolition; rule: company:`_company/rules/editor_rules.md`, rank 100 — handled in site_prep, not a PM question).

### Plans vs scope discrepancies (load-bearing)

- **Exterior finish conflict (CRITICAL):** scope says vinyl siding throughout; plans (sheets 02-A) annotate `NEW BRICK TO MATCH EXISTING` on the lower level and lap siding above. No masonry section exists in the breakdown — brick is unpriced and is a slow trade with procurement lead (`_pre/plans.md` Discrepancy 1).
- **Window count:** scope says 4 windows (3× 36"×60" + transom); extracted schedule shows only 2 types — likely an extraction artifact, scope count governs (`_pre/plans.md` Discrepancy 2). Not asking; PM verifies against full PDF.

## What we're uncertain about

### q.customer_early_items

**Question:** Did the customer ask TCR to handle any work BEFORE the main job starts — e.g. the existing hall-bath acrylic shower swap — so they can live in the home comfortably during construction?
**Category:** sequencing
**Hint:** The hall-bath tub/shower swap is the likely candidate; we need to know if it's a Day-1 item.
**Choices:**
- yes — hall bath acrylic shower swap before main demo
- yes — something else (specify)
- no early items
**Why:** Customer early items get a dedicated `early.<name>` task in `site_prep / customer_early_items`, off the critical path, separate from the hall-bath retrofit work (rule: job_type:`job_types/addition/rules/addition_rules.md`, rank 200).

### q.roof_framing

**Question:** Is the new gable roof framed with engineered trusses (long-lead procurement) or stick-framed on site (next-day lumber)?
**Category:** procurement
**Hint:** Scope says "truss or rafter, TBD in design"; plans imply stick frame tying a 3:12 into the existing 6:12 at multiple valleys. Concealed existing-rafter conditions are a real change-order risk until demo opens them — a 2–3 day discovery buffer is recommended.
**Choices:**
- stick-frame
- trusses
- unsure — design phase pending
**Why:** Trusses require a `procurement.trusses` task with 28–42 day lead; stick-frame needs none. The tie-in complexity also sizes the roof-framing duration and discovery buffer.

### q.retrofit_areas

**Question:** Several features sit OUTSIDE the new addition footprint and read as retrofit work — for each, is it retrofit (existing-area mod) or part of the main addition scope?
**Category:** scope
**Hint:** Confirm each: (a) existing hall bath (BTH. 2) window infill + drywall/repaint; (b) primary bedroom remodel ~12'5"×16'; (c) two relocated existing windows on left elevation + one on back; (d) dryer-vent relocation in the existing structure; (e) hallway switch relocation + patch/repaint.
**Choices:**
- all retrofit (existing-area work, independent of new-construction deps)
- some are main scope (specify which)
- unsure
**Why:** Retrofit items go in their own Components with no new-construction dependencies; one missed candidate produces a wrong dependency edge in the task graph (rule: job_type:`job_types/addition/rules/addition_rules.md`, rank 200).

### q.exterior_finish_material

**Question:** Is the addition exterior vinyl siding throughout (per scope), or brick veneer on the lower level with lap siding above (per the elevation drawings)?
**Category:** scope
**Hint:** Plans annotate `NEW BRICK TO MATCH EXISTING` on the lower level, but no masonry trade is priced in the breakdown.
**Choices:**
- vinyl siding throughout (scope governs)
- brick lower + siding upper (drawings govern — needs masonry sub + brick procurement)
- unsure — will confirm with designer
**Why:** Brick adds an unpriced masonry trade, brick procurement lead, and slow productivity (~150 brick/day) that the schedule must model before sheathing closes.

### q.tankless_wh

**Question:** Is the optional tankless water heater being installed (replacing the existing WH), or is the existing water heater staying with only a vent extension through the new roof?
**Category:** procurement
**Hint:** Breakdown is ambiguous — a $6,500 tankless allowance is listed optional but the title implies it's included.
**Choices:**
- tankless installed (replaces existing WH)
- existing WH stays — vent extension only
- unsure
**Why:** If a new WH is installed, the tank_set-first sequence and a WH procurement task apply; if not, plumbing rough-in proceeds with no tank predecessor (rule: company:`_company/rules/editor_rules.md`, rank 100).

### q.septic_tdec

**Question:** Is the home on septic or city sewer, and if septic, does TCR need to pull the TDEC septic permit?
**Category:** permits
**Hint:** Scope requires a septic inspection and excludes relocation/grinder pump (TBD via change order).
**Choices:**
- city sewer
- septic — TCR handles TDEC permit
- septic — homeowner handles
- unsure
**Why:** A TCR-pulled TDEC septic permit anchors at pre-construction start with a 30 working-day offset (6-week procurement window) and can gate excavation (rule: job_type:`job_types/addition/rules/tdec_septic_permit_offset.md`, rank 200).

### q.lvl_load_bearing

**Question:** Does the new addition's floor or roof load actually bear on the existing LVL beam location, or is the LVL only opening the existing load-bearing wall?
**Category:** structural
**Hint:** Determines whether new framing must wait on LVL install or can run independently.
**Choices:**
- yes — new floor/roof bears on the LVL
- no — LVL only opens the existing wall
**Why:** If the new load bears on the LVL, framing above must be FS-after LVL install; if not, the LVL/shoring sub-chain runs independently of new framing (rule: job_type:`job_types/addition/rules/addition_rules.md`, rank 200).

### q.electrical_service

**Question:** Has the existing main electrical service been verified to support the new 100A subpanel, or is a service upgrade needed?
**Category:** scope
**Hint:** Scope assumes the existing service is adequate but notes verification is required.
**Choices:**
- verified adequate
- upgrade needed
- unsure — will verify
**Why:** A service upgrade adds an early electrical task and potential utility-coordination lead time ahead of subpanel install.

## Open commitments

- None recorded. Scheduled dates are not yet set in manifest.json (`started_at` only); confirm a target on-site start before pre-construction offsets are anchored.
