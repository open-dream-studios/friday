---
generation_kind: intel_questions_v1
interview_status: needs_more
round: 1
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWBDWA7JGKMSJC48DH7GZVPT/jobs/308-evergreen-street-addition_JOB-01KWBDX5S2P1B9DP5JW5G5JKG5/generations/_pre/MANIFEST.md
  - _projects/308-evergreen-street_APPPROJ-01KWBDWA7JGKMSJC48DH7GZVPT/jobs/308-evergreen-street-addition_JOB-01KWBDX5S2P1B9DP5JW5G5JKG5/generations/_pre/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KWBDWA7JGKMSJC48DH7GZVPT/jobs/308-evergreen-street-addition_JOB-01KWBDX5S2P1B9DP5JW5G5JKG5/generations/_pre/breakdown.md
  - _projects/308-evergreen-street_APPPROJ-01KWBDWA7JGKMSJC48DH7GZVPT/jobs/308-evergreen-street-addition_JOB-01KWBDX5S2P1B9DP5JW5G5JKG5/generations/_pre/plans.md
  - _projects/308-evergreen-street_APPPROJ-01KWBDWA7JGKMSJC48DH7GZVPT/jobs/308-evergreen-street-addition_JOB-01KWBDX5S2P1B9DP5JW5G5JKG5/generations/_pre/rules_index.md
  - _projects/308-evergreen-street_APPPROJ-01KWBDWA7JGKMSJC48DH7GZVPT/jobs/308-evergreen-street-addition_JOB-01KWBDX5S2P1B9DP5JW5G5JKG5/manifest.json
last_verified_at: "2026-06-30T05:10:28.176Z"
---

## What we know

**Customer & Job**

- This is the Simons family addition at 308 Evergreen Street, job_type `addition` (manifest.json; `_pre/scope.md` Customer & Job).
- Architect of record is Rebecca Lineberry, NCIDQ — Greyscale Design, drawings dated Jan 22 2026 (`_pre/scope.md`).
- Contract is ~$173,850 total investment; base cost breakdown grand total is $100,778.92 (the gap is markup/overhead/optional packages, not missing scope) (`_pre/breakdown.md` Notes).

**Scope**

- 30'×10' two-story addition: 295 sqft 1st-floor + 295 sqft basement = 590 sqft of NEW construction; ceiling 8' both floors (`_pre/scope.md` Footprint; `_pre/plans.md` Structural Decisions).
- CSV footprint header says 789 sqft vs. plans' 590 sqft new — the ~199 sqft gap likely covers the existing primary-bedroom remodel area, not new build (`_pre/breakdown.md` Notes).
- Master bath is in the new addition: 2 lav supplies/drains, toilet, 7'×4' custom tile shower with dual diverter, niche + bench, 72" double vanity (`_pre/scope.md` MEP / Finishes / Special Features).
- Elevator shaft is FRAMING ONLY (no elevator system) with a dedicated 30A circuit; scope names one 4'×4' shaft but plans show two markers (4'×4' and 4'×5') (`_pre/scope.md` Special Features; `_pre/plans.md` Things Plans Show).

**Site**

- Foundation is monolithic — 12"×12" continuous footings + 4" slab, no CMU/stem walls — so the default single-footing-inspection monolithic pour applies (`_pre/scope.md` Foundation; rules_index §4B).
- Standard-soil assumption; rock/unsuitable soil is a change order (`_pre/scope.md` Foundation).
- Existing heat pump + electrical disconnect must be relocated BEFORE demo, triggering the site_prep prep task (`_pre/scope.md` Special Features; rules_index §4K).

**Trades**

- HVAC is a ductless **mini-split** (budget $2,500) — confirmed in scope, so MEP rough order is plumbing → electrical → mini-split line set; no follow-up question needed (`_pre/scope.md` MEP; rules_index §4G).
- Plumbing rough-in hits the master-bath multi-fixture + W/D relocation + roof-vent floor of 4 working days × 2 crew (`_pre/scope.md` MEP; plumbing_rough_min_duration.md).
- Electrical is a 100A subpanel, full rough/trim, ~12 recessed lights, plus a dedicated 30A elevator circuit; existing service is *assumed* adequate (`_pre/scope.md` MEP).

**Sequencing**

- Drywall consolidates new addition + primary-bedroom remodel + basement storage + hall-bath patch into one hang/tape/sand block (rules_index editor_rules — Drywall consolidation).
- Standard 3-finish-trade overlap (electrical finish + plumbing finish + mini-split install) applies the default HVAC-after-electrical stagger to hold the 2-interior-trade cap (rules_index §4N).
- Roof tie-in is 3/12 new gable into existing 6/12 with valleys/transitions and an existing chimney at the tie-in — flagged repeatedly as the schedule risk (`_pre/scope.md` Special Features; `_pre/plans.md`).

**Procurement**

- Long-lead/procurement items use the 3-task order/wait/arrived pattern: windows, LVL beam, mini-split unit, electrical panel, plus finish materials gated on the selections checkpoint (rules_index §4R).
- Roof framing is ambiguous ("truss or rafter framed, determined during design phase"); stick-frame default applies (no truss procurement) unless the PM confirms trusses (rules_index §4Q; stick_frame_default_for_small_additions.md).

## What we're uncertain about

### q.customer_early_items

**Question:** Did the customer ask TCR to handle any work BEFORE the main job starts — for example swapping the hall-bath tub/shower for the acrylic shower system so they keep a working bathroom during construction?
**Category:** sequencing
**Hint:** Early items get their own Day-1 component in site_prep, off the critical path.
**Choices:**
- Yes — hall-bath acrylic shower swap is a Day-1 early item
- Yes — a different early item (please name)
- No early items
**Why:** A confirmed early item becomes an `early.<name>` task in `site_prep/customer_early_items` on Day 1 rather than being collapsed into mid-job retrofit timing (Rule 4V).

### q.retrofit_hall_bath

**Question:** The hall bathroom ("BTH. 2") sits outside the new addition footprint and the scope calls for window infill, framing, drywall, acrylic shower swap, and repaint — is the non-early-item portion of that work retrofit, run in parallel with the main scope?
**Category:** scope
**Hint:** The shower swap may be a Day-1 early item; the window infill/drywall/repaint is the retrofit portion.
**Choices:**
- Retrofit (parallel with main scope)
- Part of main addition scope
- Unsure
**Why:** Confirms the hall-bath window/drywall/repaint work goes in its own retrofit component (`hall_bath_mod`) gated on physical deps, not on new-construction dependencies (Rules 4V, §9).

### q.retrofit_primary_bedroom

**Question:** The primary bedroom (~12'5"×16', existing room with an "EXISTING WINDOW, RELOCATED") is getting framing mods, drywall, LVT, and trim — is this retrofit work inside the existing house, separate from the new addition build?
**Category:** scope
**Hint:** Plans label it as an existing room being opened toward the addition via the LVL beam.
**Choices:**
- Retrofit (existing room)
- Part of new addition scope
- Unsure
**Why:** Determines whether bedroom finishes get their own retrofit component or are commingled with new-construction dependencies (§9 retrofit detection).

### q.retrofit_basement_storage

**Question:** The basement storage finish (frame + drywall + paint + one light, slab stays bare) — is this inside the NEW 295 sqft basement addition, or finishing an EXISTING basement area?
**Category:** scope
**Hint:** Plans show a 295 sqft basement addition; scope's basement storage finish location isn't explicitly tied to it.
**Choices:**
- New addition basement
- Existing basement area (retrofit)
- Unsure
**Why:** Sets whether basement-storage framing/drywall chains off new-construction tasks or runs as independent retrofit (§9, §11 warning #27).

### q.roof_framing

**Question:** Is the addition roof framed with engineered trusses (long-lead procurement) or stick-framed on site (next-day lumber)?
**Category:** procurement
**Hint:** Scope says "truss or rafter framed, determined during design phase"; the ~10'-wide span points to stick-frame.
**Choices:**
- Stick-frame
- Trusses
- Unsure — design phase pending
**Why:** Trusses add a 28-42 day procurement chain to the critical path; stick-frame needs no truss procurement task (Rule 4Q).

### q.water_heater_tankless

**Question:** Is a new water heater (the optional tankless package) actually in this contract, or does the existing gas water heater stay with only its vent extended through the new roof?
**Category:** scope
**Hint:** Base scope says "extend existing WH vent"; the HVAC CSV section is titled "Tankless WH" with $5,140 material — ambiguous whether a tank is being installed.
**Choices:**
- Existing WH stays (vent extension only)
- New tankless WH is in scope
- Unsure
**Why:** A new/replacement water heater triggers the mandatory tank-set-FIRST sequence before plumbing rough-in (Rule 4H); a vent-only scope emits no tank tasks.

### q.septic_tdec

**Question:** Is the home on city sewer or septic, and if septic, does TCR need to handle the TDEC septic permit / grinder-pump evaluation as part of this job?
**Category:** permits
**Hint:** Scope flags a pre-construction TDEC inspection and grinder-pump feasibility as change-order items; the bathroom addition adds fixture load.
**Choices:**
- City sewer
- Septic — TCR handles TDEC
- Septic — homeowner handles
- Unsure
**Why:** A TCR-handled TDEC permit adds a long-lead pre-construction permit chain that can gate excavation; city sewer removes it entirely.

### q.concealed_roof_tie_in_ack

**Question:** The existing rafter/soffit conditions at the 3/12-into-6/12 tie-in (with chimney flashing) are concealed until demo opens them — do you accept a 2-3 day discovery buffer there, or do you want to discuss it?
**Category:** risk
**Hint:** This is the single biggest schedule risk on the job; the chimney at the tie-in compounds it.
**Choices:**
- Accepted — build in a 2-3 day buffer
- Want to discuss
**Why:** Confirms whether the task graph carries a discovery/change-order buffer at the roof tie-in or treats the integration as standard.
