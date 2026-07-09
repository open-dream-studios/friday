---
generation_kind: intelligence_interview_v2
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWD0MGKWRJD1TPARY49TEJV0/jobs/308-evergreen-street-addition_JOB-01KWD0NZ8V220FX8SJQ929RKVZ/manifest.json
  - _projects/308-evergreen-street_APPPROJ-01KWD0MGKWRJD1TPARY49TEJV0/jobs/308-evergreen-street-addition_JOB-01KWD0NZ8V220FX8SJQ929RKVZ/intelligence/extracted/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KWD0MGKWRJD1TPARY49TEJV0/jobs/308-evergreen-street-addition_JOB-01KWD0NZ8V220FX8SJQ929RKVZ/intelligence/extracted/breakdown.md
  - _projects/308-evergreen-street_APPPROJ-01KWD0MGKWRJD1TPARY49TEJV0/jobs/308-evergreen-street-addition_JOB-01KWD0NZ8V220FX8SJQ929RKVZ/intelligence/extracted/plans.md
  - _projects/308-evergreen-street_APPPROJ-01KWD0MGKWRJD1TPARY49TEJV0/jobs/308-evergreen-street-addition_JOB-01KWD0NZ8V220FX8SJQ929RKVZ/intelligence/applicable_rules.json
  - _projects/308-evergreen-street_APPPROJ-01KWD0MGKWRJD1TPARY49TEJV0/jobs/308-evergreen-street-addition_JOB-01KWD0NZ8V220FX8SJQ929RKVZ/interview/round-1.md
  - _projects/308-evergreen-street_APPPROJ-01KWD0MGKWRJD1TPARY49TEJV0/jobs/308-evergreen-street-addition_JOB-01KWD0NZ8V220FX8SJQ929RKVZ/interview/round-2.md
---

# What we know — 308 Evergreen Street addition

## Customer & job

- Customer: "308 Evergreen Street" (manifest.json). Job type: addition. Status: in_progress. Started 2026-06-30.
- Job slug: `308-evergreen-street-addition_JOB-01KWD0NZ8V220FX8SJQ929RKVZ`. AppProject `APPPROJ-01KWD0MGKWRJD1TPARY49TEJV0`.
- Project pricing per scope = "Total Investment $173,850"; cost-breakdown CSV grand total = $100,778.92. **The two numbers disagree by ~$73K** — likely markup + optional packages + contingency, but unconfirmed (extracted/breakdown.md "Discrepancy" section).

## Scope (what's being built)

- Two-story addition ~30' × 10' (~295 sf per floor, 590 sf total addition footprint per drawings) tying into an existing single-family home (extracted/scope.md "Footprint").
- New PRIMARY BEDROOM (~29'-5" × 10'-0") + MASTER BATHROOM (custom tile shower ~7' × 4', 72" double vanity) + walk-in closet, all on the upper floor of the addition (extracted/scope.md "Footprint" + extracted/plans.md "Floor plan readings").
- Basement-level storage finished (frame + drywall + paint + 1 light fixture; concrete floor unfinished) (extracted/scope.md "Finishes").
- Existing primary bedroom (~12'5" × 16') is also remodeled — framing mods + drywall + paint + new LVT + full trim (extracted/scope.md "Finishes").
- Existing hall bathroom is modified: window infill + new acrylic shower (replacing tub/shower combo) + repaint (extracted/scope.md "Special features").
- Roof: new 3/12 gable system tying into existing 6/12 roof; architectural asphalt shingles to match existing; synthetic underlayment, drip edge, ridge vent, fascia, vinyl soffit, seamless gutters (extracted/scope.md "Framing" + extracted/plans.md "Structural decisions").
- Exterior: vinyl lap siding + new brick to match existing + new windows + (up to) 1 new exterior door (extracted/scope.md + extracted/plans.md).

## Site / structural conditions

- Standard soil, standard framing conditions, standard site access — all explicit scope assumptions (rule: company:`_company/rules/editor_rules.md`, rank 100; extracted/scope.md L17-22).
- Roof tie-in: new 3/12 onto existing 6/12 — concealed-rafter conditions above the existing ceiling are unknown until demo opens them (rule: job_type:`job_types/addition/rules/addition_rules.md`, rank 200 → concealed-roof-tie-in buffer mandatory).
- Floor plan footnote requires contractor to verify existing plumbing, venting, septic tank, HVAC locations BEFORE construction (extracted/plans.md "Things plans show").
- The elevator-shaft location is **inside the new addition footprint** (extracted/plans.md resolves the scope's spatial ambiguity via the floor plan ELEV. 4'-0" annotations). Shaft is NEW construction, not retrofit.
- **Property is on septic** (round 1, q.septic_tdec). TCR handles TDEC permit + soil-scientist coordination in-house. Grinder-pump path is OUT (round 1, q.grinder_pump_direction) — only kicks in as CO if soil scientist rejects perc.

## Trades — what's in scope and what the rules say

### Foundation

- Continuous 12"×12" footings + 4" gravel base + vapor barrier + reinforced 4" slab. Scope explicitly excludes CMU / full-height foundation walls (extracted/scope.md).
- **Monolithic pour pattern applies** (rule: company:`_company/rules/dev_rules.md` 4B, rank 100). Single pour task for footings + slab; one footing inspection; 2-day cure.

### Framing

- 2x4 @ 16" basement walls, dimensional-lumber or engineered floor system, 2x4 @ 16" exterior + interior walls. Framing labor = 146 hrs (extracted/breakdown.md).
- **(1) LVL (3-ply 14", ~15'-6" span) bears floor/roof load above** — NOT independent retrofit (round 1, q.lvl_load_bearing). `framing.floor_system` gates on `structural.install_lvl`. Temp shoring included. **Engineer-stamped sizing required** before procurement or installation — engineering is a new pre-construction predecessor.
- Future-elevator shaft is framing-only, NOT install. Location confirmed in new addition footprint per drawings.
- **Roof framing = stick-frame** (round 1, q.roof_framing). Confirms job-type belief default (job_types/addition/beliefs/stick_frame_default_for_small_additions.md, rank 200). **Skip `procurement.trusses`.** Lumber package collapses into framing-phase just-in-time order (rule: company:`_company/rules/dev_rules.md` 4Q).

### Plumbing

- Master bath: 2 lavs + toilet + 1 custom shower + dual-valve diverter. Full rough-in supply/waste/vent. Quarter-turn shutoffs (extracted/scope.md).
- **W/D relocation** with water + drain + roof venting (extracted/scope.md).
- Existing vent stacks extended through new roof.
- **Existing gas water heater stays — vent-extension only** (round 1, q.tankless_optional). Optional Tankless WH package is OUT of signed base scope (carry as optional add-on line item). **No `procurement.tank` and no `plumbing.tank_set`.** Rule 4H tank-set sequence does NOT fire.
- Plumbing rough-in min 4 days × 2 crew per Will's nominal (rule: company:`_company/rules/_examples/plumbing_rough_min_duration.md` mirrored in editor_rules.md productivity table). CSV labor (40 hrs) is below floor — rule wins.

### Electrical

- New 100A subpanel. Full rough + finish. ~12 recessed lights ($25 ea), (2) vanity lights, (1) bath vent fan/light combo, basement-storage outlets (IRC), (3) master-closet outlets, (1) upstairs-storage outlet, dimmer switches at bedroom/bath, GFCI/AFCI per code.
- **Dedicated 120V/30A circuit for the future elevator** (scope.md L78). Shaft has rough-in only; no elevator install.
- Relocate (1) existing hallway switch (drywall patch + paint included in scope).
- **Amperage-check task FIRES — service NOT verified** (round 1, q.electrical_service_amperage). `prep.amperage_check` 0.5d general, scheduled in pre_construction ~3 weeks before on-site start, requires **electrician site walk + utility coordination**. Service-upgrade-CO contingency stays on risk register until verified.

### HVAC

- One ductless **mini-split**, budget $2,500 (scope.md L94). Existing HVAC components relocated as required. (CSV HVAC material total $5,140 is mini-split + relocations — NOT a tankless add per round 1.)
- MEP rough order is **plumbing → electrical → mini-split rough** for mini-split jobs (rule: company:`_company/rules/dev_rules.md` 4G). Mini-split rough = 0.5d × 1 person; install = 1d × 1 person (editor_rules.md).
- **Existing heat pump + electrical disconnect relocate BEFORE demo** (scope.md L31; rule: job_type:`job_types/addition/rules/addition_rules.md`, rank 200, "Heat pump / HVAC relocation BEFORE demo"). 3+ working days before demo start.

### Insulation

- R13 walls, R30 attic/roof, R30 floor system (basement-to-living). All-penetration air sealing (extracted/scope.md).

### Drywall

- Level 3 finish (3 coats + sanded) for all new and patched walls.
- **Drywall consolidated** across new addition + existing bedroom remodel + basement storage + hall bath patch (rule: company:`_company/rules/editor_rules.md` "Drywall consolidation"; CSV section name "New Addition & Existing Bedroom" already reflects). 159 labor hrs → 9–11 working days consolidated.

### Interior finishes

- LVT flooring throughout designated areas at $3.00/sf allowance.
- Baseboard 5-1/4" MDF/finger-joint; casing 2-1/4" profile.
- 4 interior doors (1 pre-hung + 2 pocket per scope assumption — drawings show 4 interior + 1 exterior schedule but don't denote pocket).
- Master bath: custom tile shower 7'×4' with niche + bench + dual-valve diverter; 72" double vanity; (2) faucets/mirrors/lights; commode; exhaust fan/light.
- **Hall bath retrofit** (acrylic shower swap + window infill + drywall patch + repaint) stays in interior_finishes as a consolidated `hall_bath_mod` Component (round 1, q.customer_early_items). NOT in `site_prep/customer_early_items` — customer did NOT request early swap. Gates on `drywall.consolidated` / `paint.phase_1`.
- Paint: primer + 2 finish coats. **Two-phase paint mandatory** (rule: company:`_company/rules/dev_rules.md` 4E + editor_rules.md "Paint two phases").

### Closeout

- Will's final walkthrough mandatory on every addition (rule: job_type:`job_types/addition/rules/addition_rules.md`, rank 200, "Will's walkthrough"). `closeout.wills_walkthrough` 0.5d, FS lag 1 after `inspect.final_bundled`.
- 1-year warranty return for drywall cracking at tie-ins assumed but NOT in main schedule (rule: job_type:`job_types/addition/rules/addition_rules.md`, rank 200, "Drywall cracking").

## Sequencing (the must-respects)

1. **TDEC septic permit FIRES** — longest pole, 42 calendar days lead, `pre_construction_offset_working_days: 30` (round 1, q.septic_tdec; rule: job_type:`job_types/addition/rules/tdec_septic_permit_offset.md`, rank 200). Permit gates `excavation.dig`. **Soil-scientist perc test runs UPSTREAM of TDEC submission** — TCR to book; 14-21 days to first available perc test (round 2, q.soil_scientist). New `permit.soil_scientist_perc` predecessor anchors the earliest realistic pre-con start.
2. **Engineer-stamped LVL sizing** must precede LVL procurement (round 1, q.lvl_load_bearing). **Supplier-bundled stamp via Forte/iLevel from 84 Lumber/BMD; 3-7 business days from spec submission** (round 2, q.lvl_engineering). `prep.lvl_engineering` 1d general + `wait.lvl_engineering` 5d → FS `procurement.lvl_beam` (14d). Engineering is fast enough that LVL procurement chain (14d), not engineering, stays the binding constraint.
3. `prep.amperage_check` runs ~3 weeks before on-site start, requires electrician + utility coordination (round 1, q.electrical_service_amperage; rule: job_type:`job_types/addition/rules/addition_rules.md`, rank 200; offset 15).
4. Heat pump + electrical disconnect relocation 3+ days before demo (rule: job_type:`job_types/addition/rules/addition_rules.md`, rank 200; site_prep phase).
5. **No customer-early items** (round 1, q.customer_early_items). Hall-bath retrofit stays in interior_finishes; Rule 4V two-bucket pattern does NOT fire.
6. Foundation: monolithic pour (rule: company:`_company/rules/dev_rules.md` 4B).
7. Windows install IMMEDIATELY after `framing.roof`, in parallel with `roofing.underlayment` — NOT after dried-in milestone (rule: job_type:`job_types/addition/rules/addition_rules.md`, rank 200 + dev_rules.md 4J).
8. MEPs (electrical, plumbing, mini-split) gated on `roofing.underlayment` + `windows.install` — NOT on dried-in milestone (rule: job_type:`job_types/addition/rules/addition_rules.md`, rank 200 + dev_rules.md 4I).
9. Bundled rough inspection: electrical + plumbing + mini-split-rough + framing all on one day, one inspector (rule: company:`_company/rules/dev_rules.md` 4C + editor_rules.md). Followed by 2-day buffer.
10. Concealed roof tie-in buffer: SS lag 1 after `framing.roof`, 3-day lead_time (rule: job_type:`job_types/addition/rules/addition_rules.md`, rank 200, "Concealed roof tie-in").
11. Paint two-phase: phase 1 after drywall sand; phase 2 last, gated on every finish trade (rule: company:`_company/rules/dev_rules.md` 4E/4F).
12. Interior trade cap: max 2 trades on site at once. HVAC stagger after electrical-finish when the 3-trade overlap pops (rule: company:`_company/rules/dev_rules.md` 4N + editor_rules.md "Crew concurrency").

## Procurement (the 3-task pattern applies to each)

Per rule: company:`_company/rules/dev_rules.md` 4R + editor_rules.md "Procurement pattern":

| Item | Trigger | Lead days | Notes |
|---|---|---:|---|
| Windows — DH (stock) | FIRES (round 1) | 21 stock | (3) 36"×60" DH = stock per PM. Single `wait.windows_stock` task. |
| Window — transom (semi-custom) | FIRES (round 1) | 42 cal (budget 6 weeks) | Andersen/Pella/MI stocking distributor (round 2, q.transom_semi_custom_lead). Best case 14-21d regional stock; budget 6 weeks safe. **Transom lead EXCEEDS DH 21d → transom = binding constraint on `windows.install`.** |
| Exterior door | FIRES (round 1) | 14 stock | PM confirmed stock per q.window_order_type. |
| LVL engineer stamp | FIRES (round 1, round 2) | 5–7 (supplier-bundled) | `prep.lvl_engineering` 1d + `wait.lvl_engineering` 5d. Forte/iLevel via 84 Lumber/BMD. Pre-con phase. |
| LVL beam | FIRES (round 1) | 14 (after stamped sizing) | `procurement.lvl_beam` FS-after `wait.lvl_engineering`. Procurement chain (14d) is the binding constraint, not engineering. |
| Soil scientist perc test | FIRES (round 2) | 14–21 cal | `permit.soil_scientist_perc` (TCR books). Pre-con phase; anchors UPSTREAM of TDEC submission. |
| Subpanel | Always | 14 | 100A panel. |
| Mini-split unit | Always | 7–14 | Order at dried-in per editor rules. |
| Tile (custom master bath) | Always | 14–21 | Master bath custom tile shower + mosaic floor. |
| Vanity (72") | Always | 7 stock | Allowance item. |
| Fixtures (faucets, mirrors, commode) | Always | 7 | Allowance items. |
| LVT flooring (stock) | Always | 7 (collapse to 1d order) | $3/sf allowance. |
| Paint | Always | 1–2 (collapse to 1d order) | 1 week before paint phase 1. |
| TDEC septic permit | **FIRES** (round 1, septic) | 42 calendar | Phase: pre_construction; offset 30 working days. |
| Trusses | **SKIP** (round 1, stick-frame) | — | PM confirmed stick-frame; no truss procurement. |
| Tankless water heater | **SKIP** (round 1, tankless OUT) | — | Optional add-on; not in base scope. |
| Grinder pump | **SKIP** (round 1, septic path) | — | CO contingency only if soil scientist rejects perc. |

All procurement chains live in the **`procurement_long_leads` phase**, NOT in pre_construction (rule: job_type:`job_types/addition/rules/addition_rules.md`, rank 200, "CRITICAL: do NOT put procurement chains in pre_construction"). Only the genuinely pre-con-anchored work (permits, TDEC, amperage check, **LVL engineer-stamped sizing**, selections-finalized, equipment-confirmed checkpoints) stays in pre_construction.

## Risks / known watch-items

- **Concealed roof tie-in** — single biggest schedule risk. 3-day discovery buffer reserved.
- **TDEC septic + soil scientist** — 6-week TDEC pole CONFIRMED in play (round 1). Soil-scientist perc test 14-21d UPSTREAM of submission, TCR to book (round 2, q.soil_scientist). Combined: soil-scientist booking is the **new earliest-start anchor**; TDEC chain effectively starts ~14-21d into pre-con.
- **LVL engineer-stamped sizing** — supplier-bundled via Forte/iLevel from 84 Lumber/BMD; 3-7 business days (round 2, q.lvl_engineering). Fast path — LVL procurement (14d) stays the binding constraint, not engineering. Risk-level downgraded from CRITICAL to CONTEXT.
- **Transom window lead** — 6 weeks budgeted (round 2, q.transom_semi_custom_lead). Transom EXCEEDS the 21d DH stock lead, making it the binding constraint on `windows.install`. Stock DHs arrive first; install task waits for transom.
- **Existing service amperage** — verification required pre-construction (round 1). Service-upgrade CO contingency if utility says capacity insufficient.
- **Optional tankless** — OUT of base scope (round 1). Add-on line item only.
- **Optional closet system** — modeled vs not? Affects interior finishes scope. Low-impact CONTEXT.
- **Chimney on roof plan** (extracted/plans.md) — not in scope text. Low-impact CONTEXT.
- **$73K gap between scope total $173,850 and breakdown grand total $100,779** — contract value clarity for the PM. CONTEXT.
- **Window count discrepancy** — scope says 4 (3 DH + 1 transom); drawing schedule lists 2 new (1 DH + 1 transom). Trust scope per dev-rules.
- **Pocket-vs-pre-hung door split** — scope says 1 pre-hung + 2 pocket = only 3 of the 4 interior doors. Low-impact CONTEXT.
- **Grinder-pump fallback** — only fires if soil scientist rejects perc (round 1). Watch for soil-scientist report; CO trigger if rejection.
