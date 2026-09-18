# DECISIONS — Addition · JOB-01M2410PQXYPJ3V5XPHZAWJGY6

generation `01M2V9DVVZDFVA5Q0S1W5J0NYW` · structure v15 · trunk 28ce9ba0
effort: include=medium · sizing=medium · foreman=default
timings: Resolving the Addition checklist (structure v15) 14s · Resolving inclusion against scope + answers 54s · Sizing 9 components against the evidence 62s · Foreman review — challenging the estimate 93s · Assembling the task graph 0s · TOTAL 223s

## Summary

- verdicts: 32 included · 40 excluded · 0 needs-info · 0 extra task(s)
- canon: 35/72 decisions cited canon (37 judged without — see CANON GAPS)
- validator: clean on the first pass

## Procurement

### Procurement Items
- ✅ INCLUDE **Foundation** (`proc_foundation_package`) — 8 footers, 16 bags hand-mix, brackets, form stock — pickup [cn_answer_01m2h07a109r3bkg5a08t2fpmp "Post/footer count for deck installation"]
    - 🚚 pickup: 1 cal day (dedicated trip) — 8 footers 12x12x12 = 0.3 cy hand-mix (~16 bags 80-lb), 8 post brackets, rebar stubs, form boards/cutoffs — all on-shelf at local lumberyard/box store; no truck, no block, no pump
    - sizing canon: cn_answer_01m2h07a109r3bkg5a08t2fpmp "Post/footer count for deck installation"
    - 🚩 No slab or perimeter wall (settled post-and-beam) — package is bag mix + brackets + form scrap only
    - 🚩 Footers hand-dug; confirm bracket type matches 6x6 PT post before pickup
- ✅ INCLUDE **Windows & exterior doors** (`proc_windows_doors`) — 6 stock 36x60 DH + 3068 door, 1-2 wk lead [cn_answer_01m2h05z9rcpxmbbhdre94zax0 "Window and exterior door sizing"]
    - delivery: 14 cal days — 6 stock 36x60 DH + 1 stock 3068 exterior door; settled stock 1-2 wk, upper bound 2 wk carried = 14 cal days
    - sizing canon: cn_answer_01m2h05z9rcpxmbbhdre94zax0 "Window and exterior door sizing" · cn_answer_01m2h04gwya5z01r8ksa4m72n3 "Scope of signed proposal vs presentation extras"
    - 🚩 Presentation p4's 7 windows / 6568 double door not adopted — order exactly 6 + 1
    - 🚩 Settled lead is at the low end of the 14-42 guardrail; stock confirmed by PM answer
- ✖ EXCLUDE **LVL / engineered beams** (`proc_lvl`) — beam 3-ply 2x12, headers built-up 2x — no LVL [cn_answer_01m2h07n7p3c346ya4jcq01stt "Window and door header material"]
- ✅ INCLUDE **Framing Package** (`proc_framing_package`) — posts, beam, joists, walls, OSB — full framing package [cn_company_no_demo_without_materials "No demo without materials"]
    - delivery: 10 cal days — 8 6x6 PT posts ~10 ft, 132 LF 2x12 (3-ply 44 LF beam), ~34 2x10 joists + ledger/rim ~106 LF, 15 sheets subfloor, 63 LF wall stock, ~16 sheets 7/16 OSB, built-up 2x headers (no LVL) — all commodity dim
    - sizing canon: cn_answer_01m2h07n7p3c346ya4jcq01stt "Window and door header material" · cn_company_no_demo_without_materials "No demo without materials" · cn_answer_01m2h04q3316zv1j8g1hk0hwe6 "existing shed-roof bearing height"
    - 🚩 No LVL in order (settled built-up 2x headers)
    - 🚩 Plate height 8 ft unverified — wall stud length provisional until bearing line measured; order after field check or carry precut studs
    - 🚩 Lumber market swings — order early rather than halt framing; must be on site before demo (no-demo-without-materials)
- ✖ EXCLUDE **Roof trusses (custom)** (`proc_trusses`) — existing shed roof retained; no trusses
- ✅ INCLUDE **Subpanel / service equipment** (`proc_subpanel`) — disconnect→breaker conversion kit after electrician assessment, ~1 wk [cn_answer_01m2h06ydaqtcgtwsd52f71taw "Fused disconnect suitability verification" · cn_answer_01m242n6gdhw5e8383q8cdjdjh "Existing main electrical service ampacity"]
    - delivery: 4 cal days — Breaker subpanel conversion kit ($180 + breakers) from electrical supply house ~3-5 days; gated on electrician assessment of fused disconnect not yet done
    - sizing canon: cn_answer_01m2h06ydaqtcgtwsd52f71taw "Fused disconnect suitability verification" · cn_answer_01m242n6gdhw5e8383q8cdjdjh "Existing main electrical service ampacity"
    - 🚩 Order is gated: electrician must verify fused disconnect suitability before kit is ordered (settled, not yet done)
    - 🚩 If disconnect is unsuitable, a full replacement subpanel is an add with longer lead outside this takeoff; mini-split circuit depends on it
- ✅ INCLUDE **HVAC equipment (mini-split / system)** (`proc_hvac_equipment`) — 1 ductless mini-split, $2,500 allowance, ~1-2 wk lead [cn_answer_01m2h07380zf2f2b6d5mq7087j "Mini-split condenser mounting location"]
    - delivery: 7 cal days — 1 single-zone mini-split, $2,500 allowance, BTU TBD but 430 sf room = common 12-18k size; stock at HVAC supply ~1 week incl. line set + grade pad
    - sizing canon: cn_answer_01m2h07380zf2f2b6d5mq7087j "Mini-split condenser mounting location"
    - 🚩 BTU/size TBD — a specialty size pushes toward 3 weeks; confirm selection before ordering
    - 🚩 Condenser on grade-level pad beneath sunroom — include pad + ~10 ft vertical line set/line-hide in order
- ✅ INCLUDE **Electrical Package** (`proc_electrical_package`) — ~10 receptacles, raceway, lights, fans, circuits — delivery [cn_answer_01m2v8hr4cnrajcmahesr0yfxn "Brick wall receptacle mounting method"]
    - 🚚 pickup: 1 cal day (dedicated trip) — Rough package: ~10 receptacles (2 GFCI), boxes, Romex, 2 fan boxes, mini-split circuit wire/disconnect, plus 43 LF Wiremold-type raceway + surface boxes for brick wall — stock at supply house/box stor
    - sizing canon: cn_answer_01m2v8hr4cnrajcmahesr0yfxn "Brick wall receptacle mounting method"
    - 🚩 43 LF surface raceway for the brick wall is not in the JBD material list — add to the order
    - 🚩 Receptacle count carried as 10 room total (medium confidence); confirm layout before pickup
- ✖ EXCLUDE **Water heater (tank or tankless)** (`proc_water_heater`) — no water heater in scope
- ✖ EXCLUDE **Plumbing Package** (`proc_plumbing_package`) — outside scope footprint
- ✖ EXCLUDE **Tile & setting materials** (`proc_tile`) — no tile in scope
- ✖ EXCLUDE **Hard flooring** (`proc_hard_flooring`) — outside scope footprint — Option 2 unselected [cn_answer_01m2h04gwya5z01r8ksa4m72n3 "Scope of signed proposal vs presentation extras"]
- ✖ EXCLUDE **Carpet / floating floor** (`proc_carpet`) — outside scope footprint
- ✅ INCLUDE **Insulation** (`proc_insulation`) — wall, floor, vented ceiling batts + baffles — pickup [cn_answer_01m2h06f3g9rynf1qtwg3vd8zr "Sunroom ceiling finish scope"]
    - 🚚 pickup: 1 cal day (dedicated trip) — R-13 batts for 504 sf walls, floor batts 430 sf, ceiling batts 430 sf + rafter-bay baffles (vented) — stock at box store/supply, dedicated trip
    - sizing canon: cn_answer_01m2h06f3g9rynf1qtwg3vd8zr "Sunroom ceiling finish scope" · cn_answer_01m2h05t36bf78eb76f3m7fas3 "Floor soffit vs floor-cavity batt install sequence"
    - 🚩 Ceiling insulation + baffles (430 sf) are settled in scope but priced nowhere in the JBD — include in order
    - 🚩 Wall batt area provisional on 8 ft plate height
- ✅ INCLUDE **Drywall** (`proc_drywall`) — ~30 sheets walls + ceiling, ~5 day delivery [cn_answer_01m2h06f3g9rynf1qtwg3vd8zr "Sunroom ceiling finish scope" · cn_answer_01m2h06rhtkfd9r0jcakqcvsnv "Brick wall drywall treatment"]
    - delivery: 5 cal days — 30 sheets 4x8 (504 sf walls + 430 sf ceiling ÷ 32 w/ waste), mud, tape, screws — stock; supplier boom delivery to elevated second-story room ~5 days
    - sizing canon: cn_answer_01m2h06rhtkfd9r0jcakqcvsnv "Brick wall drywall treatment" · cn_answer_01m2h06f3g9rynf1qtwg3vd8zr "Sunroom ceiling finish scope"
    - 🚩 Sheet count matches JBD's 30 by coincidence — split differs (ceiling in, brick wall out); do not order per JBD's 344 sf brick-wall share
    - 🚩 Elevated room with scaffold-only access: request boom truck stock into the room — hand-carry up scaffold is real hours on the drywall task
- ✖ EXCLUDE **Cabinets / vanities** (`proc_cabinets`) — no cabinetry in scope
- ✖ EXCLUDE **Countertops** (`proc_countertops`) — no countertops in scope
- ✖ EXCLUDE **Paint + Primer** (`proc_paint`) — outside scope footprint — paint is unselected Option 2 [cn_answer_01m2h04gwya5z01r8ksa4m72n3 "Scope of signed proposal vs presentation extras"]
- ✖ EXCLUDE **Shower glass (template after tile)** (`proc_shower_glass`) — no shower in scope
- ✖ EXCLUDE **Interior doors & trim package** (`proc_doors_trim`) — outside scope footprint — trim/casing unselected Option 2 [cn_answer_01m2h04gwya5z01r8ksa4m72n3 "Scope of signed proposal vs presentation extras"]
- ✖ EXCLUDE **Plumbing fixtures (faucets, sinks, commodes, shower trim)** (`proc_plumbing_fixtures`) — outside scope footprint
- ✅ INCLUDE **Light fixtures & devices** (`proc_light_fixtures`) — 6 lights + 2 fans, allowance items — pickup
    - delivery: 7 cal days — 6 fixtures @ $75 + 2 ceiling fans @ $150 allowance — allowance-grade stock items, customer-selected; ~1 week once selections made
    - sizing canon: cn_company_no_demo_without_materials "No demo without materials"
    - 🚩 Customer selections not yet made — no-schedule-before-selections policy applies; specialty picks push to 3 weeks
    - 🚩 Fan locations not shown on any drawing — confirm before rough-in
- ✖ EXCLUDE **Concrete + Patio Work** (`proc_concrete_patio`) — covered by proc_foundation_package; no flatwork
- ✖ EXCLUDE **Fireplace kit (firebox + Class A chimney)** (`proc_fireplace_kit`) — outside scope footprint

## Permits

### Permit Items
- ✅ INCLUDE **Building permit** (`permit_building`) — building permit w/ electrical+mechanical, not yet applied [cn_answer_01m2h05g2rkknn9h4zpxfwm31y "Building permit application status" · cn_answer_01m2v8hrn6k4zsjdjkpk9wk6cc "Permitting AHJ for 333 Toy Crawford Road"]
- ✖ EXCLUDE **TDEC septic permit** (`permit_tdec_septic`) — no septic work
- ✖ EXCLUDE **Electrical service / meter permit** (`permit_electrical_service`) — subpanel only rides building permit; 200A main untouched [cn_answer_01m242n6gdhw5e8383q8cdjdjh "Existing main electrical service ampacity"]
- ✖ EXCLUDE **Plumbing Permit** (`permit_plumbing`) — outside scope footprint
- ✅ INCLUDE **Mechanical Permit** (`permit_mechanical`) — mini-split install; rides building permit application

## Retrofit (pre-addition work)

### Retrofit Work
- ✖ EXCLUDE **Utility & equipment relocations (heat pump, disconnect, lines)** (`utility_relocations`) — disconnect survives demo untouched; no relocations
- ✖ EXCLUDE **Retrofit demolition (interior areas outside the addition)** (`retrofit_demo`) — no pre-addition interior work
- ✖ EXCLUDE **Retrofit rough MEPs** (`retrofit_rough_meps`) — no pre-addition work
- ✖ EXCLUDE **Retrofit drywall & patching** (`retrofit_drywall`) — no pre-addition work
- ✖ EXCLUDE **Retrofit finishes (paint, tile, flooring, fixtures)** (`retrofit_finishes`) — no pre-addition work

## Demolition

### Main Demolition
- ✅ INCLUDE **Demolition (site + structure at addition footprint)** (`site_and_structure_demo`) — full 430 sf sunroom demo under shored roof, 3 dump runs [cn_answer_01m2h04ypdna2xyz4epatkc24q "Temporary shoring design authority" · cn_policy_elevated_access "Elevated / second-story access premium"]
    - duration: 68h ÷ (3 crew × 8h) = 2.83 → **3wd**
    - basis: shoring erect 43LF temp beam+posts+bracing 12 · ceiling 430sf×0.02=9 · walls+6 win 63LF×0.25=16 · floor/subfloor 430sf×0.025=11 · posts/beam 4 · load 3 runs×2=6 · +20% elev/hand-lower on 46=9 · de-energize 1 → 68h
    - crew: 3 — Card demo crew 3; 43 ft workface on scaffold needs a lowering hand plus two strippers
    - quantities: demo_area_sqft=430, temp_shoring_span_lf=43, dump_runs=3, stories=elevated second-story structure, site_access_constraints=scaffold from sloped grade, hand-lower debris, demo_electrical_prep=de-energize only, window_count=6, wall_lf_new=63
    - sizing canon: cn_policy_elevated_access "Elevated / second-story access premium" · cn_rates_inspections_crews "Inspections & crew norms" · cn_answer_01m2h055eewewa4x5800phewke "Elevated work access and debris removal method" · cn_answer_01m2h04ypdna2xyz4epatkc24q "Temporary shoring design authority" · cn_policy_rate_card_governs "Rate card governs"
    - ↪ scope moved to: `site_prep`, `roof_reintegration`
    - jbd: agrees — JBD 48h demo + ~16h shoring-erect share of general_conditions ≈ 64h vs 68h; strike/maintain → framing, protection/staging → site_prep
    - 🚩 Site protection, staging, dumpster spot and scaffold erect/strike excluded here — billed once on site_prep
    - 🚩 Shoring strike and maintenance through roof reseat sit in roof_reintegration/framing, not here
    - 🚩 Elevated premium taken at 20% (low end) since sunroom is outside house envelope and access is direct from grade
    - 🚩 Hand-lowering debris on sloped grade is the main uncertainty; no lift assumed per settled access

## Site Prep & Foundation

### Groundwork
- ✅ INCLUDE **Site prep (protection, staging, access)** (`site_prep`) — protection below, scaffold from sloped grade, staging [cn_answer_01m2h055eewewa4x5800phewke "Elevated work access and debris removal method" · cn_policy_elevated_access "Elevated / second-story access premium"]
    - duration: 16h ÷ (2 crew × 8h) = 1 → **1wd**
    - basis: site protection (condenser/finishes below) 2 · staging+dumpster spot+access path+post layout 6 · scaffold erect/strike once, sloped grade 43 LF run 8 → 16h
    - crew: 2 — Scaffold and staging on sloped grade is 2-person work; 3rd adds nothing
    - quantities: site_access_constraints=scaffold from sloped grade, occupied_home=yes, stories=elevated second-story structure, post_count=8
    - sizing canon: cn_rates_demo_site "Demo & site rates" · cn_policy_elevated_access "Elevated / second-story access premium" · cn_answer_01m2h055eewewa4x5800phewke "Elevated work access and debris removal method"
    - 🚩 Scaffold moves for later trades ride on elevated premium, not here
    - 🚩 Dump-run/dumpster setup counted here once; demo owns hauling
- ✅ INCLUDE **Excavation (footings, slab, access)** (`excavation`) — 8 hand-dug footer pockets, ~4 saw-cut through pad [cn_answer_01m2h06kyz1cqvxetrtfth59py "Footer pocket excavation method at existing pad"]
    - duration: 16h ÷ (2 crew × 8h) = 1 → **1wd**
    - basis: pockets hand-dug 8×1.0=8 (card 0.25 machine rate n/a: shores+slope block machine) · sawcut+breakout 4×1.5=6 · condenser pad grade+spoils 2 → 16h
    - crew: 2 — Hand-dig pockets under shores; 2 laborers alternate saw/dig, no operator needed
    - quantities: post_count=8, footer_excavation_method=hand-dug, saw_cut_pocket_count=4, condenser_location=grade-level pad, footprint_sqft=430
    - sizing canon: cn_rates_demo_site "Demo & site rates" · cn_rates_excavation_concrete "Excavation & concrete rates" · cn_answer_01m2h06kyz1cqvxetrtfth59py "Footer pocket excavation method at existing pad" · cn_policy_rate_card_governs "Rate card governs"
    - jbd: disagrees — JBD 44h splits ~24h groundwork/20h post+beam; JBD prices no saw and 12h for all footers — hand-dig+cut deviation adds hours
    - 🚩 Saw-cut count 3-5 open until pad exposed (carried 4)
    - 🚩 Rock/hand-dig on sloped grade could run longer; rock is a change order
    - 🚩 Post layout must be field-marked before cutting (presentation shows 7, settled 8)
- ✅ INCLUDE **Prepare Foundation** (`foundation_prep`) — form/prep 8 footers + condenser pad [cn_answer_01m2h07a109r3bkg5a08t2fpmp "Post/footer count for deck installation"]
    - duration: 12h ÷ (2 crew × 8h) = 0.75 → **1wd**
    - basis: form 8 pockets ×0.25=2 · hand-mix 16 bags/0.3cy + place 8×0.5=4 · set/anchor brackets 8×0.25=2 · condenser pad form+pour 2 · footing inspection 2 → 12h
    - crew: 2 — Bag-mix pour on 8 small footers; 2 hands is the workface
    - quantities: footer_concrete_cy=0.3, post_count=8, foundation_type=post-and-beam 8 footers 12x12x12, condenser_location=grade-level pad
    - sizing canon: cn_rates_excavation_concrete "Excavation & concrete rates" · cn_rates_inspections_crews "Inspections & crew norms" · cn_policy_mobilization_floor "Mobilization floor"
    - ↪ scope moved to: `framing`
    - jbd: disagrees — Groundwork share of JBD 44h ≈24h vs my 28h (exc+fdn); gap is unpriced sawcut/hand-dig, not padding
    - 🚩 Post set + 3-ply beam hours live in framing, not here
    - 🚩 Footing inspection 2h carried here; permit not yet applied (gates visit)
    - 🚩 Bracket anchoring assumed wet-set/anchored at pour
- ✅ INCLUDE **Foundation Inspection** (`foundation_inspection`) — footing inspection before hand-mix pour
    - sizing: none (structure default used)
- ✅ INCLUDE **Foundation Pour** (`foundation_pour`) — 16-bag hand-mix pour, 8 footers w/ brackets [cn_answer_01m2h07a109r3bkg5a08t2fpmp "Post/footer count for deck installation"]
    - sizing: none (structure default used)

## Framing & Shell

### Structural Framing
- ✅ INCLUDE **Framing (floor, walls, roof structure, sheathing)** (`framing`) — posts, 44 LF beam, floor, 63 LF walls, sheathing, in-house [cn_company_never_split_framing "Never split framing" · cn_answer_01m2h04q3316zv1j8g1hk0hwe6 "existing shed-roof bearing height"]
    - duration: 102h ÷ (3 crew × 8h) = 4.25 → **5wd**
    - basis: posts 8×0.75=6 · beam 44LF=2seg×7=14 · joists 34×0.5=17 · ledger/rim 106LF=6 · subfloor 15sh×0.4=6 · floor batt 430sf×0.015=6 · walls 63LF×0.3=19 · headers 7×0.5=3.5 · sheathing 16sh×0.4=6.4 → 84 ×1.22 elevated → 102h
    - crew: 3 — Card framing crew 3; 43×10 single-story footprint, no room for more at workface
    - quantities: post_count=8, beam_lf=44, floor_joist_count=34, subfloor_sheets=15, floor_insulation_sqft=430, wall_lf_new=63, header_material=built-up 2x, wall_sheathing_sqft=504, stories=elevated, plate_height_ft=8
    - sizing canon: cn_rates_framing "Framing rates" · cn_policy_elevated_access "Elevated / second-story access premium" · cn_policy_rate_card_governs "Rate card governs" · cn_company_never_split_framing "Never split framing" · cn_answer_01m2h05t36bf78eb76f3m7fas3 "Floor soffit vs floor-cavity batt install sequence" · cn_answer_01m2h07n7p3c346ya4jcq01stt "Window and door header material"
    - ↪ scope moved to: `siding`, `site_prep`
    - jbd: disagrees — JBD ~125h (posts/beam ~18 + floor 62 + walls 45) runs hot vs card; kept 102h. WRB → siding.
    - 🚩 Plate height 8 ft provisional — must land existing roof bearing; wall/sheathing hours may shift
    - 🚩 Floor batt (430 sf) laid from above before subfloor carried here per PM answer, not on insulation task
    - 🚩 Post heights vary on sloped lot (post_height_ft low confidence)
    - 🚩 Hoisting/scaffold moves covered by +22% elevated premium, not billed separately
- ✅ INCLUDE **Roof reintegration (reseat preserved roof, bearing transfer, strike shoring)** (`roof_reintegration`) — retained shed roof reseated onto new walls, strike shoring [cn_answer_01m2h04ypdna2xyz4epatkc24q "Temporary shoring design authority"]
    - duration: 36h ÷ (3 crew × 8h) = 1.5 → **2wd**
    - basis: bearing transfer+shim 43LF×0.3=13 · rafter ties ~33×0.25=8 · level/attach verify 3 · strike shoring 43LF=8 → 32 ×1.15 elevated → 36h (flashing on roofing)
    - crew: 3 — Shore-to-wall transfer on 43 LF needs 3 hands to jack, shim and fasten safely
    - quantities: temp_shoring_span_lf=43, roof_area_sqft=430, plate_height_ft=8, stories=elevated
    - sizing canon: cn_answer_01m2h04ypdna2xyz4epatkc24q "Temporary shoring design authority" · cn_answer_01m2h04q3316zv1j8g1hk0hwe6 "existing shed-roof bearing height" · cn_policy_elevated_access "Elevated / second-story access premium"
    - ↪ scope moved to: `roofing`, `site_and_structure_demo`
    - jbd: disagrees — JBD ~22h (roof 24h less roofing share + GC strike share); rafter fastening + strike realistically 36h.
    - 🚩 Roof pitch and rafter count unknown — ties count assumed at 16 in o.c.
    - 🚩 Shoring erection billed with demo; only maintenance/strike here
    - 🚩 Strike only after tie-in flashing watertight — sequencing dependency on roofing
- ✅ INCLUDE **Exterior windows & doors install** (`exterior_windows_doors`) — 6 windows + 1 exterior door install [cn_answer_01m2h05z9rcpxmbbhdre94zax0 "Window and exterior door sizing"]
    - duration: 30h ÷ (2 crew × 8h) = 1.88 → **2wd**
    - basis: windows 6×3.5h=21 · door 3068 card floor 4 → 25 ×1.2 elevated → 30h
    - crew: 2 — Card window pace assumes 2-man; stock 36x60 units set from scaffold
    - quantities: window_count=6, exterior_door_count=1, stories=elevated
    - sizing canon: cn_rates_cladding_finish "Cladding & finish rates" · cn_policy_elevated_access "Elevated / second-story access premium" · cn_answer_01m2h05z9rcpxmbbhdre94zax0 "Window and exterior door sizing"
    - jbd: disagrees — JBD 19h lower; rechecked at production speed, elevated scaffold set + flashing justifies 30h.
    - 🚩 Stock 36x60 DH + 3068, 2-week lead — must be on site before siding
    - 🚩 Elevated premium applied per canon; no separate hoisting line

### Deck
- ✖ EXCLUDE **Deck build** (`deck_build`) — outside scope footprint — presentation deck not adopted [cn_answer_01m2h04gwya5z01r8ksa4m72n3 "Scope of signed proposal vs presentation extras"]

### Fireplace Structure
- ✖ EXCLUDE **Fireplace chase, firebox set & Class A chimney** (`fireplace_chase_install`) — outside scope footprint

## Exterior Finishes

### Cladding & Roof
- ✅ INCLUDE **Roofing (underlayment, shingles, flashing, tie-in blend)** (`roofing`) — 63 LF tie-in flashing, 2 vent patches reused as exhaust vents [cn_answer_01m2h06f3g9rynf1qtwg3vd8zr "Sunroom ceiling finish scope"]
    - duration: 17h ÷ (3 crew × 8h) = 0.71 → **1wd**
    - basis: tie-in flash 63LF×0.2=12.6 · house-wall counterflash 3 · vent reuse 2×1.5=3 · eave intake 43LF×0.1=4.3 · no shingles (roof retained) → 23h
    - crew: 3 — card roofing crew 3; small shed roof, flashing/vent work from scaffold
    - quantities: roof_tie_in_lf=63, roof_vent_reuse_count=2, roof_patch_count=0, eave_intake_vent_lf=43, roof_area_sqft=430
    - sizing canon: cn_rates_roofing "Roofing rates" · cn_rates_inspections_crews "Inspections & crew norms"
    - ↪ scope moved to: `roof_reintegration`
    - jbd: agrees — JBD roof 24h split: reseat framing → roof_reintegration; flashing/vents/intake ≈23h here
    - foreman: 23h → 17h — Roof is retained (basis: no shingles) — the 63 LF 'tie-in flash' applies the 0.2 h/LF eave shingle-WEAVE rate to what is an edge re-flash/drip detail under existing shingles over the three new walls; ~0.1 h/LF is the field number for lifting the shingle edge and sliding drip in (6.3h), counterflash 
    - 🚩 roof pitch unknown; tie-in LF is low-confidence
    - 🚩 eave intake vent + 2 roof vents not in material takeoff
    - 🚩 intake rate 0.1 h/LF is judgment — no card rate
- ✅ INCLUDE **Siding (WRB, siding, tie-in blend)** (`siding`) — WRB + ~394 sf vinyl lap on 3 walls, corner trim [cn_policy_elevated_access "Elevated / second-story access premium"]
    - duration: 58h ÷ (2 crew × 8h) = 3.63 → **4wd**
    - basis: WRB 504×0.015=7.6 · vinyl lap 394×0.08=31.5 · J-channel/corners ~100LF×0.1=10 (vinyl faster than 0.15 card) · ×1.2 elevated → 58h
    - crew: 2 — card siding crew 2; 63 LF workface from scaffold on sloped grade
    - quantities: wall_sheathing_sqft=504, siding_sqft_net=394, window_count=6, exterior_door_count=1, stories=elevated second-story structure
    - sizing canon: cn_rates_cladding_finish "Cladding & finish rates" · cn_policy_elevated_access "Elevated / second-story access premium" · cn_policy_rate_card_governs "Rate card governs" · cn_answer_01m2h055eewewa4x5800phewke "Elevated work access and debris removal method"
    - jbd: disagrees — JBD 24h siding+trim is ground-calibrated and light for elevated 394 sf + WRB; card math governs
    - 🚩 trim LF unknown — ~100 LF assumed for corners/surrounds
    - 🚩 wall area provisional until 8 ft bearing height field-verified
    - 🚩 JBD WRB double-count (3h) ignored
- ✅ INCLUDE **Fascia, soffit & gutters** (`fascia_soffit_gutters`) — 430 sf under-floor vinyl soffit from below; no gutters [cn_answer_01m2h05t36bf78eb76f3m7fas3 "Floor soffit vs floor-cavity batt install sequence"]
    - duration: 21h ÷ (2 crew × 8h) = 1.31 → **2wd**
    - basis: no fascia/gutters in proposal · under-floor vinyl soffit 430sf×0.04=17.2 overhead from scaffold · ×1.2 elevated → 21h
    - crew: 2 — same 2-man siding crew, overhead soffit from scaffold below floor
    - quantities: soffit_under_floor_sqft=430, stories=elevated second-story structure
    - sizing canon: cn_answer_01m2h05t36bf78eb76f3m7fas3 "Floor soffit vs floor-cavity batt install sequence" · cn_policy_elevated_access "Elevated / second-story access premium"
    - jbd: agrees — JBD 25h soffit line mapped here; 21h at production speed. No roof fascia/gutter scope
    - 🚩 task carries under-floor vinyl soffit only — no gutters/fascia contracted
    - 🚩 soffit rate 0.04 h/sf is judgment — no card rate
- ✖ EXCLUDE **Extend existing appliance vents through new roof** (`appliance_vent_extension`) — no appliance vents through retained roof

### Fireplace Finish
- ✖ EXCLUDE **Fireplace veneer, hearth & mantel** (`fireplace_finish_work`) — outside scope footprint

## Rough Trades (MEPs)

### Rough MEPs
- ✖ EXCLUDE **Rough plumbing** (`rough_plumbing`) — outside scope footprint
- ✅ INCLUDE **Rough HVAC (line set / duct extension)** (`rough_hvac`) — mini-split line set drop to grade-level condenser pad [cn_answer_01m2h07380zf2f2b6d5mq7087j "Mini-split condenser mounting location"]
    - duration: 6h ÷ (2 crew × 8h) = 0.38 → **1wd**
    - basis: 1 mini-split: line set ~10ft post drop + wall run 2×~2h=4 · wall/soffit penetration + line-hide 2 · condenser pad set at grade 2 → 8h; head set + startup → mep_fixture_install
    - crew: 2 — line set run from scaffold on sloped grade needs a second hand
    - quantities: mini_split_count=1, condenser_location=grade-level pad beneath sunroom, post_height_ft=10
    - sizing canon: cn_answer_01m2h07380zf2f2b6d5mq7087j "Mini-split condenser mounting location" · cn_answer_01m2h055eewewa4x5800phewke "Elevated work access and debris removal method" · cn_policy_mobilization_floor "Mobilization floor"
    - ↪ scope moved to: `mep_fixture_install`
    - jbd: agrees — JBD lumps 10h for rough+finish; ~8h rough here, ~2h head/startup to mep_fixture_install
    - foreman: 8h → 6h — Condenser pad billed three times across tasks: excavation grades it (2h), foundation_prep forms+pours it (2h), then rough_hvac carries 'condenser pad set at grade 2' again while mep_fixture_install already carries the unit set (2h) — drop the duplicate 2h; line set 4 + penetration/line-hide 2 stand 
    - 🚩 BTU/model TBD under $2,500 allowance
    - 🚩 condenser pad presumed poured at groundwork, not here
    - 🚩 elevated access via scaffold, no lift
- ✅ INCLUDE **Rough electrical (circuits, subpanel, boxes)** (`rough_electrical`) — subpanel conversion, ~10 receptacles w/ raceway, lights, fans [cn_answer_01m2v8hr4cnrajcmahesr0yfxn "Brick wall receptacle mounting method" · cn_answer_01m2h06ydaqtcgtwsd52f71taw "Fused disconnect suitability verification"]
    - duration: 30h ÷ (2 crew × 8h) = 1.88 → **2wd**
    - basis: disconnect→breaker subpanel conversion 4 · boxes 10 recept+6 lights+2 fans+~4 switches=22 → 3.5h @~6/hr · circuits/homeruns 8 (incl mini-split ckt) · brick-wall raceway 43LF×0.2=9 · assess/coord 4 → ~29 → 30h
    - crew: 2 — ~6 boxes/hr pace and raceway anchoring assume a 2-man crew
    - quantities: receptacle_count=10, brick_wall_raceway_lf=43, subpanel_conversion=1, light_fixture_count=6, ceiling_fan_count=2, mini_split_count=1, existing_service_amps=200
    - sizing canon: cn_answer_01m2v8hr4cnrajcmahesr0yfxn "Brick wall receptacle mounting method" · cn_answer_01m2h06ydaqtcgtwsd52f71taw "Fused disconnect suitability verification" · cn_answer_01m242n6gdhw5e8383q8cdjdjh "Existing main electrical service ampacity" · cn_policy_rate_card_governs "Rate card governs"
    - ↪ scope moved to: `mep_fixture_install`, `bundled_rough_inspections`
    - jbd: agrees — JBD 30h rough incl subpanel; matches quantity math once 43 LF raceway is added
    - 🚩 subpanel conversion contingent on electrician assessment not yet done — replacement panel would be an add
    - 🚩 receptacle count 10 carried as room total, brick-wall share in raceway
    - 🚩 permit not yet applied; electrical rough inspection billed on bundled_rough_inspections

## Rough Inspections

### Bundled Inspections
- ✅ INCLUDE **Rough inspections (MEPs then framing, bundled)** (`bundled_rough_inspections`) — electrical + mechanical rough, then framing
    - duration: 6h ÷ (1 crew × 8h) = 0.75 → **1wd**
    - basis: rough visits bundled: electrical rough 2h + mechanical rough 2h + framing 2h = 3×2h card → 6h (no plumbing; footing/insulation/final visits live outside this component)
    - crew: 1 — one lead walks inspector; fixed crew of 1
    - quantities: plumbing_scope=none, permit_ahj=City of Kingsport (confirm at application), permit_status=not yet applied
    - sizing canon: cn_rates_inspections_crews "Inspections & crew norms" · cn_answer_01m2h05g2rkknn9h4zpxfwm31y "Building permit application status" · cn_answer_01m2v8hrn6k4zsjdjkpk9wk6cc "Permitting AHJ for 333 Toy Crawford Road"
    - 🚩 Inherited gap: permit not yet applied, AHJ defaulted to Kingsport — visit scheduling may slip; hint of 2 wd for scheduling reality is duration, not hours
    - 🚩 Order strict: MEP rough first, framing last within the bundle; a failed MEP visit re-walks framing
    - 🚩 Footing, insulation and final inspections are not in this component — ensure they carry hours elsewhere
- ✖ EXCLUDE **Fireplace/chimney inspection** (`fireplace_chimney_inspection`) — no fireplace in scope

## Insulation & Drywall

### Insulation, Drywall & Prime
- ✅ INCLUDE **Insulation & air sealing** (`insulation`) — R-13 walls, floor batt, vented rafter-bay ceiling batts [cn_answer_01m2h06f3g9rynf1qtwg3vd8zr "Sunroom ceiling finish scope" · cn_01m2gwxjenvqkzjam46b1bc14r "Demolished ceiling assemblies require an explicit ceiling rebuild scope before insulation and drywall tasks are generated"]
    - duration: 22h ÷ (2 crew × 8h) = 1.38 → **2wd**
    - basis: wall batts R-13 504sf×0.012=6 · ceiling baffles 33 bays×0.15=5 · ceiling batts overhead 430sf×0.02=8.6 · air seal/foam 2 → 22h (floor batt on framing)
    - crew: 2 — overhead sloped-ceiling batt + baffles needs a second set of hands; 430 sf room
    - quantities: wall_insulation_sqft=504, ceiling_insulation_sqft=430, ceiling_finish=vented rafter-bay, floor_insulation_sqft=430
    - sizing canon: cn_answer_01m2h06f3g9rynf1qtwg3vd8zr "Sunroom ceiling finish scope" · cn_answer_01m2h05t36bf78eb76f3m7fas3 "Floor soffit vs floor-cavity batt install sequence" · cn_policy_rate_card_governs "Rate card governs"
    - ↪ scope moved to: `framing`
    - jbd: disagrees — JBD 7h is walls-only; settled vented ceiling (baffles+batt, overhead) adds ~14h priced nowhere in JBD
    - 🚩 No card rate for insulation — judgment rates
    - 🚩 Wall 504 sf provisional on 8 ft plate height
    - 🚩 Floor batt 430 sf excluded — carried in framing floor system per PM answer
- ✅ INCLUDE **Insulation inspection** (`insulation_inspection`) — insulation inspection incl ceiling
    - sizing: none (structure default used)
- ✅ INCLUDE **Drywall (hang, tape, sand)** (`drywall`) — Level 3 on 3 framed walls + ceiling; brick exposed [cn_answer_01m2h06f3g9rynf1qtwg3vd8zr "Sunroom ceiling finish scope" · cn_answer_01m2h06rhtkfd9r0jcakqcvsnv "Brick wall drywall treatment"]
    - duration: 48h ÷ (2 crew × 8h) = 3 → **3wd**
    - basis: hang walls 16sh×0.5=8 · hang sloped ceiling overhead 14sh×0.8=11 · tape/3 coats/sand L3 934sf×0.03=28 · bead/cleanup 1 → 48h (JBD 65h hot)
    - crew: 2 — 430 sf room, 30 sheets; 2-man hang/finish crew fits the workface
    - quantities: drywall_sqft=504, ceiling_drywall_sqft=430, drywall_sheets_total=30
    - sizing canon: cn_answer_01m2h06rhtkfd9r0jcakqcvsnv "Brick wall drywall treatment" · cn_answer_01m2h06f3g9rynf1qtwg3vd8zr "Sunroom ceiling finish scope" · cn_job_breakdown_usage_for_analysis "Job Breakdown Usage for analysis"
    - jbd: disagrees — JBD 65h/848 sf mis-shaped (344 sf brick out, 430 sf ceiling in); finish hours 20-40% over production — 48h governs
    - 🚩 Inherited: JBD drywall scope mis-shaped and hot
    - 🚩 No prime in base scope — component prime step empty
    - 🚩 Wall area provisional on 8 ft plate height
    - 🚩 Duration ~3 wd at crew 2 sits at guardrail floor; coat dry time not in hours
- ✖ EXCLUDE **Paint phase 1 (prime + wall prep + ceilings)** (`paint_phase_1`) — outside scope footprint — paint/prime unselected Option 2 [cn_answer_01m2h04gwya5z01r8ksa4m72n3 "Scope of signed proposal vs presentation extras"]

## Interior Finishes

### Interior Installs
- ✖ EXCLUDE **Shower work (waterproofing, tile, grout)** (`shower_work`) — outside scope footprint
- ✖ EXCLUDE **Hard flooring install (LVP, hardwood, tile floors)** (`hard_flooring`) — outside scope footprint — LVP unselected Option 2 [cn_answer_01m2h04gwya5z01r8ksa4m72n3 "Scope of signed proposal vs presentation extras"]
- ✖ EXCLUDE **Cabinets, counters, vanities & fixed items** (`cabinets_counters`) — outside scope footprint
- ✖ EXCLUDE **Carpet & floating floors** (`carpet_floating`) — outside scope footprint
- ✖ EXCLUDE **Enclosure finishes (screening, panel infill, interior cladding)** (`enclosure_finishes`) — conditioned drywalled room, no screening or cladding

### Final Trades & Paint 2
- ✅ INCLUDE **Final Trades (fixture install for HVAC, Plumbing, and Electrical)** (`mep_fixture_install`) — lights, fans, devices, mini-split head/condenser set
    - duration: 24h ÷ (3 crew × 8h) = 1 → **1wd**
    - basis: elec trim: recept 10×0.4=4 · lights 6×0.75=4.5 · fans 2×1.5=3 · switches 3×0.4=1.2 · subpanel cover/labels 1 · HVAC: head 2 + condenser set 2 + line set/vac/charge/test 4 + whip 1 · plumbing 0 → ~24h
    - crew: 3 — 1 electrician + 2-man HVAC (head inside, condenser/line set at grade on scaffold); 2 interior trades max
    - quantities: receptacle_count=10, light_fixture_count=6, ceiling_fan_count=2, mini_split_count=1, condenser_location=grade-level pad beneath sunroom, brick_wall_raceway_lf=43, plumbing_scope=none, subpanel_conversion=1
    - sizing canon: cn_company_interior_concurrency "Interior trade concurrency" · cn_policy_mobilization_floor "Mobilization floor" · cn_answer_01m2h07380zf2f2b6d5mq7087j "Mini-split condenser mounting location" · cn_answer_01m2v8hr4cnrajcmahesr0yfxn "Brick wall receptacle mounting method" · cn_answer_01m2h06ydaqtcgtwsd52f71taw "Fused disconnect suitability verification"
    - 🚩 no plumbing in scope — task covers electrical trim + mini-split final only
    - 🚩 subpanel conversion suitability unverified; a replacement panel would add hours here and at rough-in
    - 🚩 fan locations not shown on any drawing
    - 🚩 condenser pad set assumed done at groundwork; only unit set/hookup carried here
- ✖ EXCLUDE **Finish Carpentry** (`finish_carpentry`) — outside scope footprint — trim/casing unselected Option 2 [cn_answer_01m2h04gwya5z01r8ksa4m72n3 "Scope of signed proposal vs presentation extras"]
- ✖ EXCLUDE **Stairs (build/finish)** (`stair_build`) — outside scope footprint — presentation stairs not adopted [cn_answer_01m2h04gwya5z01r8ksa4m72n3 "Scope of signed proposal vs presentation extras"]
- ✖ EXCLUDE **Paint phase 2 (final coats)** (`paint_phase_2`) — outside scope footprint — paint unselected Option 2 [cn_answer_01m2h04gwya5z01r8ksa4m72n3 "Scope of signed proposal vs presentation extras"]

## Concrete & Landscaping

### Concrete & Landscape
- ✖ EXCLUDE **Concrete flatwork (patios, driveways, walkways)** (`concrete_flatwork`) — outside scope footprint — no patio; pad rides foundation
- ✖ EXCLUDE **Landscaping & site restoration** (`landscaping`) — outside scope footprint — no seed/straw

## Closeout

### Walkthrough & Final Inspection
- ✅ INCLUDE **Customer walkthrough & punch list** (`customer_walkthrough`) — always — punch list at substantial completion
    - sizing: none (structure default used)
- ✅ INCLUDE **Final inspections (building + E/P/M, bundled)** (`final_inspections`) — final building + electrical + mechanical
    - sizing: none (structure default used)

## CANON GAPS — decisions made with no canon behind them

These are honest "judged from scope/understanding alone" calls. Each one is a place where a canon entry (a policy, a default, a reference) would make the next generation more grounded — the owners' ask-list.

- **Procurement**:
    - `proc_trusses` exclude — existing shed roof retained; no trusses
    - `proc_water_heater` exclude — no water heater in scope
    - `proc_plumbing_package` exclude — outside scope footprint
    - `proc_tile` exclude — no tile in scope
    - `proc_carpet` exclude — outside scope footprint
    - `proc_cabinets` exclude — no cabinetry in scope
    - `proc_countertops` exclude — no countertops in scope
    - `proc_shower_glass` exclude — no shower in scope
    - `proc_plumbing_fixtures` exclude — outside scope footprint
    - `proc_light_fixtures` include — 6 lights + 2 fans, allowance items — pickup
    - `proc_concrete_patio` exclude — covered by proc_foundation_package; no flatwork
    - `proc_fireplace_kit` exclude — outside scope footprint
- **Permits**:
    - `permit_tdec_septic` exclude — no septic work
    - `permit_plumbing` exclude — outside scope footprint
    - `permit_mechanical` include — mini-split install; rides building permit application
- **Retrofit (pre-addition work)**:
    - `utility_relocations` exclude — disconnect survives demo untouched; no relocations
    - `retrofit_demo` exclude — no pre-addition interior work
    - `retrofit_rough_meps` exclude — no pre-addition work
    - `retrofit_drywall` exclude — no pre-addition work
    - `retrofit_finishes` exclude — no pre-addition work
- **Site Prep & Foundation**:
    - `foundation_inspection` include — footing inspection before hand-mix pour
- **Framing & Shell**:
    - `fireplace_chase_install` exclude — outside scope footprint
- **Exterior Finishes**:
    - `appliance_vent_extension` exclude — no appliance vents through retained roof
    - `fireplace_finish_work` exclude — outside scope footprint
- **Rough Trades (MEPs)**:
    - `rough_plumbing` exclude — outside scope footprint
- **Rough Inspections**:
    - `bundled_rough_inspections` include — electrical + mechanical rough, then framing
    - `fireplace_chimney_inspection` exclude — no fireplace in scope
- **Insulation & Drywall**:
    - `insulation_inspection` include — insulation inspection incl ceiling
- **Interior Finishes**:
    - `shower_work` exclude — outside scope footprint
    - `cabinets_counters` exclude — outside scope footprint
    - `carpet_floating` exclude — outside scope footprint
    - `enclosure_finishes` exclude — conditioned drywalled room, no screening or cladding
    - `mep_fixture_install` include — lights, fans, devices, mini-split head/condenser set
- **Concrete & Landscaping**:
    - `concrete_flatwork` exclude — outside scope footprint — no patio; pad rides foundation
    - `landscaping` exclude — outside scope footprint — no seed/straw
- **Closeout**:
    - `customer_walkthrough` include — always — punch list at substantial completion
    - `final_inspections` include — final building + electrical + mechanical

## Canon entries that worked this run

- `cn_answer_01m2h04gwya5z01r8ksa4m72n3` — Scope of signed proposal vs presentation extras [job] · cited 10×
- `cn_policy_elevated_access` — Elevated / second-story access premium [company/project] · cited 10×
- `cn_answer_01m2h06f3g9rynf1qtwg3vd8zr` — Sunroom ceiling finish scope [job] · cited 9×
- `cn_policy_rate_card_governs` — Rate card governs [company/project] · cited 6×
- `cn_answer_01m2h06ydaqtcgtwsd52f71taw` — Fused disconnect suitability verification [job] · cited 5×
- `cn_answer_01m2h07380zf2f2b6d5mq7087j` — Mini-split condenser mounting location [job] · cited 5×
- `cn_answer_01m2v8hr4cnrajcmahesr0yfxn` — Brick wall receptacle mounting method [job] · cited 5×
- `cn_answer_01m2h05t36bf78eb76f3m7fas3` — Floor soffit vs floor-cavity batt install sequence [job] · cited 5×
- `cn_answer_01m2h055eewewa4x5800phewke` — Elevated work access and debris removal method [job] · cited 5×
- `cn_answer_01m2h07a109r3bkg5a08t2fpmp` — Post/footer count for deck installation [job] · cited 4×
- `cn_answer_01m2h05z9rcpxmbbhdre94zax0` — Window and exterior door sizing [job] · cited 4×
- `cn_answer_01m242n6gdhw5e8383q8cdjdjh` — Existing main electrical service ampacity [property] · cited 4×
- `cn_answer_01m2h06rhtkfd9r0jcakqcvsnv` — Brick wall drywall treatment [job] · cited 4×
- `cn_answer_01m2h04ypdna2xyz4epatkc24q` — Temporary shoring design authority [job] · cited 4×
- `cn_rates_inspections_crews` — Inspections & crew norms [company/project] · cited 4×
- `cn_answer_01m2h07n7p3c346ya4jcq01stt` — Window and door header material [job] · cited 3×
- `cn_company_no_demo_without_materials` — No demo without materials [company/project] · cited 3×
- `cn_answer_01m2h04q3316zv1j8g1hk0hwe6` — existing shed-roof bearing height [job] · cited 3×
- `cn_policy_mobilization_floor` — Mobilization floor [company/project] · cited 3×
- `cn_answer_01m2h05g2rkknn9h4zpxfwm31y` — Building permit application status [job] · cited 2×
- `cn_answer_01m2v8hrn6k4zsjdjkpk9wk6cc` — Permitting AHJ for 333 Toy Crawford Road [property] · cited 2×
- `cn_rates_demo_site` — Demo & site rates [company/project] · cited 2×
- `cn_answer_01m2h06kyz1cqvxetrtfth59py` — Footer pocket excavation method at existing pad [job] · cited 2×
- `cn_rates_excavation_concrete` — Excavation & concrete rates [company/project] · cited 2×
- `cn_company_never_split_framing` — Never split framing [company/project] · cited 2×
- `cn_rates_cladding_finish` — Cladding & finish rates [company/project] · cited 2×
- `cn_rates_framing` — Framing rates [company/project] · cited 1×
- `cn_rates_roofing` — Roofing rates [company/project] · cited 1×
- `cn_01m2gwxjenvqkzjam46b1bc14r` — Demolished ceiling assemblies require an explicit ceiling rebuild scope before insulation and drywall tasks are generated [company/project] · cited 1×
- `cn_job_breakdown_usage_for_analysis` — Job Breakdown Usage for analysis [company/project] · cited 1×
- `cn_company_interior_concurrency` — Interior trade concurrency [company/project] · cited 1×

## Warnings & findings

- Coverage: 1 PM-SETTLED quantity was consumed by NO task (window_door_lead_time_weeks=2weeks) — a human ruled on these numbers; verify each either feeds a derived quantity (dimension inputs do) or check which document value the sizing rode instead.
- Coverage: JBD section "electrical" pays into component "interior_installs" but no included task carries it — paid-for scope with zero tasks.
- Coverage: JBD section "hvac" pays into component "interior_installs" but no included task carries it — paid-for scope with zero tasks.
- Foreman check: "roofing" 23h → 17h — Roof is retained (basis: no shingles) — the 63 LF 'tie-in flash' applies the 0.2 h/LF eave shingle-WEAVE rate to what is an edge re-flash/drip detail under existing shingles over the three new walls; ~0.1 h/LF is the field number for lifting the shingle edge and sliding drip in (6.3h), counterflash 
- Foreman check: "rough_hvac" 8h → 6h — Condenser pad billed three times across tasks: excavation grades it (2h), foundation_prep forms+pours it (2h), then rough_hvac carries 'condenser pad set at grade 2' again while mep_fixture_install already carries the unit set (2h) — drop the duplicate 2h; line set 4 + penetration/line-hide 2 stand 

## Assumptions

- "Foundation Inspection" (foundation_inspection) is included but its structure row is UNVETTED — confirm with Will.
- "Foundation Pour" (foundation_pour) is included but its structure row is UNVETTED — confirm with Will.
