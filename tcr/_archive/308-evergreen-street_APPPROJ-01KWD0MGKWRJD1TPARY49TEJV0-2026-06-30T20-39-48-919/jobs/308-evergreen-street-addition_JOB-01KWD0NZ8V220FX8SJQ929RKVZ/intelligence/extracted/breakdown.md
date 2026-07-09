---
generation_kind: intelligence_rebuild_v2
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWD0MGKWRJD1TPARY49TEJV0/jobs/308-evergreen-street-addition_JOB-01KWD0NZ8V220FX8SJQ929RKVZ/inputs/files/308_Evergreen_Addition.xlsx - Summary (1).csv.txt
  - _projects/308-evergreen-street_APPPROJ-01KWD0MGKWRJD1TPARY49TEJV0/jobs/308-evergreen-street-addition_JOB-01KWD0NZ8V220FX8SJQ929RKVZ/inputs/scope.md
---

# Cost breakdown distillation — 308 Evergreen Street

Source: `Summary` tab of `308_Evergreen_Addition.xlsx`.

## Project totals (CSV header rows)

- Labor: $45,167.59
- Material: $52,171.33
- Equipment: $3,440.00
- **Grand Total: $100,778.92**
- Total labor hours: 1,287.00

**Discrepancy — flag for PM:** scope PDF lists "Total Investment: $173,850" (scope.md L121); breakdown CSV grand total is $100,778.92. Gap of ~$73K. The $173,850 likely includes markup, the two optional packages, the allowance schedule, contingency, and/or "Total Investment" pricing distinct from raw cost. **Do not pass scope's $173,850 through as the customer contract value without PM confirmation.**

## Project meta (CSV header)

- Project: "Simons Addition – 30'×10' Two-Story + Bedroom Remodel"
- Source scope: `Simons_Addition_Scope_v2.txt`
- Template anchor: `Basement_Remodel_Breakdown_Locked_Template_v1.xlsx`
- Overall Footprint: 789 sf (CSV) — does not equal 295+295 = 590 sf shown on the addition-area lines. Confirm whether 789 includes the bedroom-remodel area (~12'5"×16' ≈ 199 sf would close the gap).
- Ceiling height: 8'

## Per-section totals (CSV rows 10-26)

| Section | Labor $ | Material $ | Equip $ | Section Total | Labor hrs |
|---|---:|---:|---:|---:|---:|
| General Conditions, Permitting & Pre-Construction | 2,316.08 | 2,130.00 | 0.00 | 4,446.08 | 56 |
| Selective Demolition & Site Work | 1,982.00 | 2,040.00 | 220.00 | 4,242.00 | 56 |
| Excavation, Foundation – Footings & Slab | 2,698.60 | 2,416.18 | 1,950.00 | 7,064.78 | 78 |
| Structural Modifications – LVL Beam & Shoring | 2,117.80 | 2,422.00 | 0.00 | 4,539.80 | 60 |
| Framing – Floor System, Walls & Elevator Shaft | 5,037.50 | 8,850.05 | 120.00 | 14,007.55 | 146 |
| Roof Framing, Sheathing & Roofing System | 3,319.80 | 5,997.50 | 335.00 | 9,652.30 | 96 |
| Exterior Finishes – Siding, Trim & Gutters | 2,474.70 | 2,696.61 | 560.00 | 5,731.31 | 72 |
| Windows, Exterior Door & Weatherproofing | 1,493.80 | 2,172.00 | 0.00 | 3,665.80 | 44 |
| Electrical – 100A Subpanel, Rough-In & Finish | 3,042.00 | 3,680.13 | 0.00 | 6,722.13 | 78 |
| Plumbing – Rough-In, Master Bath & W/D Relocation | 1,356.80 | 2,160.00 | 0.00 | 3,516.80 | 40 |
| HVAC – Mini Split, Tankless WH & Relocations | 1,363.36 | 5,140.00 | 0.00 | 6,503.36 | 36 |
| Insulation & Air Sealing | 1,493.80 | 1,590.64 | 0.00 | 3,084.44 | 44 |
| Drywall – New Addition & Existing Bedroom | 5,428.35 | 3,647.35 | 255.00 | 9,330.70 | 159 |
| Interior Finish Carpentry, Painting & Flooring | 5,540.30 | 7,291.28 | 0.00 | 12,831.58 | 162 |
| Master Bathroom – Custom Tile Shower & Finishes | 3,017.90 | 4,136.60 | 0.00 | 7,154.50 | 88 |
| Existing Hall Bath Mod, Bedroom Remodel & Closeout | 2,484.80 | **−4,199.00** | 0.00 | **−1,714.20** | 72 |

## Anomalies + flags

- **Negative section total — "Existing Hall Bath Mod, Bedroom Remodel & Closeout"** = −$1,714.20 (material = −$4,199). This matches the dev-rules edge-case pattern: probable credit/rebate/scope-subtraction. With labor_hours = 72 (above the 40-hour threshold), this is NOT a 1–2 close-out task — actual work happens here (hall bath retrofit + existing bedroom remodel + closeout walkthrough). Surface for human resolution; do NOT collapse the work just because the total is negative.
- **HVAC section name "Mini Split, Tankless WH & Relocations"** includes "Tankless WH" — but the tankless is listed as an OPTIONAL PACKAGE in the scope ($6,500). Confirm whether this CSV section already bakes the tankless allowance into the line, or whether the tankless is a separate add. Material total $5,140 for HVAC suggests mini-split ($2,500) + tankless allowance components (heater unit) are commingled.
- **HVAC labor_hours = 36 only.** Mini-split rough+install per editor rules is 0.5d + 1d = 1.5 days @ 1 person ≈ 12 hours. 36 hours suggests additional HVAC scope (relocations) — consistent with "Relocate existing HVAC components" + tankless add.
- **Plumbing labor_hours = 40** — at 2 crew, that's 2.5 days. Below Will's nominal 4d × 2 crew (32 hours minimum) for any master-bath job. Plumbing section breakdown LOOKS LIGHT for: master bath rough + W/D relocation + vent stack extensions + existing gas WH vent extension. Editor-rules min duration 4d × 2 = 64 hours. Resolve in task_graph (apply rule's 4-day floor regardless of breakdown hours).
- **Framing labor_hours = 146** — heuristic at 3 crew ≈ 6.1 days. Editor-rules template for 2-story addition splits this into basement_walls / floor_system / exterior_walls / interior_walls / roof / sheathing.
- **Drywall labor_hours = 159** — heuristic at 3 crew ≈ 6.6 days, plus cure waits ≈ 9-11 consolidated. Section name explicitly says "New Addition & Existing Bedroom" so retrofit drywall is consolidated as the rule wants.

## Silent omissions (scope items missing OR thin in CSV)

- No section line for **TDEC septic permit fee** ($500 per addition rules + scope.md L26). Pre-Construction GC labor $2,316 likely covers PM time but no separate permit-fee line.
- No section line for **dump trailer pulls** at $450 each (scope rate). Demo Equipment $220 + Roofing Equipment $335 are too small to be the entire haul-away. PM should price the trailer pulls separately or confirm they're rolled into Equipment.
- No section line for **backhoe weekly** at $1,100/wk (scope rate). Excavation Equipment $1,950 covers ~1.8 weeks — confirm.
- No procurement-fee line for **long-lead items**. Windows $2,172 material likely just for the 4 windows ($300×4 = $1,200 + framing flashing + WRB). No "procurement cost" line, which is correct per the 3-task pattern.
- No **scaffolding** explicit line. Two-story addition needs scaffolding for exterior siding + roof tie-in. Material/Equipment for siding $560 may include it.
- **Optional Tankless** at $6,500 (scope) — partially baked into HVAC section ($5,140 material). Confirm if scope is approved tankless or not.
- **Optional Closet System** at $7,000 (scope) — NOT in CSV. If approved, add procurement + install.
- No line for **selections-coordination** time. Wrapped in GC Permitting.
- No line for **Will's final walkthrough** — wrapped in last section's labor.

## Cross-section notes

- Equipment totals: $3,440 ≈ Excavation $1,950 + Roof Equip $335 + Demo Equip $220 + Framing Equip $120 + Drywall Equip $255 + Exterior Equip $560. Reasonable.
- Total labor $45,167.59 ÷ 1,287 hrs = $35.10/hr average. Scope's stated rate is $70/hr base + differentials — average suggests breakdown rates were modeled differently (possibly raw labor cost, not billable).
