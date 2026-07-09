---
generation_kind: intelligence_rebuild_v2
stage: extract_breakdown
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWFCFSFZDJ01ZGRTNF78GYHC/jobs/308-evergreen-street-addition_JOB-01KWFCGKXVEGGGJZV1JB762C1C/inputs/files/308_Evergreen_Addition.xlsx - Summary (1).csv.txt
  - _projects/308-evergreen-street_APPPROJ-01KWFCFSFZDJ01ZGRTNF78GYHC/jobs/308-evergreen-street-addition_JOB-01KWFCGKXVEGGGJZV1JB762C1C/inputs/scope.md
---

# Breakdown extraction — 308 Evergreen Addition

**Source file:** `308_Evergreen_Addition.xlsx - Summary (1).csv`
**Project totals (header rows 2–5):**
- Labor Cost: $45,167.59
- Material Cost: $52,171.33
- Equipment Cost: $3,440.00
- **Grand Total: $100,778.92**
- Total labor hours: 1,287.00
- Footprint: 789 sqft, 8' ceilings
- Template anchor: `Basement_Remodel_Breakdown_Locked_Template_v1.xlsx`
- Source scope: `Simons_Addition_Scope_v2.txt`

## Trade totals

Sixteen line-item sections. All figures are Section Total / Labor Hours.

| # | Section (verbatim) | Labor $ | Material $ | Equip $ | Section Total | Labor hrs |
|---|---|---:|---:|---:|---:|---:|
| 1 | General Conditions, Permitting & Pre-Construction (row 11) | 2,316.08 | 2,130.00 | 0.00 | **4,446.08** | 56 |
| 2 | Selective Demolition & Site Work (row 12) | 1,982.00 | 2,040.00 | 220.00 | **4,242.00** | 56 |
| 3 | Excavation, Foundation – Footings & Slab (row 13) | 2,698.60 | 2,416.18 | 1,950.00 | **7,064.78** | 78 |
| 4 | Structural Modifications – LVL Beam & Shoring (row 14) | 2,117.80 | 2,422.00 | 0.00 | **4,539.80** | 60 |
| 5 | Framing – Floor System, Walls & Elevator Shaft (row 15) | 5,037.50 | 8,850.05 | 120.00 | **14,007.55** | 146 |
| 6 | Roof Framing, Sheathing & Roofing System (row 16) | 3,319.80 | 5,997.50 | 335.00 | **9,652.30** | 96 |
| 7 | Exterior Finishes – Siding, Trim & Gutters (row 17) | 2,474.70 | 2,696.61 | 560.00 | **5,731.31** | 72 |
| 8 | Windows, Exterior Door & Weatherproofing (row 18) | 1,493.80 | 2,172.00 | 0.00 | **3,665.80** | 44 |
| 9 | Electrical – 100A Subpanel, Rough-In & Finish (row 19) | 3,042.00 | 3,680.13 | 0.00 | **6,722.13** | 78 |
| 10 | Plumbing – Rough-In, Master Bath & W/D Relocation (row 20) | 1,356.80 | 2,160.00 | 0.00 | **3,516.80** | 40 |
| 11 | HVAC – Mini Split, Tankless WH & Relocations (row 21) | 1,363.36 | 5,140.00 | 0.00 | **6,503.36** | 36 |
| 12 | Insulation & Air Sealing (row 22) | 1,493.80 | 1,590.64 | 0.00 | **3,084.44** | 44 |
| 13 | Drywall – New Addition & Existing Bedroom (row 23) | 5,428.35 | 3,647.35 | 255.00 | **9,330.70** | 159 |
| 14 | Interior Finish Carpentry, Painting & Flooring (row 24) | 5,540.30 | 7,291.28 | 0.00 | **12,831.58** | 162 |
| 15 | Master Bathroom – Custom Tile Shower & Finishes (row 25) | 3,017.90 | 4,136.60 | 0.00 | **7,154.50** | 88 |
| 16 | Existing Hall Bath Mod, Bedroom Remodel & Closeout (row 26) | 2,484.80 | **-4,199.00** | 0.00 | **-1,714.20** | 72 |
| — | **TOTALS (row 27)** | **45,167.59** | **52,171.33** | **3,440.00** | **100,778.92** | **1,287** |

Totals row math checks out: sum of the 16 section totals = $100,778.92, matching row 27.

## Allowances

The CSV **does not itemize allowances**. Allowances live only in scope.md's "Material Allowance Schedule" section. For reference (from scope, not from CSV):

- LVT flooring — $3.00/sqft
- Windows — $300 each (spec calls for 3× 36"×60" DH + 1 transom = 4 total)
- Interior doors — $250 each × 4 total; pocket-door systems $400 each × 2
- Recessed lights — $25 each, up to 18 fixtures (scope specifies ~12)
- Vanity (72") — $1,000
- Faucets — $150 each (× 2)
- Vanity lights — $100 each (× 2)
- Commode — $250
- Shower valve & trim — $250
- Tile (walls) — $3.00/sqft
- Tile (mosaic floor) — $6.00/sqft
- Waterproofing / setting materials — $500
- Mirrors — $150 each (× 2)
- Mini split — $2,500 (appears folded into CSV row 21 material cost $5,140)
- Exterior door — $500
- Guest-bath acrylic shower system (pan + walls) — $1,000
- **Optional — closet & cabinet system: $7,000 (labor + materials)** — NOT in CSV
- **Optional — tankless water heater: $6,500 (labor + materials)** — CSV row 21 title says "Tankless WH" but see Notes

Verdict: the CSV rolls allowance dollars up into each section's material line. Individual allowance items are not broken out.

## Silent omissions (scoped items with NO obvious matching CSV row)

Cross-referenced against `inputs/scope.md`. Items in scope that don't have a clean CSV home:

1. **Septic / TDEC coordination** — scope Pre-Construction section calls for septic inspection with TDEC, feasibility study for septic relocation vs. grinder pump connection. Scope explicitly excludes the cost of relocation/grinder ("addressed via change order") — but the CSV also has NO line for the coordination/inspection labor itself. Row 11 (General Conditions, 56 hrs) may absorb this, but it is not called out.
2. **Grinder pump install** — scope evaluates feasibility only. Confirmed NOT in CSV. This is a known change-order placeholder, not a silent omission per se.
3. **Elevator shaft framing** — scope says "Frame (1) future elevator shaft approximately 4' x 4'" and also "rough-in electrical for 30 amp circuit run from sub panel." Row 15 title ("Framing – Floor System, Walls & **Elevator Shaft**") appears to absorb the framing. The dedicated 30A elevator circuit is presumably inside row 19 electrical but is not itemized.
4. **Optional closet & cabinet system ($7,000 allowance)** — clearly an optional add-on; NOT in CSV. Confirm with PM whether accepted.
5. **Optional tankless water heater ($6,500 allowance)** — CSV row 21 is titled "HVAC – Mini Split, **Tankless WH** & Relocations" but the section total is only $6,503.36 with $5,140 material. That's roughly consistent with mini-split ($2,500) + tankless allowance ($6,500 material portion) minus… the math is soft. Row 21's $6,503.36 barely covers the mini-split PLUS the tankless allowance if the tankless is included. **See Notes — likely partial inclusion, needs PM clarification.**
6. **Interior doors (4 total, 2 pocket-door systems)** — no dedicated CSV row. Presumably folded into row 14 (Interior Finish Carpentry) material $7,291.28.
7. **Vent stack extensions through roof / existing gas WH vent extension** — scope mentions both under Selective Demo and Plumbing. Presumably inside rows 12 and 20 but not itemized.
8. **Heat pump relocation** — scope Selective Demo item. Presumably inside row 12 (Selective Demolition & Site Work), but a dedicated HVAC-trade day is typically needed (per rule 4K). Not itemized as its own line.
9. **Electrical disconnect relocation** — scope Selective Demo item. Same as above; presumably inside row 12 or row 19. Not itemized.
10. **Amperage check on existing service** — required by `_company/rules/service_amperage_check.md` (adds subpanel + mini-split + tankless + 30A elevator circuit → clearly triggers). CSV has NO pre-construction electrical prep line. Should be added.
11. **Concealed roof tie-in discovery / structural contingency** — scope says "Roof tie-in assumes standard integration; additional structural modifications not included." No buffer line in CSV. Change-order placeholder.
12. **Water management / French drains / foundation waterproofing** — scope explicitly excludes. Consistent with CSV.

## Notes (anomalies, negative rows, credits)

- **⚠ Scope vs CSV total mismatch — MANDATORY interview question per `scope_vs_csv_total_reconciliation` rule.** Scope's "Total Investment: $173,850" vs CSV Grand Total $100,778.92. Delta = **$73,071.08 (72.5% gap — CSV is 42% below scope)**. Well past the 5% threshold. This MUST surface as `q.scope_vs_csv_total_reconciliation` in `questions.md` and gate `interview_status: needs_more`. Possible explanations to probe:
  - CSV is labor+material+equip only; scope's $173,850 may include markup, overhead, contingency, subcontractor mark-ups (cost+30% per scope Rates section), and the two optional packages ($7,000 closet + $6,500 tankless = $13,500).
  - CSV may be missing entire scopes (elevator rough electrical, interior doors, several allowances).
  - Even after adding both optional allowances ($13,500) and applying naive 15% material markup and 30% sub markup, CSV would top out around $125k–$135k — still $40k+ short.
- **⚠ Row 16 has a NEGATIVE material cost of −$4,199.00 and a NEGATIVE section total of −$1,714.20** (Existing Hall Bath Mod, Bedroom Remodel & Closeout). Labor hours are positive at 72 hrs / labor $2,484.80. This is a credit line — likely a template artifact where material was double-counted elsewhere and this row nets it out. Per dev_rules §12, negative section_total with labor_hours ≤ 24 = single close-out task; here labor_hours = 72, which is substantial → treat as real retrofit + closeout work (hall bath mod + bedroom remodel + closeout) with a material credit. This row bundles at least three distinct scope blocks that would normally live in different components:
  - Existing hall bath modification (window infill, insulation, drywall, acrylic shower swap, repaint) — retrofit
  - Primary bedroom remodel (drywall, prime/paint, LVT, trim) — retrofit
  - Closeout (final clean, punch, final inspection)
  Should be split during task-graph generation, and the acrylic shower swap flagged as a candidate customer-early-item (rule 4V) — confirm with PM.
- **Row 21 (HVAC) coverage ambiguity.** Title lists "Mini Split, Tankless WH & Relocations" — three distinct scopes. Material $5,140 is barely enough for mini-split allowance ($2,500) + tankless allowance ($6,500) — arithmetic says one of these is only partially in. If tankless is IN, CSV is under-priced. If tankless is OUT, the row title is misleading. **Interview question candidate.**
- **Row 5 equipment $120 and row 6 equipment $335** — small equipment line items; likely nail-gun rental / roof jacks / similar consumables. Row 3 equipment $1,950 is the excavation machine ("Backhoe Usage: $1,100/wk." per scope rates → roughly 1.75 weeks — reasonable).
- **Row 2 equipment $220** — likely one dumpster load (scope rate says "$450 per removal"; $220 is lower — possibly a partial-load rate or a haul-only fee). Multiple dump runs are mentioned in scope but only one appears priced. Worth flagging.
- **Row 13 equipment $255** — likely drywall lift rental.
- **No dedicated "Selections finalized" or "Amperage check" pre-construction lines** — CSV has one general pre-con row (row 11, 56 hrs). Rule `service_amperage_check` requires an amperage check task; will need to be added at task-graph time regardless of whether it's priced.
- **Hall bath acrylic shower swap** ($1,000 allowance per scope) sits inside row 16's negative bundle. Rule 4V requires this to be treated as a customer-requested early item candidate if the PM interview confirms — flag for PM.
- **Roof system uncertainty** — scope says "truss or rafter framed, determined during design phase." Rule 4Q says: default to stick-frame for small additions unless span > 24 ft or footprint > 800 sqft. Footprint here = 789 sqft (right at the edge). Row 6 material $5,997.50 is more consistent with stick lumber than trusses ($28–$42d lead pre-manufactured trusses would typically add supplier costs and no on-site framing hours reduction — but 96 labor hrs is high enough to accommodate either). No `procurement.trusses` should be emitted unless PM confirms trusses. Interview question candidate.
