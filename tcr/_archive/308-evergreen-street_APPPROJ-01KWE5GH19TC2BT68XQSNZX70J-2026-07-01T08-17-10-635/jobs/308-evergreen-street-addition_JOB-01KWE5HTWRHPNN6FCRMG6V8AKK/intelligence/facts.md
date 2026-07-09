---
generation_kind: intelligence_rebuild_v2
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWE5GH19TC2BT68XQSNZX70J/jobs/308-evergreen-street-addition_JOB-01KWE5HTWRHPNN6FCRMG6V8AKK/manifest.json
  - _projects/308-evergreen-street_APPPROJ-01KWE5GH19TC2BT68XQSNZX70J/jobs/308-evergreen-street-addition_JOB-01KWE5HTWRHPNN6FCRMG6V8AKK/inputs/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KWE5GH19TC2BT68XQSNZX70J/jobs/308-evergreen-street-addition_JOB-01KWE5HTWRHPNN6FCRMG6V8AKK/inputs/files/308_Evergreen_Addition.xlsx - Summary (1).csv.txt
  - _projects/308-evergreen-street_APPPROJ-01KWE5GH19TC2BT68XQSNZX70J/jobs/308-evergreen-street-addition_JOB-01KWE5HTWRHPNN6FCRMG6V8AKK/inputs/files/3725 SIMONS 012226.pdf.txt
  - _projects/308-evergreen-street_APPPROJ-01KWE5GH19TC2BT68XQSNZX70J/jobs/308-evergreen-street-addition_JOB-01KWE5HTWRHPNN6FCRMG6V8AKK/intelligence/extracted/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KWE5GH19TC2BT68XQSNZX70J/jobs/308-evergreen-street-addition_JOB-01KWE5HTWRHPNN6FCRMG6V8AKK/intelligence/extracted/breakdown.md
  - _projects/308-evergreen-street_APPPROJ-01KWE5GH19TC2BT68XQSNZX70J/jobs/308-evergreen-street-addition_JOB-01KWE5HTWRHPNN6FCRMG6V8AKK/intelligence/extracted/plans.md
  - _projects/308-evergreen-street_APPPROJ-01KWE5GH19TC2BT68XQSNZX70J/jobs/308-evergreen-street-addition_JOB-01KWE5HTWRHPNN6FCRMG6V8AKK/intelligence/applicable_rules.json
  - _company/rules/editor_rules.md
  - _company/rules/dev_rules.md
  - job_types/addition/rules/addition_rules.md
  - job_types/addition/rules/tdec_septic_permit_offset.md
  - job_types/addition/beliefs/stick_frame_default_for_small_additions.md
---
# facts.md — what we know

Round 1 synthesis. No PM interview answers yet (`confirmed.md` empty). Open items live in `questions.md`.

## Customer & job
- **Customer / site:** 308 Evergreen Street (design set titled "SIMONS ADDITION," 647 AA Deakins Rd, Jonesborough TN 37659 on the drawings' title block — TCR job manifest carries the address slug 308-evergreen-street) `(manifest.json; plans.md L4)`.
- **Job type:** addition — 30' x 10' two-story `(scope.md L4-8 via extracted/scope.md#Footprint)`.
- **Design authority:** Rebecca Lineberry, NCIDQ / Greyscale Design, LLC — full 5-page drawing set stamped Jan 22, 2026 `(plans.md source)`.
- **Contract:** $173,850 total investment, $20K deposit to schedule, weekly invoicing `(extracted/scope.md#Contract-level facts)`.
- **Breakdown grand total:** $100,778.92 (labor $45,167.59 + material $52,171.33 + equip $3,440) across 1,287 labor hours `(extracted/breakdown.md#Totals)`.

## Scope — addition objective
- Two-story addition, ~30' x 10', comprising: **basement-level storage** below and **second-floor primary-suite expansion** (primary bedroom + master bathroom + walk-in closet) above `(extracted/scope.md#Footprint)`.
- Addition-only footprint per drawings: **590 sqft** (295 first-floor + 295 basement) `(extracted/plans.md#Structural)`.
- Ceiling heights: 8'-0" both stories `(extracted/plans.md; extracted/scope.md)`.

## Scope — retrofit / existing-structure work bundled into contract
- Existing hall bathroom modification: remove existing window + infill, remove tub/shower combo, install acrylic shower system (reuses existing valve + trim), PVC trim, patch + repaint `(extracted/scope.md#Existing hall bathroom modification)`.
- Existing primary bedroom (~12'5" x 16') remodel: modify framing as required, drywall Level 3, prime + paint, new LVT, full trim `(extracted/scope.md#Primary bedroom)`.
- Existing hallway switch relocation with drywall patch + prime + paint `(extracted/scope.md#MEP — Electrical)`.
- **Plans indicate additional retrofit not clearly narrated in scope:** Bedroom 2 window relocation, Bedroom 3 window relocation + new window `(extracted/plans.md#Retrofit indicators)`. See `questions.md q.retrofit_bedroom_2_3`.
- Extend existing gas WH vent through new roof `(extracted/scope.md#Site)`.

## Scope — customer-requested early item candidates
- **Hall bath acrylic shower swap** is a strong candidate for the `customer_early_items` bucket (Rule 4V; addition_rules Customer-Requested Early Items). Scope doesn't explicitly say "customer wants shower before demo," but Will's canonical 308 example in the rules names this exact pattern *(rule: job_type:job_types/addition/rules/addition_rules.md, rank 200)*. **Interview must confirm** — see `questions.md q.customer_early_items`.

## Site / demo / prep
- **Heat pump relocation + electrical disconnect relocation** are required BEFORE main demo per Rule 4K *(rule: company:_company/rules/dev_rules.md, rank 100)*. Scope confirms both are in scope `(extracted/scope.md#Site)`.
- Saw-cut + remove portions of existing walkway + railroad ties + site obstructions `(extracted/scope.md#Site)`.
- Excavate for footings + slab `(extracted/scope.md#Foundation)`.
- Multi-trip dump-trailer debris removal (breakdown has $220 + $255 + $560 equipment lines) `(extracted/breakdown.md#Allowances)`.

## Foundation — monolithic
- Applies Rule 4B default: **ONE monolithic footing + slab pour** — 12"x12" continuous footings + 4" gravel + vapor barrier + rebar + 4" slab smooth finish `(extracted/scope.md#Foundation)`. Scope has NO stem-walls / no CMU / no foundation walls — monolithic default holds *(rule: company:_company/rules/dev_rules.md, rank 100, 4B)*.
- Standard soil assumed; rock excavation excluded (change-order) `(extracted/scope.md#Foundation)`.

## Structural
- **1x LVL beam, 3-ply 14", spanning ~15'-6"** to open existing load-bearing wall, temporary shoring required `(extracted/scope.md#Framing)`. Per addition_rules LVL section: standard 3-ply LVL = 1wk supplier lead, safety default 14 calendar days *(rule: job_type:job_types/addition/rules/addition_rules.md, rank 200, LVL beams)*. **Interview must confirm** stock vs pressure-treated/custom — see `questions.md q.lvl_type`.
- LVL retrofit is its own sub-chain (`structural.temp_shoring → install_lvl → remove_temp_shoring`), does NOT gate the new addition's floor system UNLESS the new floor/roof load actually bears on this LVL. Scope reads "open existing load-bearing wall" — ambiguous whether new floor above sits on the LVL. See `questions.md`.
- Elevator shaft framing only + 30A stub — plans place the shaft INSIDE the new addition footprint `(extracted/plans.md#Retrofit indicators)` → NOT retrofit, part of new construction. Elevator itself excluded.

## Framing
- Basement walls, floor system, all exterior + interior walls: 2x4 @ 16" O.C. `(extracted/scope.md#Framing)`.
- Framing labor budget: 146 hrs → ~6 working days for crew of 3 at labor rate, but per editor rules the correct split is basement_walls (2d) + floor_system (2d) + exterior_walls (3d) + interior_walls (2d) + roof (3d) + sheathing (1d) *(rule: company:_company/rules/editor_rules.md, rank 100, Worked duration examples)*.
- **Roof framing method AMBIGUOUS in scope** ("truss OR rafter framed — determined during design phase") `(extracted/scope.md#Roof)`. Belief `stick_frame_default_for_small_additions` applies because addition footprint = 590 sqft < 800 sqft AND roof span = 10' < 24' *(belief: job_type:job_types/addition/beliefs/stick_frame_default_for_small_additions.md, rank 200)*. Default: **stick-frame, no `procurement.trusses`.** Confirmation asked in `questions.md q.roof_framing`.

## Roof
- New gable, 3/12 pitch tying into existing 6/12 `(extracted/scope.md#Roof)`.
- Architectural asphalt shingles matched to existing, synthetic underlayment, drip edge, flashing, ridge vent `(extracted/scope.md#Roof)`.
- Fascia board + fascia metal + vinyl soffit + seamless gutters `(extracted/scope.md#Roof)`.
- **Concealed roof tie-in risk applies** per addition_rules Concealed Roof Tie-in: plans show multiple valleys + chimney at the tie-in area on page 5 `(extracted/plans.md#Structural)` → apply `roof.concealed_buffer` (3-day lead_time, SS lag 1 after `framing.roof`) *(rule: job_type:job_types/addition/rules/addition_rules.md, rank 200)*. Standard rule application, no PM interview needed to enable.

## Exterior finishes — SCOPE-vs-DRAWINGS conflict (unresolved)
- **Scope: vinyl siding** to match existing `(extracted/scope.md#Exterior)`.
- **Drawings: dual-material "NEW BRICK TO MATCH EXISTING" + "NEW LAP SIDING"** on all three elevations `(extracted/plans.md#Discrepancies)`.
- This is a material-and-cost conflict; breakdown line "Exterior Finishes – Siding, Trim & Gutters" ($5,731 total, 72 labor hrs) is sized for a single-material vinyl install, not a masonry-plus-lap-siding install. **Interview MUST resolve** — see `questions.md q.siding_scope_vs_drawings`.

## Windows / doors
- Scope: (3) 36" x 60" DH + (1) transom + up to (1) new exterior door `(extracted/scope.md#Exterior)`.
- Plans' window schedule counts only (1) new 3'0"x3'0" DH + (1) transom + relocated existings — DH quantity mismatch `(extracted/plans.md#Discrepancies)`.
- Stock vs custom window unknown at $300/ea allowance suggests **stock** — confirm at interview. Stock 14-21 supplier days, custom 28-42 *(rule: job_type:job_types/addition/rules/addition_rules.md, rank 200, Windows)*.

## MEP — HVAC type
- **Mini-split** — explicitly stated in scope with $2,500 material allowance `(extracted/scope.md#MEP — HVAC)`. Rule 4G confirmed: MEP order = plumbing → electrical → mini-split rough `(line set)` *(rule: company:_company/rules/dev_rules.md, rank 100, 4G)*. No PM interview question needed on HVAC type.
- Mini-split rough = 0.5d/1p; install = 1d/1p per editor rules *(rule: company:_company/rules/editor_rules.md, rank 100)*.

## MEP — water heater (CRITICAL BRANCHING FACT)
- **Base scope: EXISTING gas water heater stays** — only vent is extended through new roof `(extracted/scope.md#MEP — Water heater)`. Per Rule 4H scope-condition: if existing WH stays, **DO NOT emit `procurement.tank` or `plumbing.tank_set`** *(rule: company:_company/rules/dev_rules.md, rank 100, 4H)*. Plumbing rough-in proceeds without tank predecessor.
- **Optional tankless package** ($6,500 allowance) MAY be exercised by customer, which would flip to Rule 4H tank-set-first sequence. **Interview must confirm which path** — see `questions.md q.tankless_or_existing_wh`.

## MEP — plumbing
- Full rough-in: supply + waste + vent, quarter-turn shutoffs, master bath (2 lav + 1 toilet + custom shower dual-valve), W/D relocation with roof-vented dryer duct, extended vent stacks `(extracted/scope.md#MEP — Plumbing)`.
- Breakdown budget: 40 labor hrs. **Rule 4H/editor plumbing.rough_in default is 4 working days × 2 crew for master bath + W/D relocation** — do NOT shave to breakdown hours *(rule: company:_company/rules/editor_rules.md, rank 100, Plumbing rough-in duration)*.

## MEP — electrical
- 100A subpanel + full rough-in + trim-out + 12 recessed + 2 vanity lights + fan/light combo + outlets per code + hallway switch relocation (retrofit) + dimmers + GFCI/AFCI + 30A elevator stub `(extracted/scope.md#MEP — Electrical)`.
- Subpanel install = 1d, 1 person per editor rules *(rule: company:_company/rules/editor_rules.md, rank 100)*.
- **Amperage check required** per addition_rules (subpanel scope present) — `prep.amperage_check` (0.5d, general, pre_construction, `pre_construction_offset_working_days: 15`) *(rule: job_type:job_types/addition/rules/addition_rules.md, rank 200)*. Applied automatically, no PM Q needed to fire.

## Septic — TDEC LONG-LEAD
- **Scope confirms TCR is coordinating TDEC septic inspection** `(scope.md L32-35)`. Home IS on septic (scope evaluates septic relocation feasibility + grinder pump alternative).
- Adds a bedroom + bathroom → TDEC applies per addition_rules `(rule: job_type:job_types/addition/rules/tdec_septic_permit_offset.md, rank 200)`.
- Emit `permit.tdec_septic`, `kind: lead_time`, `lead_time_days: 42` (calendar), **`pre_construction_offset_working_days: 30` MANDATORY** *(hard rule)*. Gates `excavation.dig` via FS.
- **Grinder pump: explicitly excluded as change order** — no scheduling task, but PM must decide direction before rough plumbing (Jul 15-ish in a normal schedule). Excluded from questions.md because scope is explicit.

## Insulation
- R13 walls, R30 attic, R30 floor between basement + living space, air-seal all penetrations `(extracted/scope.md#Insulation)`.
- Applies editor default duration: 1 working day install for a typical addition *(rule: company:_company/rules/editor_rules.md, rank 100)*.

## Drywall — consolidated block
- Applies Rule 4-drywall consolidation: **one hang/tape/sand block for addition + existing primary bedroom + basement storage + hall-bath patch** *(rule: job_type:job_types/addition/rules/addition_rules.md, rank 200, Retrofit drywall consolidates)*. Do NOT model separate retrofit drywall sub-chain.
- Editor rules budget: 9-11 working days consolidated (cure baked in). Breakdown labor hours 159 support this. Small addition tilt → use 9d default.

## Interior finish — sequencing (rule-locked, no PM Q needed)
- Paint two-phase mandatory (Rule 4E). Paint phase 1 = primer + ceiling finish coat in ONE day. Paint phase 2 = LAST work task, gated on every finish trade.
- Flooring gated on `paint.phase_1` + shower pan set (wet area present) — Rule 4L.
- Trim gated on `flooring.install` (NOT paint) — Rule 4L.
- Cabinets/vanity gated on flooring + paint phase 1.
- Electrical finish gated on paint phase 1 (NOT phase 2) — Rule 4L.
- Plumbing finish gated on cabinets + flooring + tile grout.
- HVAC-stagger rule 4N: `hvac.minisplit_install` depends on `electrical.finish` to keep interior trade count ≤ 2.

## Master bathroom
- Custom tile shower 7' x 4' → waterproofing + wall tile + mosaic floor tile + niche + bench + dual-valve diverter `(extracted/scope.md#Master bathroom)`.
- 72" double vanity ($1K), 2 faucets, 2 mirrors, 2 vanity lights, commode, exhaust fan/light `(extracted/scope.md#Master bathroom)`.
- Tile allowances: $3/sqft wall, $6/sqft mosaic floor. Grout/seal apply Rule 4L (last predecessor before plumbing finish).

## Basement storage
- Frame + drywall + Level 3 + paint + 1 lighting fixture; concrete slab left unfinished `(extracted/scope.md#Basement storage finish)`.

## Elevator shaft (in-addition feature — plans-resolved)
- 4' x 4' framed shaft on second floor addition, next to primary bath / linen `(extracted/plans.md)`. Framing + 30A rough-in electrical only. TCR coordinates with 101 Mobility on homeowner request.

## Closeout
- Debris removal + final cleaning + inspection coordination `(extracted/scope.md#Closeout)`.
- Apply addition_rules Will's walkthrough: `closeout.wills_walkthrough` (0.5d, general, FS lag 1 after `inspect.final_bundled`) as final task *(rule: job_type:job_types/addition/rules/addition_rules.md, rank 200)*.

## Procurement chains to emit (all in `procurement_long_leads` phase per Rule "CRITICAL: do NOT put procurement chains in pre_construction")
- **Windows** — order/wait/checkpoint chain, `wait.windows` lead_time 21 calendar days (assuming stock, confirm at interview).
- **LVL beam** — chain with 14 calendar days safety default (confirm stock vs custom at interview; if custom, bump to 21).
- **Electrical subpanel + main breaker** — 14-day chain.
- **Mini-split unit** — order at dried-in, 14-day chain.
- **Custom tile** — 14-21 calendar days chain, ordered ~3wk before tile install; gated on `checkpoint.selections_finalized`.
- **LVT flooring** — 7-day chain, may collapse to single 1d order task.
- **Vanity + master bath fixtures** — 7-day chain, may collapse.
- **Paint** — 1-day order 1wk before paint phase 1 (collapsed).
- **Exterior door** — if custom, 21-28 day chain; if stock, collapse.
- **Optional tankless (IF exercised)** — 7-14 day chain gated on `checkpoint.tankless_arrived`.

## Explicit exclusions (change-order triggers, NOT scheduled)
- Rock excavation, unsuitable soils `(scope.md#Exclusions)`.
- Concealed conditions discovered during demo `(scope.md#Exclusions)`.
- Septic relocation / new septic / grinder pump install `(scope.md#Exclusions)`.
- French drains / foundation waterproofing / drainage `(scope.md#Exclusions)`.
- Closet system (optional package, decision unmade).
- Tankless WH (optional package — see q.tankless_or_existing_wh).
- Elevator system itself.
- Utility upgrades (specifically called out on tankless option).

## Pre-construction anchors (rule-required, offsets locked)
- `general.permitting` — 1d, offset 15 *(rule: company:editor_rules.md)*.
- `general.pre_construction_walkthrough` — 0.5d, offset 15.
- `checkpoint.selections_finalized` — milestone, offset 15, `lead_up_working_days: 5`.
- `permit.tdec_septic` — lead_time 42 cal-d, offset 30 (**HARD rule**).
- `prep.amperage_check` — 0.5d, offset 15.
- `checkpoint.equipment_confirmed_demo` — milestone, offset 10.

## Scheduling risks (surface in generations' `warnings[]`)
1. **Siding scope-vs-drawings conflict** — brick + lap vs vinyl. Fatal to exterior finishes phase estimate if not resolved.
2. **Concealed roof tie-in** — multiple valleys + chimney per plans page 5. Standard 3-day buffer applies but this is a higher-than-typical risk tie-in.
3. **TDEC septic** — 6-week lead is the anchor. Any delay pushes on-site start proportionally.
4. **Grinder pump decision (change order)** — must resolve before rough plumbing (~Jul 15 in a nominal schedule). Currently excluded but may be forced by TDEC results.
5. **Tankless option** — customer decision affects Rule 4H tank-set sequence and procurement chain.
6. **LVL load path** — if new floor/roof bears on LVL, framing.floor_system gates on LVL; if not, independent (default per addition_rules).
7. **Bedroom 2/3 window relocations shown on plans but not in breakdown row detail** — labor may be under-budgeted for these retrofit windows.
8. **Existing hallway switch relocation retrofit** — small but not surfaced as a task; must be captured in retrofit_zones or existing_electrical_touch-ups component.
