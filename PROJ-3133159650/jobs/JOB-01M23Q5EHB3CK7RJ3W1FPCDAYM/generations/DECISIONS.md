# DECISIONS — Addition · JOB-01M23Q5EHB3CK7RJ3W1FPCDAYM

generation `01M6FBSYFVC6PEZH46Q8PH2GFV` · structure v15 · trunk 3ffa0149
effort: include=medium · sizing=medium · foreman=default
timings: Resolving the Addition checklist (structure v15) 12s · Resolving inclusion against scope + answers 54s · Sizing 9 components against the evidence 35s · Foreman review — challenging the estimate 16s · Assembling the task graph 0s · TOTAL 117s

## Summary

- verdicts: 22 included · 49 excluded · 1 needs-info · 0 extra task(s)
- canon: 32/72 decisions cited canon (40 judged without — see CANON GAPS)
- validator: clean on the first pass

## Procurement

### Procurement Items
- ✅ INCLUDE **Foundation** (`proc_foundation_package`) — slab/footing gravel, rebar, forms, ready-mix staged before demo [cn_answer_01m27c146prjakvbspqnvant86 "Roof support post bearing method" · cn_company_no_demo_without_materials "No demo without materials"]
    - delivery: 7 cal days — Stock yard order: gravel 4cy, mesh/rebar, chairs, form boards + bracing; ready-mix 4.2cy scheduled direct-truck, no pump per access answer
- ✅ INCLUDE **Windows & exterior doors** (`proc_windows_doors`) — stock screen door — pickup; no new windows [cn_answer_01m27dd8dav16xy6brxr4k8dnv "Screen door sourcing"]
    - delivery: 18 cal days — No windows/exterior doors new; only stock screen door, settled 2-3 wk (carried 2.5 wk) — ships near guardrail floor
- ✖ EXCLUDE **LVL / engineered beams** (`proc_lvl`) — beam is built-up dimensional lumber, no LVL [cn_answer_01m27c9eh5crgq0g8793tdjx8q "Is the beam carrying the rafters over the open screen side dimensional lumber or"]
- ✅ INCLUDE **Framing Package** (`proc_framing_package`) — posts, beams, rafters, knee walls, chase lumber, ~1-2 wk [cn_answer_01m27c17wtw9dfmx15rrdbakxa "Shed roof-to-house connection method"]
    - delivery: 10 cal days — Small stock lumber package: 8 posts, 2x10/2x12 built-up beams, ~18 2x8 rafters, 10 OSB sheets, kneewall/screen framing; early-order vs market swings
- ✖ EXCLUDE **Roof trusses (custom)** (`proc_trusses`) — shed roof is stick-framed 2x8 rafters
- ✖ EXCLUDE **Subpanel / service equipment** (`proc_subpanel`) — no electrical scope [cn_answer_01m27c6d2c7bkk5q7rw7wknx5r "porch electrical scope"]
- ✖ EXCLUDE **HVAC equipment (mini-split / system)** (`proc_hvac_equipment`) — outside scope footprint [cn_answer_01m27c93gsa86df7raesb3nrse "HVAC condenser relative to patio footprint"]
- ✖ EXCLUDE **Electrical Package** (`proc_electrical_package`) — outside scope footprint [cn_answer_01m27c6d2c7bkk5q7rw7wknx5r "porch electrical scope"]
- ✖ EXCLUDE **Water heater (tank or tankless)** (`proc_water_heater`) — outside scope footprint
- ✖ EXCLUDE **Plumbing Package** (`proc_plumbing_package`) — outside scope footprint [cn_answer_01m27da2eqaed109nxfcsmm0tt "hose bibbs, condenser, meter, exterior lights on tie-in walls"]
- ✖ EXCLUDE **Tile & setting materials** (`proc_tile`) — no tile in scope
- ✖ EXCLUDE **Hard flooring** (`proc_hard_flooring`) — broom-finish slab, no flooring
- ✖ EXCLUDE **Carpet / floating floor** (`proc_carpet`) — no carpet or floating floor
- ✖ EXCLUDE **Insulation** (`proc_insulation`) — outside scope footprint
- ✖ EXCLUDE **Drywall** (`proc_drywall`) — outside scope footprint
- ✖ EXCLUDE **Cabinets / vanities** (`proc_cabinets`) — no cabinetry in scope
- ✖ EXCLUDE **Countertops** (`proc_countertops`) — no countertops in scope
- ✖ EXCLUDE **Paint + Primer** (`proc_paint`) — stock — rides install task
- ✖ EXCLUDE **Shower glass (template after tile)** (`proc_shower_glass`) — no shower in scope
- ✖ EXCLUDE **Interior doors & trim package** (`proc_doors_trim`) — no interior doors; trim stock rides install task
- ✖ EXCLUDE **Plumbing fixtures (faucets, sinks, commodes, shower trim)** (`proc_plumbing_fixtures`) — outside scope footprint
- ✖ EXCLUDE **Light fixtures & devices** (`proc_light_fixtures`) — zero electrical confirmed [cn_answer_01m27c6d2c7bkk5q7rw7wknx5r "porch electrical scope"]
- ✖ EXCLUDE **Concrete + Patio Work** (`proc_concrete_patio`) — covered by proc_foundation_package
- ✅ INCLUDE **Fireplace kit (firebox + Class A chimney)** (`proc_fireplace_kit`) — firebox + Class A kit, 3-4 wk lead; veneer/hearth ~1 wk [cn_answer_01m27dd24aq4mt61yjapbqmrrv "Firebox and chimney kit lead time" · cn_answer_01m27dar1xcbw3yvg7ymcc1ccs "Fireplace veneer and hearth material sourcing" · cn_answer_01m27c0w60xvysq0qzpw0kzpdc "Fireplace construction type"]
    - delivery: 25 cal days — Settled 3-4 wk lead (3.5 wk carried); spec sheet needed before slab forms for footing thickening

## Permits

### Permit Items
- ✅ INCLUDE **Building permit** (`permit_building`) — Johnson City permit for roof tie-in and fireplace [cn_answer_01m27c1bf0nqhsfmddp5aeyvth "Building permit for roof tie-in and fireplace"]
- ✖ EXCLUDE **TDEC septic permit** (`permit_tdec_septic`) — no septic work
- ✖ EXCLUDE **Electrical service / meter permit** (`permit_electrical_service`) — no electrical service work [cn_answer_01m27c6d2c7bkk5q7rw7wknx5r "porch electrical scope"]
- ✖ EXCLUDE **Plumbing Permit** (`permit_plumbing`) — outside scope footprint
- ✖ EXCLUDE **Mechanical Permit** (`permit_mechanical`) — outside scope footprint

## Retrofit (pre-addition work)

### Retrofit Work
- ✖ EXCLUDE **Utility & equipment relocations (heat pump, disconnect, lines)** (`utility_relocations`) — fixtures and condenser protected in place, nothing moved [cn_answer_01m27da2eqaed109nxfcsmm0tt "hose bibbs, condenser, meter, exterior lights on tie-in walls" · cn_answer_01m27c93gsa86df7raesb3nrse "HVAC condenser relative to patio footprint"]
- ✖ EXCLUDE **Retrofit demolition (interior areas outside the addition)** (`retrofit_demo`) — no pre-addition interior work
- ✖ EXCLUDE **Retrofit rough MEPs** (`retrofit_rough_meps`) — no pre-addition work
- ✖ EXCLUDE **Retrofit drywall & patching** (`retrofit_drywall`) — no pre-addition work
- ✖ EXCLUDE **Retrofit finishes (paint, tile, flooring, fixtures)** (`retrofit_finishes`) — no pre-addition work

## Demolition

### Main Demolition
- ✅ INCLUDE **Demolition (site + structure at addition footprint)** (`site_and_structure_demo`) — paver field and masonry fire pit removal, gutter removal [cn_answer_01m27dcv5caze1cq62m88w0jdt "Rafter tie-in at existing eave"]
    - duration: 15h ÷ (3 crew × 8h) = 0.63 → **1wd**
    - basis: pavers 294sf×0.02=6 · fire pit demo+haul 4 · sawcut 9sf×0.15=1.5 · gutter pull 23LF+end-cap 1.5 · dumpster load/sweep 2 → 15h
    - crew: 3 — Machine-assist paver pull with 3-man demo crew per card norm; open rear-yard access
    - quantities: demo_paver_area_sqft=294, demo_concrete_cut_sqft=9, dumpster_yd=12, eave_tie_in_gutter_removal_lf=22.92, gutter_end_cap_count=1, stories=1
    - sizing canon: cn_rates_demo_site "Demo & site rates" · cn_rates_inspections_crews "Inspections & crew norms" · cn_policy_rate_card_governs "Rate card governs" · cn_answer_01m27dcv5caze1cq62m88w0jdt "Rafter tie-in at existing eave" · cn_answer_01m2f38k9tdnjdx1p5q71y65vk "Gutter tie-in end-cap and downspout handling" · cn_company_no_demo_without_materials "No demo without materials"
    - ↪ scope moved to: `site_prep`
    - jbd: disagrees — JBD 20h runs ~33% hot vs card math; kept 15h. Staging/protection billed on site_prep.
    - 🚩 Gutter removal+end-cap carried here as demo; if framing/roofing owns it, move ~1.5h
    - 🚩 Paver area 294sf is existing field per proposal; field may be closer to 267sf
    - 🚩 Fire pit size not given; card 4h flat assumed
    - 🚩 No demo until slab materials and fireplace kit spec on site per policy

## Site Prep & Foundation

### Groundwork
- ✅ INCLUDE **Site prep (protection, staging, access)** (`site_prep`) — staging, dumpster, condenser and fixture protection [cn_answer_01m27da2eqaed109nxfcsmm0tt "hose bibbs, condenser, meter, exterior lights on tie-in walls" · cn_answer_01m27c988ay7g5epmnmf9k6950 "Rear-yard patio equipment access route"]
    - duration: 7h ÷ (2 crew × 8h) = 0.44 → **1wd**
    - basis: staging/dumpster/access/layout 5 · protect condenser+wall fixtures 2 → 7h
    - crew: 2 — Small rear-yard site; two hands spot dumpster, lay access path, wrap fixtures
    - quantities: site_access=side-yard direct access; condenser protect in place, utility_relocation_count=0, dumpster_yd=12
    - sizing canon: cn_rates_demo_site "Demo & site rates" · cn_answer_01m27c93gsa86df7raesb3nrse "HVAC condenser relative to patio footprint" · cn_answer_01m27da2eqaed109nxfcsmm0tt "hose bibbs, condenser, meter, exterior lights on tie-in walls" · cn_policy_mobilization_floor "Mobilization floor"
    - jbd: agrees — JBD GC carries ~4h GL staging/protection; card staging 4-6h + 2h protection lands at 7h.
    - 🚩 Protection billed once here; demo and later trades should not re-bill it
    - 🚩 No scaffold: single-story, no elevated premium
- ✅ INCLUDE **Excavation (footings, slab, access)** (`excavation`) — slab excavation plus turned-down post footings [cn_answer_01m27c146prjakvbspqnvant86 "Roof support post bearing method"]
    - duration: 9h ÷ (2 crew × 8h) = 0.56 → **1wd**
    - basis: strip/grade 276sf×9in=7.7cy×0.75=6 · post pockets 8×0.25=2 · fireplace thickening dig 1 → 9h
    - crew: 2 — Operator + laborer standard dig crew on mini-ex via side yard
    - quantities: excavation_area_sqft=276, post_footing_count=8, foundation_type=4in slab on gravel w/ turned-down footings, site_access=direct mini-ex access
    - sizing canon: cn_rates_excavation_concrete "Excavation & concrete rates" · cn_answer_01m27c988ay7g5epmnmf9k6950 "Rear-yard patio equipment access route" · cn_answer_01m27d8cznp4xkg2cqebxqemwq "roof post count including footings"
    - ↪ scope moved to: `site_and_structure_demo`
    - jbd: agrees — JBD concrete_patio 42h split: ~9h dig here, ~29h foundation_prep; its 303sf basis runs ~9% high.
    - 🚩 Paver/fire-pit removal and sawcut carried by site_and_structure_demo, not here
    - 🚩 Rock hit = change order, not padded into hours
    - 🚩 Depth unstated; 8-10in assumed, deeper at footings
- ✅ INCLUDE **Prepare Foundation** (`foundation_prep`) — gravel, forms, rebar, thickened footings [cn_answer_01m27c146prjakvbspqnvant86 "Roof support post bearing method"]
    - duration: 29h ÷ (3 crew × 8h) = 1.21 → **2wd**
    - basis: gravel 4cy×1=4 · forms 35LF×0.15=5 · post footing form/rebar 8×0.5=4 · mesh 276sf×0.01=3 · pour+broom 4.2cy×2.5=11 · joints/strip 2 → 29h
    - crew: 3 — Pour/finish of ~4cy slab with integral footings needs 3 at the truck
    - quantities: gravel_base_cy=4, foundation_perimeter_lf=69, post_footing_count=8, concrete_slab_area_sqft=276, concrete_volume_cy=4.2, slab_thickness_in=4
    - sizing canon: cn_rates_excavation_concrete "Excavation & concrete rates" · cn_answer_01m27c146prjakvbspqnvant86 "Roof support post bearing method" · cn_answer_01m27d8cznp4xkg2cqebxqemwq "roof post count including footings" · cn_answer_01m27c988ay7g5epmnmf9k6950 "Rear-yard patio equipment access route" · cn_rates_inspections_crews "Inspections & crew norms"
    - jbd: agrees — JBD 42h for patio prices no turned-down footings; my 9h dig + 29h here = 38h covers them.
    - 🚩 Free-edge forms only ~35LF; house side pours against existing foundation
    - 🚩 Fireplace kit spec sheet (3-4 wk lead) must be in hand before forms — sets thickening
    - 🚩 Possible footing inspection gate before pour, unconfirmed
    - 🚩 Post layout (7-9, carried 8) must be locked before forming
- ✅ INCLUDE **Foundation Inspection** (`foundation_inspection`) — post and fireplace footings ahead of pour
    - sizing: none (structure default used)
- ✅ INCLUDE **Foundation Pour** (`foundation_pour`) — new 4-inch slab with integral footings [cn_answer_01m27c146prjakvbspqnvant86 "Roof support post bearing method"]
    - sizing: none (structure default used)

## Framing & Shell

### Structural Framing
- ✅ INCLUDE **Framing (floor, walls, roof structure, sheathing)** (`framing`) — posts, beams, shed rafters, sheathing, knee/screen walls [cn_answer_01m27c17wtw9dfmx15rrdbakxa "Shed roof-to-house connection method" · cn_company_never_split_framing "Never split framing"]
    - duration: 60h ÷ (3 crew × 8h) = 2.5 → **3wd**
    - basis: posts 8×0.75=6 · beams 2×7=14 · rafters 18×0.5=9 · sheathing 10×0.4=4 · eave tie-in/gutter pull/blocking 4 · layout 3 · kneewall 32LF×0.25=8 · screen frames 35LF×0.35=12 → 60h
    - crew: 3 — Card framing crew of 3; beam lifts need 3, single-story 267sf footprint caps workface
    - quantities: post_count=8, open_side_beam_lf=22.92, ledger_lf=22.92, rafter_count=18, roof_sheathing_sheets=10, eave_tie_in_gutter_removal_lf=22.92, screen_wall_lf=35, knee_wall_height_ft=3.33, stories=1
    - sizing canon: cn_rates_framing "Framing rates" · cn_policy_rate_card_governs "Rate card governs" · cn_answer_01m27c17wtw9dfmx15rrdbakxa "Shed roof-to-house connection method" · cn_answer_01m27dcv5caze1cq62m88w0jdt "Rafter tie-in at existing eave" · cn_answer_01m27d8cznp4xkg2cqebxqemwq "roof post count including footings" · cn_answer_01m27cb9sw1yae52vcmpgawaa4 "Screen porch open sides count"
    - ↪ scope moved to: `fireplace_chase_install`
    - jbd: disagrees — JBD roof 70h + share of 48h enclosure runs hot; card math gives 39h roof + 20h kneewall/screen framing.
    - 🚩 Post count carried at 8 of settled 7-9; ±1 post ≈ ±1h
    - 🚩 Roof pitch unknown; plan area used, no slope factor
    - 🚩 Frieze/clerestory screen framing unconfirmed and not carried; add ~4-6h if built
    - 🚩 Chase framing excluded, carried on fireplace_chase_install
    - 🚩 Gutter end-cap included in tie-in line; downspout-side question still open
- ✖ EXCLUDE **Roof reintegration (reseat preserved roof, bearing transfer, strike shoring)** (`roof_reintegration`) — new roof framed, no preserved roof
- ✅ INCLUDE **Exterior windows & doors install** (`exterior_windows_doors`) — stock screen door hang [cn_answer_01m27dd8dav16xy6brxr4k8dnv "Screen door sourcing"]
    - duration: 4h ÷ (2 crew × 8h) = 0.25 → **1wd**
    - basis: no evidence basis — range judgment · windows 0 · ext doors 0 · screen door hang → enclosure_finishes · mobilization floor 4 → 4h
    - crew: 2 — Card floor crew; no real install scope on this job
    - quantities: window_count_new=0, exterior_door_count_new=0, screen_door_count=1
    - sizing canon: cn_policy_mobilization_floor "Mobilization floor"
    - ↪ scope moved to: `enclosure_finishes`
    - 🚩 Task has zero scope: no new windows or exterior doors; recommend PM delete it rather than schedule a phantom 4h
    - 🚩 Screen door hang carried on enclosure_finishes per mapping

### Deck
- ✖ EXCLUDE **Deck build** (`deck_build`) — no deck; porch structure covered by framing [cn_answer_01m2f8xsw3wrzmpyx958j86psd "Itemized scope overrides deck labeling"]

### Fireplace Structure
- ✅ INCLUDE **Fireplace chase, firebox set & Class A chimney** (`fireplace_chase_install`) — framed chase, manufactured firebox, Class A pipe [cn_answer_01m27c0w60xvysq0qzpw0kzpdc "Fireplace construction type" · cn_answer_01m27c697dj12q6v2yfm9vs4h6 "Fireplace and chimney placement"]
    - duration: 32h ÷ (2 crew × 8h) = 2 → **2wd**
    - basis: chase box 12 · firebox set 5 · Class A pipe+cap 7 · cement board substrate ~6 · layout/coord w/ roofing 2 → 32h; counterflash on roofing; JBD 98h hot (masonry basis)
    - crew: 2 — Short ~6' chase at low eave, single-story; card fireplace crew 2
    - quantities: fireplace_system_type=framed wood chase, manufactured firebox, Class A, fireplace_width_in=72, chimney_termination=just above low eave, roof_penetration_count=0, stories=1
    - sizing canon: cn_rates_fireplace "Fireplace (manufactured kit) rates" · cn_rates_framing "Framing rates" · cn_rates_inspections_crews "Inspections & crew norms" · cn_answer_01m27c0w60xvysq0qzpw0kzpdc "Fireplace construction type" · cn_answer_01m27c697dj12q6v2yfm9vs4h6 "Fireplace and chimney placement" · cn_answer_01m27dazmbrgc1wt9kq8r4rdtd "Chimney chase termination height"
    - ↪ scope moved to: `roofing`
    - jbd: disagrees — JBD 98h priced vs masonry option + roof penetration/10-3-2 work now off the table; card math gives ~32h
    - 🚩 Chase/cap height undimensioned; 10-3-2 at low-eave termination may be rejected at fireplace inspection — taller chase would add hours
    - 🚩 Chase-to-eave counterflash (2-4h) carried on roofing task
    - 🚩 Kit (3-4 wk lead) or spec sheet needed before slab forms

## Exterior Finishes

### Cladding & Roof
- ✅ INCLUDE **Roofing (underlayment, shingles, flashing, tie-in blend)** (`roofing`) — ~3.2 sq shingles, tie-in flashing, gutter end-cap [cn_answer_01m2f38k9tdnjdx1p5q71y65vk "Gutter tie-in end-cap and downspout handling"]
    - duration: 21h ÷ (3 crew × 8h) = 0.88 → **1wd**
    - basis: underlay 290sf×0.01=2.9 · shingles 3.2sq×2.5=8 · eave tie-in 22.92LF×0.2=4.6 · drip edge ~47LF×0.03=1.4 · chase counterflash 3 · gutter pull+end cap 1.5 → 21.4≈22h
    - crew: 3 — Card roofing crew of 3; small single-plane roof, one-story ladder access
    - quantities: roof_area_sqft=290, shingle_squares=3.2, eave_tie_in_gutter_removal_lf=22.92, gutter_end_cap_count=1, roof_penetration_count=0, stories=1
    - sizing canon: cn_rates_roofing "Roofing rates" · cn_answer_01m27dcv5caze1cq62m88w0jdt "Rafter tie-in at existing eave" · cn_answer_01m2f38k9tdnjdx1p5q71y65vk "Gutter tie-in end-cap and downspout handling" · cn_answer_01m27c7y1jx7vq37p8ccdd2nvp "Shed roof fascia/soffit/gutters exclusion" · cn_answer_01m27c697dj12q6v2yfm9vs4h6 "Fireplace and chimney placement"
    - jbd: agrees — JBD 24h vs 22h derived; within rounding.
    - foreman: 22h → 21h — Gutter pull + end cap (1.5h) is already carried on site_and_structure_demo's own basis (gutter pull 23LF+end-cap 1.5), so it is billed twice; card math without it is 2.9+8+4.6+1.4+3=19.9, plus a little rounding, which gives 21h.
    - 🚩 Roof pitch unknown; plan area used with no slope factor (±5%)
    - 🚩 Drip edge LF assumed: low eave + two rakes, no fascia/gutter per exclusion
    - 🚩 Downspout side of removed gutter run unknown; if on removed run, an unpriced downspout follows
- ✅ INCLUDE **Siding (WRB, siding, tie-in blend)** (`siding`) — lap siding on knee-wall exterior face [cn_answer_01m2f8xpsxfjdmck8ynwjmjh4g "Footprint and knee wall dimensions source"]
    - duration: 15h ÷ (2 crew × 8h) = 0.94 → **1wd**
    - basis: WRB 107sf×0.015=1.6 · vinyl lap 107sf×0.08=8.6 · ext trim/band 32LF×0.15=4.8 → 15h; one story, no access premium
    - crew: 2 — Card siding crew of 2; ~32 LF of 3'-4" knee wall at grade
    - quantities: knee_wall_face_sqft=107, screen_wall_lf=35, knee_wall_height_ft=3.33, stories=1
    - sizing canon: cn_rates_cladding_finish "Cladding & finish rates" · cn_answer_01m2f8xpsxfjdmck8ynwjmjh4g "Footprint and knee wall dimensions source"
    - ↪ scope moved to: `framing`, `enclosure_finishes`, `fireplace_finish_work`
    - jbd: disagrees — JBD 48h covers whole enclosure (framing+siding+beadboard+screen+door); siding share ~15h, rest elsewhere.
    - 🚩 15h at crew 2 is ~1 wd, below the 2-wd guardrail floor — finding, not padding
    - 🚩 Exterior chase finish (brick vs stone) unsettled; carried by fireplace_finish_work, not siding
    - 🚩 Vinyl inferred from proposal 'white vinyl finish'
    - 🚩 below structure min 2 (derived value kept — floors are advisory for hours-derived durations)
- ✖ EXCLUDE **Fascia, soffit & gutters** (`fascia_soffit_gutters`) — new-roof fascia/soffit/gutters excluded from contract [cn_answer_01m27c7y1jx7vq37p8ccdd2nvp "Shed roof fascia/soffit/gutters exclusion"]
- ✖ EXCLUDE **Extend existing appliance vents through new roof** (`appliance_vent_extension`) — no vents in tie-in area [cn_answer_01m27cbqnj01k7av9fzz9470zy "existing roof/wall vents under new shed roof tie-in"]

### Fireplace Finish
- ✅ INCLUDE **Fireplace veneer, hearth & mantel** (`fireplace_finish_work`) — stone veneer, hearth, and mantel contracted [cn_answer_01m27dar1xcbw3yvg7ymcc1ccs "Fireplace veneer and hearth material sourcing"]
    - duration: 42h ÷ (2 crew × 8h) = 2.63 → **3wd**
    - basis: lath+scratch 145sf×0.06=8.7 · stone veneer 145sf×0.17=24.7 · raised hearth 24sf×0.25=6 · mantel 2.5 → 42h (interior-face-only 35sf alt ≈17h)
    - crew: 2 — Card fireplace crew of 2; one sets veneer, one mixes, cuts and hands up on a ~6' chase
    - quantities: fireplace_veneer_sqft=145, hearth_sqft=24, fireplace_width_in=72, stories=1
    - sizing canon: cn_rates_fireplace "Fireplace (manufactured kit) rates" · cn_policy_rate_card_governs "Rate card governs" · cn_rates_inspections_crews "Inspections & crew norms" · cn_company_interior_concurrency "Interior trade concurrency"
    - jbd: agrees — JBD 40h on a 150sf plan; card math on 145sf all-faces gives 42h. Whole JBD line sits on this one task.
    - 🚩 Veneer coverage unsettled (35-145sf). Carried all faces per the proposal's stone veneer and the JBD 150sf. If only the interior face is veneered, ~17h.
    - 🚩 p5 shows the exterior chase as painted brick. Brick veneer would need a different crew and rate, and sits outside the $5/sf allowance. PM should confirm the exterior face.
    - 🚩 Hearth 24sf is low-confidence (JBD 6'x4'; no plan depth).
    - 🚩 Must follow the fireplace/chimney inspection. Counts toward the max-two-trades limit inside the porch with beadboard/screening and the screen door.

## Rough Trades (MEPs)

### Rough MEPs
- ✖ EXCLUDE **Rough plumbing** (`rough_plumbing`) — outside scope footprint
- ✖ EXCLUDE **Rough HVAC (line set / duct extension)** (`rough_hvac`) — outside scope footprint
- ✖ EXCLUDE **Rough electrical (circuits, subpanel, boxes)** (`rough_electrical`) — outside scope footprint [cn_answer_01m27c6d2c7bkk5q7rw7wknx5r "porch electrical scope"]

## Rough Inspections

### Bundled Inspections
- ✅ INCLUDE **Rough inspections (MEPs then framing, bundled)** (`bundled_rough_inspections`) — framing inspection required under building permit [cn_answer_01m27c1bf0nqhsfmddp5aeyvth "Building permit for roof tie-in and fireplace"]
    - duration: 4h ÷ (1 crew × 8h) = 0.5 → **1wd**
    - basis: no MEP · visits 2×2h (framing + fireplace/chimney)=4 · = no-MEP bundle 4h → 4h
    - crew: 1 — Fixed single PM/lead for inspector coordination and walk
    - quantities: inspection_count=2, electrical_device_count=0, permit_count=1
    - sizing canon: cn_rates_inspections_crews "Inspections & crew norms" · cn_answer_01m27c1bf0nqhsfmddp5aeyvth "Building permit for roof tie-in and fireplace" · cn_answer_01m27c6d2c7bkk5q7rw7wknx5r "porch electrical scope" · cn_policy_mobilization_floor "Mobilization floor"
    - 🚩 Footing inspection on turned-down footings plausible but unconfirmed — would add a pre-pour visit (+2h) and a hard gate
    - 🚩 Chimney termination below 10-3-2 geometry may fail fireplace inspection — re-inspect risk
    - 🚩 No MEP rough exists; 'MEPs first' ordering is moot — framing + fireplace/chimney only
- ✅ INCLUDE **Fireplace/chimney inspection** (`fireplace_chimney_inspection`) — wood-burning unit; AHJ chimney inspection required [cn_answer_01m27c1bf0nqhsfmddp5aeyvth "Building permit for roof tie-in and fireplace"]
    - sizing: none (structure default used)

## Insulation & Drywall

### Insulation, Drywall & Prime
- ✖ EXCLUDE **Insulation & air sealing** (`insulation`) — outside scope footprint
- ✖ EXCLUDE **Insulation inspection** (`insulation_inspection`) — outside scope footprint
- ✖ EXCLUDE **Drywall (hang, tape, sand)** (`drywall`) — outside scope footprint
- ✖ EXCLUDE **Paint phase 1 (prime + wall prep + ceilings)** (`paint_phase_1`) — outside scope footprint

## Interior Finishes

### Interior Installs
- ✖ EXCLUDE **Shower work (waterproofing, tile, grout)** (`shower_work`) — no shower in scope
- ✖ EXCLUDE **Hard flooring install (LVP, hardwood, tile floors)** (`hard_flooring`) — broom-finish slab, no flooring
- ✖ EXCLUDE **Cabinets, counters, vanities & fixed items** (`cabinets_counters`) — no cabinetry or fixed installs
- ✖ EXCLUDE **Carpet & floating floors** (`carpet_floating`) — no carpet in scope
- ✅ INCLUDE **Enclosure finishes (screening, panel infill, interior cladding)** (`enclosure_finishes`) — screening, beadboard knee-wall face, cap trim [cn_answer_01m2f8xpsxfjdmck8ynwjmjh4g "Footprint and knee wall dimensions source" · cn_answer_01m27cb9sw1yae52vcmpgawaa4 "Screen porch open sides count"]
    - duration: 25h ÷ (2 crew × 8h) = 1.56 → **2wd**
    - basis: beadboard 107sf×0.08=8.6 · screen+stops (146sf−fp bay 26−door 12=108sf)×0.08=8.6 · kneewall cap 32LF×0.1=3.2 → 21h
    - crew: 2 — Two carpenters tension mesh and hold beadboard; small single-level porch workface
    - quantities: knee_wall_face_sqft=107, screen_area_sqft=146, screen_wall_lf=35, screen_bay_height_ft=4.17, knee_wall_finish=white vinyl lap siding on exterior face; beadboard on interior face, screen_door_count=1
    - sizing canon: cn_rates_cladding_finish "Cladding & finish rates" · cn_policy_rate_card_governs "Rate card governs" · cn_answer_01m27cb9sw1yae52vcmpgawaa4 "Screen porch open sides count" · cn_answer_01m2f8xpsxfjdmck8ynwjmjh4g "Footprint and knee wall dimensions source"
    - ↪ scope moved to: `exterior_windows_doors`
    - jbd: agrees — JBD 48h covers framing+siding+interior; ~21h interior share is consistent once framing/siding take theirs
    - foreman: 21h → 25h — Screen door hang is missing: exterior_windows_doors routes it to this task, but this basis has no line for it. Added the card's stock door hang + hardware rate of 4h to 21h.
    - 🚩 Frieze/clerestory screening (~25sf, low confidence, unconfirmed) excluded; adds ~2-3h if built
    - 🚩 Fireplace-bay deduction (~6.3' × 4.17') assumes chase fills that bay; beadboard kept at settled 107sf
    - 🚩 Beadboard prefinish vs field paint unsettled; no paint carried

### Final Trades & Paint 2
- ✖ EXCLUDE **Final Trades (fixture install for HVAC, Plumbing, and Electrical)** (`mep_fixture_install`) — no MEPs in scope
- ✖ EXCLUDE **Finish Carpentry** (`finish_carpentry`) — no interior doors/base; cap trim covered by enclosure_finishes
- ✖ EXCLUDE **Stairs (build/finish)** (`stair_build`) — no stairs
- ❓ NEEDS INFO **Paint phase 2 (final coats)** (`paint_phase_2`) — whether any field painting is contracted is unresolved

## Concrete & Landscaping

### Concrete & Landscape
- ✖ EXCLUDE **Concrete flatwork (patios, driveways, walkways)** (`concrete_flatwork`) — covered by foundation_pour
- ✖ EXCLUDE **Landscaping & site restoration** (`landscaping`) — yard restoration excluded; minor edge grading only

## Closeout

### Walkthrough & Final Inspection
- ✅ INCLUDE **Customer walkthrough & punch list** (`customer_walkthrough`) — standard closeout walkthrough
    - sizing: none (structure default used)
- ✅ INCLUDE **Final inspections (building + E/P/M, bundled)** (`final_inspections`) — building permit final inspection [cn_answer_01m27c1bf0nqhsfmddp5aeyvth "Building permit for roof tie-in and fireplace"]
    - sizing: none (structure default used)

## Open questions (needs_info → Questions tab)

- `paint_phase_2` — whether any field painting is contracted is unresolved

## CANON GAPS — decisions made with no canon behind them

These are honest "judged from scope/understanding alone" calls. Each one is a place where a canon entry (a policy, a default, a reference) would make the next generation more grounded — the owners' ask-list.

- **Procurement**:
    - `proc_trusses` exclude — shed roof is stick-framed 2x8 rafters
    - `proc_water_heater` exclude — outside scope footprint
    - `proc_tile` exclude — no tile in scope
    - `proc_hard_flooring` exclude — broom-finish slab, no flooring
    - `proc_carpet` exclude — no carpet or floating floor
    - `proc_insulation` exclude — outside scope footprint
    - `proc_drywall` exclude — outside scope footprint
    - `proc_cabinets` exclude — no cabinetry in scope
    - `proc_countertops` exclude — no countertops in scope
    - `proc_paint` exclude — stock — rides install task
    - `proc_shower_glass` exclude — no shower in scope
    - `proc_doors_trim` exclude — no interior doors; trim stock rides install task
    - `proc_plumbing_fixtures` exclude — outside scope footprint
    - `proc_concrete_patio` exclude — covered by proc_foundation_package
- **Permits**:
    - `permit_tdec_septic` exclude — no septic work
    - `permit_plumbing` exclude — outside scope footprint
    - `permit_mechanical` exclude — outside scope footprint
- **Retrofit (pre-addition work)**:
    - `retrofit_demo` exclude — no pre-addition interior work
    - `retrofit_rough_meps` exclude — no pre-addition work
    - `retrofit_drywall` exclude — no pre-addition work
    - `retrofit_finishes` exclude — no pre-addition work
- **Site Prep & Foundation**:
    - `foundation_inspection` include — post and fireplace footings ahead of pour
- **Framing & Shell**:
    - `roof_reintegration` exclude — new roof framed, no preserved roof
- **Rough Trades (MEPs)**:
    - `rough_plumbing` exclude — outside scope footprint
    - `rough_hvac` exclude — outside scope footprint
- **Insulation & Drywall**:
    - `insulation` exclude — outside scope footprint
    - `insulation_inspection` exclude — outside scope footprint
    - `drywall` exclude — outside scope footprint
    - `paint_phase_1` exclude — outside scope footprint
- **Interior Finishes**:
    - `shower_work` exclude — no shower in scope
    - `hard_flooring` exclude — broom-finish slab, no flooring
    - `cabinets_counters` exclude — no cabinetry or fixed installs
    - `carpet_floating` exclude — no carpet in scope
    - `mep_fixture_install` exclude — no MEPs in scope
    - `finish_carpentry` exclude — no interior doors/base; cap trim covered by enclosure_finishes
    - `stair_build` exclude — no stairs
    - `paint_phase_2` needs_info — whether any field painting is contracted is unresolved
- **Concrete & Landscaping**:
    - `concrete_flatwork` exclude — covered by foundation_pour
    - `landscaping` exclude — yard restoration excluded; minor edge grading only
- **Closeout**:
    - `customer_walkthrough` include — standard closeout walkthrough

## Canon entries that worked this run

- `cn_answer_01m27c6d2c7bkk5q7rw7wknx5r` — porch electrical scope [job] · cited 6×
- `cn_answer_01m27c146prjakvbspqnvant86` — Roof support post bearing method [job] · cited 5×
- `cn_answer_01m27c1bf0nqhsfmddp5aeyvth` — Building permit for roof tie-in and fireplace [job] · cited 5×
- `cn_rates_inspections_crews` — Inspections & crew norms [company/project] · cited 5×
- `cn_answer_01m27da2eqaed109nxfcsmm0tt` — hose bibbs, condenser, meter, exterior lights on tie-in walls [job] · cited 4×
- `cn_answer_01m27dcv5caze1cq62m88w0jdt` — Rafter tie-in at existing eave [job] · cited 4×
- `cn_policy_rate_card_governs` — Rate card governs [company/project] · cited 4×
- `cn_answer_01m2f8xpsxfjdmck8ynwjmjh4g` — Footprint and knee wall dimensions source [job] · cited 4×
- `cn_answer_01m27c17wtw9dfmx15rrdbakxa` — Shed roof-to-house connection method [job] · cited 3×
- `cn_answer_01m27c93gsa86df7raesb3nrse` — HVAC condenser relative to patio footprint [job] · cited 3×
- `cn_answer_01m27c0w60xvysq0qzpw0kzpdc` — Fireplace construction type [job] · cited 3×
- `cn_answer_01m2f38k9tdnjdx1p5q71y65vk` — Gutter tie-in end-cap and downspout handling [job] · cited 3×
- `cn_answer_01m27c988ay7g5epmnmf9k6950` — Rear-yard patio equipment access route [job] · cited 3×
- `cn_policy_mobilization_floor` — Mobilization floor [company/project] · cited 3×
- `cn_answer_01m27d8cznp4xkg2cqebxqemwq` — roof post count including footings [job] · cited 3×
- `cn_answer_01m27cb9sw1yae52vcmpgawaa4` — Screen porch open sides count [job] · cited 3×
- `cn_answer_01m27c697dj12q6v2yfm9vs4h6` — Fireplace and chimney placement [job] · cited 3×
- `cn_company_no_demo_without_materials` — No demo without materials [company/project] · cited 2×
- `cn_answer_01m27dd8dav16xy6brxr4k8dnv` — Screen door sourcing [job] · cited 2×
- `cn_answer_01m27dar1xcbw3yvg7ymcc1ccs` — Fireplace veneer and hearth material sourcing [job] · cited 2×
- `cn_rates_demo_site` — Demo & site rates [company/project] · cited 2×
- `cn_rates_excavation_concrete` — Excavation & concrete rates [company/project] · cited 2×
- `cn_rates_framing` — Framing rates [company/project] · cited 2×
- `cn_rates_fireplace` — Fireplace (manufactured kit) rates [company/project] · cited 2×
- `cn_answer_01m27c7y1jx7vq37p8ccdd2nvp` — Shed roof fascia/soffit/gutters exclusion [job] · cited 2×
- `cn_rates_cladding_finish` — Cladding & finish rates [company/project] · cited 2×
- `cn_answer_01m27c9eh5crgq0g8793tdjx8q` — Is the beam carrying the rafters over the open screen side dimensional lumber or [job] · cited 1×
- `cn_answer_01m27dd24aq4mt61yjapbqmrrv` — Firebox and chimney kit lead time [job] · cited 1×
- `cn_company_never_split_framing` — Never split framing [company/project] · cited 1×
- `cn_answer_01m2f8xsw3wrzmpyx958j86psd` — Itemized scope overrides deck labeling [job] · cited 1×
- `cn_answer_01m27dazmbrgc1wt9kq8r4rdtd` — Chimney chase termination height [job] · cited 1×
- `cn_rates_roofing` — Roofing rates [company/project] · cited 1×
- `cn_answer_01m27cbqnj01k7av9fzz9470zy` — existing roof/wall vents under new shed roof tie-in [job] · cited 1×
- `cn_company_interior_concurrency` — Interior trade concurrency [company/project] · cited 1×

## Warnings & findings

- Coverage: 8 PM-SETTLED quantities were consumed by NO task (footprint_sqft=267sqft, patio_length_ft=22.92ft, patio_depth_ft=11.67ft, rafter_span_ft=11.67ft, eave_height_ft=8.16ft, screen_door_lead_weeks=2.5weeks, fireplace_kit_lead_weeks=3.5weeks, veneer_hearth_lead_weeks=1weeks) — a human ruled on these numbers; verify each either feeds a derived quantity (dimension inputs do) or check which document value the sizing rode instead.
- Duration for "siding": 1wd is below structure min 2 (derived value kept — floors are advisory for hours-derived durations).
- Quantity drift: "fireplace_finish_work" cited fireplace_veneer_sqft=145; evidence sheet says 150 — check which source it rode.
- Foreman check: "roofing" 22h → 21h — Gutter pull + end cap (1.5h) is already carried on site_and_structure_demo's own basis (gutter pull 23LF+end-cap 1.5), so it is billed twice; card math without it is 2.9+8+4.6+1.4+3=19.9, plus a little rounding, which gives 21h.
- Foreman check RAISED "enclosure_finishes" 21h → 25h — Screen door hang is missing: exterior_windows_doors routes it to this task, but this basis has no line for it. Added the card's stock door hang + hardware rate of 4h to 21h.

## Assumptions

- "Paint phase 2 (final coats)" (paint_phase_2) EXCLUDED pending answer: whether any field painting is contracted is unresolved.
- "Foundation Inspection" (foundation_inspection) is included but its structure row is UNVETTED — confirm with Will.
- "Foundation Pour" (foundation_pour) is included but its structure row is UNVETTED — confirm with Will.
- "Fireplace kit (firebox + Class A chimney)" (proc_fireplace_kit) is included but its structure row is UNVETTED — confirm with Will.
- "Fireplace chase, firebox set & Class A chimney" (fireplace_chase_install) is included but its structure row is UNVETTED — confirm with Will.
- "Fireplace/chimney inspection" (fireplace_chimney_inspection) is included but its structure row is UNVETTED — confirm with Will.
- "Fireplace veneer, hearth & mantel" (fireplace_finish_work) is included but its structure row is UNVETTED — confirm with Will.
