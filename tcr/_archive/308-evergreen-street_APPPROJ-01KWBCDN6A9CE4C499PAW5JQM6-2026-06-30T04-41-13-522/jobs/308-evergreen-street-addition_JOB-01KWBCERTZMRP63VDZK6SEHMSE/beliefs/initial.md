---
generation_kind: intel_questions_v1
interview_status: needs_more
round: 1
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWBCDN6A9CE4C499PAW5JQM6/jobs/308-evergreen-street-addition_JOB-01KWBCERTZMRP63VDZK6SEHMSE/generations/_pre/MANIFEST.md
  - _projects/308-evergreen-street_APPPROJ-01KWBCDN6A9CE4C499PAW5JQM6/jobs/308-evergreen-street-addition_JOB-01KWBCERTZMRP63VDZK6SEHMSE/generations/_pre/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KWBCDN6A9CE4C499PAW5JQM6/jobs/308-evergreen-street-addition_JOB-01KWBCERTZMRP63VDZK6SEHMSE/generations/_pre/breakdown.md
  - _projects/308-evergreen-street_APPPROJ-01KWBCDN6A9CE4C499PAW5JQM6/jobs/308-evergreen-street-addition_JOB-01KWBCERTZMRP63VDZK6SEHMSE/generations/_pre/plans.md
  - _projects/308-evergreen-street_APPPROJ-01KWBCDN6A9CE4C499PAW5JQM6/jobs/308-evergreen-street-addition_JOB-01KWBCERTZMRP63VDZK6SEHMSE/generations/_pre/rules_index.md
  - _projects/308-evergreen-street_APPPROJ-01KWBCDN6A9CE4C499PAW5JQM6/jobs/308-evergreen-street-addition_JOB-01KWBCERTZMRP63VDZK6SEHMSE/manifest.json
last_verified_at: "2026-06-30T04:36:03.571Z"
---

## What we know

### Customer & job

- Customer is 308 Evergreen Street; job type is `addition` (manifest.json).
- Designer: Rebecca Lineberry NCIDQ, Greyscale Design LLC; drawings dated Jan 22 2026, 5 sheets (`_pre/plans.md` "Drawing set").
- Quoted total investment $173,850 (scope L179) vs. breakdown CSV grand total $100,778.92 — ~$73K gap, likely margin/overhead/contingency not on the cost CSV (`_pre/breakdown.md` Notes).

### Scope (addition core)

- Two-story addition ~29'5" × 10', basement + first floor. Per plan schedule: 295 sqft each level = **590 sqft total addition area** (`_pre/plans.md` "Structural decisions"; scope L3).
- Addition objective areas: primary bedroom, master bath, walk-in closet (upstairs) + basement storage (downstairs) (`_pre/scope.md` "Special features"; scope L130-140).
- Foundation is monolithic — 12"×12" perimeter footings + 4" slab, NO CMU / NO stem walls (`_pre/scope.md` "Foundation"; scope L40-45). Triggers single-pour pattern per dev_rules §4B.
- Framing: 2x4 @ 16" OC; floor system glued + fastened; 3-ply 14" LVL spans ~15'-6" to open an existing load-bearing wall, with temporary shoring; 4'×4' future elevator shaft framed in (`_pre/scope.md` "Framing"; scope L47-55).
- Roof: new gable, 3/12 new tying into existing 6/12; framing method explicitly UNDETERMINED — scope says "truss or rafter framed, determined during design phase" (scope L57-58).

### Trades

- HVAC is mini-split (scope L99, $2,500 allowance). MEP rough order per dev_rules §4G = plumbing → electrical → mini-split rough.
- Plumbing scope: master bath rough (2 lav + 1 toilet + 1 custom shower w/ dual-valve diverter), W/D relocation incl. roof venting, extend vent stacks through new roof (scope L88-96). Per `_company/rules/_examples/plumbing_rough_min_duration.md`, this forces ≥4d × 2 crew floor; CSV's 40 hrs is under-budgeted and must be overridden upward.
- Water heater: existing gas WH STAYS, only vent extended through new roof (scope L37). Tank-set rule §4H does NOT apply at baseline — UNLESS the optional tankless package (scope L183-185, $6,500 allowance) is taken.
- Electrical: new 100A subpanel, ~12 recessed lights, dedicated 120V 30A circuit for the future elevator (scope L73-85). Subpanel install per editor_rules = 1d / 1 person.
- Insulation, drywall, paint, LVT, trim, tile, vanity all per allowances at standard productivity (`_pre/scope.md` "Finishes").
- Drywall consolidation candidate across 4 zones: addition + bedroom remodel + basement storage + hall bath patch (rules_index drywall note).

### Site & pre-construction

- Heat pump relocation + electrical disconnect relocation explicitly in scope (L36) — both gate before demo per dev_rules §4K.
- Saw-cut existing concrete walkway + remove railroad ties / site obstructions (scope L33-34).
- TDEC septic inspection coordination + grinder pump feasibility study explicitly carved out as change-order placeholders, NOT in baseline scope (scope L25-29).
- Permits handled by contractor (scope L11) — applies dev_rules §4A 1-day work pattern with `pre_construction_offset_working_days: 15`.

### Procurement (per editor_rules + dev_rules §4R)

- Apply 3-task pattern (order/wait/checkpoint) to: windows, exterior door, LVL beam (3-ply 14"), electrical panel/subpanel, mini-split unit, custom shower tile + mosaic floor tile, 72" vanity, LVT flooring.
- Stick-frame default for small additions (<800 sqft, <24' span) per `_company/beliefs/_examples/stick_frame_default_for_small_additions.md` — confidence 0.92, fits 590 sqft / ~10' span. **No `procurement.trusses` task** unless PM overrides at interview.

### Sequencing

- Customer early item candidate: hall bath acrylic shower swap (scope L145-147) — rule §4V mandates two-bucket pattern (early item in `site_prep / customer_early_items` Day 1, retrofit work in `hall_bath_mod` parallel with main scope). Scope doesn't explicitly state "before main demo", so PM confirmation required.
- Retrofit candidates outside addition objective: hall bathroom modification (existing area, scope L141-149), primary bedroom remodel ~12'5" × 16' (scope L130-135), multiple existing-window relocations visible on Left/Back/Right elevations (`_pre/plans.md` "Retrofit indicators").
- Interior 2-trades-max + default mini-split-after-electrical stagger applies (dev_rules §4N).

### Scope-vs-plan discrepancies (Stage A flagged)

- **MAJOR exterior finish conflict**: plans show "NEW BRICK TO MATCH EXISTING" AND "NEW LAP SIDING" on all three elevations; scope L67 says vinyl siding only, no brick mention.
- **Window count**: scope L68 says (4) windows incl. (3) 36"×60" + (1) transom; plan schedule shows only 1 transom + 1 DH (3'×3') — 2 windows on plan vs 4 on scope.
- **Existing window relocations**: plans annotate 2-3 existing windows being relocated across Left/Back/Right elevations; scope mentions only the hall bath window removal.
- Door count math: scope says "(4) interior doors total" but enumerates (1) pre-hung + (2) pocket = 3.
- Chimney shown on roof plan (existing); not mentioned in scope.
- HVAC CSV line title bundles "Tankless WH" in $6,503 even though tankless is OPTIONAL in scope.

## What we're uncertain about

### q.customer_early_items

**Question:** The hall bathroom scope (scope L145-147) includes swapping the existing tub/shower combo for an acrylic shower system. Is this a customer-requested early item — meaning they want the swap done BEFORE main demo so they have a working shower during construction? Or does it happen alongside the rest of the hall bath retrofit work?
**Category:** sequencing
**Hint:** Affects whether the swap lands Day 1 in `site_prep` or parallel-tracks with main scope.
**Choices:**
- Early item — homeowner wants it Day 1 before main demo
- Bundled with hall bath retrofit (window infill, drywall, repaint)
- Unsure — will confirm with homeowner
**Why:** Determines whether to emit `early.acrylic_shower_swap` in `customer_early_items` Day 1 (rule §4V two-bucket pattern) or fold into `hall_bath_mod`.

### q.retrofit_primary_bedroom

**Question:** Scope describes a "Primary bedroom remodel (~12'5" × 16')" (L130-135) with framing modifications, drywall, paint, LVT, trim. The plans show the NEW primary bedroom in the addition footprint and label Bedroom 2 + Bedroom 3 as EXISTING. Is the "primary bedroom remodel" line referring to an EXISTING bedroom being remodeled (retrofit, parallel with main scope) or to additional finish work in the NEW addition primary bedroom?
**Category:** scope
**Hint:** If retrofit, it goes in its own Component and won't gate on new-construction tasks.
**Choices:**
- Existing bedroom — retrofit, parallel with main addition work
- New primary bedroom in addition — same component as addition build
- Different scope entirely — please clarify
**Why:** Decides whether to emit a separate retrofit Component (dev_rules §9) or bundle with addition finish tasks.

### q.windows_discrepancy

**Question:** Plans show only 2 NEW windows in the addition (1 transom + 1 DH 3'×3') AND annotate 2-3 EXISTING windows being relocated across the Left/Back/Right elevations. Scope L68 says (4) new windows including (3) 36"×60" + (1) transom and mentions only ONE existing-window scenario (hall bath infill). Which is right for procurement and sequencing?
**Category:** scope
**Hint:** Drives windows procurement count and whether the existing-window relocations are retrofit tasks or part of addition framing.
**Choices:**
- 4 new windows per scope; plan schedule incomplete
- 2 new windows per plans + 2-3 existing-window relocations into the addition framing
- 2 new windows per plans + 2-3 existing-window relocations are separate retrofit work
- Unsure — will reconcile with designer
**Why:** Procurement count for `order.windows` AND placement of relocation tasks (addition build vs retrofit Component).

### q.roof_framing

**Question:** Scope L57 says the roof is "truss OR rafter framed — determined during design phase". Addition is 590 sqft with ~10' span. Stick-frame is the TCR default for this size; trusses would add 4-6 weeks of procurement lead time. Which is it?
**Category:** structural
**Hint:** Trusses trigger a 28-42 calendar-day procurement chain on the critical path.
**Choices:**
- Stick-frame on site (default)
- Engineered trusses (long-lead procurement)
- Unsure — design phase still pending
**Why:** Determines whether to emit `procurement.trusses` (28-42d lead) or rely on stick-frame default per rule §4Q + stick_frame_default belief.

### q.exterior_finish_brick_vs_siding

**Question:** Major scope/plan conflict — plans show "NEW BRICK TO MATCH EXISTING" AND "NEW LAP SIDING" on all three addition elevations, but scope L67 says vinyl siding only with no mention of brick. Is there masonry work on the addition?
**Category:** scope
**Hint:** Brick adds a masonry crew + ~150 brick/day productivity + separate procurement. Big impact.
**Choices:**
- Brick + lap siding per plans (masonry IS in scope)
- Vinyl siding only per scope (plans annotation is wrong / TBD)
- Hybrid — partial brick (which elevations?), siding elsewhere
- Unsure — will clarify with designer
**Why:** Adds or removes a masonry trade entirely, plus brick procurement chain and a multi-day install task.

### q.tankless_option

**Question:** The CSV cost build is the "With Tankless WH Option" variant ($6,500 bundled in HVAC line). Scope frames the tankless as OPTIONAL (L183-185). Has the homeowner committed to taking the tankless option, or is the existing gas WH staying?
**Category:** scope
**Hint:** If tankless taken, dev_rules §4H re-applies and we need the full tank-set chain BEFORE plumbing rough.
**Choices:**
- Tankless option IS taken (replace existing WH)
- Existing gas WH stays (vent extension only)
- Undecided — pricing being finalized
**Why:** Drives whether to emit `procurement.tank` + `plumbing.tank_set` and whether the WH chain gates plumbing rough-in.

### q.electrical_service

**Question:** Scope adds a new 100A subpanel (L73) plus a 30A dedicated circuit for the future elevator. Has the existing main electrical service been verified to support the additional load (typically need 200A main minimum for a 100A subpanel add)? Or might a service upgrade be needed?
**Category:** structural
**Hint:** A service upgrade would add a utility coordination + permit chain that becomes a critical-path item.
**Choices:**
- Verified adequate — existing service supports 100A subpanel add
- Service upgrade needed — utility coordination required
- Unsure — will field-verify amperage before subpanel install
**Why:** A service upgrade adds a major utility/permit task; the agent needs to know whether to schedule one.

### q.lvl_load_bearing

**Question:** Scope L51-53 specifies a 3-ply 14" LVL spanning ~15'-6" to open an existing load-bearing wall. Does the NEW addition's floor system OR roof load also bear through that LVL location, or does the addition load independently on its own perimeter framing?
**Category:** structural
**Hint:** If addition loads through the LVL, structural mods must complete BEFORE addition framing can proceed above. If independent, structural mods and addition framing can parallel.
**Choices:**
- Yes — addition floor/roof loads through the LVL
- No — addition framing is independent of the LVL location
- Unsure — structural engineer to confirm
**Why:** Decides whether `structural.install_lvl` is a serial predecessor of addition floor/roof framing (editor_rules cheat-sheet) or runs parallel.
