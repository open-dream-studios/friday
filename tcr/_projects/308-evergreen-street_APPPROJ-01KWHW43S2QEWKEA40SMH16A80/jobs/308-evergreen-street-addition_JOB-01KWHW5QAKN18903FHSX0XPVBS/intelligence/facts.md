---
generation_kind: intelligence_rebuild_v2
stage: synthesis
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWHW43S2QEWKEA40SMH16A80/jobs/308-evergreen-street-addition_JOB-01KWHW5QAKN18903FHSX0XPVBS/intelligence/extracted/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KWHW43S2QEWKEA40SMH16A80/jobs/308-evergreen-street-addition_JOB-01KWHW5QAKN18903FHSX0XPVBS/intelligence/extracted/breakdown.md
  - _projects/308-evergreen-street_APPPROJ-01KWHW43S2QEWKEA40SMH16A80/jobs/308-evergreen-street-addition_JOB-01KWHW5QAKN18903FHSX0XPVBS/intelligence/extracted/plans.md
  - _projects/308-evergreen-street_APPPROJ-01KWHW43S2QEWKEA40SMH16A80/jobs/308-evergreen-street-addition_JOB-01KWHW5QAKN18903FHSX0XPVBS/intelligence/applicable_rules.json
  - _projects/308-evergreen-street_APPPROJ-01KWHW43S2QEWKEA40SMH16A80/jobs/308-evergreen-street-addition_JOB-01KWHW5QAKN18903FHSX0XPVBS/manifest.json
---

# Facts — 308 Evergreen Street addition

## Customer & Job

- Job is titled "308 Evergreens Scope" and represents an addition-type job at 308 Evergreen Street, Church Hill, Tennessee (manifest.json address_line1/address_city/address_state; extracted/scope.md Customer & Job).
- Scheduled on-site start date is 2026-08-24 (manifest.json scheduled_start_date).
- Job type is `addition` and drives the applicable job-type rule layer (manifest.json job_type; applicable_rules.json).
- Total Investment quoted in the scope is $173,850 (extracted/scope.md Customer & Job).
- Two optional packages are priced separately: Closet & Cabinet System at $7,000 allowance and Tankless Water Heater at $6,500 allowance; utility upgrades not included for the tankless option (extracted/scope.md Customer & Job; Special features). **PM confirms NEITHER optional package elected — base contract scope only.** (interview round 1)
- Billing structure: $70/hr general with trade differentials (+$15 teamlead, +$30 electrical/HVAC, +$40 plumbing), materials at cost +15%, subs at cost +30%, dump trailer $450/removal, backhoe $1,100/wk (extracted/scope.md Customer & Job).
- Contract triggers on signed agreement plus $20,000 deposit; weekly invoicing after work begins (extracted/scope.md Customer & Job).
- No breakdown CSV attached to this job — the scope PDF is the sole authoritative pricing document (extracted/breakdown.md).
- No drawings PDF attached — spatial questions cannot be resolved from plans and must go to the PM (extracted/plans.md).

## Scope

- Objective: construct a two-story addition approximately 30' x 10' with basement-level storage and second-floor expansion of primary bedroom, master bathroom, and walk-in closet (extracted/scope.md Footprint).
- Scope covers structural integration, foundation, framing, roofing, exterior finishes, interior finishes, and full MEP systems (extracted/scope.md Customer & Job).
- Master bathroom scope includes a 7' x 4' custom tile shower with waterproofing, wall tile, mosaic floor tile, niche, bench, dual-valve diverter, 72" double vanity, 2 faucets, 2 mirrors, 2 vanity lights, commode, and exhaust fan/light combo vented outside (extracted/scope.md Finishes).
- Primary bedroom remodel is ~12'5" x 16' and includes framing mods, drywall/L3 finish, prime + paint, new LVT flooring, and full trim package (extracted/scope.md Finishes).
- Basement storage finish is frame + drywall + L3 paint + one lighting fixture; concrete floor remains unfinished (extracted/scope.md Finishes).
- LVT flooring is budgeted at $3.00/sqft throughout designated areas (extracted/scope.md Finishes).
- Interior door count is 4 total: **PM confirms 2 pre-hung + 2 pocket doors.** (interview round 1; replaces prior "assumed as 1 pre-hung and 2 pocket" ambiguity)
- Existing hall bathroom modification is a retrofit: remove existing window and frame the opening, insulate/drywall/finish, remove tub-shower combo ($1,000 allowance for pan and walls), install acrylic shower reusing existing valve/trim (confirmed round 1), PVC trim, patch and repaint (extracted/scope.md Special features). **PM confirms early execution: hall bath acrylic shower swap happens on Day 1 in site_prep/customer_early_items to give customer a working shower during construction; window-infill/repaint work remains in interior_finishes as retrofit component.** (interview round 1)
- Walk-in closet remains empty room — **PM confirms closet system optional package NOT elected; no millwork install.** (interview round 1)
- Elevator scope is framing-only for a ~4' x 4' shaft plus a rough-in 120V/30A circuit from the subpanel; elevator system itself is NOT included; PM to coordinate with 101 Mobility if requested (extracted/scope.md Special features).
- Water management explicitly EXCLUDES French drains, foundation waterproofing, or drainage improvements unless specified (extracted/scope.md Special features).

## Site

- Pre-construction includes TDEC septic inspection coordination. **PM confirms: keep existing septic system — TDEC inspection only, no excavation, relocation, or grinder pump work.** (interview round 1) Emit `permit.tdec_septic` with `pre_construction_offset_working_days: 30` per job-type rule `tdec_septic_permit_offset`; no excavation/plumbing sub-chain required.
- Costs for septic relocation, replacement, or grinder pump are NOT included in the $173,850 — all handled via change order (extracted/scope.md Customer & Job). **Confirmed moot — no change-order septic work in play.** (interview round 1)
- Selective demo includes saw-cutting portions of existing concrete walkway, removing designated railroad ties and site obstructions, excavating for footing/slab, and relocating existing heat pump and electrical disconnect (extracted/scope.md Foundation; MEP).
- Existing gas water heater vent must be extended through the new roof system per code — **PM confirms existing WH stays in place (tankless optional package NOT elected); only vent extends.** (interview round 1)
- Standard site access is assumed for equipment, material staging, and construction operations (extracted/scope.md Customer & Job).
- Standard soil is assumed; rock, unsuitable soils, or additional structural requirements are change-order items (extracted/scope.md Customer & Job).
- Debris removal via multiple dump runs is included (extracted/scope.md Foundation).

## Trades

- Foundation is monolithic-compatible per scope: continuous 12"x12" perimeter footings, 4" gravel base, vapor barrier, in-slab rebar/wire mesh, 4" slab with smooth finish; no CMU or full-height foundation wall (extracted/scope.md Foundation). Consistent with dev_rules 4B monolithic default (applicable_rules.json).
- Framing includes basement-level 2x4 @ 16" OC walls, dimensional/engineered floor system, glue-and-fasten subfloor, one 3-ply 14" LVL beam ~15'-6" spanning existing load-bearing wall (temporary shoring included), 2x4 @ 16" OC exterior/interior walls, and the future 4x4 elevator shaft frame (extracted/scope.md Framing).
- Roof is a new gable, 3/12 pitch tying into existing 6/12. **PM confirms stick-framed rafters — lumber arrives day-of with framing crew; no truss procurement.** (interview round 1; resolves prior "truss OR rafter" ambiguity per belief `stick_frame_default_for_small_additions`)
- Roofing package: architectural asphalt shingles, synthetic underlayment, drip edge, flashing, ridge vent, fascia board + fascia metal, vinyl soffit, seamless gutters, temporary dry-in (extracted/scope.md Framing).
- Exterior: sheathing + WRB, vinyl siding to match existing, 4 windows (3× 36"x60" + 1 transom), up to 1 new exterior door (**PM confirms stock unit, 7-day lead** per interview round 1), sealed penetrations with flashing (extracted/scope.md Finishes).
- Electrical: new 100A subpanel, full rough + trim, ~12 recessed lights ($25 each; allowance schedule allows up to 18), 2 vanity lights, 1 bath fan/light combo, outlets per IRC in basement storage, 3 outlets in master closet, 1 upstairs storage outlet, 1 hall switch relocation (with drywall patch/paint), dimmer switches at bedroom/bath, standard devices, GFCI/AFCI per code, and 1 dedicated 120V/30A circuit for the future elevator (extracted/scope.md MEP).
- Existing main electrical service is ASSUMED to support the new 100A subpanel — rule `service_amperage_check` requires a `prep.amperage_check` task to verify BEFORE panel procurement and electrical rough (applicable_rules.json).
- Plumbing: full rough (supply/waste/vent), quarter-turn shutoffs at all fixtures, master bath fixtures (2 lav sup/drain, 1 toilet, 1 custom shower w/ dual-valve diverter), W/D relocation with water/drain/roof vent, vent stacks extended through roof (extracted/scope.md MEP). **Hall bath acrylic shower reuses existing valve/trim per PM confirmation (round 1) — no hall bath plumbing rough or valve procurement.**
- Plumbing rough defaults to 4d × 2 crew per `_company/rules/_examples/plumbing_rough_min_duration` — scope has master bath + W/D relocation + multiple fixture branches, which trigger the 4d floor.
- Existing water heater stays and only its vent extends through the new roof — **PM confirms tankless optional package NOT elected (round 1).** Per dev_rules 4H, DO NOT emit `procurement.tank` or `plumbing.tank_set`.
- HVAC: 1 ductless mini-split ($2,500 budget), plus relocation of existing HVAC components; final sizing subject to load calc (extracted/scope.md MEP). Mini-split → MEP order is plumbing → electrical → mini-split per dev_rules 4G (applicable_rules.json).
- Insulation: R13 exterior walls, R30 attic/roof, R30 floor between basement and living space, air-sealing at penetrations (extracted/scope.md MEP).
- Drywall: Level 3 finish across new-construction + retrofit rooms; per belief `drywall_soft_schedule`, drywall is a soft-start behind insulation inspection and consolidates across addition + primary bedroom + basement storage + hall bath retrofit (applicable_rules.json).
- Paint: primer + 2 coats finish; per dev_rules 4E, MUST emit exactly two paint phases (extracted/scope.md Finishes; applicable_rules.json).
- Flooring: LVT throughout at $3/sqft including new addition areas and primary bedroom (extracted/scope.md Finishes).
- Tile in master bath: wall tile $3/sqft, mosaic floor $6/sqft, waterproofing/setting $500 allowance (extracted/scope.md Finishes).
- Trim: 5-1/4" MDF/finger-jointed pine baseboard, 2-1/4" casing, caulk/fill/sand/paint (extracted/scope.md Finishes).

## Sequencing

- Roof and siding default to same-crew serial rendering per belief `roof_and_siding_same_crew` unless PM flags a two-crew scenario (applicable_rules.json).
- Addition ties into existing structure at the roof (3/12 into existing 6/12), at the primary bedroom (framing mods), and at the hall bathroom — triggers `retrofit_tie_in_discovery` rule requiring `framing.tie_in_discovery` SS with tie-in framing (applicable_rules.json).
- Heat pump and electrical disconnect relocations must happen BEFORE demo per dev_rules 4K (in `site_prep` phase, not demo phase) (extracted/scope.md MEP; applicable_rules.json).
- **Hall bath early shower swap: PM confirms customer requested this work on Day 1 to maintain a working shower during construction. Per dev_rules 4V two-bucket pattern, emit `site_prep / customer_early_items / early.hall_bath_shower` on Day 1. Hall bath retrofit window-infill/repaint work remains SEPARATE in interior_finishes as a distinct retrofit component.** (interview round 1)
- Windows install runs immediately after roof framing (parallel with roofing underlayment) per dev_rules 4J (applicable_rules.json).
- Rough MEPs gate on `roofing.underlayment` + `windows.install`, NOT on the dried-in milestone, per dev_rules 4I (applicable_rules.json).
- Siding may start once underlayment + windows are in per job-type rule `siding_starts_at_underlayment` — do NOT hard-chain siding after shingles/fascia (applicable_rules.json).

## Procurement

- Windows (3× 36"x60" DH + 1 transom, $300 each allowance) — likely stock, 14-21 calendar-day supplier lead per editor_rules; use 3-task pattern (order/wait/checkpoint) per dev_rules 4R (extracted/scope.md Finishes).
- 100A subpanel: 7-14 calendar-day lead per editor_rules; use 3-task pattern gated on `prep.amperage_check` completion (extracted/scope.md MEP).
- 3-ply 14" LVL beam: 7-14 calendar-day lead (standard LVL) — order gates structural install (extracted/scope.md Framing).
- Mini-split unit ($2,500 budget): 7-14 calendar-day lead per editor_rules (extracted/scope.md MEP).
- LVT flooring (stock, $3/sqft): 7-day lead — collapse to 1-day order task 1 week before install per dev_rules 4R exception (extracted/scope.md Finishes).
- Tile (wall + mosaic floor): if custom, 14-21 days; if stock, 7 days — default to stock 7-day unless PM specifies custom during selections lock-in (extracted/scope.md Finishes).
- Vanity/fixtures ($1,000 vanity, $150/faucet, $150/mirror, $100/vanity light, $250 commode, $250 shower valve/trim): stock 7-day lead (extracted/scope.md Finishes).
- Interior doors (4 total: **PM confirms 2 pre-hung + 2 pocket** per round 1): stock, 7-day lead (extracted/scope.md Finishes).
- Exterior door ($500 allowance): **PM confirms stock unit, 7-day lead** (interview round 1).
- Permit is a 1-day walk-in per dev_rules 4A with `pre_construction_offset_working_days: 15` — NOT a 14-day lead (applicable_rules.json).
- Selections-finalized checkpoint mandatory 3 weeks before on-site start per dev_rules 4P — anchors all finish-material procurement (applicable_rules.json).
- TDEC septic inspection permit application requires `pre_construction_offset_working_days: 30` per job-type rule `tdec_septic_permit_offset` — **PM confirms inspection-only, no excavation or septic replacement work** (interview round 1).