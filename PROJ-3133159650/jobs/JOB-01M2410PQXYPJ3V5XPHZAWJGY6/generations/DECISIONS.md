# DECISIONS — Addition · JOB-01M2410PQXYPJ3V5XPHZAWJGY6

generation `01M6FG2PMJ5DSSE67Q36BW0M03` · structure v15 · trunk 2e3c1450
effort: include=medium · sizing=medium · foreman=default
timings: Resolving the Addition checklist (structure v15) 5s · Resolving inclusion against scope + answers 57s · Sizing 9 components against the evidence 47s · Foreman review — challenging the estimate 12s · Assembling the task graph 0s · TOTAL 121s

## Summary

- verdicts: 32 included · 40 excluded · 0 needs-info · 0 extra task(s)
- canon: 25/72 decisions cited canon (47 judged without — see CANON GAPS)
- validator: clean on the first pass

## Procurement

### Procurement Items
- ✅ INCLUDE **Foundation** (`proc_foundation_package`) — Footer bag concrete, post brackets, pad mix — pickup [cn_answer_01m2h07a109r3bkg5a08t2fpmp "Post/footer count for deck installation" · cn_answer_01m2h07380zf2f2b6d5mq7087j "Mini-split condenser mounting location"]
    - 🚚 pickup: 1 cal day (dedicated trip) — Stock bag concrete (16×80lb), 8 post brackets, anchors, form/brace scrap lumber — local supply yard/big-box; no truck, no pump, no block
- ✅ INCLUDE **Windows & exterior doors** (`proc_windows_doors`) — 6 stock 36x60 DH + stock 3068 door, 1-2 wk lead [cn_answer_01m2h05z9rcpxmbbhdre94zax0 "Window and exterior door sizing"]
    - delivery: 14 cal days — 6 stock 36x60 DH + 1 stock 3068; settled 1-2 wk lead, upper bound carried
- ✖ EXCLUDE **LVL / engineered beams** (`proc_lvl`) — Built-up 2x headers and 3-ply 2x12 beam; no LVL [cn_answer_01m2h07n7p3c346ya4jcq01stt "Window and door header material"]
- ✅ INCLUDE **Framing Package** (`proc_framing_package`) — PT posts, beam, joists, walls, OSB delivery, ~10 day lead
    - delivery: 10 cal days — 8 6x6 PT posts, 132LF 2x12 beam stock, 34 joists, walls/rafters, 15 subfloor + ~16-18 OSB; yard stock, order early
- ✖ EXCLUDE **Roof trusses (custom)** (`proc_trusses`) — Existing shed roof retained and reseated; no trusses
- ✅ INCLUDE **Subpanel / service equipment** (`proc_subpanel`) — Disconnect-to-subpanel kit, ~5 day lead after electrician assessment [cn_answer_01m2h06ydaqtcgtwsd52f71taw "Fused disconnect suitability verification" · cn_answer_01m242n6gdhw5e8383q8cdjdjh "Existing main electrical service ampacity"]
    - delivery: 5 cal days — Conversion kit + breakers, stock at supply house; gated on electrician assessment of fused disconnect first
- ✅ INCLUDE **HVAC equipment (mini-split / system)** (`proc_hvac_equipment`) — Ductless mini-split, ~1 wk lead after BTU sizing
    - delivery: 7 cal days — Single common ductless mini-split (~$2,500 allowance) + line set; distributor stock ~1 wk once BTU set
- ✅ INCLUDE **Electrical Package** (`proc_electrical_package`) — Rough wire, boxes, raceway delivery, ~5 day lead [cn_answer_01m2v8hr4cnrajcmahesr0yfxn "Brick wall receptacle mounting method"]
    - delivery: 3 cal days — Wire, boxes, ~10 receptacles (2 GFCI), 43LF Wiremold raceway + surface boxes; supply house stock
- ✖ EXCLUDE **Water heater (tank or tankless)** (`proc_water_heater`) — outside scope footprint
- ✖ EXCLUDE **Plumbing Package** (`proc_plumbing_package`) — outside scope footprint
- ✖ EXCLUDE **Tile & setting materials** (`proc_tile`) — outside scope footprint
- ✖ EXCLUDE **Hard flooring** (`proc_hard_flooring`) — outside scope footprint
- ✖ EXCLUDE **Carpet / floating floor** (`proc_carpet`) — outside scope footprint
- ✅ INCLUDE **Insulation** (`proc_insulation`) — Wall, floor, ceiling batts plus baffles — pickup [cn_answer_01m2h06f3g9rynf1qtwg3vd8zr "Sunroom ceiling finish scope"]
    - delivery: 3 cal days — Batts for 430sf floor + 504sf walls + 430sf ceiling, plus rafter-bay baffles; stock, supplier drop
- ✅ INCLUDE **Drywall** (`proc_drywall`) — ~30 sheets walls + ceiling, ~5 day delivery [cn_answer_01m2h06f3g9rynf1qtwg3vd8zr "Sunroom ceiling finish scope" · cn_answer_01m2h06rhtkfd9r0jcakqcvsnv "Brick wall drywall treatment"]
    - delivery: 5 cal days — ~30 sheets (504sf walls + 430sf ceiling) + mud/tape/beads; stock board, boom/hand delivery to elevated room
- ✖ EXCLUDE **Cabinets / vanities** (`proc_cabinets`) — outside scope footprint
- ✖ EXCLUDE **Countertops** (`proc_countertops`) — outside scope footprint
- ✖ EXCLUDE **Paint + Primer** (`proc_paint`) — outside scope footprint
- ✖ EXCLUDE **Shower glass (template after tile)** (`proc_shower_glass`) — outside scope footprint
- ✖ EXCLUDE **Interior doors & trim package** (`proc_doors_trim`) — outside scope footprint
- ✖ EXCLUDE **Plumbing fixtures (faucets, sinks, commodes, shower trim)** (`proc_plumbing_fixtures`) — outside scope footprint
- ✅ INCLUDE **Light fixtures & devices** (`proc_light_fixtures`) — 6 lights, 2 fans customer-selected, ~1 wk lead
    - delivery: 7 cal days — 6 fixtures @ $75 + 2 fans @ $150 allowance — stock-grade; ~1 wk once customer selects
- ✖ EXCLUDE **Concrete + Patio Work** (`proc_concrete_patio`) — covered by proc_foundation_package; no patio
- ✖ EXCLUDE **Fireplace kit (firebox + Class A chimney)** (`proc_fireplace_kit`) — outside scope footprint

## Permits

### Permit Items
- ✅ INCLUDE **Building permit** (`permit_building`) — Building permit contracted, not yet applied [cn_answer_01m2h05g2rkknn9h4zpxfwm31y "Building permit application status" · cn_answer_01m2v8hrn6k4zsjdjkpk9wk6cc "Permitting AHJ for 333 Toy Crawford Road"]
- ✖ EXCLUDE **TDEC septic permit** (`permit_tdec_septic`) — No septic work in scope
- ✖ EXCLUDE **Electrical service / meter permit** (`permit_electrical_service`) — Subpanel only on existing 200A service; rides building permit [cn_answer_01m242n6gdhw5e8383q8cdjdjh "Existing main electrical service ampacity"]
- ✖ EXCLUDE **Plumbing Permit** (`permit_plumbing`) — outside scope footprint
- ✅ INCLUDE **Mechanical Permit** (`permit_mechanical`) — Ductless mini-split HVAC in scope

## Retrofit (pre-addition work)

### Retrofit Work
- ✖ EXCLUDE **Utility & equipment relocations (heat pump, disconnect, lines)** (`utility_relocations`) — Disconnect converted in place under rough electrical
- ✖ EXCLUDE **Retrofit demolition (interior areas outside the addition)** (`retrofit_demo`) — No pre-addition interior work on existing home
- ✖ EXCLUDE **Retrofit rough MEPs** (`retrofit_rough_meps`) — No pre-addition MEP work
- ✖ EXCLUDE **Retrofit drywall & patching** (`retrofit_drywall`) — No pre-addition walls opened
- ✖ EXCLUDE **Retrofit finishes (paint, tile, flooring, fixtures)** (`retrofit_finishes`) — No pre-addition finish work

## Demolition

### Main Demolition
- ✅ INCLUDE **Demolition (site + structure at addition footprint)** (`site_and_structure_demo`) — Full 430 sf room demo under shored roof [cn_answer_01m2h04ypdna2xyz4epatkc24q "Temporary shoring design authority" · cn_answer_01m2h055eewewa4x5800phewke "Elevated work access and debris removal method"]
    - duration: 59h ÷ (3 crew × 8h) = 2.46 → **3wd**
    - basis: shoring erect 43LF=12 · ceiling 430sf=6 · walls 63LF+7 openings=10 · subfloor+34 joists+ledger=12 · old posts=5 · load 3 dump runs=6 → 39×1.2 elev=47 · +12 shoring → 59h
    - crew: 3 — Card demo crew 3; shoring plus hand-lowering debris from scaffold needs 3
    - quantities: demo_area_sqft=430, temp_shoring_span_lf=43, wall_lf_new=63, floor_joist_count=34, dump_runs=3, window_count=6, exterior_door_count=1, stories=elevated second-story structure
    - sizing canon: cn_policy_elevated_access "Elevated / second-story access premium" · cn_answer_01m2h04ypdna2xyz4epatkc24q "Temporary shoring design authority" · cn_answer_01m2h055eewewa4x5800phewke "Elevated work access and debris removal method" · cn_rates_inspections_crews "Inspections & crew norms" · cn_company_no_demo_without_materials "No demo without materials"
    - ↪ scope moved to: `site_prep`, `roof_reintegration`, `excavation`
    - jbd: agrees — JBD demo 48h + ~14h shoring-erect share of GC 36h (PM 8h, protection, strike excluded) ≈ 62h vs 59h
    - 🚩 Old post count not stated; assumed ~6-8 existing posts at ~0.6-0.75h each
    - 🚩 Shoring erect billed here; strike carried in roof_reintegration
    - 🚩 Saw-cut footer pockets (count unknown) left to groundwork tasks, not demo
    - 🚩 Canon: next-phase materials must be on site before demo starts

## Site Prep & Foundation

### Groundwork
- ✅ INCLUDE **Site prep (protection, staging, access)** (`site_prep`) — Scaffold on sloped grade, protection below work [cn_answer_01m2h055eewewa4x5800phewke "Elevated work access and debris removal method" · cn_policy_elevated_access "Elevated / second-story access premium"]
    - duration: 17h ÷ (2 crew × 8h) = 1.06 → **2wd**
    - basis: protection below/condenser 2 (card, once) · staging+dumpster+access+layout 5 · scaffold erect 6 + strike 4 on sloped grade (canon: once, on site prep) → 17h
    - crew: 2 — Two hands to stand and strike scaffold safely on sloped grade
    - quantities: site_access_constraints=scaffold from sloped grade, hand-lowered debris, footprint_sqft=430, occupied_home=yes
    - sizing canon: cn_policy_elevated_access "Elevated / second-story access premium" · cn_rates_demo_site "Demo & site rates" · cn_answer_01m2h055eewewa4x5800phewke "Elevated work access and debris removal method"
    - 🚩 Scaffold strike is billed here but happens at job end, after soffit, siding and tie-in.
    - 🚩 Shoring is excluded here; it belongs to demo/roof_reintegration.
- ✅ INCLUDE **Excavation (footings, slab, access)** (`excavation`) — 8 hand-dug footer pockets, some saw-cut through pad [cn_answer_01m2h06kyz1cqvxetrtfth59py "Footer pocket excavation method at existing pad" · cn_answer_01m2h07a109r3bkg5a08t2fpmp "Post/footer count for deck installation"]
    - duration: 15h ÷ (2 crew × 8h) = 0.94 → **1wd**
    - basis: hand-dig pockets 8×1h=8 (no machine; card 0.25h n/a) · saw-cut+break pad ASSUMED 4×1.5=6 · condenser pad grade 1 → 15h
    - crew: 2 — Laborer pair: saw/break plus hand dig; no operator because there is no machine
    - quantities: post_count=8, footer_excavation_method=hand-dug, footer_excavation_note=saw-cut at some pockets, saw_cut_pocket_count=UNKNOWN (assumed 4), condenser_location=grade-level pad
    - sizing canon: cn_rates_demo_site "Demo & site rates" · cn_rates_excavation_concrete "Excavation & concrete rates" · cn_answer_01m2h06kyz1cqvxetrtfth59py "Footer pocket excavation method at existing pad" · cn_answer_01m2h07a109r3bkg5a08t2fpmp "Post/footer count for deck installation"
    - jbd: agrees — JBD 44h: ~20h post set + beam to framing, ~24h groundwork. Excavation 15 + foundation 14 = 29, near the 24h share.
    - 🚩 Saw-cut count is assumed at 4 of 8; range 1-8 swings ±4.5h.
    - 🚩 Rock hit becomes a change order, not padding.
    - 🚩 The JBD prices no saw. Add saw rental.
- ✅ INCLUDE **Prepare Foundation** (`foundation_prep`) — Prep 8 footer pockets and condenser pad [cn_answer_01m2h07a109r3bkg5a08t2fpmp "Post/footer count for deck installation"]
    - duration: 14h ÷ (2 crew × 8h) = 0.88 → **1wd**
    - basis: mixer setup/cleanup 2 · hand-mix+place 0.3cy (16 bags) 8×0.75=6 · brackets 8×0.25=2 · condenser pad gravel+set 2 · footing inspect 2 → 14h
    - crew: 2 — One mixes, one places and sets brackets; tiny bag-mix pour
    - quantities: footer_concrete_cy=0.3, post_count=8, foundation_type=8 discrete 12x12x12 footers w/ brackets, condenser_location=grade-level pad
    - sizing canon: cn_rates_excavation_concrete "Excavation & concrete rates" · cn_rates_inspections_crews "Inspections & crew norms" · cn_policy_mobilization_floor "Mobilization floor"
    - jbd: agrees — Shares the 44h JBD section with excavation (29h combined vs ~24h). Post set + beam stay on framing.
    - 🚩 The footing inspection visit is carried here because the bundled rough task covers only MEP/framing. Drop it here if that task absorbs it.
    - 🚩 The permit is not yet applied for, which gates the footing inspection.
- ✅ INCLUDE **Foundation Inspection** (`foundation_inspection`) — Footing inspection required for new footers
    - sizing: none (structure default used)
- ✅ INCLUDE **Foundation Pour** (`foundation_pour`) — Pour 8 12x12x12 footers [cn_answer_01m2h07a109r3bkg5a08t2fpmp "Post/footer count for deck installation"]
    - sizing: none (structure default used)

## Framing & Shell

### Structural Framing
- ✅ INCLUDE **Framing (floor, walls, roof structure, sheathing)** (`framing`) — Posts, beam, PT floor, 63 LF walls, in-house [cn_company_never_split_framing "Never split framing"]
    - duration: 101h ÷ (3 crew × 8h) = 4.21 → **5wd**
    - basis: posts 8×0.75=6 · beam 44LF 2seg×7=14 · ledger/rim 106LF=8 · joists 34×0.4=14 · subfloor 15×0.4=6 · walls 63LF×0.3=19 · hdrs 7×1=7 · sheath 16×0.4=6 → 80×1.2 elev=96 · floor batt 5 → 101h
    - crew: 3 — Card framing crew 3; beam lift and joist work from scaffold need 3 hands
    - quantities: post_count=8, beam_lf=44, floor_joist_count=34, subfloor_sheets=15, wall_lf_new=63, wall_sheathing_sqft=504, floor_insulation_sqft=430, window_count=6, exterior_door_count=1, plate_height_ft=8
    - sizing canon: cn_rates_framing "Framing rates" · cn_policy_elevated_access "Elevated / second-story access premium" · cn_policy_rate_card_governs "Rate card governs" · cn_company_never_split_framing "Never split framing" · cn_answer_01m2h05t36bf78eb76f3m7fas3 "Floor soffit vs floor-cavity batt install sequence" · cn_answer_01m2h07a109r3bkg5a08t2fpmp "Post/footer count for deck installation"
    - ↪ scope moved to: `siding`
    - jbd: disagrees — JBD ~120h (floor 62 + walls 45 + post/beam ~20, less WRB); flagged hot, quantity math governs
    - 🚩 WRB moved to siding (its task owns WRB); JBD double-counts WRB
    - 🚩 Floor batt kept here: must go in from above before subfloor closes; insulation task must not re-carry it
    - 🚩 No roof framing: existing shed roof preserved; reseat lives on roof_reintegration
    - 🚩 Wall/sheathing areas provisional on unverified ~8 ft plate height
    - 🚩 Elevated +20% applied to framing lines only, not floor batt
- ✅ INCLUDE **Roof reintegration (reseat preserved roof, bearing transfer, strike shoring)** (`roof_reintegration`) — Retained shed roof reseated on new walls, strike shoring [cn_answer_01m2h04q3316zv1j8g1hk0hwe6 "existing shed-roof bearing height" · cn_answer_01m2h04ypdna2xyz4epatkc24q "Temporary shoring design authority"]
    - duration: 32h ÷ (3 crew × 8h) = 1.33 → **2wd**
    - basis: shim/plane bearing 43LF×0.2=9 · rafter ties ~34×0.25=8.5 · transfer+fasten verify 3 · strike/remove shores 6 → 26.5×1.2 elev=32h
    - crew: 3 — Transfer bearing and strike shores along 43 LF needs 3 for safe sequencing
    - quantities: temp_shoring_span_lf=43, plate_height_ft=8, roof_area_sqft=430
    - sizing canon: cn_answer_01m2h04ypdna2xyz4epatkc24q "Temporary shoring design authority" · cn_answer_01m2h04q3316zv1j8g1hk0hwe6 "existing shed-roof bearing height" · cn_policy_elevated_access "Elevated / second-story access premium"
    - ↪ scope moved to: `roofing`
    - jbd: agrees — Reseat share of JBD 24h roof section + shoring-strike share of 36h general conditions ≈ 30h
    - 🚩 Rafter count inferred at 16in OC; roof framing layout unverified
    - 🚩 Flashing/patches stay on roofing; shoring erection stays with demo
    - 🚩 Add time if actual bearing height differs from ~8 ft assumption
- ✅ INCLUDE **Exterior windows & doors install** (`exterior_windows_doors`) — 6 stock windows + 1 exterior door [cn_answer_01m2h05z9rcpxmbbhdre94zax0 "Window and exterior door sizing"]
    - duration: 19h ÷ (2 crew × 8h) = 1.19 → **2wd**
    - basis: windows 6×2=12 · door 3068 1×4=4 → 16×1.2 elev=19h
    - crew: 2 — Card norm: 2-man crew sets and flashes stock windows from scaffold
    - quantities: window_count=6, exterior_door_count=1
    - sizing canon: cn_answer_01m2h05z9rcpxmbbhdre94zax0 "Window and exterior door sizing" · cn_rates_cladding_finish "Cladding & finish rates" · cn_policy_elevated_access "Elevated / second-story access premium"
    - jbd: agrees
    - 🚩 Stock 36x60 DH + 3068 assumed per answer; special-order would change lead, not hours

### Deck
- ✖ EXCLUDE **Deck build** (`deck_build`) — outside scope footprint [cn_answer_01m2h04gwya5z01r8ksa4m72n3 "Scope of signed proposal vs presentation extras"]

### Fireplace Structure
- ✖ EXCLUDE **Fireplace chase, firebox set & Class A chimney** (`fireplace_chase_install`) — outside scope footprint

## Exterior Finishes

### Cladding & Roof
- ✅ INCLUDE **Roofing (underlayment, shingles, flashing, tie-in blend)** (`roofing`) — Wall-line flashing, 2 vent patches, ceiling vent work [cn_answer_01m2h06f3g9rynf1qtwg3vd8zr "Sunroom ceiling finish scope"]
    - duration: 22h ÷ (3 crew × 8h) = 0.92 → **1wd**
    - basis: tie-in flash 63LF×0.2=12.6 · drip edge 63LF×0.03=1.9 · vent patches 2×2=4 · house-wall counterflash 3 → 22h (JBD 24h also carries reseat)
    - crew: 3 — Card roofing crew of 3; small 430 sf shed roof, scaffold edge work
    - quantities: roof_tie_in_lf=63, roof_patch_count=2, roof_area_sqft=430
    - sizing canon: cn_rates_roofing "Roofing rates" · cn_policy_rate_card_governs "Rate card governs"
    - jbd: disagrees — JBD 24h covers reseat + flashing; reseat goes to roof_reintegration (~10h), leaving ~14h vs my 22h
    - 🚩 roof_tie_in_lf=63 is low-confidence; edge flashing LF may be shorter
    - 🚩 Vented ceiling needs intake/exhaust; 0h priced here for vents — the 2 patches may need to become vents
    - 🚩 roof_pitch unknown
- ✅ INCLUDE **Siding (WRB, siding, tie-in blend)** (`siding`) — WRB + ~394 sf vinyl lap siding, three walls
    - duration: 49h ÷ (2 crew × 8h) = 3.06 → **4wd**
    - basis: siding 394sf×0.08=31.5 · +20% elevated=37.8 · corner boards 16LF×0.15=2.4 → 40h; WRB 504sf moved to framing
    - crew: 2 — Card siding crew of 2; one 43 ft wall plus two 10 ft ends on scaffold
    - quantities: siding_sqft_net=394, wall_sheathing_sqft=504, plate_height_ft=8
    - sizing canon: cn_rates_cladding_finish "Cladding & finish rates" · cn_policy_elevated_access "Elevated / second-story access premium" · cn_policy_rate_card_governs "Rate card governs"
    - ↪ scope moved to: `framing`
    - jbd: disagrees — JBD siding+trim 24h is ground-calibrated; card rate +20% elevated premium gives 40h
    - foreman: 40h → 49h — WRB 504sf says 'moved to framing' but framing's basis has no WRB line, so it is scope lost; restore it here at card 0.015 h/sf × 504sf = 7.6h, plus the 20% elevated premium ≈ 9h (40 → 49).
    - 🚩 Siding area is provisional on the 8 ft plate height
    - 🚩 exterior_trim_lf unknown; assumed 2 outside corners ×8 ft
    - 🚩 WRB billed on framing per JBD mapping; confirm the framing sizer carries the ~8h
- ✅ INCLUDE **Fascia, soffit & gutters** (`fascia_soffit_gutters`) — 430 sf under-floor vinyl soffit; no fascia/gutters [cn_answer_01m2h05t36bf78eb76f3m7fas3 "Floor soffit vs floor-cavity batt install sequence"]
    - duration: 34h ÷ (2 crew × 8h) = 2.13 → **3wd**
    - basis: under-floor soffit 430sf×0.045=19.4 · perimeter channel/rim trim 63LF×0.1=6.3 · +20% elevated=31 · gutter reset 43LF≈3 → 34h
    - crew: 2 — Same 2-man siding crew; overhead soffit work from scaffold on sloped grade
    - quantities: soffit_under_floor_sqft=430, wall_lf_new=63
    - sizing canon: cn_answer_01m2h05t36bf78eb76f3m7fas3 "Floor soffit vs floor-cavity batt install sequence" · cn_answer_01m2h055eewewa4x5800phewke "Elevated work access and debris removal method" · cn_policy_elevated_access "Elevated / second-story access premium" · cn_rates_cladding_finish "Cladding & finish rates"
    - jbd: disagrees — JBD soffit 25h matches my ~23h soffit share; I added perimeter trim + gutter reset that the JBD does not price
    - 🚩 No card rate for soffit; 0.045 h/sf is a judgment rate
    - 🚩 Gutter scope is not in the proposal; 3h reset of the existing low-eave gutter is assumed
    - 🚩 Rim/fascia wrap LF is assumed at the full 63 LF perimeter
- ✖ EXCLUDE **Extend existing appliance vents through new roof** (`appliance_vent_extension`) — Old vent holes patched under roofing, not extended

### Fireplace Finish
- ✖ EXCLUDE **Fireplace veneer, hearth & mantel** (`fireplace_finish_work`) — outside scope footprint

## Rough Trades (MEPs)

### Rough MEPs
- ✖ EXCLUDE **Rough plumbing** (`rough_plumbing`) — outside scope footprint
- ✅ INCLUDE **Rough HVAC (line set / duct extension)** (`rough_hvac`) — Mini-split line set to grade-pad condenser [cn_answer_01m2h07380zf2f2b6d5mq7087j "Mini-split condenser mounting location"]
    - duration: 6h ÷ (2 crew × 8h) = 0.38 → **1wd**
    - basis: head bracket + wall core 1.5 · line set+drain ~25ft down post line w/ line-hide 3 · condenser set on grade pad 1.5 → 6h; head hang+vac/charge+startup ~4h at finish
    - crew: 2 — Elevated line run from scaffold plus grade condenser needs a two-man HVAC crew
    - quantities: mini_split_count=1, condenser_location=grade-level pad beneath sunroom, post_height_ft=10
    - ↪ scope moved to: `mep_fixture_install`
    - jbd: agrees — JBD lumps 10h; split 6h rough here, ~4h head set/startup to mep_fixture_install
    - 🚩 Mini-split BTU TBD; line set length assumes ~25 ft from head down post line to grade pad
    - 🚩 Condenser pad itself is set at groundwork, not billed here
- ✅ INCLUDE **Rough electrical (circuits, subpanel, boxes)** (`rough_electrical`) — Subpanel conversion, circuits, brick-wall surface raceway [cn_answer_01m2v8hr4cnrajcmahesr0yfxn "Brick wall receptacle mounting method" · cn_answer_01m2h06ydaqtcgtwsd52f71taw "Fused disconnect suitability verification"]
    - duration: 30h ÷ (2 crew × 8h) = 1.88 → **2wd**
    - basis: framed boxes+cable 18×0.5=9 · brick raceway 43LF×0.15=6.5 · subpanel conversion 8 · home runs 4ckt×1=4 · mini-split ckt+disconnect 2 → 30h
    - crew: 2 — 2-man electrical crew per the ~6 boxes/hr norm; subpanel work pairs well
    - quantities: receptacle_count=10, light_fixture_count=6, ceiling_fan_count=2, brick_wall_raceway_lf=43, subpanel_conversion=1, existing_service_amps=200, mini_split_count=1
    - sizing canon: cn_answer_01m2v8hr4cnrajcmahesr0yfxn "Brick wall receptacle mounting method" · cn_answer_01m2h06ydaqtcgtwsd52f71taw "Fused disconnect suitability verification" · cn_answer_01m242n6gdhw5e8383q8cdjdjh "Existing main electrical service ampacity"
    - ↪ scope moved to: `mep_fixture_install`
    - jbd: agrees — JBD 40h: 30h rough here incl. unpriced raceway; ~6h device/fixture trim to mep_fixture_install
    - 🚩 Subpanel conversion contingent on electrician assessment of fused disconnect; replacement panel would add hours and lead time
    - 🚩 Receptacle count 10 read as room total; ~4 on brick wall in surface raceway
    - 🚩 No load calc on file for 200A service

## Rough Inspections

### Bundled Inspections
- ✅ INCLUDE **Rough inspections (MEPs then framing, bundled)** (`bundled_rough_inspections`) — Electrical, mechanical, framing rough inspections
    - duration: 6h ÷ (1 crew × 8h) = 0.75 → **1wd**
    - basis: visits: elec rough + mech rough + framing = 3×2h=6 (no plumbing) → 6h
    - crew: 1 — Fixed single-person inspection coordination and walk
    - quantities: plumbing_scope=none, permit_ahj=City of Kingsport (confirm at application)
    - sizing canon: cn_rates_inspections_crews "Inspections & crew norms" · cn_answer_01m2v8hrn6k4zsjdjkpk9wk6cc "Permitting AHJ for 333 Toy Crawford Road" · cn_answer_01m2h05g2rkknn9h4zpxfwm31y "Building permit application status"
    - 🚩 Sequence within the visit: electrical and mechanical rough first, framing last.
    - 🚩 Footing, insulation and final inspections are not in this task; no listed task carries them, so they may be missing from the plan.
    - 🚩 Permit not yet applied (Kingsport AHJ assumed); inspection scheduling depends on permit issue ahead of 2027-03-01.
    - 🚩 Mechanical rough visit assumes the AHJ inspects the mini-split line set; if the AHJ waives it, the bundle drops to 4h.
- ✖ EXCLUDE **Fireplace/chimney inspection** (`fireplace_chimney_inspection`) — outside scope footprint

## Insulation & Drywall

### Insulation, Drywall & Prime
- ✅ INCLUDE **Insulation & air sealing** (`insulation`) — Wall batts + vented rafter-bay ceiling insulation [cn_answer_01m2h06f3g9rynf1qtwg3vd8zr "Sunroom ceiling finish scope" · cn_01m2gwxjenvqkzjam46b1bc14r "Demolished ceiling assemblies require an explicit ceiling rebuild scope before insulation and drywall tasks are generated"]
    - duration: 17h ÷ (2 crew × 8h) = 1.06 → **2wd**
    - basis: wall batt 504sf×0.01=5 · ceiling batt overhead 430sf×0.015=6.5 · baffles 34 bays×0.1=3.5 · air seal/penetrations 2 → 17h (floor batt w/ framing)
    - crew: 2 — overhead sloped ceiling batts and baffles need a second set of hands
    - quantities: wall_insulation_sqft=504, ceiling_insulation_sqft=430, floor_insulation_sqft=430, floor_joist_count=34
    - sizing canon: cn_answer_01m2h06f3g9rynf1qtwg3vd8zr "Sunroom ceiling finish scope" · cn_answer_01m2h05t36bf78eb76f3m7fas3 "Floor soffit vs floor-cavity batt install sequence" · cn_answer_01m2h06rhtkfd9r0jcakqcvsnv "Brick wall drywall treatment"
    - ↪ scope moved to: `framing`
    - jbd: disagrees — JBD 7h covers walls+floor only; floor batt goes to framing; vented ceiling batt+baffles (0h in JBD) added here
    - 🚩 Floor-cavity batt (430sf) is installed from above before subfloor, so it is carried in framing per the PM answer
    - 🚩 Vent intake/exhaust path unspecified; baffles assume a vent path exists (roofing scope gap)
    - 🚩 Wall areas provisional on 8ft plate height
- ✅ INCLUDE **Insulation inspection** (`insulation_inspection`) — Insulation visit follows insulation install
    - sizing: none (structure default used)
- ✅ INCLUDE **Drywall (hang, tape, sand)** (`drywall`) — Level 3 on framed walls + 430 sf ceiling [cn_answer_01m2h06f3g9rynf1qtwg3vd8zr "Sunroom ceiling finish scope" · cn_answer_01m2h06rhtkfd9r0jcakqcvsnv "Brick wall drywall treatment"]
    - duration: 57h ÷ (2 crew × 8h) = 3.56 → **4wd**
    - basis: wall hang 16sh×0.5=8 · ceiling hang sloped overhead 14sh×0.9=13 · tape/mud L3 934sf×0.03=28 · sand 934sf×0.008=7.5 → 57h; prime none (options $0)
    - crew: 2 — 430sf room; 2 hangers handle sheets, and mud dry cycles gate the pace, not hands
    - quantities: drywall_sqft=504, ceiling_drywall_sqft=430, drywall_sheets_total=30
    - sizing canon: cn_answer_01m2h06rhtkfd9r0jcakqcvsnv "Brick wall drywall treatment" · cn_answer_01m2h06f3g9rynf1qtwg3vd8zr "Sunroom ceiling finish scope"
    - jbd: disagrees — JBD 65h for mis-shaped 848sf walls (incl 344sf brick); reshaped 934sf incl ceiling lands at 57h
    - 🚩 Prime step empty: Option 2 interior finish at $0, no paint in base scope
    - 🚩 Coat dry times stretch calendar beyond labor-hour duration
    - 🚩 Wall drywall provisional on unverified 8ft plate height
- ✖ EXCLUDE **Paint phase 1 (prime + wall prep + ceilings)** (`paint_phase_1`) — outside scope footprint

## Interior Finishes

### Interior Installs
- ✖ EXCLUDE **Shower work (waterproofing, tile, grout)** (`shower_work`) — outside scope footprint
- ✖ EXCLUDE **Hard flooring install (LVP, hardwood, tile floors)** (`hard_flooring`) — outside scope footprint
- ✖ EXCLUDE **Cabinets, counters, vanities & fixed items** (`cabinets_counters`) — outside scope footprint
- ✖ EXCLUDE **Carpet & floating floors** (`carpet_floating`) — outside scope footprint
- ✖ EXCLUDE **Enclosure finishes (screening, panel infill, interior cladding)** (`enclosure_finishes`) — Conditioned drywalled room, not screened enclosure

### Final Trades & Paint 2
- ✅ INCLUDE **Final Trades (fixture install for HVAC, Plumbing, and Electrical)** (`mep_fixture_install`) — Lights, fans, devices, mini-split head set
    - duration: 11h ÷ (2 crew × 8h) = 0.69 → **1wd**
    - basis: lights 6×0.4=2.4 · fans 2×0.75=1.5 · recepts+switches ~14×0.15=2.1 · breakers/test 1 · mini-split head set+connect+startup 4 · plumbing 0 → 11h
    - crew: 2 — Electrician + HVAC tech, one per trade; stays within the 2-interior-trade limit
    - quantities: light_fixture_count=6, ceiling_fan_count=2, receptacle_count=10, mini_split_count=1, plumbing_scope=none
    - sizing canon: cn_company_interior_concurrency "Interior trade concurrency" · cn_policy_mobilization_floor "Mobilization floor"
    - jbd: agrees — JBD elec 6h finish + ~4h of HVAC 10h (head/startup; line set/condenser at rough) ≈10h vs 11h
    - 🚩 Switch count is not in evidence; ~4 switches assumed for 6 lights and 2 fans
    - 🚩 Mini-split BTU is TBD; startup assumes a standard single-zone wall head
    - 🚩 Mini-split circuit depends on the unverified subpanel conversion
- ✖ EXCLUDE **Finish Carpentry** (`finish_carpentry`) — outside scope footprint
- ✖ EXCLUDE **Stairs (build/finish)** (`stair_build`) — outside scope footprint [cn_answer_01m2h04gwya5z01r8ksa4m72n3 "Scope of signed proposal vs presentation extras"]
- ✖ EXCLUDE **Paint phase 2 (final coats)** (`paint_phase_2`) — outside scope footprint

## Concrete & Landscaping

### Concrete & Landscape
- ✖ EXCLUDE **Concrete flatwork (patios, driveways, walkways)** (`concrete_flatwork`) — No patio/flatwork; condenser pad rides groundwork
- ✖ EXCLUDE **Landscaping & site restoration** (`landscaping`) — No seed and straw in scope

## Closeout

### Walkthrough & Final Inspection
- ✅ INCLUDE **Customer walkthrough & punch list** (`customer_walkthrough`) — Always — punch list at substantial completion
    - sizing: none (structure default used)
- ✅ INCLUDE **Final inspections (building + E/P/M, bundled)** (`final_inspections`) — Final building + electrical/mechanical inspection
    - sizing: none (structure default used)

## CANON GAPS — decisions made with no canon behind them

These are honest "judged from scope/understanding alone" calls. Each one is a place where a canon entry (a policy, a default, a reference) would make the next generation more grounded — the owners' ask-list.

- **Procurement**:
    - `proc_framing_package` include — PT posts, beam, joists, walls, OSB delivery, ~10 day lead
    - `proc_trusses` exclude — Existing shed roof retained and reseated; no trusses
    - `proc_hvac_equipment` include — Ductless mini-split, ~1 wk lead after BTU sizing
    - `proc_water_heater` exclude — outside scope footprint
    - `proc_plumbing_package` exclude — outside scope footprint
    - `proc_tile` exclude — outside scope footprint
    - `proc_hard_flooring` exclude — outside scope footprint
    - `proc_carpet` exclude — outside scope footprint
    - `proc_cabinets` exclude — outside scope footprint
    - `proc_countertops` exclude — outside scope footprint
    - `proc_paint` exclude — outside scope footprint
    - `proc_shower_glass` exclude — outside scope footprint
    - `proc_doors_trim` exclude — outside scope footprint
    - `proc_plumbing_fixtures` exclude — outside scope footprint
    - `proc_light_fixtures` include — 6 lights, 2 fans customer-selected, ~1 wk lead
    - `proc_concrete_patio` exclude — covered by proc_foundation_package; no patio
    - `proc_fireplace_kit` exclude — outside scope footprint
- **Permits**:
    - `permit_tdec_septic` exclude — No septic work in scope
    - `permit_plumbing` exclude — outside scope footprint
    - `permit_mechanical` include — Ductless mini-split HVAC in scope
- **Retrofit (pre-addition work)**:
    - `utility_relocations` exclude — Disconnect converted in place under rough electrical
    - `retrofit_demo` exclude — No pre-addition interior work on existing home
    - `retrofit_rough_meps` exclude — No pre-addition MEP work
    - `retrofit_drywall` exclude — No pre-addition walls opened
    - `retrofit_finishes` exclude — No pre-addition finish work
- **Site Prep & Foundation**:
    - `foundation_inspection` include — Footing inspection required for new footers
- **Framing & Shell**:
    - `fireplace_chase_install` exclude — outside scope footprint
- **Exterior Finishes**:
    - `siding` include — WRB + ~394 sf vinyl lap siding, three walls
    - `appliance_vent_extension` exclude — Old vent holes patched under roofing, not extended
    - `fireplace_finish_work` exclude — outside scope footprint
- **Rough Trades (MEPs)**:
    - `rough_plumbing` exclude — outside scope footprint
- **Rough Inspections**:
    - `bundled_rough_inspections` include — Electrical, mechanical, framing rough inspections
    - `fireplace_chimney_inspection` exclude — outside scope footprint
- **Insulation & Drywall**:
    - `insulation_inspection` include — Insulation visit follows insulation install
    - `paint_phase_1` exclude — outside scope footprint
- **Interior Finishes**:
    - `shower_work` exclude — outside scope footprint
    - `hard_flooring` exclude — outside scope footprint
    - `cabinets_counters` exclude — outside scope footprint
    - `carpet_floating` exclude — outside scope footprint
    - `enclosure_finishes` exclude — Conditioned drywalled room, not screened enclosure
    - `mep_fixture_install` include — Lights, fans, devices, mini-split head set
    - `finish_carpentry` exclude — outside scope footprint
    - `paint_phase_2` exclude — outside scope footprint
- **Concrete & Landscaping**:
    - `concrete_flatwork` exclude — No patio/flatwork; condenser pad rides groundwork
    - `landscaping` exclude — No seed and straw in scope
- **Closeout**:
    - `customer_walkthrough` include — Always — punch list at substantial completion
    - `final_inspections` include — Final building + electrical/mechanical inspection

## Canon entries that worked this run

- `cn_policy_elevated_access` — Elevated / second-story access premium [company/project] · cited 8×
- `cn_answer_01m2h06f3g9rynf1qtwg3vd8zr` — Sunroom ceiling finish scope [job] · cited 7×
- `cn_answer_01m2h07a109r3bkg5a08t2fpmp` — Post/footer count for deck installation [job] · cited 6×
- `cn_answer_01m2h055eewewa4x5800phewke` — Elevated work access and debris removal method [job] · cited 5×
- `cn_answer_01m2h06rhtkfd9r0jcakqcvsnv` — Brick wall drywall treatment [job] · cited 4×
- `cn_answer_01m2h04ypdna2xyz4epatkc24q` — Temporary shoring design authority [job] · cited 4×
- `cn_answer_01m2h05t36bf78eb76f3m7fas3` — Floor soffit vs floor-cavity batt install sequence [job] · cited 4×
- `cn_answer_01m2h05z9rcpxmbbhdre94zax0` — Window and exterior door sizing [job] · cited 3×
- `cn_answer_01m2h06ydaqtcgtwsd52f71taw` — Fused disconnect suitability verification [job] · cited 3×
- `cn_answer_01m242n6gdhw5e8383q8cdjdjh` — Existing main electrical service ampacity [job] · cited 3×
- `cn_answer_01m2v8hr4cnrajcmahesr0yfxn` — Brick wall receptacle mounting method [job] · cited 3×
- `cn_rates_inspections_crews` — Inspections & crew norms [company/project] · cited 3×
- `cn_policy_rate_card_governs` — Rate card governs [company/project] · cited 3×
- `cn_rates_cladding_finish` — Cladding & finish rates [company/project] · cited 3×
- `cn_answer_01m2h07380zf2f2b6d5mq7087j` — Mini-split condenser mounting location [job] · cited 2×
- `cn_answer_01m2h05g2rkknn9h4zpxfwm31y` — Building permit application status [job] · cited 2×
- `cn_answer_01m2v8hrn6k4zsjdjkpk9wk6cc` — Permitting AHJ for 333 Toy Crawford Road [job] · cited 2×
- `cn_rates_demo_site` — Demo & site rates [company/project] · cited 2×
- `cn_answer_01m2h06kyz1cqvxetrtfth59py` — Footer pocket excavation method at existing pad [job] · cited 2×
- `cn_rates_excavation_concrete` — Excavation & concrete rates [company/project] · cited 2×
- `cn_policy_mobilization_floor` — Mobilization floor [company/project] · cited 2×
- `cn_company_never_split_framing` — Never split framing [company/project] · cited 2×
- `cn_answer_01m2h04q3316zv1j8g1hk0hwe6` — existing shed-roof bearing height [job] · cited 2×
- `cn_answer_01m2h04gwya5z01r8ksa4m72n3` — Scope of signed proposal vs presentation extras [job] · cited 2×
- `cn_answer_01m2h07n7p3c346ya4jcq01stt` — Window and door header material [job] · cited 1×
- `cn_company_no_demo_without_materials` — No demo without materials [company/project] · cited 1×
- `cn_rates_framing` — Framing rates [company/project] · cited 1×
- `cn_rates_roofing` — Roofing rates [company/project] · cited 1×
- `cn_01m2gwxjenvqkzjam46b1bc14r` — Demolished ceiling assemblies require an explicit ceiling rebuild scope before insulation and drywall tasks are generated [company/project] · cited 1×
- `cn_company_interior_concurrency` — Interior trade concurrency [company/project] · cited 1×

## Warnings & findings

- Coverage: 1 PM-SETTLED quantity was consumed by NO task (window_door_lead_time_weeks=2weeks) — a human ruled on these numbers; verify each either feeds a derived quantity (dimension inputs do) or check which document value the sizing rode instead.
- Foreman check RAISED "siding" 40h → 49h — WRB 504sf says 'moved to framing' but framing's basis has no WRB line, so it is scope lost; restore it here at card 0.015 h/sf × 504sf = 7.6h, plus the 20% elevated premium ≈ 9h (40 → 49).

## Assumptions

- "Foundation Inspection" (foundation_inspection) is included but its structure row is UNVETTED — confirm with Will.
- "Foundation Pour" (foundation_pour) is included but its structure row is UNVETTED — confirm with Will.
