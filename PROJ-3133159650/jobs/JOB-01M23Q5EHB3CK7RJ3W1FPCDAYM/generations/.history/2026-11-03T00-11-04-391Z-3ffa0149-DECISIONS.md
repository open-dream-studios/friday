# DECISIONS — Addition · JOB-01M23Q5EHB3CK7RJ3W1FPCDAYM

generation `01M2V6VXHK1Y41FFFX7CMG36V5` · structure v15 · trunk 2c712f2e
effort: include=medium · sizing=medium · foreman=default
timings: Resolving the Addition checklist (structure v15) 12s · Updating evidence with your answers 10s · Updating quantities + labor evidence 161s · Resolving inclusion against scope + answers 76s · Sizing 9 components against the evidence 46s · Foreman review — challenging the estimate 34s · Assembling the task graph 0s · TOTAL 339s

## Summary

- verdicts: 22 included · 50 excluded · 0 needs-info · 0 extra task(s)
- canon: 29/72 decisions cited canon (43 judged without — see CANON GAPS)
- validator: clean on the first pass

## Procurement

### Procurement Items
- ✅ INCLUDE **Foundation** (`proc_foundation_package`) — slab + turned-down footings: forms, rebar, gravel, ready-mix [cn_answer_01m27c146prjakvbspqnvant86 "Roof support post bearing method" · cn_company_no_demo_without_materials "No demo without materials"]
    - delivery: 7 cal days — Stock order: ~4.2-4.5 cy ready-mix (truck direct via side yard, no pump), 4 cy gravel, mesh/rebar+chairs, ~35 LF free-edge form boards + stakes/bracing for 8 turned-down post pockets + fireplace thick
    - sizing canon: cn_answer_01m27c988ay7g5epmnmf9k6950 "Rear-yard patio equipment access route" · cn_answer_01m27c146prjakvbspqnvant86 "Roof support post bearing method" · cn_answer_01m27d8cznp4xkg2cqebxqemwq "roof post count including footings"
    - 🚩 Kit footing/clearance spec must be in hand before forms — post layout and firebox dims drive the pockets/thickening (see proc_fireplace_kit)
    - 🚩 concrete_volume_cy is medium confidence; order 4.2-4.5 cy with a short-load allowance
- ✅ INCLUDE **Windows & exterior doors** (`proc_windows_doors`) — stock screen door, off shelf — pickup [cn_answer_01m27dd8dav16xy6brxr4k8dnv "Screen door sourcing"]
    - delivery: 17 cal days — Zero windows, zero exterior doors — only the stock screen door (PM: off the shelf or 2-3 wk) → carried at ~2.5 wk = 17 cal days; not a driver
    - sizing canon: cn_answer_01m27dd8dav16xy6brxr4k8dnv "Screen door sourcing" · cn_answer_01m27c9b9qqz7rkt4ef81ynrb7 "Selection finality: veneer, hearth, mantel, shingle, screen door"
    - 🚩 Task is effectively the screen door only (window_count_new=0, exterior_door_count_new=0); guardrail floor of 14 days is longer than a true pickup would need
    - 🚩 Selections all final — order can be placed immediately
- ✖ EXCLUDE **LVL / engineered beams** (`proc_lvl`) — beam is built-up dimensional lumber, no engineered members [cn_answer_01m27c9eh5crgq0g8793tdjx8q "Is the beam carrying the rafters over the open screen side dimensional lumber or"]
- ✅ INCLUDE **Framing Package** (`proc_framing_package`) — posts, beams, rafters, sheathing, knee walls, chase framing
    - delivery: 7 cal days — Stock dimensional package: ~8 6x6 posts, double 2x10/2x12 built-up beams (2 × ~23 LF), ~18-19 2x8 rafters ~14', 10 sheets 7/16 OSB, knee-wall/screen-frame/chase framing, hangers/hardware — no LVL, no 
    - sizing canon: cn_answer_01m27c9eh5crgq0g8793tdjx8q "Is the beam carrying the rafters over the open screen side dimensional lumber or" · cn_answer_01m27c4e2fm17nv78gc01d1svk "Who sizes the rafters, ledger/beam, and posts — in-house per IRC tables or a str" · cn_company_no_demo_without_materials "No demo without materials"
    - 🚩 Rafter/beam/post sizing is in-house per IRC but not yet done — finalize sizes before ordering
    - 🚩 Lumber-market availability swing; early-order per task note
- ✖ EXCLUDE **Roof trusses (custom)** (`proc_trusses`) — stick-framed 2x8 shed roof, no trusses
- ✖ EXCLUDE **Subpanel / service equipment** (`proc_subpanel`) — zero electrical scope [cn_answer_01m27c6d2c7bkk5q7rw7wknx5r "porch electrical scope"]
- ✖ EXCLUDE **HVAC equipment (mini-split / system)** (`proc_hvac_equipment`) — unconditioned porch, no HVAC
- ✖ EXCLUDE **Electrical Package** (`proc_electrical_package`) — zero electrical confirmed [cn_answer_01m27c6d2c7bkk5q7rw7wknx5r "porch electrical scope"]
- ✖ EXCLUDE **Water heater (tank or tankless)** (`proc_water_heater`) — no plumbing in scope
- ✖ EXCLUDE **Plumbing Package** (`proc_plumbing_package`) — no plumbing in scope
- ✖ EXCLUDE **Tile & setting materials** (`proc_tile`) — no tile in scope
- ✖ EXCLUDE **Hard flooring** (`proc_hard_flooring`) — broom-finish slab, no flooring
- ✖ EXCLUDE **Carpet / floating floor** (`proc_carpet`) — no carpet or floating floor
- ✖ EXCLUDE **Insulation** (`proc_insulation`) — unconditioned space, no insulation
- ✖ EXCLUDE **Drywall** (`proc_drywall`) — no drywall in scope
- ✖ EXCLUDE **Cabinets / vanities** (`proc_cabinets`) — no cabinetry
- ✖ EXCLUDE **Countertops** (`proc_countertops`) — no countertops
- ✖ EXCLUDE **Paint + Primer** (`proc_paint`) — no field painting — prefinished materials per PM
- ✖ EXCLUDE **Shower glass (template after tile)** (`proc_shower_glass`) — no shower
- ✖ EXCLUDE **Interior doors & trim package** (`proc_doors_trim`) — no interior doors; trim stock — rides install task
- ✖ EXCLUDE **Plumbing fixtures (faucets, sinks, commodes, shower trim)** (`proc_plumbing_fixtures`) — no plumbing fixtures
- ✖ EXCLUDE **Light fixtures & devices** (`proc_light_fixtures`) — zero electrical, no fixtures [cn_answer_01m27c6d2c7bkk5q7rw7wknx5r "porch electrical scope"]
- ✖ EXCLUDE **Concrete + Patio Work** (`proc_concrete_patio`) — covered by proc_foundation_package
- ✅ INCLUDE **Fireplace kit (firebox + Class A chimney)** (`proc_fireplace_kit`) — manufactured firebox + Class A kit, 3-4 wk lead [cn_answer_01m27c0w60xvysq0qzpw0kzpdc "Fireplace construction type" · cn_answer_01m27dd24aq4mt61yjapbqmrrv "Firebox and chimney kit lead time"]
    - delivery: 25 cal days — PM-settled 3-4 wk lead on manufactured wood-burning firebox + Class A pipe kit, hearth extension, termination cap → carried at 3.5 wk = 25 cal days; longest lead on the job
    - sizing canon: cn_answer_01m27dd24aq4mt61yjapbqmrrv "Firebox and chimney kit lead time" · cn_answer_01m27c0w60xvysq0qzpw0kzpdc "Fireplace construction type" · cn_answer_01m27dazmbrgc1wt9kq8r4rdtd "Chimney chase termination height" · cn_company_no_demo_without_materials "No demo without materials"
    - 🚩 Kit dims/footing spec gate the slab forms and footing inspection — get the spec sheet at order placement, not at delivery
    - 🚩 Chase termination just above the low eave may conflict with 10-3-2 / manufacturer termination table — confirm pipe length before the order finalizes
    - 🚩 Short Class A run (chase outside roof edge, ~8' eave) — no tall-run upcharge or extended lead expected

## Permits

### Permit Items
- ✅ INCLUDE **Building permit** (`permit_building`) — Johnson City permit for roof tie-in and fireplace [cn_answer_01m27c1bf0nqhsfmddp5aeyvth "Building permit for roof tie-in and fireplace"]
- ✖ EXCLUDE **TDEC septic permit** (`permit_tdec_septic`) — no septic work
- ✖ EXCLUDE **Electrical service / meter permit** (`permit_electrical_service`) — no service or meter work
- ✖ EXCLUDE **Plumbing Permit** (`permit_plumbing`) — no plumbing in scope
- ✖ EXCLUDE **Mechanical Permit** (`permit_mechanical`) — no HVAC work

## Retrofit (pre-addition work)

### Retrofit Work
- ✖ EXCLUDE **Utility & equipment relocations (heat pump, disconnect, lines)** (`utility_relocations`) — condenser and wall fixtures protected in place, nothing moves [cn_answer_01m27da2eqaed109nxfcsmm0tt "hose bibbs, condenser, meter, exterior lights on tie-in walls" · cn_answer_01m27c93gsa86df7raesb3nrse "HVAC condenser relative to patio footprint"]
- ✖ EXCLUDE **Retrofit demolition (interior areas outside the addition)** (`retrofit_demo`) — no interior pre-addition work
- ✖ EXCLUDE **Retrofit rough MEPs** (`retrofit_rough_meps`) — no retrofit MEP work
- ✖ EXCLUDE **Retrofit drywall & patching** (`retrofit_drywall`) — no retrofit work
- ✖ EXCLUDE **Retrofit finishes (paint, tile, flooring, fixtures)** (`retrofit_finishes`) — no retrofit work

## Demolition

### Main Demolition
- ✅ INCLUDE **Demolition (site + structure at addition footprint)** (`site_and_structure_demo`) — paver removal, fire pit cut-out, gutter removal at tie-in [cn_answer_01m27dcv5caze1cq62m88w0jdt "Rafter tie-in at existing eave" · cn_rates_demo_site "Demo & site rates"]
    - duration: 14h ÷ (3 crew × 8h) = 0.58 → **1wd**
    - basis: pavers 294sf×0.02=6 · fire pit demo+haul 4 · sawcut 9sf pad 1.5 · dumpster load/haul + gutter pull at tie-in 2.5 → 14h; JBD 20h runs hot, quantity math governs
    - crew: 3 — Card demo crew 3 w/ mini-ex for pavers + heavy fire-pit loading
    - quantities: demo_paver_area_sqft=294, demo_concrete_cut_sqft=9, dumpster_yd=12, eave_tie_in_gutter_removal_lf=22.92, stories=1
    - sizing canon: cn_rates_demo_site "Demo & site rates" · cn_rates_inspections_crews "Inspections & crew norms" · cn_policy_rate_card_governs "Rate card governs" · cn_policy_mobilization_floor "Mobilization floor" · cn_company_no_demo_without_materials "No demo without materials"
    - ↪ scope moved to: `site_prep`
    - jbd: disagrees — JBD 20h ~40% over card math (11.5h + loading/gutter); 14h keeps 3-man crew at ~2 days
    - 🚩 Paver field carried at proposal 294 sqft; actual may be nearer 267 sqft (slab)
    - 🚩 Fire pit size not given — card 4h flat
    - 🚩 Site protection (2h) + staging/layout (4-6h) billed on site_prep, not here
    - 🚩 Gutter removal at tie-in carried here (2h); if framing crew pulls it instead, overlap is small

## Site Prep & Foundation

### Groundwork
- ✅ INCLUDE **Site prep (protection, staging, access)** (`site_prep`) — protection of condenser/fixtures, staging, dumpster, layout [cn_answer_01m27da2eqaed109nxfcsmm0tt "hose bibbs, condenser, meter, exterior lights on tie-in walls"]
    - duration: 7h ÷ (2 crew × 8h) = 0.44 → **1wd**
    - basis: staging/dumpster spot/access path/layout 5h (card 4-6) · site protection condenser+wall fixtures+glazing 2h · no scaffold (1 story) · paver/fire-pit demo → demo task → 7h
    - crew: 2 — Two hands to set dumpster/protection on a rear-yard inside corner; no scaffold or hoisting
    - quantities: stories=1, occupied_home=yes (implied), utility_relocation_count=0, site_access=rear-yard inside corner; direct access via side yard, dumpster_yd=12
    - sizing canon: cn_rates_demo_site "Demo & site rates" · cn_policy_mobilization_floor "Mobilization floor" · cn_answer_01m27c93gsa86df7raesb3nrse "HVAC condenser relative to patio footprint" · cn_answer_01m27da2eqaed109nxfcsmm0tt "hose bibbs, condenser, meter, exterior lights on tie-in walls"
    - ↪ scope moved to: `site_and_structure_demo`
    - jbd: agrees — JBD general-conditions 4h GL staging/protection pays this; concrete_patio 42h split to excavation+foundation_prep
    - 🚩 Occupied home implied, never stated — exterior-only work so impact is access/noise; no premium applied
    - 🚩 Site protection billed ONCE here; demo/excavation carry none
- ✅ INCLUDE **Excavation (footings, slab, access)** (`excavation`) — strip/grade for new slab and post footings [cn_answer_01m27c988ay7g5epmnmf9k6950 "Rear-yard patio equipment access route"]
    - duration: 10h ÷ (2 crew × 8h) = 0.63 → **1wd**
    - basis: strip/grade 276sf×0.75ft≈7.7cy×0.75=5.8 · post footing pockets 8×0.25=2 · fireplace thickening pocket 1 · spoils/rough grade 1 → ~10h (paver/fire-pit removal → demo)
    - crew: 2 — Operator + laborer, TCR standard dig crew; small 276 sf footprint has one workface
    - quantities: excavation_area_sqft=276, post_footing_count=8, concrete_slab_area_sqft=276, site_access=direct mini-ex access via side yard
    - sizing canon: cn_rates_excavation_concrete "Excavation & concrete rates" · cn_rates_inspections_crews "Inspections & crew norms" · cn_answer_01m27c146prjakvbspqnvant86 "Roof support post bearing method" · cn_answer_01m27d8cznp4xkg2cqebxqemwq "roof post count including footings" · cn_answer_01m27c988ay7g5epmnmf9k6950 "Rear-yard patio equipment access route"
    - ↪ scope moved to: `site_and_structure_demo`
    - jbd: agrees — Concrete_patio 42h split ~10h dig / ~30h forms-gravel-rebar-pour; JBD priced no post footings
    - 🚩 Depth not stated — carried ~9in (4in slab + gravel), deeper at 8 turned-down footings and fireplace thickening
    - 🚩 Rock is common locally — hitting rock is a change order, not padded here
    - 🚩 Paver field measured 294 sqft vs 276 dig area; over-dig at free edges absorbed in the 1h rough grade line
- ✅ INCLUDE **Prepare Foundation** (`foundation_prep`) — forms, gravel, rebar, turned-down post and fireplace footings [cn_answer_01m27c146prjakvbspqnvant86 "Roof support post bearing method" · cn_answer_01m27d8cznp4xkg2cqebxqemwq "roof post count including footings"]
    - duration: 30h ÷ (3 crew × 8h) = 1.25 → **2wd**
    - basis: gravel 4cy×1=4 · free-edge forms 35LF×0.15=5.3 · 8 turned-down footing forms×0.5=4 · fireplace thickening 1 · mesh 276sf×0.01=2.8 · footing inspection 2 · pour+broom 4.2cy×2.5=10.5 → 30h
    - crew: 3 — Pour day needs 3 on a 4.2 cy direct-chute slab with 8 footing pockets; forms/rebar day runs 2-3
    - quantities: gravel_base_cy=4, foundation_perimeter_lf=69, post_footing_count=8, concrete_slab_area_sqft=276, concrete_volume_cy=4.2, slab_thickness_in=4, inspection_count=3, foundation_type=4in slab-on-grade; turned-down post footings; footing inspection before pour
    - sizing canon: cn_rates_excavation_concrete "Excavation & concrete rates" · cn_rates_inspections_crews "Inspections & crew norms" · cn_answer_01m27c146prjakvbspqnvant86 "Roof support post bearing method" · cn_answer_01m27c988ay7g5epmnmf9k6950 "Rear-yard patio equipment access route" · cn_company_no_demo_without_materials "No demo without materials"
    - jbd: agrees — JBD 42h concrete_patio ≈ my 10h excavation + 30h here; JBD assumed no footings or inspection gate
    - 🚩 Slab pour (no separate pour task exists) is carried here — day 2 after footing inspection passes; cure before framing not in these hours
    - 🚩 Footing inspection 2h carried here since bundled_rough_inspections is labeled MEP/framing only — drop if that task also counts it
    - 🚩 Fireplace kit dims (3-4 wk lead) must be on hand before forms — thickened-footing size depends on it
    - 🚩 Free-edge forms ~35 LF assumed; house-side 35 LF butts existing foundation, no forms
- ✅ INCLUDE **Foundation Inspection** (`foundation_inspection`) — footing inspection required before pour per PM
    - sizing: none (structure default used)
- ✅ INCLUDE **Foundation Pour** (`foundation_pour`) — 4-in broom-finish slab with integral footings [cn_answer_01m27c146prjakvbspqnvant86 "Roof support post bearing method"]
    - sizing: none (structure default used)

## Framing & Shell

### Structural Framing
- ✅ INCLUDE **Framing (floor, walls, roof structure, sheathing)** (`framing`) — posts, beams, shed rafters, sheathing, knee walls, screen framing [cn_answer_01m27c17wtw9dfmx15rrdbakxa "Shed roof-to-house connection method" · cn_answer_01m27cb9sw1yae52vcmpgawaa4 "Screen porch open sides count" · cn_company_never_split_framing "Never split framing"]
    - duration: 61h ÷ (3 crew × 8h) = 2.54 → **3wd**
    - basis: posts 8×0.75=6 · beams 2×7=14 · rafters 18×0.5=9 · sheathing 10×0.4=4 · kneewall 32×0.25=8 · screen frames 35×0.35=12 · frieze bays 4 · gutter pull+cap 3 · layout/blocking 4 → 64h
    - crew: 3 — Single-story ~267 sqft shed over patio; card baseline framing crew of 3.
    - quantities: post_count=8, open_side_beam_lf=22.92, ledger_lf=22.92, rafter_count=18, roof_sheathing_sheets=10, screen_wall_lf=35, knee_wall_height_ft=3.33, screen_frieze_area_sqft=25, eave_tie_in_gutter_removal_lf=22.92, stories=1
    - sizing canon: cn_rates_framing "Framing rates" · cn_rates_inspections_crews "Inspections & crew norms" · cn_policy_rate_card_governs "Rate card governs" · cn_answer_01m27d8cznp4xkg2cqebxqemwq "roof post count including footings" · cn_answer_01m27c17wtw9dfmx15rrdbakxa "Shed roof-to-house connection method" · cn_answer_01m27dcv5caze1cq62m88w0jdt "Rafter tie-in at existing eave"
    - ↪ scope moved to: `fireplace_chase_install`
    - jbd: disagrees — JBD 70h roof + ~24h framing share of 48h enclosure ≈ 94h; card math gives 64h — JBD hot, kept mine.
    - foreman: 64h → 61h — 'gutter pull+cap 3h' is billed twice — demo already carries gutter pull at the tie-in (2.5h w/ dumpster load) and roofing carries the gutter end-cap 1h; drop the 3h from framing, rest of card math (posts/beams/rafters/kneewall/screen frames) is honest
    - 🚩 Chase box framing (12h) carried on fireplace_chase_install, not here
    - 🚩 Knee wall 32 LF at 3'-4" per settled answer, not JBD 60 LF × 2'
    - 🚩 Roof pitch and beam/post sizing not yet done (in-house IRC); ±5%
    - 🚩 Post count carried at settled midpoint 8 of 7-9
- ✖ EXCLUDE **Roof reintegration (reseat preserved roof, bearing transfer, strike shoring)** (`roof_reintegration`) — new shed roof framed, no preserved roof
- ✅ INCLUDE **Exterior windows & doors install** (`exterior_windows_doors`) — stock screen door hang + hardware [cn_answer_01m27dd8dav16xy6brxr4k8dnv "Screen door sourcing"]
    - duration: 4h ÷ (2 crew × 8h) = 0.25 → **1wd**
    - basis: windows 0 · exterior doors 0 · screen door hang carried on enclosure_finishes → 4h mobilization floor only
    - crew: 2 — Residual coordination only; range minimum.
    - quantities: window_count_new=0, exterior_door_count_new=0, screen_door_count=1
    - sizing canon: cn_policy_mobilization_floor "Mobilization floor"
    - ↪ scope moved to: `enclosure_finishes`
    - 🚩 Task has no real scope — zero windows/doors; consider dropping from schedule
    - 🚩 Hours are canon floor, not work

### Deck
- ✖ EXCLUDE **Deck build** (`deck_build`) — no deck; porch roof covered by framing [cn_answer_01m2f8xsw3wrzmpyx958j86psd "Itemized scope overrides deck labeling"]

### Fireplace Structure
- ✅ INCLUDE **Fireplace chase, firebox set & Class A chimney** (`fireplace_chase_install`) — framed chase, firebox set, Class A pipe [cn_answer_01m27c0w60xvysq0qzpw0kzpdc "Fireplace construction type" · cn_answer_01m27c697dj12q6v2yfm9vs4h6 "Fireplace and chimney placement" · cn_answer_01m27dazmbrgc1wt9kq8r4rdtd "Chimney chase termination height"]
    - duration: 29h ÷ (2 crew × 8h) = 1.81 → **2wd**
    - basis: chase box 6x8 12 · firebox set 5 · Class A ~10ft+cap 7 · chase-to-eave counterflash 3 · cement-board substrate/sheathing ~8 sheets×0.4=3 · layout+coord 2 → 32h
    - crew: 2 — Card fireplace crew 2; short chase at low eave, one workface, no roof penetration
    - quantities: fireplace_system_type=framed chase, manufactured firebox, Class A pipe, fireplace_location=centered open long side, chimney outside roof edge, chimney_termination=just above low eave, roof_penetration_count=0, fireplace_width_in=72, stories=1, jbd_labor_hours_total=390
    - sizing canon: cn_rates_fireplace "Fireplace (manufactured kit) rates" · cn_rates_framing "Framing rates" · cn_rates_roofing "Roofing rates" · cn_rates_inspections_crews "Inspections & crew norms" · cn_answer_01m27c0w60xvysq0qzpw0kzpdc "Fireplace construction type" · cn_answer_01m27c697dj12q6v2yfm9vs4h6 "Fireplace and chimney placement"
    - ↪ scope moved to: `fireplace_finish_work`, `roofing`, `bundled_rough_inspections`
    - jbd: disagrees — JBD 98h built on masonry-optional basis + roof penetration; settled kit chase at low eave = ~32h, kept my figure
    - foreman: 32h → 29h — 'chase-to-eave counterflash 3h' is billed twice — roofing task shows the same 'chase counterflash 3' and the card lists counterflash under roofing rates; keep it on the roofer, drop 3h here (chase box 12, firebox 5, Class A 7, cement board 3, layout 2 stand)
    - 🚩 chase/cap height undimensioned — manufacturer termination table or inspector could push chase taller (+4-8h)
    - 🚩 10-3-2 geometry at low-eave termination may be rejected at chimney inspection
    - 🚩 veneer substrate (lath) hours sit in fireplace_finish_work; only cement board/sheathing carried here
    - 🚩 exterior chase faces veneer moved to fireplace_finish_work per coverage answer

## Exterior Finishes

### Cladding & Roof
- ✅ INCLUDE **Roofing (underlayment, shingles, flashing, tie-in blend)** (`roofing`) — underlayment, matched shingles, tie-in and chase flashing [cn_answer_01m27dcv5caze1cq62m88w0jdt "Rafter tie-in at existing eave"]
    - duration: 21h ÷ (3 crew × 8h) = 0.88 → **1wd**
    - basis: underlayment 290sf×0.01=2.9 · shingles 3.2sq×2.5=8 · eave weave 22.92LF×0.2=4.6 · drip edge ~48LF×0.03=1.4 · chase counterflash 3 · gutter end-cap 1 → 21h
    - crew: 3 — Card crew for roofing; 290 sf single-plane shed is one workface
    - quantities: roof_area_sqft=290, shingle_squares=3.2, eave_tie_in_gutter_removal_lf=22.92, gutter_end_cap_count=1, roof_penetration_count=0, fascia_soffit_gutter_lf=0
    - sizing canon: cn_rates_roofing "Roofing rates" · cn_rates_inspections_crews "Inspections & crew norms" · cn_policy_rate_card_governs "Rate card governs" · cn_answer_01m27dcv5caze1cq62m88w0jdt "Rafter tie-in at existing eave" · cn_answer_01m2f38k9tdnjdx1p5q71y65vk "Gutter tie-in end-cap and downspout handling"
    - ↪ scope moved to: `framing`
    - jbd: agrees — JBD 24h vs 21h card math — within rounding; no penetration, only chase-to-eave counterflash
    - 🚩 Roof pitch unknown; 290 sf is plan area, no slope factor (±5%)
    - 🚩 Chase counterflash 3h billed here, not on fireplace_chase_install — do not double-count
    - 🚩 Downspout side of removed gutter run unknown; if an outlet is lost, unpriced downspout
- ✅ INCLUDE **Siding (WRB, siding, tie-in blend)** (`siding`) — vinyl lap siding on knee-wall exterior face [cn_answer_01m2f8xpsxfjdmck8ynwjmjh4g "Footprint and knee wall dimensions source"]
    - duration: 15h ÷ (2 crew × 8h) = 0.94 → **1wd**
    - basis: WRB 107sf×0.015=1.6 · vinyl lap 107sf×0.08=8.6 · ext trim/J-channel ~32LF×0.15=4.8 → 15h; kneewall cap + interior beadboard on enclosure_finishes
    - crew: 2 — Card crew for siding; ~32 LF one-story knee wall, no elevated premium
    - quantities: knee_wall_face_sqft=107, screen_wall_lf=35, knee_wall_height_ft=3.33, stories=1, paint_sqft=0
    - sizing canon: cn_rates_cladding_finish "Cladding & finish rates" · cn_rates_inspections_crews "Inspections & crew norms" · cn_policy_rate_card_governs "Rate card governs" · cn_answer_01m2f8xpsxfjdmck8ynwjmjh4g "Footprint and knee wall dimensions source"
    - ↪ scope moved to: `enclosure_finishes`
    - jbd: agrees — Split of 48h enclosure: ~15h exterior siding here, ~20h framing, ~13h interior/screening; JBD basis (60LF×2') not derived
    - 🚩 Math lands at 1 wd, below the 2-7 wd guardrail — small prefinished knee wall
    - 🚩 Kneewall cap (32LF×0.1) and beadboard carried on enclosure_finishes
    - 🚩 below structure min 2 (derived value kept — floors are advisory for hours-derived durations)
- ✖ EXCLUDE **Fascia, soffit & gutters** (`fascia_soffit_gutters`) — excluded from contracted scope; gutter end-cap rides demo [cn_answer_01m27c7y1jx7vq37p8ccdd2nvp "Shed roof fascia/soffit/gutters exclusion" · cn_answer_01m2f38k9tdnjdx1p5q71y65vk "Gutter tie-in end-cap and downspout handling"]
- ✖ EXCLUDE **Extend existing appliance vents through new roof** (`appliance_vent_extension`) — no existing vents in tie-in area [cn_answer_01m27cbqnj01k7av9fzz9470zy "existing roof/wall vents under new shed roof tie-in"]

### Fireplace Finish
- ✅ INCLUDE **Fireplace veneer, hearth & mantel** (`fireplace_finish_work`) — stone veneer interior + chase faces, hearth, mantel [cn_answer_01m27dar1xcbw3yvg7ymcc1ccs "Fireplace veneer and hearth material sourcing" · cn_answer_01m27c9b9qqz7rkt4ef81ynrb7 "Selection finality: veneer, hearth, mantel, shingle, screen door"]
    - duration: 44h ÷ (2 crew × 8h) = 2.75 → **3wd**
    - basis: lath/scratch 150sf×0.06=9 · veneer w/ corners 150sf×0.17=25.5 · hearth 24sf×0.25=6 · mantel 2.5 · seal/cleanup 1 → 44h (jbd 40h ≈ agrees)
    - crew: 2 — Card fireplace crew = 2; ~6' wide chase, one workface, veneer needs mixer + setter
    - quantities: fireplace_veneer_sqft=150, hearth_sqft=24, fireplace_width_in=72, stories=1
    - sizing canon: cn_rates_fireplace "Fireplace (manufactured kit) rates" · cn_rates_inspections_crews "Inspections & crew norms" · cn_policy_rate_card_governs "Rate card governs" · cn_answer_01m27dar1xcbw3yvg7ymcc1ccs "Fireplace veneer and hearth material sourcing"
    - jbd: agrees — jbd 40h vs 44h card math — within rounding; single task carries all fireplace finish scope
    - 🚩 veneer_sqft ±20% (chase depth/cap height undimensioned) — hours swing ±6h
    - 🚩 exterior chase faces may be brick veneer vs stone per p5 — different rate/crew if brick
    - 🚩 hearth_sqft low confidence (jbd planning 6'×4')
    - 🚩 interior face/hearth/mantel are inside porch — follows chimney inspection; max two inside trades
    - 🚩 cement board substrate on chase carried in fireplace_chase_install, not here

## Rough Trades (MEPs)

### Rough MEPs
- ✖ EXCLUDE **Rough plumbing** (`rough_plumbing`) — no plumbing in scope
- ✖ EXCLUDE **Rough HVAC (line set / duct extension)** (`rough_hvac`) — unconditioned screened porch
- ✖ EXCLUDE **Rough electrical (circuits, subpanel, boxes)** (`rough_electrical`) — zero electrical confirmed [cn_answer_01m27c6d2c7bkk5q7rw7wknx5r "porch electrical scope"]

## Rough Inspections

### Bundled Inspections
- ✅ INCLUDE **Rough inspections (MEPs then framing, bundled)** (`bundled_rough_inspections`) — framing inspection required, no MEPs [cn_answer_01m27c1bf0nqhsfmddp5aeyvth "Building permit for roof tie-in and fireplace"]
    - duration: 4h ÷ (1 crew × 8h) = 0.5 → **1wd**
    - basis: no-MEP job; rough visit = framing inspection only (footing visit gates the pour, chimney visit follows chase) · 1 visit×2h + coordination/walk floor 2h → 4h (card 'bundle, no-MEP job' 4h)
    - crew: 1 — one lead meets the inspector; fixed crew of 1
    - quantities: inspection_count=3, electrical_device_count=0, permit_count=1
    - sizing canon: cn_rates_inspections_crews "Inspections & crew norms" · cn_answer_01m27c1bf0nqhsfmddp5aeyvth "Building permit for roof tie-in and fireplace" · cn_answer_01m27c6d2c7bkk5q7rw7wknx5r "porch electrical scope" · cn_policy_mobilization_floor "Mobilization floor"
    - 🚩 Zero electrical/plumbing/HVAC — 'MEPs first' note is moot; only framing rough remains in this visit
    - 🚩 Footing (pre-pour) and fireplace/chimney visits are separate gates not carried here; if code bundles all 3 visits into this task, raise to 6h
    - 🚩 Chimney termination at low eave may fail 10-3-2 at inspection — re-inspection risk not sized
    - 🚩 Duration 1 wd from math; hint of 2 wd is scheduling slack, not labor
- ✅ INCLUDE **Fireplace/chimney inspection** (`fireplace_chimney_inspection`) — wood-burning unit, AHJ fireplace/chimney visit [cn_answer_01m27c1bf0nqhsfmddp5aeyvth "Building permit for roof tie-in and fireplace"]
    - sizing: none (structure default used)

## Insulation & Drywall

### Insulation, Drywall & Prime
- ✖ EXCLUDE **Insulation & air sealing** (`insulation`) — unconditioned, exposed rafters [cn_answer_01m27c2jvv0nzmg3pfp8jq411f "Is there a finished ceiling (beadboard or T&G) under the shed rafters, or do the"]
- ✖ EXCLUDE **Insulation inspection** (`insulation_inspection`) — no insulation
- ✖ EXCLUDE **Drywall (hang, tape, sand)** (`drywall`) — no drywall in scope
- ✖ EXCLUDE **Paint phase 1 (prime + wall prep + ceilings)** (`paint_phase_1`) — no painting per PM

## Interior Finishes

### Interior Installs
- ✖ EXCLUDE **Shower work (waterproofing, tile, grout)** (`shower_work`) — no shower
- ✖ EXCLUDE **Hard flooring install (LVP, hardwood, tile floors)** (`hard_flooring`) — broom-finish slab is the floor
- ✖ EXCLUDE **Cabinets, counters, vanities & fixed items** (`cabinets_counters`) — no cabinetry or fixed items
- ✖ EXCLUDE **Carpet & floating floors** (`carpet_floating`) — no carpet
- ✅ INCLUDE **Enclosure finishes (screening, panel infill, interior cladding)** (`enclosure_finishes`) — screen mesh, frieze bays, beadboard interior knee-wall face [cn_answer_01m27cb9sw1yae52vcmpgawaa4 "Screen porch open sides count" · cn_answer_01m2f8xpsxfjdmck8ynwjmjh4g "Footprint and knee wall dimensions source"]
    - duration: 28h ÷ (2 crew × 8h) = 1.75 → **2wd**
    - basis: beadboard int 107sf×0.08=8.6 · screen mesh+spline 146sf×0.08=11.7 · frieze bays 25sf×0.08×1.5 choppy=3 · kneewall cap 32LF×0.1=3.2 · int trim ~10LF×0.15=1.5 → 28h; door→exterior_windows_doors
    - crew: 2 — Two carpenters tension/spline screen across 35 LF; card finish carpentry 1-2
    - quantities: knee_wall_face_sqft=107, screen_area_sqft=146, screen_frieze_area_sqft=25, screen_wall_lf=35, knee_wall_height_ft=3.33, knee_wall_finish=prefinished beadboard interior, paint_sqft=0
    - sizing canon: cn_rates_cladding_finish "Cladding & finish rates" · cn_policy_rate_card_governs "Rate card governs" · cn_answer_01m2f8xpsxfjdmck8ynwjmjh4g "Footprint and knee wall dimensions source" · cn_answer_01m27cb9sw1yae52vcmpgawaa4 "Screen porch open sides count" · cn_rates_inspections_crews "Inspections & crew norms" · cn_company_interior_concurrency "Interior trade concurrency"
    - ↪ scope moved to: `exterior_windows_doors`, `siding`, `framing`
    - jbd: disagrees — JBD 48h covers framing+siding+interior on wrong 60LF×2' wall; ~28h interior share here, rest to framing/siding
    - 🚩 JBD screened_enclosure built on superseded 60 LF × 2' vinyl wall — split is judgment, not derived
    - 🚩 Frieze/transom band height undimensioned (25 sqft low-confidence); +50% choppy-piece deviation applied
    - 🚩 Screen door hang (4h) excluded — carried on exterior_windows_doors
    - 🚩 Exterior vinyl lap siding + cap band exterior trim excluded — carried on siding
    - 🚩 Interior concurrency: max two trades inside porch alongside fireplace veneer/door hang

### Final Trades & Paint 2
- ✖ EXCLUDE **Final Trades (fixture install for HVAC, Plumbing, and Electrical)** (`mep_fixture_install`) — no MEPs on job
- ✖ EXCLUDE **Finish Carpentry** (`finish_carpentry`) — no interior doors/trim; kneewall cap rides enclosure_finishes
- ✖ EXCLUDE **Stairs (build/finish)** (`stair_build`) — no stairs
- ✖ EXCLUDE **Paint phase 2 (final coats)** (`paint_phase_2`) — no painting per PM

## Concrete & Landscaping

### Concrete & Landscape
- ✖ EXCLUDE **Concrete flatwork (patios, driveways, walkways)** (`concrete_flatwork`) — covered by foundation_pour
- ✖ EXCLUDE **Landscaping & site restoration** (`landscaping`) — no seed/straw; yard restoration excluded

## Closeout

### Walkthrough & Final Inspection
- ✅ INCLUDE **Customer walkthrough & punch list** (`customer_walkthrough`) — standard closeout walkthrough
    - sizing: none (structure default used)
- ✅ INCLUDE **Final inspections (building + E/P/M, bundled)** (`final_inspections`) — building final on permit [cn_answer_01m27c1bf0nqhsfmddp5aeyvth "Building permit for roof tie-in and fireplace"]
    - sizing: none (structure default used)

## CANON GAPS — decisions made with no canon behind them

These are honest "judged from scope/understanding alone" calls. Each one is a place where a canon entry (a policy, a default, a reference) would make the next generation more grounded — the owners' ask-list.

- **Procurement**:
    - `proc_framing_package` include — posts, beams, rafters, sheathing, knee walls, chase framing
    - `proc_trusses` exclude — stick-framed 2x8 shed roof, no trusses
    - `proc_hvac_equipment` exclude — unconditioned porch, no HVAC
    - `proc_water_heater` exclude — no plumbing in scope
    - `proc_plumbing_package` exclude — no plumbing in scope
    - `proc_tile` exclude — no tile in scope
    - `proc_hard_flooring` exclude — broom-finish slab, no flooring
    - `proc_carpet` exclude — no carpet or floating floor
    - `proc_insulation` exclude — unconditioned space, no insulation
    - `proc_drywall` exclude — no drywall in scope
    - `proc_cabinets` exclude — no cabinetry
    - `proc_countertops` exclude — no countertops
    - `proc_paint` exclude — no field painting — prefinished materials per PM
    - `proc_shower_glass` exclude — no shower
    - `proc_doors_trim` exclude — no interior doors; trim stock — rides install task
    - `proc_plumbing_fixtures` exclude — no plumbing fixtures
    - `proc_concrete_patio` exclude — covered by proc_foundation_package
- **Permits**:
    - `permit_tdec_septic` exclude — no septic work
    - `permit_electrical_service` exclude — no service or meter work
    - `permit_plumbing` exclude — no plumbing in scope
    - `permit_mechanical` exclude — no HVAC work
- **Retrofit (pre-addition work)**:
    - `retrofit_demo` exclude — no interior pre-addition work
    - `retrofit_rough_meps` exclude — no retrofit MEP work
    - `retrofit_drywall` exclude — no retrofit work
    - `retrofit_finishes` exclude — no retrofit work
- **Site Prep & Foundation**:
    - `foundation_inspection` include — footing inspection required before pour per PM
- **Framing & Shell**:
    - `roof_reintegration` exclude — new shed roof framed, no preserved roof
- **Rough Trades (MEPs)**:
    - `rough_plumbing` exclude — no plumbing in scope
    - `rough_hvac` exclude — unconditioned screened porch
- **Insulation & Drywall**:
    - `insulation_inspection` exclude — no insulation
    - `drywall` exclude — no drywall in scope
    - `paint_phase_1` exclude — no painting per PM
- **Interior Finishes**:
    - `shower_work` exclude — no shower
    - `hard_flooring` exclude — broom-finish slab is the floor
    - `cabinets_counters` exclude — no cabinetry or fixed items
    - `carpet_floating` exclude — no carpet
    - `mep_fixture_install` exclude — no MEPs on job
    - `finish_carpentry` exclude — no interior doors/trim; kneewall cap rides enclosure_finishes
    - `stair_build` exclude — no stairs
    - `paint_phase_2` exclude — no painting per PM
- **Concrete & Landscaping**:
    - `concrete_flatwork` exclude — covered by foundation_pour
    - `landscaping` exclude — no seed/straw; yard restoration excluded
- **Closeout**:
    - `customer_walkthrough` include — standard closeout walkthrough

## Canon entries that worked this run

- `cn_rates_inspections_crews` — Inspections & crew norms [company/project] · cited 10×
- `cn_answer_01m27c146prjakvbspqnvant86` — Roof support post bearing method [job] · cited 6×
- `cn_policy_rate_card_governs` — Rate card governs [company/project] · cited 6×
- `cn_company_no_demo_without_materials` — No demo without materials [company/project] · cited 5×
- `cn_answer_01m27c6d2c7bkk5q7rw7wknx5r` — porch electrical scope [job] · cited 5×
- `cn_answer_01m27c1bf0nqhsfmddp5aeyvth` — Building permit for roof tie-in and fireplace [job] · cited 5×
- `cn_answer_01m27c988ay7g5epmnmf9k6950` — Rear-yard patio equipment access route [job] · cited 4×
- `cn_answer_01m27d8cznp4xkg2cqebxqemwq` — roof post count including footings [job] · cited 4×
- `cn_answer_01m27c0w60xvysq0qzpw0kzpdc` — Fireplace construction type [job] · cited 4×
- `cn_answer_01m27dcv5caze1cq62m88w0jdt` — Rafter tie-in at existing eave [job] · cited 4×
- `cn_policy_mobilization_floor` — Mobilization floor [company/project] · cited 4×
- `cn_answer_01m2f8xpsxfjdmck8ynwjmjh4g` — Footprint and knee wall dimensions source [job] · cited 4×
- `cn_answer_01m27dd8dav16xy6brxr4k8dnv` — Screen door sourcing [job] · cited 3×
- `cn_answer_01m27da2eqaed109nxfcsmm0tt` — hose bibbs, condenser, meter, exterior lights on tie-in walls [job] · cited 3×
- `cn_rates_demo_site` — Demo & site rates [company/project] · cited 3×
- `cn_answer_01m27cb9sw1yae52vcmpgawaa4` — Screen porch open sides count [job] · cited 3×
- `cn_answer_01m27c9b9qqz7rkt4ef81ynrb7` — Selection finality: veneer, hearth, mantel, shingle, screen door [job] · cited 2×
- `cn_answer_01m27c9eh5crgq0g8793tdjx8q` — Is the beam carrying the rafters over the open screen side dimensional lumber or [job] · cited 2×
- `cn_answer_01m27dd24aq4mt61yjapbqmrrv` — Firebox and chimney kit lead time [job] · cited 2×
- `cn_answer_01m27dazmbrgc1wt9kq8r4rdtd` — Chimney chase termination height [job] · cited 2×
- `cn_answer_01m27c93gsa86df7raesb3nrse` — HVAC condenser relative to patio footprint [job] · cited 2×
- `cn_rates_excavation_concrete` — Excavation & concrete rates [company/project] · cited 2×
- `cn_answer_01m27c17wtw9dfmx15rrdbakxa` — Shed roof-to-house connection method [job] · cited 2×
- `cn_rates_framing` — Framing rates [company/project] · cited 2×
- `cn_answer_01m27c697dj12q6v2yfm9vs4h6` — Fireplace and chimney placement [job] · cited 2×
- `cn_rates_fireplace` — Fireplace (manufactured kit) rates [company/project] · cited 2×
- `cn_rates_roofing` — Roofing rates [company/project] · cited 2×
- `cn_answer_01m2f38k9tdnjdx1p5q71y65vk` — Gutter tie-in end-cap and downspout handling [job] · cited 2×
- `cn_rates_cladding_finish` — Cladding & finish rates [company/project] · cited 2×
- `cn_answer_01m27dar1xcbw3yvg7ymcc1ccs` — Fireplace veneer and hearth material sourcing [job] · cited 2×
- `cn_answer_01m27c4e2fm17nv78gc01d1svk` — Who sizes the rafters, ledger/beam, and posts — in-house per IRC tables or a str [job] · cited 1×
- `cn_company_never_split_framing` — Never split framing [company/project] · cited 1×
- `cn_answer_01m2f8xsw3wrzmpyx958j86psd` — Itemized scope overrides deck labeling [job] · cited 1×
- `cn_answer_01m27c7y1jx7vq37p8ccdd2nvp` — Shed roof fascia/soffit/gutters exclusion [job] · cited 1×
- `cn_answer_01m27cbqnj01k7av9fzz9470zy` — existing roof/wall vents under new shed roof tie-in [job] · cited 1×
- `cn_answer_01m27c2jvv0nzmg3pfp8jq411f` — Is there a finished ceiling (beadboard or T&G) under the shed rafters, or do the [job] · cited 1×
- `cn_company_interior_concurrency` — Interior trade concurrency [company/project] · cited 1×

## Warnings & findings

- Coverage: 9 PM-SETTLED quantities were consumed by NO task (footprint_sqft=267sqft, patio_length_ft=22.92ft, patio_depth_ft=11.67ft, rafter_span_ft=11.67ft, eave_height_ft=8.16ft, screen_bay_height_ft=4.17ft, screen_door_lead_weeks=2.5weeks, fireplace_kit_lead_weeks=3.5weeks, veneer_hearth_lead_weeks=1weeks) — a human ruled on these numbers; verify each either feeds a derived quantity (dimension inputs do) or check which document value the sizing rode instead.
- Duration for "siding": 1wd is below structure min 2 (derived value kept — floors are advisory for hours-derived durations).
- Foreman check: "framing" 64h → 61h — 'gutter pull+cap 3h' is billed twice — demo already carries gutter pull at the tie-in (2.5h w/ dumpster load) and roofing carries the gutter end-cap 1h; drop the 3h from framing, rest of card math (posts/beams/rafters/kneewall/screen frames) is honest
- Foreman check: "fireplace_chase_install" 32h → 29h — 'chase-to-eave counterflash 3h' is billed twice — roofing task shows the same 'chase counterflash 3' and the card lists counterflash under roofing rates; keep it on the roofer, drop 3h here (chase box 12, firebox 5, Class A 7, cement board 3, layout 2 stand)

## Assumptions

- "Foundation Inspection" (foundation_inspection) is included but its structure row is UNVETTED — confirm with Will.
- "Foundation Pour" (foundation_pour) is included but its structure row is UNVETTED — confirm with Will.
- "Fireplace kit (firebox + Class A chimney)" (proc_fireplace_kit) is included but its structure row is UNVETTED — confirm with Will.
- "Fireplace chase, firebox set & Class A chimney" (fireplace_chase_install) is included but its structure row is UNVETTED — confirm with Will.
- "Fireplace/chimney inspection" (fireplace_chimney_inspection) is included but its structure row is UNVETTED — confirm with Will.
- "Fireplace veneer, hearth & mantel" (fireplace_finish_work) is included but its structure row is UNVETTED — confirm with Will.
