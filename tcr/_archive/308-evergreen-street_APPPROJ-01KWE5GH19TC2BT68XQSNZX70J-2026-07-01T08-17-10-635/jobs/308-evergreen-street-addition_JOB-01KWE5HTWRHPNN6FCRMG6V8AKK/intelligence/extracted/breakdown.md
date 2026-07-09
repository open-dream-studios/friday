---
generation_kind: intelligence_rebuild_v2
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWE5GH19TC2BT68XQSNZX70J/jobs/308-evergreen-street-addition_JOB-01KWE5HTWRHPNN6FCRMG6V8AKK/inputs/files/308_Evergreen_Addition.xlsx - Summary (1).csv.txt
---
# breakdown.md — distilled

Source: `308_Evergreen_Addition.xlsx - Summary (1).csv` — locked template row-by-row summary. Rows referenced below by section name.

## Totals
- Labor cost: $45,167.59 · Material cost: $52,171.33 · Equipment cost: $3,440.00 · **Grand total: $100,778.92** `(csv L1-6, TOTALS L27)`.
- Labor hours: 1,287.00 hours total `(csv TOTALS L27)`.
- Footprint (header): 789 sqft · ceiling: 8' `(csv L7-8)`.
- Template anchor: `Basement_Remodel_Breakdown_Locked_Template_v1.xlsx`; source scope: `Simons_Addition_Scope_v2.txt` `(csv L4-5)`.

**NOTE:** Contract quotes $173,850 total investment `(scope.md L200)`. Breakdown grand total is $100,778.92. Delta of ~$73K is unaccounted for in the summary CSV — likely markup, subcontractor +30%, materials +15%, allowances not rolled up, or profit margin. Not a fatal discrepancy but the CSV is a partial cost view, not the customer's number.

## Trade / section totals (labor hours in parens)
| Section | Labor $ | Material $ | Equip $ | Section total | Hrs |
|---|---:|---:|---:|---:|---:|
| General Conditions, Permitting & Pre-Construction | 2,316.08 | 2,130.00 | 0 | 4,446.08 | 56 |
| Selective Demolition & Site Work | 1,982.00 | 2,040.00 | 220.00 | 4,242.00 | 56 |
| Excavation, Foundation – Footings & Slab | 2,698.60 | 2,416.18 | 1,950.00 | 7,064.78 | 78 |
| Structural Modifications – LVL Beam & Shoring | 2,117.80 | 2,422.00 | 0 | 4,539.80 | 60 |
| Framing – Floor System, Walls & Elevator Shaft | 5,037.50 | 8,850.05 | 120.00 | 14,007.55 | 146 |
| Roof Framing, Sheathing & Roofing System | 3,319.80 | 5,997.50 | 335.00 | 9,652.30 | 96 |
| Exterior Finishes – Siding, Trim & Gutters | 2,474.70 | 2,696.61 | 560.00 | 5,731.31 | 72 |
| Windows, Exterior Door & Weatherproofing | 1,493.80 | 2,172.00 | 0 | 3,665.80 | 44 |
| Electrical – 100A Subpanel, Rough-In & Finish | 3,042.00 | 3,680.13 | 0 | 6,722.13 | 78 |
| Plumbing – Rough-In, Master Bath & W/D Relocation | 1,356.80 | 2,160.00 | 0 | 3,516.80 | 40 |
| HVAC – Mini Split, Tankless WH & Relocations | 1,363.36 | 5,140.00 | 0 | 6,503.36 | 36 |
| Insulation & Air Sealing | 1,493.80 | 1,590.64 | 0 | 3,084.44 | 44 |
| Drywall – New Addition & Existing Bedroom | 5,428.35 | 3,647.35 | 255.00 | 9,330.70 | 159 |
| Interior Finish Carpentry, Painting & Flooring | 5,540.30 | 7,291.28 | 0 | 12,831.58 | 162 |
| Master Bathroom – Custom Tile Shower & Finishes | 3,017.90 | 4,136.60 | 0 | 7,154.50 | 88 |
| Existing Hall Bath Mod, Bedroom Remodel & Closeout | 2,484.80 | **−4,199.00** | 0 | **−1,714.20** | 72 |

## Allowances / equipment lines
- Debris removal (dumpster/trailer): $220 in Demo line; $255 in Drywall line; $560 in Exterior finishes → multi-trip dump pattern `(csv L11, L23, L17)`.
- Excavation equipment: $1,950 (backhoe / mini-ex) `(csv L12)`.
- Roofing equipment: $335 (scaffolding / lifts) `(csv L16)`.
- Framing equipment: $120 (small tool + saw) `(csv L15)`.

## Silent omissions (things in scope but NOT surfaced as own row in the CSV)
The template rolls up sub-scopes into parent sections, so absence of a row is not necessarily missing work — but each of these is worth PM confirmation:

- **Basement storage finish** — scope has a dedicated section `(scope.md L172-176)` but breakdown lumps into `Drywall – New Addition & Existing Bedroom` and `Interior Finish Carpentry, Painting & Flooring`. No separate line.
- **Elevator shaft framing + 30A stub** — scope explicitly calls for framing + electrical `(scope.md L143-146)`. Framing labor is likely inside `Framing – Floor System, Walls & Elevator Shaft` (name confirms). The 30A dedicated circuit sits inside `Electrical – 100A Subpanel, Rough-In & Finish`.
- **Existing hallway switch relocation** (with drywall patch + prime + paint) — retrofit item `(scope.md L103)` — buried in `Existing Hall Bath Mod, Bedroom Remodel & Closeout` OR `Electrical` row; not surfaced.
- **Bedroom 2 / Bedroom 3 existing-window relocations** — drawings show two existing windows relocated `(plans page 4)` but breakdown does not surface a dedicated retrofit line for either. May be buried in the negative-material closeout row.
- **Tankless water heater** — optional package ($6,500 `(scope.md L195-198)`) NOT reflected in the breakdown grand total. The HVAC row is named "HVAC – Mini Split, **Tankless WH** & Relocations" but the material cost of $5,140 is closer to just the mini-split ($2,500) + relocations + venting. If tankless IS included the row is under-budgeted; if NOT, the row is mis-named.
- **Closet / cabinet system** — optional package ($7,000 `(scope.md L191-193)`) NOT in the breakdown.
- **TDEC septic permit fee / soil scientist** — scope covers TCR coordination `(scope.md L32-35)` but no dedicated line for the ~$500 permit fee.
- **Grinder pump** — explicitly excluded (change order) `(scope.md L34)`.

## Anomalies / notes
- The `Existing Hall Bath Mod, Bedroom Remodel & Closeout` row has a **negative material total of −$4,199.00** with a section total of −$1,714.20 and 72 labor hours. Per Rule 12 (`section_total < 0` and `labor_hours ≤ 24` → treat as credit) — but here `labor_hours = 72`, exceeding the 24-hour cutoff. This is a bundle of: (a) the acrylic-shower-swap credit for reusing existing valve + trim, (b) hall-bath window infill work, (c) existing primary bedroom re-drywall + paint + LVT, (d) closeout / punch. Treat as SCOPE AMBIGUITY — flag in `warnings[]` and expand into named tasks via retrofit component modeling.
- Drywall row (159 hrs, $5,428 labor) is the highest labor row after finish carpentry — consistent with Rule "consolidate drywall into ONE block" spanning addition + existing bedroom + basement storage + hall-bath patch.
- Roofing equipment $335 is low — likely just scaffolding rental; consistent with 3/12 pitch + shingles labor being a 1-day job per editor rules.
- No dedicated INSPECTION lines — inspections are inside general/permitting.

## Trade-total sanity vs editor rules
- Plumbing labor 40 hrs at crew 2 = 2.5 working days. **Below Rule 4H / plumbing.rough_in default of 4d × 2 crew for master bath + W/D relocation** (`_company/rules/editor_rules.md`). Duration bump warranted — model as 4d, not 2.5d.
- HVAC labor 36 hrs. Mini-split rough = 0.5d/1p and install = 1d/1p per editor rules. Balance is relocations + venting. Reasonable.
- Framing 146 hrs at crew 3 = 6.1 working days. Fits editor-rules example "Framing labor_hours=146, crew=3 → 6d, split into basement_walls (2d), floor_system (2d), exterior_walls (3d), interior_walls (2d), roof (3d), sheathing (1d)". Actually 13d if fully split — the summed splits exceed the calendar because it becomes crew-serialized. Reasonable, matches spine.
- Drywall 159 hrs at crew 3 → 6.6d if labor-only. Editor rules calls for 9-11 working days consolidated (cure days baked in). PM should not shave the schedule to labor hours.
