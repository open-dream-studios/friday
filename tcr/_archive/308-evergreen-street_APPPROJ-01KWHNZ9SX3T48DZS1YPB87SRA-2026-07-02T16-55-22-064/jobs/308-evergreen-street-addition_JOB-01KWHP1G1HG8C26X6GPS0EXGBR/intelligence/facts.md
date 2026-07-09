---
generation_kind: intelligence_rebuild_v2
stage: synthesis
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWHNZ9SX3T48DZS1YPB87SRA/jobs/308-evergreen-street-addition_JOB-01KWHP1G1HG8C26X6GPS0EXGBR/manifest.json
  - _projects/308-evergreen-street_APPPROJ-01KWHNZ9SX3T48DZS1YPB87SRA/jobs/308-evergreen-street-addition_JOB-01KWHP1G1HG8C26X6GPS0EXGBR/intelligence/extracted/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KWHNZ9SX3T48DZS1YPB87SRA/jobs/308-evergreen-street-addition_JOB-01KWHP1G1HG8C26X6GPS0EXGBR/intelligence/extracted/breakdown.md
  - _projects/308-evergreen-street_APPPROJ-01KWHNZ9SX3T48DZS1YPB87SRA/jobs/308-evergreen-street-addition_JOB-01KWHP1G1HG8C26X6GPS0EXGBR/intelligence/extracted/plans.md
  - _projects/308-evergreen-street_APPPROJ-01KWHNZ9SX3T48DZS1YPB87SRA/jobs/308-evergreen-street-addition_JOB-01KWHP1G1HG8C26X6GPS0EXGBR/intelligence/applicable_rules.json
---

# Facts — 308 Evergreen Street Addition (Simons)

## Customer & Job

- Job address is 308 Evergreen Street, Church Hill, Tennessee. *(manifest.json: address_line1, address_city, address_state)*
- Job type is `addition`. *(manifest.json: job_type)*
- Scheduled on-site start is 2026-08-24. *(manifest.json: scheduled_start_date)*
- Priority is medium; current status is `waiting_work`. *(manifest.json: priority, status)*
- Design set is dated 2026-01-22, prepared by Greyscale Design LLC / Rebecca Lineberry NCIDQ. *(extracted/plans.md — sheet title blocks)*
- Plans title-block address (647 AA Deakins Rd, Jonesborough TN) is the designer's office, not the site. *(extracted/plans.md — "Note on address discrepancy")*
- Contract Total Investment quoted in scope is $173,850. *(extracted/scope.md — Customer & Job; scope.md L179)*
- CSV grand total is $100,778.92 (Labor $45,167.59 + Material $52,171.33 + Equipment $3,440.00 across 1,287 labor hours). *(extracted/breakdown.md — Trade totals)*
- Deposit required to start is $20,000; invoicing weekly for prior week's work. *(extracted/scope.md — Customer & Job)*
- Labor rate structure: $70/hr general, +$15 team lead, +$30 electrical/HVAC, +$40 plumbing. Materials at cost +15%, subs at cost +30%. *(extracted/scope.md — Customer & Job)*
- Backhoe rental $1,100/week; dump-trailer runs $450 each. *(extracted/scope.md — Customer & Job)*

## Scope

- Objective is a two-story addition approximately 30' × 10' with basement-level storage below and a second-floor primary bedroom, master bathroom, and walk-in closet above. *(extracted/scope.md — Customer & Job; extracted/plans.md — Structural decisions)*
- Total addition area is 590 SF (295 SF basement + 295 SF upper). *(extracted/plans.md — Structural decisions)*
- Ceiling height is 8'-0" on both floors. *(extracted/plans.md — Structural decisions; CSV metadata)*
- Roof is a NEW 3/12 gable tying into an EXISTING 6/12 roof via multiple valleys and ridges. *(extracted/plans.md — Structural decisions)*
- Framing method is scope-ambiguous ("truss OR rafter framed, determined during design phase") but plans do not annotate trusses; stick-frame is the default per the small-addition belief. *(extracted/plans.md — Structural decisions; belief stick_frame_default_for_small_additions)*
- Foundation is a monolithic pour: continuous 12"×12" footings + 4" slab over gravel + vapor barrier + rebar/mesh; no CMU or full-height foundation walls. *(extracted/scope.md — Foundation)*
- Framing scope includes (1) 3-ply 14" LVL, ~15'-6" span, opening an existing load-bearing wall, with temporary shoring. *(extracted/scope.md — Framing)*
- A future 4'×4' elevator shaft is framed on both levels with a dedicated 30A / 120V circuit; elevator equipment itself is NOT included. *(extracted/scope.md — Special features; extracted/plans.md — Structural decisions)*
- Master bath includes a ~7'×4' custom tile shower with waterproofing, wall tile, mosaic floor tile, niche, bench, and dual-valve diverter; plus a 72" double vanity, 2 faucets, 2 mirrors, 2 lights, commode, and exhaust fan/light. *(extracted/scope.md — Finishes)*
- Primary bedroom remodel (~12'5" × 16') scope: framing mods + Level 3 drywall patch + prime/paint + new LVT + full trim. *(extracted/scope.md — Finishes)*
- Basement storage: frame + drywall + Level 3 finish + paint + light fixture; concrete floor stays unfinished. *(extracted/scope.md — Finishes)*
- Existing hall bath modification: remove existing window and frame the opening, insulate/drywall/finish, remove existing tub-shower combo, install acrylic shower system, reuse existing valve/trim, PVC trim, patch and repaint. *(extracted/scope.md — Finishes; scope.md L141-149)*
- The hall bath acrylic shower is a customer-request area with a $1,000 pan-and-walls allowance. *(extracted/breakdown.md — Allowances; scope.md L145)*
- Exterior finish per scope is vinyl siding + fascia metal + vinyl soffit + seamless gutters; plans additionally show new brick on the basement level (see Trades — masonry discrepancy). *(extracted/scope.md — Framing; extracted/plans.md — Discrepancies #3)*
- (4) new windows per scope: (3) 36"×60" + (1) transom, plus (1) new exterior door. Plans window schedule lists only 2 (1 transom + 1 D.H. 3'0"×3'0") — discrepancy. *(extracted/scope.md — Framing; extracted/plans.md — Discrepancies #1, #2)*
- (2) existing windows are being relocated and (1) existing door is being relocated — enumerated on plans but NOT itemized in scope labor. *(extracted/plans.md — Retrofit indicators; extracted/plans.md — Things plans show scope doesn't mention)*
- Interior doors: (4) total per scope, breakdown "(1) pre-hung + (2) pocket doors" — reconcile pocket-vs-panel with plans door schedule. *(extracted/scope.md — Finishes; extracted/plans.md — Things plans show scope doesn't mention)*
- LVT flooring throughout designated areas at $3.00/sqft allowance. *(extracted/scope.md — Finishes; extracted/breakdown.md — Allowances)*
- Insulation: R13 exterior walls, R30 attic/roof, R30 floor between basement and living space; air-seal all penetrations. *(extracted/scope.md — Finishes)*
- Optional package — Closet & Cabinet System, $7,000 allowance (labor + materials), not in CSV base. *(extracted/scope.md — Customer & Job; extracted/breakdown.md — Allowances)*
- Optional package — Tankless Water Heater removal + install with venting and connections, $6,500 allowance; utility upgrades not included; not in CSV base. *(extracted/scope.md — Customer & Job; extracted/breakdown.md — Notes)*
- Scope base case keeps the existing gas water heater and extends its vent through the new roof; no new WH procurement/tank_set in base scope (Rule 4H exemption). *(extracted/scope.md — Special features; extracted/breakdown.md — Silent omissions #4)*

## Site

- Existing house is one-story (per elevations showing addition wrap-around) with EXISTING GARAGE, LOUNGE, LIVING, KITCHEN, DINING, COVERED DECK, FRONT PORCH, BDRM 2, BDRM 3 labelled on plans. *(extracted/plans.md — Retrofit indicators)*
- Existing hall bath (BTH 2) sits between bedrooms 2 and 3; plans show "NEW SHWR." callout confirming acrylic-swap location. *(extracted/plans.md — Retrofit indicators)*
- Existing chimney is adjacent to the 6/12 roof and needs flashing tie-in during roofing. *(extracted/plans.md — Retrofit indicators)*
- Existing plumbing, venting, septic tank, and HVAC locations are field-verify per plans note. *(extracted/plans.md — Retrofit indicators; plans p.4 note)*
- Existing roof slopes and soffit depth are field-verify per plans note. *(extracted/plans.md — Retrofit indicators; plans p.5 note)*
- Site is on septic per scope; TDEC septic inspection is required. Feasibility of septic relocation, new septic tank + leach field, OR grinder pump to sewer is UNRESOLVED — all three treated as change-order items in current pricing. *(extracted/scope.md — Customer & Job; extracted/scope.md — Special features)*
- Selective demo tasks: saw cut concrete walkway, remove railroad ties + obstructions, excavate for footings/slab, multiple dump-trailer runs. *(extracted/scope.md — Finishes)*
- Standard soil / standard site access assumptions apply; rock excavation or unsuitable soils would be a change order. *(extracted/scope.md — Customer & Job)*
- Existing heat pump and electrical disconnect must be relocated BEFORE main demo (per Rule 4K). *(extracted/scope.md — MEP; extracted/scope.md — Customer & Job)*

## Trades

- **Framing** — largest labor line: 146 hours / $14,008 (CSV row 14). Includes basement walls, floor system, LVL install + shoring, all interior/exterior walls at 16" O.C., elevator shaft framing. *(extracted/breakdown.md — Trade totals)*
- **Interior Finish/Paint/Flooring** — 162 hours / $12,832 (row 23). Highest labor-hour section: drywall paint, LVT, baseboard 5-1/4", 2-1/4" casing, trim/caulk/paint, (4) interior doors. *(extracted/breakdown.md — Trade totals)*
- **Drywall** — 159 hours / $9,331 (row 22). Consolidated across addition + existing bedroom; aligns with editor rule 9-11d typical addition drywall. *(extracted/breakdown.md — Notes)*
- **Roof framing / roofing** — 96 hours / $9,652 (row 15). Includes sheathing, synthetic underlayment, architectural asphalt shingles, drip edge, flashing, ridge vent, fascia board/metal, vinyl soffit, seamless gutters. Runs as same-crew block per belief `roof_and_siding_same_crew`. *(extracted/breakdown.md — Trade totals; belief roof_and_siding_same_crew)*
- **Master Bathroom** — 88 hours / $7,155 (row 24). Custom tile shower + finishes. *(extracted/breakdown.md — Trade totals)*
- **Excavation / Foundation** — 78 hours / $7,065 (row 12) with $1,950 equipment (mini-ex + backhoe ~2 weeks). *(extracted/breakdown.md — Trade totals; Notes)*
- **Electrical** — 78 hours / $6,722 (row 18): 100A subpanel + full rough + finish + ~12 recessed + 2 vanity lights + fan/light + hall switch relocate + dimmer switches + (3) closet outlets + storage outlets + basement outlets + 30A elevator circuit + GFCI/AFCI protection. *(extracted/breakdown.md — Trade totals; extracted/scope.md — MEP)*
- **HVAC** — 36 hours / $6,503 (row 20). Ductless mini-split ($2,500 budget) + heat pump relocation; row title says "Tankless WH" but tankless is treated as optional package (see Procurement). *(extracted/breakdown.md — Notes)*
- **Exterior finishes** — 72 hours / $5,731 (row 16). Vinyl siding, trim, gutters; runs same-crew with roofing. *(extracted/breakdown.md — Trade totals)*
- **Structural mods** — 60 hours / $4,540 (row 13). LVL + shoring. *(extracted/breakdown.md — Trade totals)*
- **General Conditions / Permits** — 56 hours / $4,446 (row 10). *(extracted/breakdown.md — Trade totals)*
- **Selective Demo** — 56 hours / $4,242 (row 11). *(extracted/breakdown.md — Trade totals)*
- **Insulation** — 44 hours / $3,084 (row 21). R13/R30/R30 per scope; ~1 day install per editor rule. *(extracted/breakdown.md — Trade totals; editor productivity table)*
- **Windows/Doors/Weatherproofing** — 44 hours / $3,666 (row 17). Sheathing, WRB, (4) new windows, (1) new exterior door, flashing. *(extracted/breakdown.md — Trade totals)*
- **Plumbing** — 40 hours / $3,517 (row 19). Master bath rough + W/D relocation + vent stack extension + existing hall bath swap. CSV allocation is BELOW company-rule floor of 4d × 2 crew = 64 hours for master-bath jobs. *(extracted/breakdown.md — Notes; company rule plumbing_rough_min_duration)*
- **Existing Hall Bath / Bedroom Remodel / Closeout** — 72 hours labor, section total NEGATIVE at -$1,714.20 due to a -$4,199 material line (row 25). Labor hours are real work; negative material is a credit whose meaning is unclear. *(extracted/breakdown.md — Notes)*
- Masonry (brick) trade is on plans but NOT priced in CSV (see Procurement/discrepancy). *(extracted/plans.md — Discrepancies #3)*

## Sequencing

- Pre-construction anchor is 3 weeks before on-site start per editor rules (permits, selections-finalized, amperage check). *(rule dev_rules Rule 4P; rule service_amperage_check)*
- Building permit is a same-day walk-in modeled as 1-day work task with `pre_construction_offset_working_days: 15`. *(rule dev_rules Rule 4A)*
- TDEC septic permit (if triggered) requires `pre_construction_offset_working_days: 30` (~6 weeks) per job-type rule. *(applicable_rules — tdec_septic_permit_offset)*
- `prep.amperage_check` MUST be emitted 2 weeks before on-site because scope adds a 100A subpanel, ≥4 new circuits, mini-split, and optionally a tankless WH — the trigger conditions in `service_amperage_check`. *(rule service_amperage_check)*
- Heat pump and electrical disconnect relocation MUST land in `site_prep / prep_work_before_demo` at least 3 working days BEFORE main demo. *(rule dev_rules Rule 4K; extracted/scope.md — MEP)*
- Foundation is monolithic (Rule 4B default): excavation → form_and_prep → footing inspection → single monolithic pour → 2-day cure. NO secondary slab inspection. *(rule dev_rules Rule 4B)*
- HVAC type is mini-split → MEP rough order is plumbing → electrical → mini-split rough (0.5d line set). *(rule dev_rules Rule 4G; extracted/scope.md — MEP)*
- Windows install AS SOON AS roof is framed (FS after `framing.roof` + procurement), parallel with underlayment — NOT after `milestone.dried_in`. *(rule dev_rules Rule 4J)*
- Rough MEPs are FS after `roofing.underlayment` AND `windows.install`, NOT after dried-in milestone. *(rule dev_rules Rule 4I)*
- Existing gas WH vent extension happens during roofing (no `plumbing.tank_set` since no new WH in base scope). *(rule dev_rules Rule 4H exemption; extracted/scope.md — Special features)*
- Plumbing rough-in floor is 4 working days × 2 crew (master bath + W/D relocation + vent stack extension) regardless of CSV's 40-hour allocation. *(company rule plumbing_rough_min_duration; extracted/breakdown.md — Notes)*
- Rough inspections bundle onto ONE day (Rule 4C) followed by a 2-4 day punch-list buffer (Rule 4D). *(rule dev_rules Rule 4C, 4D)*
- Insulation material lands ON the rough-inspection day so it's staged for immediate install after buffer clears. *(editor_rules — Material delivery tied to inspection date)*
- Drywall is consolidated hang/tape/sand/prime — 9-11 days for typical addition; CSV 159 hours across addition + existing bedroom aligns. Drywall crew is a `soft_start` per belief `drywall_soft_schedule`; PM calls crew when first insulation inspection is calendared. *(belief drywall_soft_schedule; extracted/breakdown.md)*
- Paint is TWO phases mandatory (Rule 4E): phase 1 = primer walls+ceilings AM + ceiling finish PM same day (1d); phase 2 = LAST work task, gated on ALL finish trades. *(rule dev_rules Rule 4E, 4F)*
- Interior finish dependency chain: paint.phase_1 → flooring + tile substrate + electrical finish → cabinets → plumbing finish → trim → paint.phase_2 → substantial completion. *(rule dev_rules Rule 4L; editor_rules — Interior finish dependencies)*
- 2-trades-max interior cap enforced: mini-split install serializes AFTER electrical.finish per default HVAC-stagger. *(rule dev_rules Rule 4N)*
- Roof and siding run as one same-crew serialized block per TCR default. *(belief roof_and_siding_same_crew)*
- Siding may start once underlayment is on (parallel with fascia/soffit/gutters/shingles) per job-type dependency rule — but wall-clock still typically serializes on TCR jobs. *(applicable_rules — siding_starts_at_underlayment)*
- Retrofit tie-in discovery task (framing.tie_in_discovery) runs SS with the tie-in framing task to expose concealed conditions — the multi-valley 6/12→3/12 tie-in is a real discovery risk. *(applicable_rules — retrofit_tie_in_discovery; extracted/plans.md — Structural decisions)*
- Customer's existing-hall-bath acrylic shower swap is a customer-request early item and lives in `site_prep / customer_early_items`, distinct from the retrofit bucket for the hall bath's window infill + drywall patch + repaint (Rule 4V two-bucket pattern). *(rule dev_rules Rule 4V; extracted/scope.md — Finishes)*
- Final inspections bundle to ONE day (Rule 4M); walkthrough + punch + final clean + CO milestone follow. *(rule dev_rules Rule 4M; editor_rules — Closeout)*
- `checkpoint.selections_finalized` lands 3 weeks before on-site and gates finish-material procurement (Rule 4P). *(rule dev_rules Rule 4P)*

## Procurement

- Procurement uses the 3-task pattern (order / wait / arrived) for every long-lead item; ≤7-day items may collapse to a single 1-day order 1 week before install. *(rule dev_rules Rule 4R; editor_rules — Procurement pattern)*
- **Windows** — stock, 21-day supplier wait (allowance $300 × 4). *(editor_rules — Lead-time items; extracted/scope.md)*
- **Exterior door** — standard, ~14-21 day wait; $500 allowance. *(editor_rules; extracted/scope.md)*
- **LVL beam** (3-ply 14", ~15'-6") — 7-14 calendar day wait, use 14 for safety. *(editor_rules — Lead-time items; extracted/scope.md — Framing)*
- **Electrical panel** (100A subpanel) — 7-14 calendar day wait. *(editor_rules — Lead-time items)*
- **Mini-split unit** — 7-14 day wait (tied to dried-in), $2,500 budget. *(editor_rules — Lead-time items; extracted/scope.md — MEP)*
- **Tile (custom or stock)** — 7-21 days depending on stock/custom; $3/sqft walls + $6/sqft mosaic floor + $500 waterproofing/setting per allowance. *(editor_rules — Lead-time items; extracted/breakdown.md — Allowances)*
- **LVT flooring** — 7-day stock wait, $3/sqft allowance. *(editor_rules — Lead-time items; extracted/breakdown.md — Allowances)*
- **Vanity 72" double** — stock ~7 days, $1,000 allowance. *(editor_rules — Lead-time items; extracted/breakdown.md — Allowances)*
- **Fixtures** (2 faucets $150 ea, commode $250, 2 vanity lights $100 ea, 2 mirrors $150 ea, shower valve/trim $250, 12-18 recessed at $25 ea) — 7-day stock. *(editor_rules; extracted/breakdown.md — Allowances)*
- **Acrylic shower system** for hall bath — $1,000 pan/walls allowance; stock wait. *(extracted/breakdown.md — Allowances)*
- **Paint** — 1-2 day stock, collapse to single 1-day order 1 week before paint phase 1. *(editor_rules — Lead-time items)*
- **Trusses** — NOT emitted (Rule 4Q); scope is ambiguous "truss or rafter" with small footprint (590 SF) and no truss annotation on plans; stick-frame default. *(rule dev_rules Rule 4Q; belief stick_frame_default_for_small_additions)*
- **Tankless water heater** — NOT in base procurement; only if optional $6,500 package is signed. If confirmed, add procurement.tank + plumbing.tank_set + rework plumbing rough sequence per Rule 4H. *(extracted/breakdown.md — Notes)*
- **TDEC septic permit** — CONDITIONAL. Scope currently treats septic relocation, new septic, and grinder pump as change-order items. If any is confirmed as base scope, emit permit.tdec_septic with `pre_construction_offset_working_days: 30`. *(applicable_rules — tdec_septic_permit_offset; extracted/scope.md — Customer & Job)*
- Materials must be on site 1 week before install (universal rule); equipment must land the day before its phase (Rule 4O). *(editor_rules — Material ordering; rule dev_rules Rule 4O)*
- Equipment checkpoints (dumpster, mini-ex, backhoe, saw, scaffolding) land 2 weeks before their consuming phase (`pre_construction_offset_working_days: 10`). *(rule dev_rules Rule 4O; editor_rules — Equipment on site)*
- Debris removal: multiple 7'×14' dump-trailer runs at $450 each — CSV row 11 has only $220 equipment cost, likely under-priced for a job of this size. *(extracted/breakdown.md — Silent omissions #10)*

## Data-quality / risk-gate items (surfaced to interview)

- **Scope-vs-CSV $73,072 gap (72.5%)** — company rule `scope_vs_csv_total_reconciliation` requires this be a blocking interview question; interview_status MUST be `needs_more` until answered. *(rule scope_vs_csv_total_reconciliation; extracted/breakdown.md — Major anomaly)*
- Window count / size discrepancy between scope (4 windows, 3 at 36"×60") and plans schedule (2 windows, D.H. at 36"×36"). *(extracted/plans.md — Discrepancies #1, #2)*
- Exterior finish discrepancy: scope says vinyl siding, plans say lap siding + new brick to match. Masonry is a distinct trade absent from CSV. *(extracted/plans.md — Discrepancies #3)*
- Interior door count/type discrepancy: scope says 4 doors with 1 prehung + 2 pocket; plans door schedule shows 4 panel doors with no pocket-door symbols. *(extracted/plans.md — Things plans show scope doesn't mention; Discrepancies #5)*
- Two existing windows and one existing door being relocated per plans but NOT itemized in scope labor. *(extracted/plans.md — Retrofit indicators)*
- Row 25 negative section total ($-1,714) with 72 real labor hours — meaning of -$4,199 credit needs PM clarification (salvage credit? template artifact?). *(extracted/breakdown.md — Notes)*
- Row 20 title says "Tankless WH" but pricing doesn't include the $6,500 optional package — ambiguity on whether tankless is base or option. *(extracted/breakdown.md — Notes)*
- Plumbing hours in CSV (40) are BELOW company floor (≥64 hr) for master bath + W/D + vent stack scope. *(extracted/breakdown.md — Notes)*
- Concealed roof tie-in (3/12 into 6/12 with 3+ valleys) is a discovery risk requiring `framing.tie_in_discovery` SS buffer. *(applicable_rules — retrofit_tie_in_discovery; extracted/plans.md — Discrepancies)*
- Septic direction (existing capacity vs relocate vs new + leach vs grinder pump) is UNRESOLVED and materially affects schedule + procurement + permits. *(extracted/scope.md — Customer & Job; extracted/scope.md — Special features)*
