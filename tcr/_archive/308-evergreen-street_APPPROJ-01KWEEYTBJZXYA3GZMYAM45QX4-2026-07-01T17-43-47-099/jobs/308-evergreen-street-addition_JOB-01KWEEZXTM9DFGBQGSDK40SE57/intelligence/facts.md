---
generation_kind: intelligence_rebuild_v2
stage: synthesis
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWEEYTBJZXYA3GZMYAM45QX4/jobs/308-evergreen-street-addition_JOB-01KWEEZXTM9DFGBQGSDK40SE57/intelligence/extracted/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KWEEYTBJZXYA3GZMYAM45QX4/jobs/308-evergreen-street-addition_JOB-01KWEEZXTM9DFGBQGSDK40SE57/intelligence/extracted/breakdown.md
  - _projects/308-evergreen-street_APPPROJ-01KWEEYTBJZXYA3GZMYAM45QX4/jobs/308-evergreen-street-addition_JOB-01KWEEZXTM9DFGBQGSDK40SE57/intelligence/extracted/plans.md
  - _projects/308-evergreen-street_APPPROJ-01KWEEYTBJZXYA3GZMYAM45QX4/jobs/308-evergreen-street-addition_JOB-01KWEEZXTM9DFGBQGSDK40SE57/intelligence/applicable_rules.json
  - _projects/308-evergreen-street_APPPROJ-01KWEEYTBJZXYA3GZMYAM45QX4/jobs/308-evergreen-street-addition_JOB-01KWEEZXTM9DFGBQGSDK40SE57/manifest.json
  - _projects/308-evergreen-street_APPPROJ-01KWEEYTBJZXYA3GZMYAM45QX4/jobs/308-evergreen-street-addition_JOB-01KWEEZXTM9DFGBQGSDK40SE57/interview/round-1.md
---

# Facts — 308 Evergreen Addition

## Customer & Job

- Project label is "308 Evergreen Street"; job type is "addition." *(manifest.json)*
- Internal project name is "Simons Addition — 30'×10' Two-Story + Bedroom Remodel." *(breakdown.md — Project totals block)*
- Total investment (customer-facing contract price) is $173,850. *(extracted/scope.md — Special features)*
- Raw cost breakdown Grand Total is $100,778.92 (Labor $45,167.59 + Material $52,171.33 + Equipment $3,440.00), with 1,287 total labor hours. *(extracted/breakdown.md — Project totals rows 2–5)*
- Rates: general $70/hr, teamlead +$15/hr, electrical/HVAC +$30/hr, plumbing +$40/hr; materials at cost +15%; subs at cost +30%. *(extracted/scope.md — Special features)*
- Contract requires signed agreement and $20,000 deposit; weekly invoicing after start. *(extracted/scope.md — Special features)*
- All work must comply with IRC 2018 and NEC. *(extracted/scope.md — Customer & Job)*

## Scope

- Objective: construct a two-story addition approximately 30' × 10' with basement-level storage and second-floor expansion of primary bedroom, master bathroom, and walk-in closet. *(extracted/scope.md — Customer & Job)*
- Addition footprint per plans is 295 SF per floor × 2 floors = 590 SF total addition area. *(extracted/plans.md — Structural decisions)*
- Total overall footprint on CSV summary is 789 SF at 8' ceilings. *(extracted/breakdown.md — header)*
- Master bathroom includes a custom tile shower ~7' × 4' with dual valve diverter, 72" double vanity, two faucets/mirrors/lights, commode, exhaust fan/light combo. *(extracted/scope.md — Footprint, Finishes)*
- Primary Bedroom Remodel area is approximately 12'5" × 16' (existing room to be reworked: framing mods, drywall, prime + paint, LVT, full trim). *(extracted/scope.md — Footprint, Finishes)*
- Basement Storage: frame and drywall walls, Level 3 finish + paint, one light fixture; concrete floor remains unfinished. *(extracted/scope.md — Finishes)*
- Existing Hall Bathroom Modification: remove existing window and frame opening, insulate/drywall/finish; remove tub/shower combo; install acrylic shower system ($1,000 allowance for pan and walls); reuse existing valve and trim; PVC trim; minor patch and repaint. Hall bath acrylic shower swap is a Day-1 customer early item per Rule 4V; window infill/patch/repaint runs later in retrofit component. *(extracted/scope.md — Finishes; round 1, q.hall_bath_acrylic_shower_early_item)*
- Elevator shaft: framing only for ~4' × 4' future shaft plus a dedicated 120V 30A circuit; elevator hardware not included. *(extracted/scope.md — Special features)*
- Closet & cabinet system ($7,000 allowance) optional package is OUT unless customer signed add-on. *(extracted/scope.md — Special features; round 1, q.closet_cabinet_optional_package)*
- Tankless water heater ($6,500 allowance) optional package is OUT; existing gas tank stays and vent is extended through new roof per base scope. *(extracted/scope.md — Special features; round 1, q.tankless_wh_in_base_bid)*

## Site

- Standard soil conditions assumed; rock/unsuitable soils and additional structural requirements are change-order items. *(extracted/scope.md — Customer & Job)*
- Standard site access for equipment, material staging, and construction operations assumed. *(extracted/scope.md — Customer & Job)*
- Existing septic system is adequate; no septic replacement, new tank/leach field, or grinder pump installation. TDEC septic coordination is permit acknowledgment only (30 calendar-day pre-construction offset per `tdec_septic_permit_offset` rule). *(extracted/scope.md — Customer & Job, Special features; round 1, q.septic_grinder_direction)*
- Site work includes saw-cutting/removing portions of existing concrete walkway, removing railroad ties and site obstructions, and excavating for footings/slab. *(extracted/scope.md — Foundation)*
- Plans p.4 carry an explicit note: contractor to verify locations of existing plumbing, venting, septic tank, and HVAC before construction. *(extracted/plans.md — Retrofit indicators)*
- Existing heat pump and electrical disconnect must be relocated (Rule 4K: heat pump relocation in `site_prep / prep_work_before_demo` at least 3 working days before demo begins). *(extracted/scope.md — Foundation; extracted/plans.md — Retrofit indicators; applicable_rules.json)*
- Existing chimney is present on roof plan and must be worked around by new roof framing. *(extracted/plans.md — Structural decisions)*
- Drawings header carries designer Rebecca Lineberry's studio address (647 AA Deakins Rd, Jonesborough); plans are confirmed for 308 Evergreen project. *(extracted/plans.md — Discrepancies #4; round 1, q.drawings_address_is_designer)*

## Trades

- Foundation: continuous 12"×12" concrete footings + 4" gravel base + vapor barrier + rebar/wire mesh + 4" slab with smooth finish; NO CMU or full-height foundation walls → monolithic pour applies (dev_rules 4B). *(extracted/scope.md — Foundation; applicable_rules.json)*
- Framing: 2×4 basement walls at 16" O.C., dimensional/engineered floor system, subfloor glued and fastened, one 3-ply 14" LVL spanning ~15'-6" with temporary shoring to open existing load-bearing wall, exterior + interior 2×4 walls at 16" O.C., elevator shaft frame, new 3/12 gable roof tying into existing 6/12. *(extracted/scope.md — Framing; extracted/plans.md — Structural decisions)*
- Roofing: architectural asphalt shingles matching existing, synthetic underlayment, drip edge, flashing, ridge vent; fascia board/metal, vinyl soffit, seamless gutters; temporary dry-in during framing. *(extracted/scope.md — Framing)*
- Exterior: sheathing + WRB, vinyl siding to match existing (NO brick veneer — plans elevation note is stale design intent), 1 new exterior door, seal penetrations and flashing. *(extracted/scope.md — Framing; round 1, q.brick_veneer_addition_base)*
- Electrical: one new 100A subpanel, full rough-in + trim-out, ~12 recessed lights ($25 ea), 2 vanity lights, 1 vent fan/light combo, outlets for upstairs storage/basement storage/master closet (3), hallway switch relocate w/ patch+repaint, dimmers at bedroom/bath, GFCI/AFCI per code, dedicated 120V/30A for future elevator; assumes existing service supports subpanel. *(extracted/scope.md — MEP)*
- Plumbing: full rough-in (supply, waste, vent), quarter-turn shutoffs at all fixtures, master bath (2 lav + toilet + custom shower w/ dual diverter), W/D relocation with water/drain/roof venting, vent stacks extended through roof; existing sewer/septic assumed adequate. Existing gas water heater stays; vent extended through new roof per base scope (no tankless replacement). *(extracted/scope.md — MEP; round 1, q.tankless_wh_in_base_bid)*
- HVAC: one ductless mini-split ($2,500 budget) and relocation of existing HVAC components; final sizing subject to load calc. *(extracted/scope.md — MEP)*
- Insulation: R13 exterior walls, R30 attic/roof, R30 floor system between basement and living space, penetrations sealed. *(extracted/scope.md — MEP)*
- Drywall: Level 3 finish on new addition + existing bedroom + basement storage; consolidated at 159 labor hours / crew 3 → 9–11 working days per editor rules. *(extracted/scope.md — Finishes; extracted/breakdown.md — Notes)*
- Interior finishes: primer + 2 finish coats paint, LVT flooring throughout designated areas ($3/sqft), 5-1/4" MDF/pine baseboard, 2-1/4" casing, trim/caulk/paint. *(extracted/scope.md — Finishes)*
- Interior doors: best estimate 2 pocket doors (hall bath + primary closet) plus pre-hung panel doors for remainder; PM flagged need to verify against plans schedule. *(extracted/scope.md — Finishes; round 1, q.interior_doors_pocket_vs_panel)*
- Master bath tile: waterproofing, tile walls, mosaic tile floor, niche + bench. *(extracted/scope.md — Finishes)*
- Windows: procurement follows plans schedule (authoritative over scope narrative): order (1) 3'0"×1'0" transom + (1) 3'0"×3'0" DH for new addition; existing windows on Bedrooms 2 and 3 are relocated (not new). *(extracted/plans.md — Discrepancies #1; round 1, q.windows_count_and_size_reconciliation)*
- Trusses/rafters: scope says "truss or rafter framed, determined during design phase"; footprint is 300 SF (well under 800 SF threshold) and roof span ≤ 10 ft (well under 24 ft trigger) → stick-frame default belief applies, no procurement.trusses task. *(extracted/plans.md — Structural decisions; applicable_rules.json — stick_frame belief)*

## Sequencing

- Pre-construction: TDEC septic permit acknowledgment (30 calendar-day pre-construction offset per `tdec_septic_permit_offset` rule, no actual septic work), site verification with plans, permit application (walk-in, `general.permitting` 1d work, offset 15 working days), and selections finalized checkpoint at offset 15. *(extracted/scope.md — Customer & Job; applicable_rules.json — dev_rules 4A/4P, tdec_septic_permit_offset; round 1, q.septic_grinder_direction)*
- Rule 4H (tank set FIRST) does NOT apply — existing gas water heater stays, no tankless replacement, so plumbing rough-in proceeds without a tank predecessor. *(applicable_rules.json — dev_rules 4H; round 1, q.tankless_wh_in_base_bid)*
- Rule 4K: existing heat pump relocation goes in `site_prep / prep_work_before_demo` at least 3 working days before demo begins. *(applicable_rules.json — dev_rules 4K; extracted/scope.md — Foundation)*
- Rule 4G / HVAC type = mini-split → MEP rough order is plumbing → electrical → mini-split line-set rough (0.5d, 1 person); mini-split install is 1d/1 person. *(applicable_rules.json — dev_rules 4G, editor_rules HVAC; extracted/scope.md — MEP)*
- Rule 4V (customer early item + retrofit two-bucket): hall bath acrylic shower swap is Day-1 early item in `site_prep / customer_early_items`; hall bath window infill/drywall patch/repaint runs later in `interior_finishes / hall_bath_mod` component. *(applicable_rules.json — dev_rules 4V; round 1, q.hall_bath_acrylic_shower_early_item)*
- Rule 4I/4J: windows install FS-after `framing.roof` in parallel with `roofing.underlayment`; MEPs gate on `roofing.underlayment` + `windows.install`, NOT on `milestone.dried_in`. *(applicable_rules.json — dev_rules 4I/4J)*
- Rule 4N HVAC stagger: at interior-finishes phase, mini-split install serializes AFTER `electrical.finish` to hold 2-trade interior cap. *(applicable_rules.json — dev_rules 4N)*
- Plumbing rough-in duration MUST be ≥4 working days × 2 crew per company hard rule and Will's nominal — CSV row 20 shows 40 labor hours (~2.5d) which violates the floor and must be overridden. *(applicable_rules.json — plumbing_rough_min_duration rule; extracted/breakdown.md — Notes)*
- Concealed roof tie-in (3/12 into existing 6/12 + existing chimney + valley transition) is a known high-risk discovery seam — schedule needs a discovery buffer running SS with roof framing. *(extracted/plans.md — Discrepancies #5; extracted/breakdown.md — Silent omissions #6)*

## Procurement

- No procurement line items in CSV — all procurement is invisible in the summary and must be derived. *(extracted/breakdown.md — Notes)*
- Windows: order (1) 3'0"×1'0" transom + (1) 3'0"×3'0" DH per plans schedule (authoritative); stock DH + transom → wait ~21 calendar days (per editor_rules lead-time table); 3-task pattern (order / wait / checkpoint.arrived) required per dev_rules 4R. *(extracted/breakdown.md — Notes; applicable_rules.json — dev_rules 4R; round 1, q.windows_count_and_size_reconciliation)*
- LVL beam (3-ply 14"): standard LVL → 7–14 calendar days; use 14 for safety. *(applicable_rules.json — editor_rules lead-time table)*
- Mini-split unit: 7–14 calendar days. *(applicable_rules.json — editor_rules lead-time table)*
- Electrical panel (100A subpanel): 7–14 calendar days. *(applicable_rules.json — editor_rules lead-time table)*
- Custom tile (master bath walls + mosaic floor): 14–21 calendar days. *(applicable_rules.json — editor_rules lead-time table)*
- LVT flooring (stock): 7 calendar days, may collapse to 1-day order task per Rule 4R exception. *(applicable_rules.json — dev_rules 4R + editor_rules)*
- No trusses — stick-frame lumber arrives with framing crew day-of. *(applicable_rules.json — stick_frame belief)*
- No tankless water heater procurement — existing gas tank stays. *(round 1, q.tankless_wh_in_base_bid)*
- Equipment: dumpster + backhoe + concrete saw + skid steer + mini-ex per Rule 4O; excavation/foundation row shows $1,950 equipment — implies ~1.5–2 weeks machine time. *(extracted/breakdown.md — Notes; applicable_rules.json — dev_rules 4O)*

## Anomalies / Flags

- Row 26 (Existing Hall Bath Mod + Bedroom Remodel + Closeout) has NEGATIVE material cost of −$4,199 and total −$1,714.20 with 72 labor hours — likely a template-anchor credit / double-counted materials elsewhere; do not expand into a full task tree per dev_rules §12. *(extracted/breakdown.md — Notes)*
- CSV row 20 plumbing labor hours = 40 (~2.5d @ crew 2), below the 4d hard floor from `plumbing_rough_min_duration` rule — must be overridden to 4d. *(extracted/breakdown.md — Notes; _company/rules/_examples/plumbing_rough_min_duration.md)*
- Elevator shaft framing and 30A elevator circuit are folded silently into rows 15 (framing) and 19 (electrical) — no standalone lines. *(extracted/breakdown.md — Silent omissions #3)*
- Grand Total ($100,778.92) ≠ scope's Total Investment ($173,850) — CSV is raw cost, scope is customer-facing contract; use CSV labor hours for duration math. *(extracted/breakdown.md — Project totals)*
- Interior door count/type (pocket vs. panel) needs physical drawing verification; working assumption is 2 pocket + pre-hung panel remainder. *(round 1, q.interior_doors_pocket_vs_panel)*