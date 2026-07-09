---
generation_kind: intelligence_rebuild_v2
interview_status: needs_more
round: 1
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWE5GH19TC2BT68XQSNZX70J/jobs/308-evergreen-street-addition_JOB-01KWE5HTWRHPNN6FCRMG6V8AKK/inputs/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KWE5GH19TC2BT68XQSNZX70J/jobs/308-evergreen-street-addition_JOB-01KWE5HTWRHPNN6FCRMG6V8AKK/inputs/files/3725 SIMONS 012226.pdf.txt
  - _projects/308-evergreen-street_APPPROJ-01KWE5GH19TC2BT68XQSNZX70J/jobs/308-evergreen-street-addition_JOB-01KWE5HTWRHPNN6FCRMG6V8AKK/inputs/files/308_Evergreen_Addition.xlsx - Summary (1).csv.txt
  - _projects/308-evergreen-street_APPPROJ-01KWE5GH19TC2BT68XQSNZX70J/jobs/308-evergreen-street-addition_JOB-01KWE5HTWRHPNN6FCRMG6V8AKK/intelligence/extracted/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KWE5GH19TC2BT68XQSNZX70J/jobs/308-evergreen-street-addition_JOB-01KWE5HTWRHPNN6FCRMG6V8AKK/intelligence/extracted/breakdown.md
  - _projects/308-evergreen-street_APPPROJ-01KWE5GH19TC2BT68XQSNZX70J/jobs/308-evergreen-street-addition_JOB-01KWE5HTWRHPNN6FCRMG6V8AKK/intelligence/extracted/plans.md
  - _company/rules/dev_rules.md
  - job_types/addition/rules/addition_rules.md
  - job_types/addition/beliefs/stick_frame_default_for_small_additions.md
---
# questions.md — round 1

**Cut log:** 13 candidate questions drafted → 8 final. Cuts: `q.retrofit_hallway_switch` (rule already consolidates the drywall patch), `q.concealed_roof_tie_in_ack` (addition_rules auto-applies the 3-day buffer, no PM decision needed), `q.electrical_amperage` (rule already fires `prep.amperage_check` — the task IS the answer), `q.grinder_pump_decision` (scope explicitly excludes as change order, path known), `q.lvl_load_bearing` (rule default = independent LVL sub-chain covers the common case; PM can flag at task_graph review). All 5 CRITICAL survive.

Skipped as scope/manifest-answered: HVAC type (mini-split is explicit in scope `L124`), TDEC coordination (scope explicitly assigns TCR the TDEC coordination `L32-35`), customer name (in manifest).

---

### q.customer_early_items
**Question:** Is the hall bath acrylic shower swap a customer-requested EARLY item that must be done BEFORE main demo starts, so the homeowner has a working shower during construction?
**Category:** scope
**Hint:** Will's canonical 308 example describes exactly this pattern. Rule 4V (dev_rules) requires the two-bucket split — early item in `site_prep/customer_early_items` on Day 1, retrofit work (window infill, repaint) in a separate `hall_bath_mod` component running in parallel with main scope.
**Choices:**
- Yes — customer wants working shower before main demo, run acrylic swap on Day 1 (site_prep/customer_early_items)
- No — customer is OK waiting; run the acrylic swap with the rest of the hall-bath retrofit, no early item
- Other (specify in text)
**Why:** Determines whether the graph emits an `early.acrylic_shower_swap` task in `site_prep/customer_early_items` (Day 1) or rolls the swap into the `hall_bath_mod` retrofit component. Two different customer experiences.

### q.retrofit_hall_bath_scope
**Question:** Beyond the acrylic shower swap and hall-bath window infill, the drawings also show a NEW DOOR and RELOCATED DOOR in the existing hall bath ("BTH. 2"). Is the door change in scope for this contract, or was it dropped?
**Category:** scope
**Hint:** Scope narrative only mentions the acrylic shower + window infill + patch/repaint. Plans page 4 shows more work.
**Choices:**
- Full hall-bath retrofit in scope: window infill + acrylic shower + new door + relocated door + patch + repaint
- Reduced hall-bath retrofit: shower + window infill + patch/repaint ONLY (door work was dropped)
- Full retrofit + the negative material row in breakdown reflects a customer credit for reused door hardware
- Other (specify in text)
**Why:** The plans show more hall-bath work than the scope narrative describes. This drives task count + labor budget for the `hall_bath_mod` retrofit component. If door work is in, it needs a task; if not, we don't schedule it.

### q.retrofit_bedroom_2_3_windows
**Question:** Drawings show Bedroom 2 has a RELOCATED EXISTING WINDOW and Bedroom 3 has an EXISTING WINDOW RELOCATED plus a NEW WINDOW. Is this retrofit work in the current contract scope, or was it dropped between design and pricing?
**Category:** scope
**Hint:** Not mentioned in scope narrative; breakdown does not have a dedicated line. These windows sit on walls that abut the new addition and are likely required for the addition tie-in.
**Choices:**
- Yes — both bedrooms' window relocations + Bedroom 3's new window are in scope (retrofit_bedrooms_2_3 component)
- Yes for Bedroom 3 only — that new opening feeds the addition; Bedroom 2 window stays as-is
- No — window relocations were dropped from contract; drawings will be revised
- Other (specify in text)
**Why:** Adds a retrofit component with framing + drywall patch + paint tasks. If confirmed in scope, the labor budget for the negative-material closeout row (72 hrs) is where this work is buried and the graph needs explicit tasks.

### q.roof_framing_method
**Question:** For the 10' span, 3/12 pitch new addition roof — trusses or stick-frame?
**Category:** structural
**Hint:** Scope reads "truss OR rafter framed — determined during design phase." Addition footprint 590 sqft (<800 sqft) and roof span 10' (<24 ft) — the `stick_frame_default_for_small_additions` belief (rank 200, confidence 0.92) defaults to stick-frame. Trusses would add ~28-42 supplier days of lead time and drive critical path.
**Choices:**
- Stick-frame (belief default, no procurement.trusses task, lumber arrives just-in-time)
- Trusses (adds procurement.trusses with 35-day supplier lead)
- Undecided — treat as stick-frame default, revisit at structural sign-off
- Other (specify in text)
**Why:** Trusses = 4-6 wk procurement chain in the critical path. Stick = no procurement task. Choosing wrong direction adds/removes 4 weeks from the pre-construction anchor.

### q.tankless_or_existing_wh
**Question:** Is the customer exercising the optional tankless water-heater package ($6,500 allowance), or is the existing gas tank staying in place (base scope: extend existing WH vent through new roof)?
**Category:** scope
**Hint:** Rule 4H — if existing WH stays, DO NOT emit `procurement.tank` or `plumbing.tank_set`. Plumbing rough-in has NO tank predecessor. If tankless is exercised, chain `procurement.tank → plumbing.tank_set → plumbing.rough_in` and add gas + venting.
**Choices:**
- Existing gas WH stays; only vent extended through new roof (base scope, no procurement.tank, no plumbing.tank_set)
- Optional tankless package exercised — install new tankless, chain tank_set-first sequence, utility upgrades excluded
- Undecided — schedule assuming existing-stays; PM will change-order if customer opts in later
- Other (specify in text)
**Why:** Directly determines whether the graph carries the tank-set chain and 7-14d WH procurement lead. Getting this wrong misfires plumbing rough-in sequencing (Rule 4H).

### q.siding_scope_vs_drawings
**Question:** Scope says "vinyl siding to match existing." Drawings label the elevations "NEW BRICK TO MATCH EXISTING" AND "NEW LAP SIDING." Which is correct for this contract?
**Category:** scope
**Hint:** Drawings show a dual-material exterior (brick base + lap siding above); scope narrates single-material vinyl. Brick would require a masonry crew + longer install. The breakdown line "Exterior Finishes – Siding, Trim & Gutters" ($5,731, 72 hrs) is sized for vinyl only.
**Choices:**
- Vinyl siding only per scope narrative — drawings will be revised
- Brick + lap siding per drawings — scope + breakdown need updating (masonry crew + material cost added, likely change order)
- Vinyl for main field, brick veneer at foundation/knee wall only — hybrid closer to drawings but no separate masonry crew
- Other (specify in text)
**Why:** Determines whether exterior finishes phase needs a masonry sub-crew, and whether labor+material budget is right. Brick would add ~3-5 days and $10K+ in real cost.

### q.window_stock_or_custom
**Question:** For the (3) 36" x 60" DH windows + (1) transom, are these stock or custom units?
**Category:** procurement
**Hint:** Scope allowance is $300/window, which reads stock. Addition_rules windows procurement: stock = 14-21 supplier days, custom = 28-42 supplier days.
**Choices:**
- Stock (14-21 supplier days) — `wait.windows` lead_time 21 calendar days
- Custom (28-42 supplier days) — `wait.windows` lead_time 35-42 calendar days
- Semi-custom (color / grille pattern) — treat as 28 calendar days
- Other (specify in text)
**Why:** 1-4 week delta in the windows procurement chain. Windows install is FS after `framing.roof` — the chain backward-schedules to the order date, so this affects when PM has to press purchase.

### q.lvl_type
**Question:** The 3-ply 14" LVL beam spanning ~15'-6" — standard stock LVL or pressure-treated / custom?
**Category:** procurement
**Hint:** Addition_rules LVL section: standard = 1 wk supplier lead (safety default 14 calendar days); pressure-treated or custom = 21 supplier days. LVL is typically stock, but availability fluctuates with lumber market.
**Choices:**
- Standard stock LVL — `wait.lvl` lead_time 14 calendar days (safety)
- Pressure-treated LVL — `wait.lvl` lead_time 21 calendar days
- Engineered/custom LVL from an architect spec — `wait.lvl` lead_time 21+ calendar days, confirm with supplier
- Other (specify in text)
**Why:** LVL install gates the LVL sub-chain (temp shoring → install → remove shoring). Wrong lead time offsets the procurement chain against structural framing dates.
