---
generation_kind: intelligence_interview_v2
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWD458DXBEREH8PWBJTFEADS/jobs/308-evergreen-street-addition_JOB-01KWD49ZCC89C3TCH1MZVJEV2P/manifest.json
  - _projects/308-evergreen-street_APPPROJ-01KWD458DXBEREH8PWBJTFEADS/jobs/308-evergreen-street-addition_JOB-01KWD49ZCC89C3TCH1MZVJEV2P/inputs/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KWD458DXBEREH8PWBJTFEADS/jobs/308-evergreen-street-addition_JOB-01KWD49ZCC89C3TCH1MZVJEV2P/intelligence/extracted/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KWD458DXBEREH8PWBJTFEADS/jobs/308-evergreen-street-addition_JOB-01KWD49ZCC89C3TCH1MZVJEV2P/intelligence/applicable_rules.json
  - _projects/308-evergreen-street_APPPROJ-01KWD458DXBEREH8PWBJTFEADS/jobs/308-evergreen-street-addition_JOB-01KWD49ZCC89C3TCH1MZVJEV2P/interview/round-1.md
  - _company/rules/dev_rules.md
  - _company/rules/editor_rules.md
  - _company/rules/pep_rules.md
  - job_types/addition/rules/addition_rules.md
  - job_types/addition/rules/tdec_septic_permit_offset.md
---

# Facts — what we know about this job

## Customer & Job

- Customer: 308 Evergreen Street; job_type = addition; project id APPPROJ-01KWD458DXBEREH8PWBJTFEADS; job id JOB-01KWD49ZCC89C3TCH1MZVJEV2P (manifest.json).
- Total quoted investment $173,850; payment trigger = signed agreement + $20,000 deposit (extracted/scope.md "Customer & job").

## Scope — what's being built

- Two-story addition, approximately 30' × 10' footprint (extracted/scope.md "Footprint"). Total addition area ≈ 600 sqft of new construction.
- New-construction objective areas: basement-level storage (lower) + primary bedroom expansion, master bathroom, walk-in closet (upper) (extracted/scope.md "Footprint").
- Existing primary bedroom (~12'5" × 16') is being re-modeled as part of the upper-level work — this overlaps existing structure (extracted/scope.md "Primary bedroom remodel").
- Existing hall bathroom is being modified in-place: window infill, acrylic shower swap, repaint (extracted/scope.md "Existing hall bathroom modification").
- Future 4' × 4' elevator shaft is FRAMED in scope; elevator system itself is NOT in scope (extracted/scope.md "Elevator shaft"). Location CONFIRMED INSIDE the new addition footprint — framing-only stub, aligns with shaft + dedicated 30A circuit on drawings; do NOT carve out a retrofit Component for it (round 1, q.retrofit_elevator_shaft).
- Two optional packages offered separately and NOT in the base task graph: custom closet/cabinet ($7,000), tankless WH conversion ($6,500).

## Site & existing-conditions assumptions

- Heat pump + electrical disconnect on the existing house need to be relocated to clear the new addition footprint (extracted/scope.md "Site work & demolition").
- Existing gas water heater STAYS; only its vent is extended through the new roof — NO `procurement.tank` / `plumbing.tank_set` needed (rule: company:_company/rules/dev_rules.md rank 100 [Rule 4H scope condition]; extracted/scope.md "Site work & demolition").
- Standard soil; rock excavation NOT in base — change-order territory.
- Concealed wiring/plumbing/structural conditions exposed by demo → change order. Roof tie-in conditions specifically are a known change-order risk (rule: job_type:job_types/addition/rules/addition_rules.md rank 200 [Concealed roof tie-in]).

## Pre-construction & permits

- Home CONFIRMED on SEPTIC (round 1, q.septic_tdec); TCR owns the TDEC permit process including $500 fee and soil-scientist coordination. Emit `permit.tdec_septic` with `lead_time_days: 42` calendar and `pre_construction_offset_working_days: 30` (rule: job_type:job_types/addition/rules/tdec_septic_permit_offset.md rank 200). TDEC permit is the longest pre-con lead; it dominates the realistic on-site start date.
- Building permit modeled as `general.permitting`: 1-day work task, `pre_construction_offset_working_days: 15`, lead_up_working_days: 2 (rule: company:_company/rules/dev_rules.md rank 100 [Rule 4A], company:_company/rules/editor_rules.md rank 100).
- `checkpoint.selections_finalized` required in pre-construction, offset 15, lead_up 5 (rule: company:_company/rules/dev_rules.md rank 100 [Rule 4P]).
- Subpanel is in scope; existing main-service amperage NOT yet verified (extracted/scope.md "Electrical"). Emit `prep.amperage_check` (0.5d, general, pre_construction, offset 15) AND emit mandatory warning "subpanel scope present, no existing-service amperage verification" until PM confirms (rule: job_type:job_types/addition/rules/addition_rules.md rank 200 [Amperage check]).
- Window order type RESOLVED: (3) 36"×60" DH stock + (1) transom semi-custom (4–6 wk), single PO → `wait.windows` `lead_time_days: 42` calendar, upper bound (round 1, q.window_order_type).

## Trades — what's in scope

- Foundation: monolithic-pour applies — 12" × 12" continuous footings + 4" slab with gravel base, vapor barrier, rebar/mesh; NO CMU / stem walls (extracted/scope.md "Foundation"; rule: company:_company/rules/dev_rules.md rank 100 [Rule 4B]).
- Framing: 2×4 @ 16" O.C. basement walls, dimensional/engineered floor system, 2×4 exterior + interior walls, future 4'×4' elevator shaft frame, one 3-ply 14" LVL beam spanning ~15'-6" with temporary shoring to open existing load-bearing wall (extracted/scope.md "Framing").
- LVL is a known structural item. PM CONFIRMED standard stock SPF/LVL (round 1, q.lvl_type) — `wait.lvl` `lead_time_days: 14` calendar; do NOT bump to 21 (rule: job_type:job_types/addition/rules/addition_rules.md rank 200 [LVL beams]). Engineer-stamped sizing is required because the beam bears actual new load (round 1, q.lvl_load_bearing).
- Roof: 3/12 gable tying into existing 6/12, architectural asphalt shingles, synthetic underlayment, drip edge, flashing, ridge vent (extracted/scope.md "Roof system"). STICK-FRAME CONFIRMED for tie-in flexibility (round 1, q.roof_framing) — do NOT emit `procurement.trusses` (rule: job_type:job_types/addition/rules/addition_rules.md rank 200 [Roof trusses CONDITIONAL]).
- Exterior: vinyl siding to match, 4 windows (three 36"×60" DH + one transom), one exterior door, sheathing + WRB (extracted/scope.md "Exterior finishes").
- Electrical: 100A subpanel (1d / 1 person), full rough-in + trim-out, ~12 recessed lights, vanity lights, bath fan/light, GFCI/AFCI, dimmers, dedicated 120V 30A circuit for future elevator (extracted/scope.md "Electrical").
- Plumbing: full rough-in (supply/waste/vent), master bath fixtures (2 lavs + toilet + custom shower with dual-valve diverter), W/D relocation w/ roof venting, vent-stack extension. Master bath is multi-fixture → `plumbing.rough_in` floor is 4d × 2 crew per Will's nominal (rule: company:_company/rules/editor_rules.md rank 100 [Plumbing rough-in duration]).
- HVAC: 1 ductless mini-split, $2,500 budget (extracted/scope.md "HVAC") → HVAC TYPE IS MINI-SPLIT (NOT ducted). Apply mini-split MEP order: plumbing → electrical → mini-split rough (line set, 0.5d / 1 person); install 1d / 1 person (rule: company:_company/rules/editor_rules.md rank 100 [HVAC sequencing]).
- Insulation: R13 walls, R30 attic, R30 floor (extracted/scope.md "Insulation").
- Drywall: Level 3 finish on new + retrofit areas. Consolidate retrofit hall-bath drywall + bedroom drywall + basement storage drywall into single `drywall.consolidated` block (rule: company:_company/rules/editor_rules.md rank 100 [Drywall consolidation]; rule: job_type:job_types/addition/rules/addition_rules.md rank 200 [Retrofit drywall consolidates]).
- Finishes: primer + 2 coats paint (two-phase paint, mandatory), LVT ($3/sqft), 5-1/4" MDF/finger-jointed pine baseboard, 2-1/4" casing, full trim, 4 interior doors (1 pre-hung + 2 pocket — door count discrepancy: 3 specified, 4 declared).
- Master bath: custom tile shower 7'×4' with niche/bench + dual-valve diverter, 72" double vanity, 2 faucets/mirrors/lights, commode, exhaust fan/light vented to exterior.

## Sequencing — what gates what (key non-obvious edges)

- MEPs (electrical/plumbing/mini-split rough) gate on `roofing.underlayment` AND `windows.install`, NOT on `milestone.dried_in` (rule: job_type:job_types/addition/rules/addition_rules.md rank 200 [MEPs gated on underlayment + windows]).
- `windows.install` gates on `framing.roof` + `checkpoint.windows_arrived` and runs in parallel with `roofing.underlayment`; NOT after the dried-in milestone (rule: job_type:job_types/addition/rules/addition_rules.md rank 200 [Windows install]).
- Heat-pump and existing electrical-disconnect relocations live in `site_prep / prep_work_before_demo`, minimum 3 working days before demo phase begins (rule: job_type:job_types/addition/rules/addition_rules.md rank 200 [Heat pump/HVAC relocation]).
- Hall bath retrofit (window infill framing + insulation + drywall patch + repaint) belongs in its OWN retrofit Component (e.g. `hall_bath_mod`) in `interior_finishes` and runs in parallel with main scope; the drywall portion folds into `drywall.consolidated`. NOT gated on new-construction framing (rule: job_type:job_types/addition/rules/addition_rules.md rank 200 [Retrofit detection]).
- NO customer early items (round 1, q.customer_early_items) — Rule-4V two-bucket pattern does NOT apply. The hall-bath acrylic shower swap stays INSIDE the single `hall_bath_mod` retrofit Component in `interior_finishes`, NOT a Day-1 `site_prep / customer_early_items` task (rule: company:_company/rules/dev_rules.md rank 100 [Rule 4V]; rule: company:_company/rules/editor_rules.md rank 100 [Customer early items]).
- Rough inspections bundled: ONE inspector, ONE day, covers rough electrical + plumbing + mini-split rough + framing; followed by a 2–4 day `buffer.post_rough_inspection` punch-list lead_time (rule: company:_company/rules/dev_rules.md rank 100 [Rule 4C]).
- Paint is TWO phases. `paint.phase_1` (primer + ceiling finish coat, 1d) gates flooring/electrical finish/tile substrate. `paint.phase_2` (1d) is the LAST work task on site and gates on EVERY finish trade including `hvac.minisplit_install`. Substantial completion FS-after `paint.phase_2` only (rule: company:_company/rules/dev_rules.md rank 100 [Rules 4E, 4F]).
- Interior 2-trade max: in the finish cluster the standard 3-trade overlap (electrical.finish + plumbing.finish + hvac.minisplit_install) is resolved by chaining `hvac.minisplit_install` FS-after `electrical.finish` (rule: company:_company/rules/dev_rules.md rank 100 [Rule 4N], company:_company/rules/editor_rules.md rank 100 [HVAC stagger]).
- Concealed roof tie-in: emit `roof.concealed_buffer` (lead_time, 3 cal-d, SS lag 1 after `framing.roof`) and surface a warning that the PM must document existing rafter conditions on day 1 of `framing.roof` (rule: job_type:job_types/addition/rules/addition_rules.md rank 200 [Concealed roof tie-in]).
- LVL sub-chain (`demo.expose_bearing_wall` → `structural.temp_shoring` → `structural.install_lvl` → `structural.remove_temp_shoring`) is NOT an independent retrofit on this job — PM CONFIRMED the new floor + roof load above transfers through the 15'-6" span (round 1, q.lvl_load_bearing). `framing.floor_system` (and any roof load path resting on the LVL) MUST gate FS-after `structural.install_lvl`. Engineer-stamped sizing is required (rule: job_type:job_types/addition/rules/addition_rules.md rank 200 [LVL temporary shoring]).
- Will's personal final walkthrough is the LAST task: `closeout.wills_walkthrough` (0.5d, general, FS lag 1 after `inspect.final_bundled`) (rule: job_type:job_types/addition/rules/addition_rules.md rank 200 [Will's walkthrough]).

## Procurement

- Procurement chains live in a dedicated `procurement_long_leads` phase (NOT in `pre_construction`); each item uses the 3-task `order.X / wait.X / checkpoint.X_arrived` pattern with the install task gated on the checkpoint (rule: job_type:job_types/addition/rules/addition_rules.md rank 200 [Procurement phase emission rule]; rule: company:_company/rules/dev_rules.md rank 100 [Rule 4R]; rule: company:_company/rules/editor_rules.md rank 100 [Procurement pattern]).
- Windows (4 units, single PO): (3) 36"×60" DH stock + (1) transom semi-custom (4–6 wk) per PM (round 1, q.window_order_type) → `wait.windows` `lead_time_days: 42` calendar (upper bound; transom dictates the bundle). `checkpoint.windows_arrived` gates on the slowest unit.
- LVL beam: PM confirmed standard stock SPF/LVL (round 1, q.lvl_type) → `wait.lvl` `lead_time_days: 14` calendar.
- Mini-split unit: order at dried-in; `wait.minisplit` 7–14 calendar.
- Electrical 100A subpanel: 7–14 calendar.
- LVT, paint, standard fixtures, vanities: 7 calendar or collapse to a single 1-day `order.X` placed ~1 week before install.
- Custom tile (master-bath wall + mosaic floor): 14–21 calendar — order ~3 weeks before tile install.
- DO NOT emit `procurement.trusses` — PM CONFIRMED stick-frame (round 1, q.roof_framing) (rule: company:_company/rules/dev_rules.md rank 100 [Rule 4Q]; rule: job_type:job_types/addition/rules/addition_rules.md rank 200 [Roof trusses CONDITIONAL]).
- DO NOT emit `procurement.tank` / `plumbing.tank_set` — existing WH stays per scope (rule: company:_company/rules/dev_rules.md rank 100 [Rule 4H scope condition]).

## Out-of-scope / change-order territory

- Septic/grinder/leach-field install costs explicitly NOT in base price (extracted/scope.md "Pre-construction / permits").
- Rock excavation / unsuitable soils NOT in base.
- Elevator SYSTEM not included; only framing + 30A circuit included.
- French drains / foundation waterproofing / drainage improvements NOT included.
- Tankless WH conversion and custom closet/cabinet system are OPTIONAL — current base assumes existing tank WH stays and standard closet allowance.
