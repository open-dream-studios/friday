---
generation_kind: intelligence_rebuild_v2
interview_status: needs_more
round: 1
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWEC2BP83Y40787TFP8JVB29/jobs/308-evergreen-street-addition_JOB-01KWEC3C865TV60M1GFQBW0J8B/intelligence/facts.md
  - _projects/308-evergreen-street_APPPROJ-01KWEC2BP83Y40787TFP8JVB29/jobs/308-evergreen-street-addition_JOB-01KWEC3C865TV60M1GFQBW0J8B/intelligence/extracted/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KWEC2BP83Y40787TFP8JVB29/jobs/308-evergreen-street-addition_JOB-01KWEC3C865TV60M1GFQBW0J8B/intelligence/extracted/breakdown.md
  - _projects/308-evergreen-street_APPPROJ-01KWEC2BP83Y40787TFP8JVB29/jobs/308-evergreen-street-addition_JOB-01KWEC3C865TV60M1GFQBW0J8B/intelligence/extracted/plans.md
  - job_types/addition/rules/addition_rules.md
  - job_types/addition/rules/tdec_septic_permit_offset.md
  - _company/rules/dev_rules.md
---

# Open questions — round 1

Cut log: 14 drafted → 8 final. Dropped `q.hvac_type` (scope explicit: mini-split). Collapsed `q.customer_early_items` + `q.retrofit_hall_bath` into `q.hall_bath_early_or_retrofit` (they cover the same physical area — Rule 4V two-bucket decision). Dropped `q.lvl_type` (3-ply 14″ LVL is a standard item, 14-day safety buffer covers it). Rolled window count + order type into a single `q.window_spec` block. Dropped as CONTEXT-only: address discrepancy (likely designer template artifact), investment total discrepancy (doesn't affect task graph), interior doors 3-vs-4 count (doesn't affect schedule).

### q.septic_direction
**Question:** Is the home on septic or city sewer, and what path do we plan for the addition's plumbing?
**Category:** permits
**Hint:** Scope references TDEC septic inspection AND evaluating a grinder pump; plans note "verify existing septic tank location." All directions have change-order implications called out in scope.
**Choices:**
- On septic — TDEC permit needed, no grinder pump (`permit.tdec_septic` fires with 6-week pre-con offset)
- On septic — TDEC permit + septic relocation/leach field via change order
- On septic today, converting to city sewer with grinder pump — grinder + connection via change order (no TDEC)
- On city sewer already — no TDEC, no grinder pump
- Other (specify in text)
**Why:** Determines whether `permit.tdec_septic` is emitted at all, and whether it anchors the pre-construction phase at the 6-week mark or the job can start on-site sooner.

### q.roof_framing
**Question:** How will the new gable roof be framed — stick or trusses?
**Category:** structural
**Hint:** Scope says "truss OR rafter framed, determined during design phase." Addition is small (~590 sqft total, ~10′ roof span) so the default per rule is stick-frame with next-day lumber; trusses only fire a 4–6 week procurement chain if confirmed.
**Choices:**
- Stick-frame (default — no procurement task, lumber arrives with framing crew)
- Trusses (adds `procurement.trusses`, 35-day supplier lead)
- Design phase pending — default to stick-frame for now, flag for re-run
- Other (specify in text)
**Why:** Trusses = 4–6 week supplier lead added to critical path. Stick-frame = zero procurement lead. This one answer swings the pre-construction window by several weeks.

### q.hall_bath_early_or_retrofit
**Question:** How should we place the existing hall bathroom work? Specifically: did the customer ask TCR to do the acrylic shower swap BEFORE main demo starts so they have a working shower during construction?
**Category:** scope
**Hint:** Scope § Existing Hall Bathroom Modification includes window infill, drywall patch, tub/shower removal, acrylic shower install, repaint. Rule 4V splits customer early items (site_prep, day 1) from same-area retrofit (parallel with main scope) into TWO buckets, even when both live in the same room.
**Choices:**
- Two-bucket: acrylic shower swap = customer early item (day 1, before demo); window infill + drywall + repaint = retrofit component (parallel with main scope)
- All retrofit: the whole hall bath package runs in parallel with main scope, no early-item bucket
- All early: the whole hall bath package is customer-requested pre-demo work
- Other (specify in text)
**Why:** Rule 4V forbids collapsing customer early items and retrofit into one bucket. Placement drives Component + phase for each sub-task; wrong placement means the customer doesn't get their early shower fix when they were told they would.

### q.primary_bedroom_remodel_scope
**Question:** The scope has a "Primary Bedroom Remodel (~12′5″ × 16′)" section. Is that the EXISTING primary bedroom being remodeled (retrofit) OR finishing work on the new addition's primary bedroom?
**Category:** scope
**Hint:** The addition's objective explicitly names the primary bedroom (30′ × 10′ per plans). The remodel section's 12′5″ × 16′ dimension doesn't match the addition footprint, which suggests existing space being redone. Wrong placement double-counts finishes or misses retrofit work.
**Choices:**
- Existing primary bedroom being remodeled (retrofit — dedicated component, parallel with main scope)
- Finish work on the new addition's primary bedroom (subsumed into main-scope interior finishes)
- Both — old primary is remodeled AND new addition primary is finished (needs both components)
- Other (specify in text)
**Why:** Determines whether the ~72 hrs of finishes in this section go into an isolated retrofit component or into the main interior_finishes phase alongside the addition.

### q.lvl_load_bearing
**Question:** Does the new addition's floor or roof load actually bear on the LVL beam location (opening the existing load-bearing wall), or is the LVL install independent of new framing?
**Category:** structural
**Hint:** The 3-ply 14″ LVL spans ~15′-6″ across the existing load-bearing wall. Per addition_rules.md § LVL temporary shoring, the LVL sub-chain runs INDEPENDENT of new framing unless the new floor or roof load bears on it.
**Choices:**
- Independent — new addition framing does NOT depend on LVL install (LVL sub-chain runs in parallel with new framing)
- Load-bearing — new floor/roof bears on LVL, so new framing must wait for LVL install
- Partial — some new framing bears on it (specify)
- Other (specify in text)
**Why:** Determines whether `framing.floor_system` and `framing.exterior_walls` depend on `structural.install_lvl` or can run in parallel. Load-bearing case adds ~2 days to the critical path.

### q.tankless_option_status
**Question:** Is the Tankless Water Heater optional package ($6,500 allowance) in the signed base contract, or is the existing gas WH staying?
**Category:** scope
**Hint:** Base scope § Demolition/Site Work says "extend existing gas water heater vent through new roof" (existing stays). But breakdown CSV title says "(Incl. Tankless WH Option)" and Row 11 (HVAC) has $5,140 material which is more than the $2,500 mini-split budget.
**Choices:**
- Existing gas tank stays (no tank procurement, no tank_set task, plumbing rough-in proceeds without WH predecessor)
- Tankless replacement is in the sold scope (add `procurement.tankless` + `plumbing.tank_set` before rough-in per Rule 4H)
- Regular tank replacement (not tankless) is in scope
- Other (specify in text)
**Why:** Rule 4H requires `plumbing.tank_set` FIRST when a new/replacement WH is in scope; plumbing rough-in stubs into an already-set tank. Wrong answer either adds a phantom procurement chain or omits a real 3-day tank-set gate.

### q.window_spec_discrepancy
**Question:** Which is the built window spec — scope's (4) units including (3) 36″×60″ DH + (1) transom, OR plans' 2 new units (1 × 3′×3′ DH + 1 × 3′×1′ transom) plus relocated existings? And are they stock or custom?
**Category:** procurement
**Hint:** Scope § Exterior Finishes and plans window schedule disagree on both count and size. Also drives lead time (stock 21 cal-d vs. custom 35 cal-d) per addition_rules.md § Windows.
**Choices:**
- Scope is correct — 4 new (3 × 36″×60″ + 1 transom), stock (21-day lead)
- Scope is correct — 4 new, custom (35-day lead)
- Plans are correct — 2 new (3′×3′ DH + 3′×1′ transom) + relocated existings, stock (21-day lead)
- Plans are correct — 2 new + relocated existings, custom (35-day lead)
- Other (specify in text)
**Why:** Wrong count/spec throws off `procurement.windows` lead time chain AND `windows.install` duration (2 days per Will's productivity), which cascades into MEP roughs (which are gated on `windows.install`).

### q.electrical_service_amperage
**Question:** Has the existing main electrical service capacity been verified to support the new 100A subpanel, or does the amperage check still need to happen?
**Category:** trades
**Hint:** Scope § Electrical assumes existing main service supports subpanel. Per addition_rules.md § Existing electrical service, a `prep.amperage_check` (0.5d, general) must land in pre-construction whenever a subpanel is in scope, and a warning fires if there's no verification.
**Choices:**
- Verified — main service confirmed sufficient (still emit amperage_check as a formality)
- Not yet verified — emit `prep.amperage_check` in pre-construction (offset ~15 working days)
- Verified insufficient — service upgrade needed (add change order scope)
- Other (specify in text)
**Why:** Rule requires the amperage check task in pre_construction whenever a subpanel is scoped. If the existing service is actually insufficient, a service upgrade is a $$$ change-order that must be caught before signed contract, not during demo.
