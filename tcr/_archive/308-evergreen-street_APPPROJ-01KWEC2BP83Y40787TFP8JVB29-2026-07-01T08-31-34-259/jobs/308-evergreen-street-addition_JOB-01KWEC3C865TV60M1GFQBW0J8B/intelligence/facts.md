---
generation_kind: intelligence_rebuild_v2
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWEC2BP83Y40787TFP8JVB29/jobs/308-evergreen-street-addition_JOB-01KWEC3C865TV60M1GFQBW0J8B/manifest.json
  - _projects/308-evergreen-street_APPPROJ-01KWEC2BP83Y40787TFP8JVB29/jobs/308-evergreen-street-addition_JOB-01KWEC3C865TV60M1GFQBW0J8B/intelligence/extracted/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KWEC2BP83Y40787TFP8JVB29/jobs/308-evergreen-street-addition_JOB-01KWEC3C865TV60M1GFQBW0J8B/intelligence/extracted/breakdown.md
  - _projects/308-evergreen-street_APPPROJ-01KWEC2BP83Y40787TFP8JVB29/jobs/308-evergreen-street-addition_JOB-01KWEC3C865TV60M1GFQBW0J8B/intelligence/extracted/plans.md
  - _projects/308-evergreen-street_APPPROJ-01KWEC2BP83Y40787TFP8JVB29/jobs/308-evergreen-street-addition_JOB-01KWEC3C865TV60M1GFQBW0J8B/intelligence/applicable_rules.json
  - _company/rules/editor_rules.md
  - _company/rules/dev_rules.md
  - job_types/addition/rules/addition_rules.md
  - job_types/addition/rules/tdec_septic_permit_offset.md
---

# Facts — what we know (pre-interview, round 1)

Synthesized from extracted inputs + rules. Groups: Customer & Job, Scope, Site, Trades, Sequencing, Procurement, Open ambiguities.

## Customer & Job

- Customer / project label: **308 Evergreen Street**. Job type: **addition**. Job ID: `JOB-01KWEC3C865TV60M1GFQBW0J8B`. *(manifest.json)*
- Started 2026-07-01; status in-progress; no completed_at yet. *(manifest.json)*
- Project totals per breakdown: labor $45,167.59 + material $52,171.33 + equipment $3,440 = **grand total $100,778.92**, over **1,287 labor hours**. *(extracted/breakdown.md § Project totals)*
- Scope-stated Total Investment: **$173,850**. Delta of $73,071 vs. breakdown grand total — unexplained (markup/GC/contingency/options). *(extracted/breakdown.md § Notes anomalies #1; extracted/scope.md § Commercial/rates)*

## Scope (what's being built)

- Two-story addition, roughly **30′ × 10′**, attached to existing home. Basement level = storage; second floor = expanded primary bedroom + master bathroom + walk-in closet. *(extracted/scope.md § Footprint)*
- Governing codes: **IRC 2018 + NEC**. *(extracted/scope.md § Customer & job)*
- Sqft numbers do not fully agree: scope 30×10 two-story = ~600 gross; CSV footprint 789; plans schedule 295 + 295 = **590 total addition area**. *(extracted/plans.md § Discrepancies row 1; extracted/breakdown.md § Notes #2)*
- New addition scope items:
  - Monolithic-appropriate foundation: 12″×12″ continuous footings + 4″ gravel base + vapor barrier + rebar/wire mesh + 4″ slab. No CMU / no full-height foundation walls. *(extracted/scope.md § Foundation)* → applies `editor_rules.md § Foundation — monolithic by default` + `dev_rules.md § 4B` monolithic pour default. **Emit as single monolithic pour, one footing inspection.** (rule: company:_company/rules/editor_rules.md, rank 100; company:_company/rules/dev_rules.md, rank 100)
  - Framing: 2×4 walls @ 16″ O.C. + engineered floor system + subfloor + (1) 3-ply 14″ LVL beam ~15′-6″ (opens existing load-bearing wall, includes temp shoring) + elevator shaft 4′×4′ framing (elevator system out of scope). *(extracted/scope.md § Framing)*
  - Roof: gable 3/12 tying into existing 6/12; truss OR rafter — **design phase pending**. Architectural shingles + synthetic underlayment + drip edge + flashing + ridge vent; fascia, vinyl soffit, seamless gutters. *(extracted/scope.md § Roof)*
  - Exterior: sheathing + WRB, vinyl siding to match existing, (4) new windows including (3) 36″×60″ DH + (1) transom (per scope) — but plans schedule shows only 2 new window units (see Open ambiguities). Up to (1) new exterior door. *(extracted/scope.md § Exterior finishes; extracted/plans.md § Discrepancies row 2)*
  - MEP: 100A subpanel + rough/finish, ~12 recessed lights, master bath fixtures, mini-split (ductless, budget $2,500), R13/R30/R30 insulation, drywall Level 3, LVT flooring, 5-1/4″ baseboard + 2-1/4″ casing, master bath custom tile shower ~7′×4′ w/ dual valve diverter + 72″ double vanity. *(extracted/scope.md § MEP; § Finishes; § Master bathroom)*
- Retrofit / early-item scope items (see Sequencing):
  - **Existing hall bath modification** — window infill, insulation, drywall, tub/shower removal, acrylic shower install (reuses existing valve+trim), PVC trim, patching + repaint. *(extracted/scope.md § Special features)*
  - **Primary Bedroom Remodel (~12′5″ × 16′)** — separate section from addition; ambiguous whether existing bedroom retrofit or finish work on new. *(extracted/scope.md § Special features)*
  - **Basement Storage finish** — inside addition footprint, not a retrofit. *(extracted/scope.md § Special features)*
  - **Existing heat pump + electrical disconnect relocation** — required before addition can be built. *(extracted/scope.md § Special features)*
  - **Existing gas water heater vent extension through new roof** — base scope keeps existing WH. *(extracted/scope.md § Special features)*
  - **Hallway switch relocation** — retrofit outside addition footprint. *(extracted/scope.md § Special features)*
- Explicit exclusions:
  - Rock excavation / unsuitable soils / unusual structural mods → change order. *(extracted/scope.md § Assumptions)*
  - Concealed conditions found during demo → change order. *(extracted/scope.md § Assumptions)*
  - Septic relocation / replacement / grinder pump costs → change order. *(extracted/scope.md § Septic/sewer)*
  - French drains / foundation waterproofing / drainage improvements. *(extracted/scope.md § Water management)*
  - Elevator system itself (only shaft framing + 30A rough-in included). *(extracted/scope.md § Special features)*

## Site

- Plans title-block address says 647 AA Deakins Rd, Jonesborough TN — project label says 308 Evergreen Street. Likely designer template artifact; PM to confirm right drawings. *(extracted/plans.md § Discrepancies row 5)*
- Existing chimney sits at the roof tie-in zone per roof plan — not called out in scope's roof section; adds flashing complexity + concealed-condition risk. *(extracted/plans.md § Things plans show scope doesn't mention)*
- Plans note: "*Contractor to verify location of existing plumbing, venting, septic tank, and HVAC before construction*" — property IS on septic. *(extracted/plans.md § Floor plan)*
- Existing hall bath (retrofit zone), Bedroom 2, Bedroom 3, garage, lounge, kitchen/dining, front porch, covered deck all shown on floor plan — occupied living space during construction. *(extracted/plans.md § Floor plan)*
- Multiple existing windows are shown as "relocated" on left + right elevations — extra retrofit labor not explicit in scope. *(extracted/plans.md § Retrofit indicators)*

## Trades (what work + which trades touch this job)

- **Excavation / foundation**: 78 hrs, $7,064.78. Monolithic pour default; single footing inspection covers footings + slab. *(extracted/breakdown.md row 3; rule: company:editor_rules.md rank 100)*
- **Structural mods (LVL)**: 60 hrs, $4,539.80. Standard LVL 3-ply 14″; 1 week supplier lead default, use 14-day safety buffer (custom/PT = 21 days). *(extracted/breakdown.md row 4; rule: job_type:addition_rules.md § Structural long-lead items, rank 200)*
- **Framing (floor + walls + elevator shaft)**: 146 hrs, $14,007.55. 380 hrs total across structural + shell (rows 3–6). *(extracted/breakdown.md rows 3–6)*
- **Roofing**: 96 hrs, $9,652.30. Includes framing + sheathing + roofing system. Shingles typically 1 day for a 590-sqft addition. *(extracted/breakdown.md row 6; rule: company:editor_rules.md § Default productivity, rank 100)*
- **Exterior (siding/trim/gutters)**: 72 hrs, $5,731.31. Run as same-crew block per editor rules. *(extracted/breakdown.md row 7; rule: company:editor_rules.md § Same-crew exterior pattern, rank 100)*
- **Windows/doors**: 44 hrs, $3,665.80. *(extracted/breakdown.md row 8)*
- **Electrical**: 78 hrs, $6,722.13. Subpanel = 1 day/1 person by rule. *(extracted/breakdown.md row 9; rule: company:editor_rules.md § Productivity, rank 100)*
- **Plumbing**: 40 hrs, $3,516.80. Includes master bath + W/D relocation → default 4 days × 2 crew per Will's floor. *(extracted/breakdown.md row 10; rule: company:editor_rules.md § Plumbing rough-in duration, rank 100)*
- **HVAC**: 36 hrs, $6,503.36. **Mini-split scope** (budget $2,500) → mini-split rough = 0.5d/1 person, install = 1d/1 person. *(extracted/breakdown.md row 11; rule: company:editor_rules.md § HVAC sequencing, rank 100)*
- **Insulation**: 44 hrs, $3,084.44. Typical addition = 1 day install. *(extracted/breakdown.md row 12)*
- **Drywall (consolidated)**: 159 hrs, $9,330.70. Row title "New Addition & Existing Bedroom" → consolidated block per rules; retrofit hall bath patch rolls in. *(extracted/breakdown.md row 13; rule: company:editor_rules.md § Drywall consolidation, rank 100; job_type:addition_rules.md § Retrofit drywall consolidates, rank 200)*
- **Interior finish (paint/trim/flooring)**: 162 hrs, $12,831.58. *(extracted/breakdown.md row 14)*
- **Master bath tile**: 88 hrs, $7,154.50. Custom tile shower ~7′×4′ + shower niche + bench + dual valve diverter. *(extracted/breakdown.md row 15)*
- **Hall bath mod + primary bedroom remodel + closeout (bundled)**: 72 hrs, net −$1,714.20 (material credit $-4,199 = tub value or allowance offset). *(extracted/breakdown.md row 16)*

## Sequencing (rule-derived, before PM interview)

- **Pre-construction anchors (all `pre_construction_offset_working_days` set):**
  - `general.permitting` — 1d, offset 15 working days. *(rule: company:editor_rules.md § Permits, rank 100)*
  - `checkpoint.selections_finalized` — 0d milestone, offset 15. *(rule: company:dev_rules.md § 4P, rank 100)*
  - `prep.amperage_check` — 0.5d, offset ~15. Scope has subpanel + assumes main service capacity but no verification task → **must emit** and flag warning per addition_rules.md. *(rule: job_type:addition_rules.md § Existing electrical service, rank 200)*
  - `permit.tdec_septic` — `kind: lead_time`, `lead_time_days: 42` calendar, **`pre_construction_offset_working_days: 30`** — ONLY if home is confirmed on septic (see Open ambiguities). *(rule: job_type:tdec_septic_permit_offset.md rank 200; job_type:addition_rules.md § Septic-TDEC rank 200)*
- **Procurement long-leads phase (`procurement_long_leads`, NOT in `pre_construction`):**
  - `procurement.windows` — 21–28 days if stock (verify at interview); 35–49 if custom. *(rule: job_type:addition_rules.md § Windows rank 200)*
  - `procurement.lvl` — default 14 days safety (standard 3-ply 14″); 21 if custom/PT. *(rule: job_type:addition_rules.md § LVL rank 200)*
  - `procurement.electrical_panel` — 7–14 days. *(rule: company:editor_rules.md § Lead-time table rank 100)*
  - `procurement.hvac_equipment` (mini-split) — 7–14 days, ordered at dried-in. *(rule: company:editor_rules.md § Material ordering universal rule rank 100)*
  - `procurement.tile` (custom shower tile) — 14–21 days. *(rule: company:editor_rules.md § Lead-time table rank 100)*
  - `procurement.lvt` — 7 days stock. *(rule: company:editor_rules.md § Lead-time table rank 100)*
  - `procurement.paint`, `procurement.vanity`, `procurement.fixtures` — short waits, use collapsed 1-day order pattern per rule 4R exception. *(rule: company:dev_rules.md § 4R exception rank 100)*
  - NOT emitted: `procurement.trusses` — scope says "truss OR rafter framed, determined during design phase" which is ambiguous; addition ~590–789 sqft (well under 800), roof span ~10′ (well under 24′). Default **stick-frame** per rule 4Q + addition_rules.md § Trusses conditional (rank 200). PM Interview must confirm. *(rule: company:dev_rules.md § 4Q rank 100; job_type:addition_rules.md rank 200)*
  - NOT emitted: `procurement.tank` — scope keeps existing WH ("extend existing gas WH vent through new roof"); tankless is Optional Package, not in base contract. If tankless option is confirmed active, add `procurement.tankless` + `plumbing.tank_set` per rule 4H. *(rule: company:dev_rules.md § 4H rank 100)*
- **Site prep (before demo):**
  - `prep.heat_pump_relocate` — 1d, hvac; minimum 3 working days before demo. *(rule: company:dev_rules.md § 4K rank 100; job_type:addition_rules.md § Heat pump relocation rank 200)*
  - `prep.electrical_disconnect_relocate` — 0.5d, electrical. *(rule: job_type:addition_rules.md § Heat pump relocation rank 200)*
  - `customer_early_items` Component (if PM confirms) — likely `early.acrylic_shower_swap` per addition_rules.md customer-early-items pattern. See Open ambiguities. *(rule: company:dev_rules.md § 4V rank 100; job_type:addition_rules.md § Customer-requested early items rank 200)*
  - `equipment.dumpster_arrive` + `equipment.demo_machines_arrive` — 0.5d ea day before demo. *(rule: company:editor_rules.md § Equipment day-before rank 100)*
- **Structural + shell:**
  - Excavation → form_and_prep → inspect.footing (FS lag 1) → monolithic_pour → cure (2 cal-d) → framing. *(rule: company:dev_rules.md § 4B example rank 100)*
  - Basement walls → floor system → exterior walls → interior walls → roof → sheathing.
  - LVL sub-chain runs INDEPENDENTLY of new framing (unless load bears on LVL — see Open ambiguities). *(rule: job_type:addition_rules.md § LVL temporary shoring rank 200)*
  - `windows.install` — FS after `framing.roof` + `procurement.windows` arrived, in parallel with `roofing.underlayment`. NOT after dried-in. *(rule: job_type:addition_rules.md § Windows install rank 200; company:dev_rules.md § 4J rank 100)*
  - `roof.concealed_buffer` — 3 cal-d SS lag 1 after `framing.roof` (mandatory addition warning if missing). *(rule: job_type:addition_rules.md § Concealed roof tie-in rank 200; § Mandatory addition warnings rank 200)*
- **Rough trades (MEP order for mini-split scope):**
  - Order: plumbing → electrical → mini-split rough. *(rule: company:editor_rules.md § HVAC sequencing rank 100)*
  - All gated on `roofing.underlayment` + `windows.install` (NOT `milestone.dried_in`). *(rule: job_type:addition_rules.md § MEPs gated on underlayment+windows rank 200; company:dev_rules.md § 4I rank 100)*
  - Base scope keeps existing WH → NO `plumbing.tank_set` predecessor for `plumbing.rough_in`. Confirm with PM if tankless option activated. *(rule: company:dev_rules.md § 4H scope-condition rank 100)*
- **Bundled rough inspection + buffer:**
  - `inspect.rough_bundled` — 0.5d, one inspector for electrical + plumbing + mini-split + framing, FS lag 1 scheduling lead. *(rule: company:dev_rules.md § 4C rank 100; company:editor_rules.md § Bundled rough rank 100)*
  - `buffer.post_rough_inspection` — 2 working days min (4 for larger jobs). *(rule: company:dev_rules.md § 4D rank 100)*
  - `equipment.insulation_material_arrival` — same day as `inspect.rough_bundled` per Will's TCR rule. *(rule: company:editor_rules.md § Material delivery tied to inspection rank 100)*
- **Insulation → drywall → paint two-phase:**
  - Insulation 1d + insulation inspection 0.5d → drywall consolidated 9–11d (roll retrofit hall-bath drywall patch in). *(rule: company:editor_rules.md § Drywall consolidation rank 100; job_type:addition_rules.md § Retrofit drywall consolidates rank 200)*
  - `paint.phase_1` = 1d (spray primer walls+ceilings AM, ceiling finish PM per Will's sequence). *(rule: company:dev_rules.md § 4E rank 100)*
  - `paint.phase_2` = 1d, FS after ALL finish trades (trim + flooring + cabinets/vanity + tile grout + plumbing finish + electrical finish + mini-split install). *(rule: company:dev_rules.md § 4F rank 100)*
- **Interior finish dependencies (strict per rule 4L):**
  - `flooring.install` → FS after `paint.phase_1` AND `tile.shower_substrate` (wet area present).
  - `tile.shower_substrate` → FS after `paint.phase_1`.
  - `trim.install` → FS after `flooring.install`.
  - `electrical.finish` → FS after `paint.phase_1`.
  - `plumbing.finish` → FS after vanity + flooring + tile grout.
  - **HVAC stagger (Rule 4N)**: mini-split install serialized AFTER `electrical.finish` (default when 3-trade finish overlap present). *(rule: company:dev_rules.md § 4N rank 100; company:editor_rules.md § HVAC stagger rank 100)*
- **Closeout:**
  - `inspect.final_bundled` — ONE inspector, ONE day. *(rule: company:dev_rules.md § 4M rank 100)*
  - `closeout.wills_walkthrough` — 0.5d, FS lag 1 after final inspection (mandatory addition-final task). *(rule: job_type:addition_rules.md § Will's walkthrough rank 200)*
- **Assumptions to carry into `assumptions[]`:**
  - 1-year warranty drywall crack return budgeted separately (standard TCR addition). *(rule: job_type:addition_rules.md § Drywall cracking rank 200)*
  - Weather buffer NOT modeled for roofing/siding/exterior paint (v0.1 behavior). *(rule: company:dev_rules.md § 12 rank 100)*

## Procurement (chain-level summary)

Every long-lead item uses the 3-task pattern `order.X → wait.X → checkpoint.X_arrived → X.install`. Chains live in `procurement_long_leads` phase.

| Item | Chain type | Lead time default | Trigger to verify |
|---|---|---|---|
| Windows | 3-task | 21 cal-d (stock) OR 35 cal-d (custom) | q.window_order_type |
| Electrical panel | 3-task | 14 cal-d | none |
| LVL beam | 3-task | 14 cal-d (safety); 21 if custom/PT | q.lvl_type |
| Mini-split | 3-task | 14 cal-d | order at dried-in |
| Tile (custom shower) | 3-task | 21 cal-d | selections lock |
| LVT | 3-task | 7 cal-d | selections lock |
| Paint | collapsed 1-day order | 7 cal-d | 1 week before phase 1 |
| Vanity (72″ dbl) | 3-task | 7 cal-d | selections lock |
| Fixtures (faucets, commode, mirrors, exhaust fan) | collapsed 1-day order | 7 cal-d | selections lock |
| Exterior door | 3-task | 21 cal-d (custom) or collapsed if stock | q.window_order_type covers door too |
| Trusses | NOT emitted (stick default) | — | q.roof_framing |
| Tankless WH | NOT emitted (optional pkg) | — | q.tankless_option_status |
| TDEC septic permit | lead_time (not 3-task) | 42 cal-d + offset 30 | q.septic_direction |
| Grinder pump | NOT emitted (change order) | — | q.septic_direction |

## Open ambiguities (drive the interview)

1. **Home on septic or city sewer** — scope references TDEC AND grinder pump evaluation. Plans confirm existing septic tank on property. Base scope excludes TDEC/grinder costs. Determines whether `permit.tdec_septic` fires. *(extracted/scope.md § Septic/sewer; extracted/plans.md § Floor plan note)*
2. **Roof framing method** — scope says "truss OR rafter framed, determined during design phase." Small addition (< 800 sqft, roof span ~10′) points to stick-frame per rule 4Q, but requires PM confirm. *(extracted/scope.md § Roof; rule: job_type:addition_rules.md § Trusses conditional rank 200)*
3. **LVL loading path** — scope has LVL replacing existing load-bearing wall. Question is whether the new addition's floor/roof load bears on that LVL location (drives whether new framing depends on LVL install). *(extracted/scope.md § Framing; rule: job_type:addition_rules.md § LVL temporary shoring rank 200)*
4. **"Primary Bedroom Remodel" section** — is this the existing primary bedroom being retrofitted separately, or finishing work on the new addition's primary bedroom? Placement changes Component + phase. *(extracted/scope.md § Special features; extracted/plans.md § Floor plan)*
5. **Hall bath acrylic shower — early item vs. main-scope retrofit** — Will's `customer_early_items` pattern (addition_rules.md § Customer-requested early items) applies IF the customer asked TCR to do this before main demo. Emit as `early.acrylic_shower_swap` in `customer_early_items` Component if yes; otherwise as `retrofit.hall_bath_*` in `interior_finishes` phase. *(rule: job_type:addition_rules.md rank 200; company:dev_rules.md § 4V rank 100)*
6. **Tankless WH option** — CSV title says "Incl. Tankless WH Option" but scope explicitly lists tankless as Optional Package. If active, add `procurement.tankless` + `plumbing.tank_set` chain; if not, no WH procurement task and rough-in proceeds without tank predecessor. *(extracted/breakdown.md § Notes #5; extracted/scope.md § Optional packages)*
7. **Window count / spec discrepancy** — scope says (4) windows including (3) 36″×60″ DH; plans schedule lists only 2 new window units (3′×3′ DH + 3′×1′ transom) plus relocated existings. Materially affects procurement + install duration. *(extracted/plans.md § Discrepancies row 2)*
8. **Window order type (stock vs. custom)** — sizes look stock, but PM to confirm. Drives lead time (21 vs. 35 cal-d). *(rule: job_type:addition_rules.md § Windows rank 200)*
9. **Existing main electrical service capacity** — scope assumes existing main can support new 100A subpanel; addition_rules.md requires an `amperage_check` before contract. *(rule: job_type:addition_rules.md § Existing electrical service rank 200)*
10. **Concealed roof tie-in around existing chimney** — plans show chimney at tie-in zone (not called out in scope). Adds flashing + concealed condition risk beyond standard buffer. *(extracted/plans.md § Retrofit indicators + § Things plans show scope doesn't mention)*
11. **Grand-total delta** ($100,778 breakdown vs. $173,850 scope Total Investment) — unexplained. Doesn't affect the TaskGraph directly but PM should reconcile before generating downstream schedule + PEP.
12. **Address / drawing set mismatch** — plans title block reads 647 AA Deakins Rd, project label reads 308 Evergreen Street. Confirm right drawing set. *(extracted/plans.md § Discrepancies row 5)*
13. **Interior doors 3-vs-4 count** — scope says (4) total with only 3 typed out (1 pre-hung + 2 pocket). What's the 4th? *(extracted/scope.md § Interior doors)*
14. **Pocket vs. pre-hung split** — plans schedule doesn't distinguish; scope specifies 2 pocket + 1 pre-hung. Confirm.
