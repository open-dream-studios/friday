# DECISIONS — Addition · JOB-01M2410PQXYPJ3V5XPHZAWJGY6

generation `01M2VABKQKARAFT94VJ5MRYZ5J` · structure v15 · trunk e5655d96
effort: include=medium · sizing=medium · foreman=default
timings: Resolving the Addition checklist (structure v15) 7s · Resolving inclusion against scope + answers 73s · Sizing 9 components against the evidence 65s · Foreman review — challenging the estimate 43s · Assembling the task graph 0s · TOTAL 189s

## Summary

- verdicts: 32 included · 40 excluded · 0 needs-info · 0 extra task(s)
- canon: 30/72 decisions cited canon (42 judged without — see CANON GAPS)
- validator: clean on the first pass

## Procurement

### Procurement Items
- ✅ INCLUDE **Foundation** (`proc_foundation_package`) — 16 bags hand-mix + 8 post brackets — pickup [cn_answer_01m2h07a109r3bkg5a08t2fpmp "Post/footer count for deck installation"]
    - 🚚 pickup: 1 cal day (dedicated trip) — 8 footers 12x12x12 hand-mix: ~16 bags 80-lb concrete, 8 post brackets, rebar/form scrap — all on-shelf at local yard/big-box; picked up in one trip
    - sizing canon: cn_answer_01m2h07a109r3bkg5a08t2fpmp "Post/footer count for deck installation" · cn_company_no_demo_without_materials "No demo without materials"
    - 🚩 footer_concrete_cy=0.3 — no truck, no pump, no block; card note re elevated pads does not apply to post-and-beam
- ✅ INCLUDE **Windows & exterior doors** (`proc_windows_doors`) — 6 stock 36x60 DH + stock 3068, 1-2 wk lead [cn_answer_01m2h05z9rcpxmbbhdre94zax0 "Window and exterior door sizing"]
    - delivery: 14 cal days — 6 stock 36x60 DH + 1 stock 3068 door, settled 1-2 wk lead; carry upper bound 2 wk = 14 cal days
    - sizing canon: cn_answer_01m2h05z9rcpxmbbhdre94zax0 "Window and exterior door sizing" · cn_answer_01m2h04gwya5z01r8ksa4m72n3 "Scope of signed proposal vs presentation extras" · cn_company_no_demo_without_materials "No demo without materials"
    - 🚩 window_count=6, exterior_door_count=1 settled; presentation's 7 windows/6568 double door not adopted
    - 🚩 stock confirmed by PM — no custom lead
- ✖ EXCLUDE **LVL / engineered beams** (`proc_lvl`) — beam 3-ply 2x12 dimensional; headers built-up 2x [cn_answer_01m2h07n7p3c346ya4jcq01stt "Window and door header material"]
- ✅ INCLUDE **Framing Package** (`proc_framing_package`) — posts, beam, floor, 63 LF walls, sheathing — ~2 wk lead [cn_answer_01m2h07a109r3bkg5a08t2fpmp "Post/footer count for deck installation"]
    - delivery: 7 cal days — 8 6x6 PT posts, 132 LF 2x12 (3-ply beam), 34 joists + ~106 LF ledger/rim, 15 subfloor + 16 OSB sheets, 2x plate/stud stock, built-up 2x headers — all commodity yard stock, no LVL; 1 wk lumber-yard del
    - sizing canon: cn_answer_01m2h07n7p3c346ya4jcq01stt "Window and door header material" · cn_company_no_demo_without_materials "No demo without materials"
    - 🚩 no LVL (header_material settled built-up 2x)
    - 🚩 must land on site before demo per no-demo-without-materials policy
    - 🚩 post_height_ft=10 low confidence — sloped grade may vary post lengths; order long
- ✖ EXCLUDE **Roof trusses (custom)** (`proc_trusses`) — existing shed roof retained, no new roof structure
- ✅ INCLUDE **Subpanel / service equipment** (`proc_subpanel`) — fused-disconnect conversion kit after electrician assessment, ~5 days [cn_answer_01m2h06ydaqtcgtwsd52f71taw "Fused disconnect suitability verification" · cn_answer_01m242n6gdhw5e8383q8cdjdjh "Existing main electrical service ampacity"]
    - 🚚 pickup: 1 cal day (dedicated trip) — Fused-disconnect conversion kit ($180) + breakers, on-shelf at electrical supply — picked up after electrician verifies suitability
    - sizing canon: cn_answer_01m2h06ydaqtcgtwsd52f71taw "Fused disconnect suitability verification" · cn_answer_01m242n6gdhw5e8383q8cdjdjh "Existing main electrical service ampacity"
    - 🚩 subpanel_verification_status=not yet — assessment gates the order; if disconnect unsuitable, full subpanel is an add with longer lead outside this takeoff
- ✅ INCLUDE **HVAC equipment (mini-split / system)** (`proc_hvac_equipment`) — 1 ductless mini-split, ~1 wk lead after BTU sizing [cn_answer_01m2h07380zf2f2b6d5mq7087j "Mini-split condenser mounting location"]
    - delivery: 7 cal days — 1 single-zone mini-split ($2,500 allowance), common size; supplier ships ~1 wk; BTU sizing TBD but standard range
    - sizing canon: cn_answer_01m2h07380zf2f2b6d5mq7087j "Mini-split condenser mounting location"
    - 🚩 mini_split_count=1; BTU not yet sized — order once load confirmed; line set length ~10 ft drop + wall run for grade-level condenser
- ✅ INCLUDE **Electrical Package** (`proc_electrical_package`) — circuits, ~10 receptacles, raceway, boxes — ~5 days [cn_answer_01m2v8hr4cnrajcmahesr0yfxn "Brick wall receptacle mounting method"]
    - 🚚 pickup: 1 cal day (dedicated trip) — Rough wire, boxes, 10 receptacles (2 GFCI), 43 LF Wiremold-type raceway + surface boxes, mini-split circuit materials — stock at electrical supply/big-box, one trip
    - sizing canon: cn_answer_01m2v8hr4cnrajcmahesr0yfxn "Brick wall receptacle mounting method"
    - 🚩 brick_wall_raceway_lf=43 — raceway not in JBD takeoff, add to order
- ✖ EXCLUDE **Water heater (tank or tankless)** (`proc_water_heater`) — no water heater in scope
- ✖ EXCLUDE **Plumbing Package** (`proc_plumbing_package`) — outside scope footprint
- ✖ EXCLUDE **Tile & setting materials** (`proc_tile`) — no tile in scope
- ✖ EXCLUDE **Hard flooring** (`proc_hard_flooring`) — outside scope footprint (Option 2 unselected)
- ✖ EXCLUDE **Carpet / floating floor** (`proc_carpet`) — no carpet or floating floor in scope
- ✅ INCLUDE **Insulation** (`proc_insulation`) — wall, floor, and vented ceiling batts + baffles [cn_answer_01m2h06f3g9rynf1qtwg3vd8zr "Sunroom ceiling finish scope"]
    - 🚚 pickup: 1 cal day (dedicated trip) — R-13 wall batts 504 sf + floor batts 430 sf + ceiling batts 430 sf + rafter-bay baffles; commodity stock at big-box/supply, one pickup
    - sizing canon: cn_answer_01m2h06f3g9rynf1qtwg3vd8zr "Sunroom ceiling finish scope" · cn_answer_01m2h05t36bf78eb76f3m7fas3 "Floor soffit vs floor-cavity batt install sequence"
    - 🚩 ceiling batts + baffles (430 sf) settled in scope but 0 in JBD — include in order
    - 🚩 floor batt must be on hand before subfloor closes cavity (early in framing)
- ✅ INCLUDE **Drywall** (`proc_drywall`) — ~30 sheets, 3 framed walls + ceiling [cn_answer_01m2h06f3g9rynf1qtwg3vd8zr "Sunroom ceiling finish scope" · cn_answer_01m2h06rhtkfd9r0jcakqcvsnv "Brick wall drywall treatment"]
    - delivery: 5 cal days — ~30 sheets 1/2 in 4x8 (504 wall + 430 ceiling), mud, tape, screws — stock, supplier boom-delivery to elevated room ~5 cal days
    - sizing canon: cn_answer_01m2h06rhtkfd9r0jcakqcvsnv "Brick wall drywall treatment" · cn_answer_01m2h06f3g9rynf1qtwg3vd8zr "Sunroom ceiling finish scope"
    - 🚩 drywall_sheets_total=30 settled; split is walls+ceiling, not JBD's walls+brick
    - 🚩 ceiling sheets hoisted to elevated room — boom truck delivery preferred over hand-carry up scaffold
- ✖ EXCLUDE **Cabinets / vanities** (`proc_cabinets`) — no cabinetry in scope
- ✖ EXCLUDE **Countertops** (`proc_countertops`) — no countertops in scope
- ✖ EXCLUDE **Paint + Primer** (`proc_paint`) — outside scope footprint (paint is unselected Option 2)
- ✖ EXCLUDE **Shower glass (template after tile)** (`proc_shower_glass`) — no shower in scope
- ✖ EXCLUDE **Interior doors & trim package** (`proc_doors_trim`) — outside scope footprint (trim is unselected Option 2)
- ✖ EXCLUDE **Plumbing fixtures (faucets, sinks, commodes, shower trim)** (`proc_plumbing_fixtures`) — outside scope footprint
- ✅ INCLUDE **Light fixtures & devices** (`proc_light_fixtures`) — 6 allowance lights + 2 fans + devices — pickup
    - delivery: 7 cal days — 6 fixtures @ $75 + 2 ceiling fans @ $150 allowance-grade, customer-selected; typically stock/online ~1 wk
    - sizing canon: cn_company_no_demo_without_materials "No demo without materials"
    - 🚩 customer selections not yet made — must be finalized before scheduling per policy; specialty picks could push to 3 wk
- ✖ EXCLUDE **Concrete + Patio Work** (`proc_concrete_patio`) — covered by proc_foundation_package; no patio
- ✖ EXCLUDE **Fireplace kit (firebox + Class A chimney)** (`proc_fireplace_kit`) — outside scope footprint

## Permits

### Permit Items
- ✅ INCLUDE **Building permit** (`permit_building`) — not yet applied; City of Kingsport, w/ electrical+mechanical [cn_answer_01m2h05g2rkknn9h4zpxfwm31y "Building permit application status" · cn_answer_01m2v8hrn6k4zsjdjkpk9wk6cc "Permitting AHJ for 333 Toy Crawford Road"]
- ✖ EXCLUDE **TDEC septic permit** (`permit_tdec_septic`) — no septic work in scope
- ✖ EXCLUDE **Electrical service / meter permit** (`permit_electrical_service`) — subpanel conversion only; rides building permit [cn_answer_01m242n6gdhw5e8383q8cdjdjh "Existing main electrical service ampacity"]
- ✖ EXCLUDE **Plumbing Permit** (`permit_plumbing`) — outside scope footprint
- ✅ INCLUDE **Mechanical Permit** (`permit_mechanical`) — mini-split install in scope [cn_answer_01m2h07380zf2f2b6d5mq7087j "Mini-split condenser mounting location"]

## Retrofit (pre-addition work)

### Retrofit Work
- ✖ EXCLUDE **Utility & equipment relocations (heat pump, disconnect, lines)** (`utility_relocations`) — disconnect survives demo untouched; no relocations
- ✖ EXCLUDE **Retrofit demolition (interior areas outside the addition)** (`retrofit_demo`) — no pre-addition interior work
- ✖ EXCLUDE **Retrofit rough MEPs** (`retrofit_rough_meps`) — no retrofit work in scope
- ✖ EXCLUDE **Retrofit drywall & patching** (`retrofit_drywall`) — no retrofit work in scope
- ✖ EXCLUDE **Retrofit finishes (paint, tile, flooring, fixtures)** (`retrofit_finishes`) — no retrofit work in scope

## Demolition

### Main Demolition
- ✅ INCLUDE **Demolition (site + structure at addition footprint)** (`site_and_structure_demo`) — full 430 sf sunroom demo under shored roof [cn_answer_01m2h04ypdna2xyz4epatkc24q "Temporary shoring design authority" · cn_answer_01m2h055eewewa4x5800phewke "Elevated work access and debris removal method"]
    - duration: 70h ÷ (3 crew × 8h) = 2.92 → **3wd**
    - basis: walls+6 win 504sf×0.025=12.6 · ceiling 430sf×0.025=10.8 · floor/joists 430sf×0.03=13 · posts/beam 8×0.75=6 · load 3 dump runs 3×2=6 → 48 ×1.2 elevated/hand-lower=58 · shoring erect 43LF=12 → 70h
    - crew: 3 — Card demo crew 3; elevated hand-lowering needs ground man plus two up
    - quantities: demo_area_sqft=430, dump_runs=3, temp_shoring_span_lf=43, wall_lf_new=63, plate_height_ft=8, window_count=6, post_count=8, stories=elevated second-story structure, site_access_constraints=scaffold from grade, hand-lower debris
    - sizing canon: cn_policy_elevated_access "Elevated / second-story access premium" · cn_rates_inspections_crews "Inspections & crew norms" · cn_answer_01m2h055eewewa4x5800phewke "Elevated work access and debris removal method" · cn_answer_01m2h04ypdna2xyz4epatkc24q "Temporary shoring design authority" · cn_policy_rate_card_governs "Rate card governs"
    - ↪ scope moved to: `site_prep`, `framing`
    - jbd: agrees — JBD demo 48h ≈ my 58h w/ premium; gen-cond 36h split: 12h shoring erect here, rest to framing, protection to site_prep
    - 🚩 No card rate for structure demo — h/sf rates are judgment at production speed
    - 🚩 Shoring is foreman-designed; 12h erect assumes simple post/beam shores over 43 LF
    - 🚩 Elevated premium covers hand-lowering; scaffold erect and site protection (2h) billed on site_prep
    - 🚩 Circuit de-energize ~1h electrician assumed inside hours, no relocation

## Site Prep & Foundation

### Groundwork
- ✅ INCLUDE **Site prep (protection, staging, access)** (`site_prep`) — occupied-home protection, scaffold erect from sloped grade [cn_policy_elevated_access "Elevated / second-story access premium" · cn_answer_01m2h055eewewa4x5800phewke "Elevated work access and debris removal method"]
    - duration: 16h ÷ (2 crew × 8h) = 1 → **1wd**
    - basis: protection 2 (card, once) · staging/dumpster/access/layout 5 · scaffold erect on sloped grade 6 + strike 3 (once per job, canon) → 16h
    - crew: 2 — Scaffold erect on slope needs two; small 43x10 workface
    - quantities: site_access_constraints=scaffold from sloped grade, stories=elevated second-story, occupied_home=yes, footprint_sqft=430
    - sizing canon: cn_rates_demo_site "Demo & site rates" · cn_policy_elevated_access "Elevated / second-story access premium" · cn_policy_mobilization_floor "Mobilization floor"
    - 🚩 Scaffold moves for later trades ride on elevated premium in those tasks, not here
    - 🚩 Occupied home, but access is from grade — interior protection minimal
- ✅ INCLUDE **Excavation (footings, slab, access)** (`excavation`) — 8 hand-dug footer pockets, ~4 saw-cut through pad [cn_answer_01m2h06kyz1cqvxetrtfth59py "Footer pocket excavation method at existing pad" · cn_answer_01m2h07a109r3bkg5a08t2fpmp "Post/footer count for deck installation"]
    - duration: 18h ÷ (2 crew × 8h) = 1.13 → **2wd**
    - basis: layout 8 posts 2 · saw-cut 4×1.5=6 · hand-dig pockets 8×1.0=8 (deviates from card 0.25 machine — shores+slope block mini-ex, settled) · hand-haul spoils 2 → 18h
    - crew: 2 — Saw + laborer under shored roof; more bodies can't fit pockets
    - quantities: post_count=8, footer_excavation_method=hand-dug, saw_cut_pocket_count=4, footer_excavation_note=saw-cut at some pockets
    - sizing canon: cn_rates_excavation_concrete "Excavation & concrete rates" · cn_rates_demo_site "Demo & site rates" · cn_answer_01m2h06kyz1cqvxetrtfth59py "Footer pocket excavation method at existing pad" · cn_policy_rate_card_governs "Rate card governs"
    - jbd: disagrees — JBD 44h split: ~20h post set + beam → framing; ~24h left for groundwork; this 18h + foundation_prep 12h ≈ 30h
    - 🚩 Saw-cut count 3-5 open until pad exposed (±1.5h/pocket)
    - 🚩 No saw priced in JBD/proposal
    - 🚩 Rock at hand-dug pockets = change order, not padded here
    - 🚩 Hand-dig rate 1h/pocket is a card deviation cited per settled method
- ✅ INCLUDE **Prepare Foundation** (`foundation_prep`) — 8 footer pockets set for brackets + condenser pad form [cn_answer_01m2h07380zf2f2b6d5mq7087j "Mini-split condenser mounting location"]
    - duration: 12h ÷ (2 crew × 8h) = 0.75 → **1wd**
    - basis: forms 8×0.4=3.2 · hand-mix/pour 16 bags 0.3cy 3 · brackets set 8×0.25=2 · condenser grade pad 2 · footing inspection coordination 2 → 12h
    - crew: 2 — Bag-mix pour at 8 pockets is a two-person job
    - quantities: footer_concrete_cy=0.3, post_count=8, foundation_type=8 discrete footers 12x12x12, condenser_location=grade-level pad
    - sizing canon: cn_rates_excavation_concrete "Excavation & concrete rates" · cn_rates_inspections_crews "Inspections & crew norms" · cn_answer_01m2h07380zf2f2b6d5mq7087j "Mini-split condenser mounting location"
    - ↪ scope moved to: `framing`
    - jbd: agrees — Fits within the ~24h groundwork share of the 44h JBD section after framing takes post/beam
    - 🚩 Footing inspection visit priced here (2h) — no dedicated inspection task in plan; permit not yet applied
    - 🚩 Post set (8×0.75) and beam belong to framing — excluded here
- ✅ INCLUDE **Foundation Inspection** (`foundation_inspection`) — footing inspection before pour
    - sizing: none (structure default used)
- ✅ INCLUDE **Foundation Pour** (`foundation_pour`) — 8 hand-mix footers + brackets, condenser pad [cn_answer_01m2h07a109r3bkg5a08t2fpmp "Post/footer count for deck installation"]
    - sizing: none (structure default used)

## Framing & Shell

### Structural Framing
- ✅ INCLUDE **Framing (floor, walls, roof structure, sheathing)** (`framing`) — posts, 44 LF beam, PT floor, 63 LF walls, in-house [cn_answer_01m2h04q3316zv1j8g1hk0hwe6 "existing shed-roof bearing height" · cn_company_never_split_framing "Never split framing" · cn_policy_elevated_access "Elevated / second-story access premium"]
    - duration: 110h ÷ (3 crew × 8h) = 4.58 → **5wd**
    - basis: posts 8×0.75=6 · beam 44LF≈2 seg×7=14 · ledger/rim 106LF≈4 · joists 34×0.5=17 · floor batt 430sf×0.012=5 · subfloor 15×0.4=6 · walls 63LF×0.35=22 (7 built-up headers) · sheathing 16×0.4=6.4 → 80 ×1.22 elevated = 98h
    - crew: 3 — Card framing crew 3; 43×10 single-story workface from scaffold, no room for more
    - quantities: post_count=8, beam_lf=44, floor_joist_count=34, subfloor_sheets=15, floor_insulation_sqft=430, wall_lf_new=63, plate_height_ft=8, wall_sheathing_sqft=504, window_count=6, exterior_door_count=1, header_material=built-up dimensional 2x, stories=elevated second-story structure, site_access_constraints=scaffold from sloped grade, hand-handling
    - sizing canon: cn_rates_framing "Framing rates" · cn_policy_elevated_access "Elevated / second-story access premium" · cn_policy_rate_card_governs "Rate card governs" · cn_company_never_split_framing "Never split framing" · cn_answer_01m2h07a109r3bkg5a08t2fpmp "Post/footer count for deck installation" · cn_answer_01m2h07n7p3c346ya4jcq01stt "Window and door header material"
    - ↪ scope moved to: `siding`
    - jbd: disagrees — JBD share ~127h (found 20 + floor 62 + wall 45) runs hot vs card math; 98h kept, WRB 7.6h moved to siding
    - foreman: 98h → 110h — Walls 63LF priced at the screen-frames/nailers rate 0.35 h/LF — that card rate is for screen porch framing, not a full headered exterior stud wall with 7 built-up headers and 6 window + 1 door rough openings; ~0.5 h/LF (32h) is the honest number, and ledger+rim 106LF at ~0.04 h/LF is light for a fla
    - 🚩 Plate height 8 ft unverified — wall/sheathing qty provisional until bearing line measured
    - 🚩 Floor batt (430 sf, ~5h) carried HERE since it lays from above before subfloor; insulation task must not re-count it
    - 🚩 No card rate for joists/wall LF — 0.5h/joist and 0.35 h/LF used, below JBD's 0.45 h/LF
    - 🚩 Ledger into existing brick wall (anchors) not detailed; ~4h ledger/rim allowance
- ✅ INCLUDE **Roof reintegration (reseat preserved roof, bearing transfer, strike shoring)** (`roof_reintegration`) — reseat 43 ft retained roof, strike shoring [cn_answer_01m2h04ypdna2xyz4epatkc24q "Temporary shoring design authority" · cn_answer_01m2h04q3316zv1j8g1hk0hwe6 "existing shed-roof bearing height"]
    - duration: 30h ÷ (3 crew × 8h) = 1.25 → **2wd**
    - basis: reseat/shim 43LF×0.3=13 · ties+fastening 43LF≈4 · level/attachment verify 2 · strike shoring 43LF≈6 → 25 ×1.22 elevated = 30h
    - crew: 3 — Bearing transfer needs 3 to shim, fasten and drop shores in sequence
    - quantities: temp_shoring_span_lf=43, roof_area_sqft=430, plate_height_ft=8, stories=elevated second-story structure
    - sizing canon: cn_answer_01m2h04ypdna2xyz4epatkc24q "Temporary shoring design authority" · cn_policy_elevated_access "Elevated / second-story access premium" · cn_policy_mobilization_floor "Mobilization floor"
    - ↪ scope moved to: `roofing`, `site_and_structure_demo`
    - jbd: agrees — JBD roof 24h + shoring share of GC 36h; framing act only here, flashing/vents on roofing, shoring erect on demo
    - 🚩 Roof pitch unknown; shoring layout vs new wall lines could add a day
    - 🚩 Shoring erect + site protection excluded (demo/site prep own them)
- ✅ INCLUDE **Exterior windows & doors install** (`exterior_windows_doors`) — 6 stock windows + 1 exterior door [cn_answer_01m2h05z9rcpxmbbhdre94zax0 "Window and exterior door sizing"]
    - duration: 26h ÷ (2 crew × 8h) = 1.63 → **2wd**
    - basis: windows 6×3h set+flash=18 · door 3068 card 4 → 22 ×1.2 elevated = 26h
    - crew: 2 — Stock flanged units set by 2 from scaffold; a third adds nothing
    - quantities: window_count=6, exterior_door_count=1, stories=elevated second-story structure
    - sizing canon: cn_rates_cladding_finish "Cladding & finish rates" · cn_policy_elevated_access "Elevated / second-story access premium" · cn_answer_01m2h05z9rcpxmbbhdre94zax0 "Window and exterior door sizing"
    - jbd: disagrees — JBD 19h has no elevated premium; card premium +20% lifts it to ~23-26h
    - 🚩 Stock 36x60 DH assumed; lead time 2 wk gates start
    - 🚩 Exterior trim LF unknown — not in these hours

### Deck
- ✖ EXCLUDE **Deck build** (`deck_build`) — outside scope footprint; presentation deck not contracted [cn_answer_01m2h04gwya5z01r8ksa4m72n3 "Scope of signed proposal vs presentation extras"]

### Fireplace Structure
- ✖ EXCLUDE **Fireplace chase, firebox set & Class A chimney** (`fireplace_chase_install`) — outside scope footprint

## Exterior Finishes

### Cladding & Roof
- ✅ INCLUDE **Roofing (underlayment, shingles, flashing, tie-in blend)** (`roofing`) — 63 LF tie-in flashing, 2 vent penetrations reused, intake vents [cn_answer_01m2h06f3g9rynf1qtwg3vd8zr "Sunroom ceiling finish scope" · cn_rates_roofing "Roofing rates"]
    - duration: 21h ÷ (3 crew × 8h) = 0.88 → **1wd**
    - basis: tie-in flash 63LF×0.2=12.6 · vent reuse 2×1.5=3 · eave intake 43LF×0.08=3.4 · house-wall counterflash 2 → 21h (reseat lives in roof_reintegration)
    - crew: 3 — card roofing crew 3; short scaffold-access flashing run, more bodies don't help
    - quantities: roof_tie_in_lf=63, roof_vent_reuse_count=2, eave_intake_vent_lf=43, roof_patch_count=0, roof_area_sqft=430
    - sizing canon: cn_rates_roofing "Roofing rates" · cn_policy_rate_card_governs "Rate card governs" · cn_rates_inspections_crews "Inspections & crew norms"
    - ↪ scope moved to: `roof_reintegration`
    - jbd: disagrees — JBD 24h roof section includes reseat (framing) + 2 patches; roofing share ~14h; my 21h carries vent/intake work JBD lacks
    - 🚩 roof_pitch unknown; eave detail unknown — intake vent method assumed strip/edge vent
    - 🚩 roof_tie_in_lf is low-confidence
    - 🚩 no shingle work: roof retained; if damaged shingles found at reseat, add 2.5h/sq
- ✅ INCLUDE **Siding (WRB, siding, tie-in blend)** (`siding`) — WRB + ~394 sf vinyl lap on 3 walls, elevated [cn_policy_elevated_access "Elevated / second-story access premium"]
    - duration: 55h ÷ (2 crew × 8h) = 3.44 → **4wd**
    - basis: siding 394sf×0.08=31.5 · +20% elevated=38 · corner/J-channel/surrounds ~8 → 46h (WRB 504sf×0.015 in framing per mapping)
    - crew: 2 — card siding crew 2; three short walls off scaffold, one workface
    - quantities: siding_sqft_net=394, wall_sheathing_sqft=504, window_count=6, exterior_door_count=1, stories=elevated second-story structure, exterior_trim_lf=UNKNOWN
    - sizing canon: cn_rates_cladding_finish "Cladding & finish rates" · cn_policy_elevated_access "Elevated / second-story access premium" · cn_policy_rate_card_governs "Rate card governs" · cn_rates_inspections_crews "Inspections & crew norms"
    - ↪ scope moved to: `framing`
    - jbd: disagrees — JBD 24h vinyl siding+trim runs lower; card cut-up rate + elevated premium governs; vinyl long courses may beat card
    - foreman: 46h → 55h — WRB 504sf×0.015=7.6h is orphaned: siding basis says it lives in framing, framing basis says it moved to siding, and neither row's math carries it — add WRB ~7.6h +20% elevated ≈ 9h here
    - 🚩 exterior_trim_lf unknown — trim carried as 8h allowance
    - 🚩 plate height 8ft provisional; siding area shifts with bearing line
    - 🚩 JBD double-counted WRB; WRB assigned to framing, not here
- ✅ INCLUDE **Fascia, soffit & gutters** (`fascia_soffit_gutters`) — 430 sf under-floor vinyl soffit from below; no gutters [cn_answer_01m2h05t36bf78eb76f3m7fas3 "Floor soffit vs floor-cavity batt install sequence"]
    - duration: 26h ÷ (2 crew × 8h) = 1.63 → **2wd**
    - basis: under-floor vinyl soffit 430sf×0.05=21.5 · +20% elevated/overhead=26 → 26h (no roof fascia/soffit/gutters in proposal)
    - crew: 2 — overhead sheet work from scaffold needs a holder + fastener
    - quantities: soffit_under_floor_sqft=430, stories=elevated second-story structure, site_access_constraints=ground access on sloped grade below via scaffold
    - sizing canon: cn_answer_01m2h05t36bf78eb76f3m7fas3 "Floor soffit vs floor-cavity batt install sequence" · cn_policy_elevated_access "Elevated / second-story access premium" · cn_answer_01m2h055eewewa4x5800phewke "Elevated work access and debris removal method"
    - jbd: agrees — JBD 25h soffit line from floor_system mapped here; matches
    - 🚩 no card rate for vinyl soffit — 0.05 h/sf judgment (below beadboard 0.08)
    - 🚩 gutters/roof fascia not in signed proposal — zero hours carried
- ✖ EXCLUDE **Extend existing appliance vents through new roof** (`appliance_vent_extension`) — no appliance vents; roof vents handled by roofing

### Fireplace Finish
- ✖ EXCLUDE **Fireplace veneer, hearth & mantel** (`fireplace_finish_work`) — outside scope footprint

## Rough Trades (MEPs)

### Rough MEPs
- ✖ EXCLUDE **Rough plumbing** (`rough_plumbing`) — outside scope footprint
- ✅ INCLUDE **Rough HVAC (line set / duct extension)** (`rough_hvac`) — mini-split line set to grade-level condenser pad [cn_answer_01m2h07380zf2f2b6d5mq7087j "Mini-split condenser mounting location"]
    - duration: 8h ÷ (2 crew × 8h) = 0.5 → **1wd**
    - basis: line set drop ~10ft post + wall run 4h · 2 penetrations/line-hide 2h · condenser pad set + rough coord 2h → 8h (JBD 10h lumps rough+finish; ~6h rough share, +2h elevated access)
    - crew: 2 — line set run from scaffold on sloped grade needs a second hand
    - quantities: mini_split_count=1, condenser_location=grade-level pad beneath sunroom, post_height_ft=10
    - sizing canon: cn_answer_01m2h07380zf2f2b6d5mq7087j "Mini-split condenser mounting location" · cn_policy_elevated_access "Elevated / second-story access premium"
    - ↪ scope moved to: `mep_fixture_install`
    - jbd: agrees — JBD 10h split ~6h rough here, ~4h head set/startup → mep_fixture_install
    - 🚩 post height 10ft is low-confidence; sloped lot varies line set length
    - 🚩 BTU/unit unselected — allowance only
- ✅ INCLUDE **Rough electrical (circuits, subpanel, boxes)** (`rough_electrical`) — subpanel conversion, ~10 receptacles, raceway on brick, lights/fans [cn_answer_01m2v8hr4cnrajcmahesr0yfxn "Brick wall receptacle mounting method" · cn_answer_01m2h06ydaqtcgtwsd52f71taw "Fused disconnect suitability verification"]
    - duration: 26h ÷ (2 crew × 8h) = 1.63 → **2wd**
    - basis: subpanel conversion 4h · boxes 10 recep+6 lights+2 fans+~4 switches=22÷6/h≈4h · homeruns/circuits 6h · raceway 43LF×0.2=9h · mini-split circuit 2h · assess 1h → 26h (JBD 30h)
    - crew: 2 — ~6 boxes/hr pace and raceway run assume a 2-man crew
    - quantities: receptacle_count=10, light_fixture_count=6, ceiling_fan_count=2, brick_wall_raceway_lf=43, subpanel_conversion=1, existing_service_amps=200
    - sizing canon: cn_answer_01m2v8hr4cnrajcmahesr0yfxn "Brick wall receptacle mounting method" · cn_answer_01m2h06ydaqtcgtwsd52f71taw "Fused disconnect suitability verification" · cn_policy_mobilization_floor "Mobilization floor"
    - ↪ scope moved to: `mep_fixture_install`, `bundled_rough_inspections`
    - jbd: agrees — JBD 30h rough share slightly hot; raceway unpriced in JBD offsets; 6h device finish → mep_fixture_install
    - 🚩 subpanel conversion contingent on electrician assessment not yet done — replacement panel is an add
    - 🚩 receptacle count ambiguous (room total vs brick-wall-only); carried as 10 total
    - 🚩 permit not yet applied; rough inspection carried on bundled_rough_inspections

## Rough Inspections

### Bundled Inspections
- ✅ INCLUDE **Rough inspections (MEPs then framing, bundled)** (`bundled_rough_inspections`) — electrical, mechanical, then framing inspections [cn_rates_inspections_crews "Inspections & crew norms"]
    - duration: 8h ÷ (1 crew × 8h) = 1 → **1wd**
    - basis: card 2h/visit · rough electrical 2 · rough mechanical (mini-split) 2 · framing (last, after MEP drill-through) 2 → 6h; footing/insulation/final visits not in this task
    - crew: 1 — fixed 1 — superintendent walks the inspector; strict MEP-then-framing order within visit
    - quantities: plumbing_scope=none, permit_ahj=City of Kingsport (confirm at application), mini_split_count=1, subpanel_conversion=1
    - sizing canon: cn_rates_inspections_crews "Inspections & crew norms" · cn_answer_01m2h05g2rkknn9h4zpxfwm31y "Building permit application status" · cn_answer_01m2v8hrn6k4zsjdjkpk9wk6cc "Permitting AHJ for 333 Toy Crawford Road" · cn_policy_rate_card_governs "Rate card governs"
    - foreman: 6h → 8h — Insulation inspection visit (card 2h/visit) is explicitly excluded here and has no home on any other task in the list — vented ceiling with baffles+batt gets inspected before drywall; carry it here
    - 🚩 Permit not yet applied (settled) — 1-2 wk issuance lead sits ahead of 2027-03-01 start; inspection dates hinge on AHJ availability
    - 🚩 AHJ defaulted to City of Kingsport; county fallback does not change visit list
    - 🚩 If AHJ won't bundle rough visits on one day, add ~2h coordination and plan 2 wd per hint
    - 🚩 Subpanel conversion contingent on electrician assessment — a replacement panel could add a service visit outside this sizing
    - 🚩 Footing, insulation and final inspections are not listed tasks here; 6h covers rough visits only
- ✖ EXCLUDE **Fireplace/chimney inspection** (`fireplace_chimney_inspection`) — no fireplace in scope

## Insulation & Drywall

### Insulation, Drywall & Prime
- ✅ INCLUDE **Insulation & air sealing** (`insulation`) — R-13 walls, floor batt, vented ceiling baffles + batt [cn_answer_01m2h06f3g9rynf1qtwg3vd8zr "Sunroom ceiling finish scope" · cn_answer_01m2h05t36bf78eb76f3m7fas3 "Floor soffit vs floor-cavity batt install sequence"]
    - duration: 18h ÷ (2 crew × 8h) = 1.13 → **2wd**
    - basis: wall batt R-13 504sf×0.01=5 · ceiling batt overhead 430sf×0.015=6.5 · rafter-bay baffles ~33 bays×0.15=5 · air seal/penetrations 1.5 → 18h (floor batt 430sf moved to framing per answer)
    - crew: 2 — 430 sf room, overhead sloped ceiling batts + baffles need two hands
    - quantities: wall_insulation_sqft=504, ceiling_insulation_sqft=430, floor_insulation_sqft=430, ceiling_finish=vented rafter-bay insulation + ceiling drywall
    - sizing canon: cn_answer_01m2h06f3g9rynf1qtwg3vd8zr "Sunroom ceiling finish scope" · cn_answer_01m2h05t36bf78eb76f3m7fas3 "Floor soffit vs floor-cavity batt install sequence" · cn_01m2gwxjenvqkzjam46b1bc14r "Demolished ceiling assemblies require an explicit ceiling rebuild scope before insulation and drywall tasks are generated" · cn_policy_mobilization_floor "Mobilization floor"
    - ↪ scope moved to: `framing`
    - jbd: disagrees — JBD 7h is walls+floor only; floor batt lives in framing; settled vented ceiling (baffles+batt, 0h in JBD) adds ~11.5h
    - 🚩 Ceiling insulation priced nowhere in JBD — added from settled scope
    - 🚩 Wall sf provisional on 8 ft plate height (unverified bearing line)
    - 🚩 No card rate for insulation — production rates from judgment
- ✅ INCLUDE **Insulation inspection** (`insulation_inspection`) — insulation inspection incl ceiling
    - sizing: none (structure default used)
- ✅ INCLUDE **Drywall (hang, tape, sand)** (`drywall`) — Level 3 on 3 framed walls + 430 sf ceiling; brick exposed [cn_answer_01m2h06f3g9rynf1qtwg3vd8zr "Sunroom ceiling finish scope" · cn_answer_01m2h06rhtkfd9r0jcakqcvsnv "Brick wall drywall treatment"]
    - duration: 55h ÷ (2 crew × 8h) = 3.44 → **4wd**
    - basis: hang walls 16sh×0.5=8 · hang sloped ceiling overhead 14sh×0.8=11 · bead/6 win+1 door returns 4 · tape+3 coats L3 934sf×0.03=28 · sand+clean 4 → 55h (JBD 65h runs hot, kept)
    - crew: 2 — 430 sf room; 2 hang/finish, 3rd body idle during coat cycles
    - quantities: drywall_sqft=504, ceiling_drywall_sqft=430, drywall_sheets_total=30, window_count=6, exterior_door_count=1
    - sizing canon: cn_answer_01m2h06rhtkfd9r0jcakqcvsnv "Brick wall drywall treatment" · cn_answer_01m2h06f3g9rynf1qtwg3vd8zr "Sunroom ceiling finish scope" · cn_company_interior_concurrency "Interior trade concurrency"
    - jbd: disagrees — JBD 65h/848sf walls-only; settled 934sf incl. 430sf overhead ceiling, brick wall excluded; finish 43h flagged hot — mine 55h
    - 🚩 Inherited: JBD drywall mis-shaped (brick wall out, ceiling in) and finish hours hot
    - 🚩 Taping coats need dry time — 3+ calendar days regardless of hours
    - 🚩 Wall sf provisional on 8 ft plate height
    - 🚩 No prime in base scope (Option 2 at $0) — prime step empty
- ✖ EXCLUDE **Paint phase 1 (prime + wall prep + ceilings)** (`paint_phase_1`) — outside scope footprint (paint/prime unselected Option 2)

## Interior Finishes

### Interior Installs
- ✖ EXCLUDE **Shower work (waterproofing, tile, grout)** (`shower_work`) — no shower in scope
- ✖ EXCLUDE **Hard flooring install (LVP, hardwood, tile floors)** (`hard_flooring`) — outside scope footprint (LVP unselected Option 2)
- ✖ EXCLUDE **Cabinets, counters, vanities & fixed items** (`cabinets_counters`) — no cabinetry in scope
- ✖ EXCLUDE **Carpet & floating floors** (`carpet_floating`) — no carpet in scope
- ✖ EXCLUDE **Enclosure finishes (screening, panel infill, interior cladding)** (`enclosure_finishes`) — conditioned drywalled room, no screening or cladding infill

### Final Trades & Paint 2
- ✅ INCLUDE **Final Trades (fixture install for HVAC, Plumbing, and Electrical)** (`mep_fixture_install`) — 6 lights, 2 fans, devices, mini-split head/condenser set
    - duration: 22h ÷ (2 crew × 8h) = 1.38 → **2wd**
    - basis: lights 6×0.75=4.5 · fans 2×1.5=3 · devices 10 recpt+switches ~12×0.4=5 · subpanel/ckt final trim 3 · mini-split head+condenser final connect/vac/charge/commission 6 · plumbing 0 → 21.5≈22h
    - crew: 2 — one electrician + one HVAC tech; no plumbing on job; small room, 2-trade interior cap
    - quantities: light_fixture_count=6, ceiling_fan_count=2, receptacle_count=10, mini_split_count=1, plumbing_scope=none, subpanel_conversion=1
    - sizing canon: cn_company_interior_concurrency "Interior trade concurrency" · cn_policy_mobilization_floor "Mobilization floor" · cn_answer_01m2v8hr4cnrajcmahesr0yfxn "Brick wall receptacle mounting method" · cn_answer_01m2h07380zf2f2b6d5mq7087j "Mini-split condenser mounting location"
    - 🚩 plumbing_scope=none — notes mention faucets/sinks but none exist here; no plumbing hours carried
    - 🚩 mini-split allowance BTU TBD; final connect assumes line set roughed at rough_hvac
    - 🚩 subpanel conversion contingent on electrician assessment; a replacement panel would add hours outside this figure
- ✖ EXCLUDE **Finish Carpentry** (`finish_carpentry`) — outside scope footprint (trim unselected Option 2)
- ✖ EXCLUDE **Stairs (build/finish)** (`stair_build`) — outside scope footprint; presentation stairs not contracted [cn_answer_01m2h04gwya5z01r8ksa4m72n3 "Scope of signed proposal vs presentation extras"]
- ✖ EXCLUDE **Paint phase 2 (final coats)** (`paint_phase_2`) — outside scope footprint

## Concrete & Landscaping

### Concrete & Landscape
- ✖ EXCLUDE **Concrete flatwork (patios, driveways, walkways)** (`concrete_flatwork`) — condenser pad covered by foundation_pour; no patio
- ✖ EXCLUDE **Landscaping & site restoration** (`landscaping`) — outside scope footprint; no seed/straw

## Closeout

### Walkthrough & Final Inspection
- ✅ INCLUDE **Customer walkthrough & punch list** (`customer_walkthrough`) — standard closeout walkthrough
    - sizing: none (structure default used)
- ✅ INCLUDE **Final inspections (building + E/P/M, bundled)** (`final_inspections`) — final building + electrical/mechanical
    - sizing: none (structure default used)

## CANON GAPS — decisions made with no canon behind them

These are honest "judged from scope/understanding alone" calls. Each one is a place where a canon entry (a policy, a default, a reference) would make the next generation more grounded — the owners' ask-list.

- **Procurement**:
    - `proc_trusses` exclude — existing shed roof retained, no new roof structure
    - `proc_water_heater` exclude — no water heater in scope
    - `proc_plumbing_package` exclude — outside scope footprint
    - `proc_tile` exclude — no tile in scope
    - `proc_hard_flooring` exclude — outside scope footprint (Option 2 unselected)
    - `proc_carpet` exclude — no carpet or floating floor in scope
    - `proc_cabinets` exclude — no cabinetry in scope
    - `proc_countertops` exclude — no countertops in scope
    - `proc_paint` exclude — outside scope footprint (paint is unselected Option 2)
    - `proc_shower_glass` exclude — no shower in scope
    - `proc_doors_trim` exclude — outside scope footprint (trim is unselected Option 2)
    - `proc_plumbing_fixtures` exclude — outside scope footprint
    - `proc_light_fixtures` include — 6 allowance lights + 2 fans + devices — pickup
    - `proc_concrete_patio` exclude — covered by proc_foundation_package; no patio
    - `proc_fireplace_kit` exclude — outside scope footprint
- **Permits**:
    - `permit_tdec_septic` exclude — no septic work in scope
    - `permit_plumbing` exclude — outside scope footprint
- **Retrofit (pre-addition work)**:
    - `utility_relocations` exclude — disconnect survives demo untouched; no relocations
    - `retrofit_demo` exclude — no pre-addition interior work
    - `retrofit_rough_meps` exclude — no retrofit work in scope
    - `retrofit_drywall` exclude — no retrofit work in scope
    - `retrofit_finishes` exclude — no retrofit work in scope
- **Site Prep & Foundation**:
    - `foundation_inspection` include — footing inspection before pour
- **Framing & Shell**:
    - `fireplace_chase_install` exclude — outside scope footprint
- **Exterior Finishes**:
    - `appliance_vent_extension` exclude — no appliance vents; roof vents handled by roofing
    - `fireplace_finish_work` exclude — outside scope footprint
- **Rough Trades (MEPs)**:
    - `rough_plumbing` exclude — outside scope footprint
- **Rough Inspections**:
    - `fireplace_chimney_inspection` exclude — no fireplace in scope
- **Insulation & Drywall**:
    - `insulation_inspection` include — insulation inspection incl ceiling
    - `paint_phase_1` exclude — outside scope footprint (paint/prime unselected Option 2)
- **Interior Finishes**:
    - `shower_work` exclude — no shower in scope
    - `hard_flooring` exclude — outside scope footprint (LVP unselected Option 2)
    - `cabinets_counters` exclude — no cabinetry in scope
    - `carpet_floating` exclude — no carpet in scope
    - `enclosure_finishes` exclude — conditioned drywalled room, no screening or cladding infill
    - `mep_fixture_install` include — 6 lights, 2 fans, devices, mini-split head/condenser set
    - `finish_carpentry` exclude — outside scope footprint (trim unselected Option 2)
    - `paint_phase_2` exclude — outside scope footprint
- **Concrete & Landscaping**:
    - `concrete_flatwork` exclude — condenser pad covered by foundation_pour; no patio
    - `landscaping` exclude — outside scope footprint; no seed/straw
- **Closeout**:
    - `customer_walkthrough` include — standard closeout walkthrough
    - `final_inspections` include — final building + electrical/mechanical

## Canon entries that worked this run

- `cn_policy_elevated_access` — Elevated / second-story access premium [company/project] · cited 11×
- `cn_answer_01m2h06f3g9rynf1qtwg3vd8zr` — Sunroom ceiling finish scope [job] · cited 9×
- `cn_answer_01m2h07380zf2f2b6d5mq7087j` — Mini-split condenser mounting location [job] · cited 8×
- `cn_answer_01m2h07a109r3bkg5a08t2fpmp` — Post/footer count for deck installation [job] · cited 6×
- `cn_rates_inspections_crews` — Inspections & crew norms [company/project] · cited 6×
- `cn_policy_rate_card_governs` — Rate card governs [company/project] · cited 6×
- `cn_answer_01m2v8hr4cnrajcmahesr0yfxn` — Brick wall receptacle mounting method [job] · cited 5×
- `cn_answer_01m2h05t36bf78eb76f3m7fas3` — Floor soffit vs floor-cavity batt install sequence [job] · cited 5×
- `cn_policy_mobilization_floor` — Mobilization floor [company/project] · cited 5×
- `cn_company_no_demo_without_materials` — No demo without materials [company/project] · cited 4×
- `cn_answer_01m2h05z9rcpxmbbhdre94zax0` — Window and exterior door sizing [job] · cited 4×
- `cn_answer_01m2h06ydaqtcgtwsd52f71taw` — Fused disconnect suitability verification [job] · cited 4×
- `cn_answer_01m2h06rhtkfd9r0jcakqcvsnv` — Brick wall drywall treatment [job] · cited 4×
- `cn_answer_01m2h04ypdna2xyz4epatkc24q` — Temporary shoring design authority [job] · cited 4×
- `cn_answer_01m2h055eewewa4x5800phewke` — Elevated work access and debris removal method [job] · cited 4×
- `cn_answer_01m2h04gwya5z01r8ksa4m72n3` — Scope of signed proposal vs presentation extras [job] · cited 3×
- `cn_answer_01m2h07n7p3c346ya4jcq01stt` — Window and door header material [job] · cited 3×
- `cn_answer_01m242n6gdhw5e8383q8cdjdjh` — Existing main electrical service ampacity [property] · cited 3×
- `cn_answer_01m2h05g2rkknn9h4zpxfwm31y` — Building permit application status [job] · cited 2×
- `cn_answer_01m2v8hrn6k4zsjdjkpk9wk6cc` — Permitting AHJ for 333 Toy Crawford Road [property] · cited 2×
- `cn_rates_demo_site` — Demo & site rates [company/project] · cited 2×
- `cn_answer_01m2h06kyz1cqvxetrtfth59py` — Footer pocket excavation method at existing pad [job] · cited 2×
- `cn_rates_excavation_concrete` — Excavation & concrete rates [company/project] · cited 2×
- `cn_answer_01m2h04q3316zv1j8g1hk0hwe6` — existing shed-roof bearing height [job] · cited 2×
- `cn_company_never_split_framing` — Never split framing [company/project] · cited 2×
- `cn_rates_cladding_finish` — Cladding & finish rates [company/project] · cited 2×
- `cn_rates_roofing` — Roofing rates [company/project] · cited 2×
- `cn_company_interior_concurrency` — Interior trade concurrency [company/project] · cited 2×
- `cn_rates_framing` — Framing rates [company/project] · cited 1×
- `cn_01m2gwxjenvqkzjam46b1bc14r` — Demolished ceiling assemblies require an explicit ceiling rebuild scope before insulation and drywall tasks are generated [company/project] · cited 1×

## Warnings & findings

- Coverage: 1 PM-SETTLED quantity was consumed by NO task (window_door_lead_time_weeks=2weeks) — a human ruled on these numbers; verify each either feeds a derived quantity (dimension inputs do) or check which document value the sizing rode instead.
- Coverage: JBD section "electrical" pays into component "interior_installs" but no included task carries it — paid-for scope with zero tasks.
- Coverage: JBD section "hvac" pays into component "interior_installs" but no included task carries it — paid-for scope with zero tasks.
- Foreman check RAISED "framing" 98h → 110h — Walls 63LF priced at the screen-frames/nailers rate 0.35 h/LF — that card rate is for screen porch framing, not a full headered exterior stud wall with 7 built-up headers and 6 window + 1 door rough openings; ~0.5 h/LF (32h) is the honest number, and ledger+rim 106LF at ~0.04 h/LF is light for a fla
- Foreman check RAISED "siding" 46h → 55h — WRB 504sf×0.015=7.6h is orphaned: siding basis says it lives in framing, framing basis says it moved to siding, and neither row's math carries it — add WRB ~7.6h +20% elevated ≈ 9h here
- Foreman check RAISED "bundled_rough_inspections" 6h → 8h — Insulation inspection visit (card 2h/visit) is explicitly excluded here and has no home on any other task in the list — vented ceiling with baffles+batt gets inspected before drywall; carry it here

## Assumptions

- "Foundation Inspection" (foundation_inspection) is included but its structure row is UNVETTED — confirm with Will.
- "Foundation Pour" (foundation_pour) is included but its structure row is UNVETTED — confirm with Will.
