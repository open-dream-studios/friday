---
generation_kind: intelligence_rebuild_v2
stage: extract_breakdown
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWHNZ9SX3T48DZS1YPB87SRA/jobs/308-evergreen-street-addition_JOB-01KWHP1G1HG8C26X6GPS0EXGBR/inputs/files/308_Evergreen_Addition.xlsx - Summary (1).csv.txt
  - _projects/308-evergreen-street_APPPROJ-01KWHNZ9SX3T48DZS1YPB87SRA/jobs/308-evergreen-street-addition_JOB-01KWHP1G1HG8C26X6GPS0EXGBR/inputs/scope.md
---

# Breakdown extraction — 308 Evergreen Addition

**Source CSV:** `308_Evergreen_Addition.xlsx - Summary (1).csv`
**Project:** Simons Addition – 30'x10' Two-Story + Bedroom Remodel
**Footprint:** 789 sqft total; 8' ceiling height
**Template anchor:** Basement_Remodel_Breakdown_Locked_Template_v1.xlsx

## Trade totals

CSV grand total (row 20): **$100,778.92** — Labor **$45,167.59** + Material **$52,171.33** + Equipment **$3,440.00** across **1,287 labor hours**.

| Row | Section | Labor $ | Material $ | Equip $ | Section total | Labor hrs |
|---:|---|---:|---:|---:|---:|---:|
| 10 | General Conditions, Permitting & Pre-Construction | 2,316.08 | 2,130.00 | 0.00 | **4,446.08** | 56 |
| 11 | Selective Demolition & Site Work | 1,982.00 | 2,040.00 | 220.00 | **4,242.00** | 56 |
| 12 | Excavation, Foundation – Footings & Slab | 2,698.60 | 2,416.18 | 1,950.00 | **7,064.78** | 78 |
| 13 | Structural Modifications – LVL Beam & Shoring | 2,117.80 | 2,422.00 | 0.00 | **4,539.80** | 60 |
| 14 | Framing – Floor System, Walls & Elevator Shaft | 5,037.50 | 8,850.05 | 120.00 | **14,007.55** | 146 |
| 15 | Roof Framing, Sheathing & Roofing System | 3,319.80 | 5,997.50 | 335.00 | **9,652.30** | 96 |
| 16 | Exterior Finishes – Siding, Trim & Gutters | 2,474.70 | 2,696.61 | 560.00 | **5,731.31** | 72 |
| 17 | Windows, Exterior Door & Weatherproofing | 1,493.80 | 2,172.00 | 0.00 | **3,665.80** | 44 |
| 18 | Electrical – 100A Subpanel, Rough-In & Finish | 3,042.00 | 3,680.13 | 0.00 | **6,722.13** | 78 |
| 19 | Plumbing – Rough-In, Master Bath & W/D Relocation | 1,356.80 | 2,160.00 | 0.00 | **3,516.80** | 40 |
| 20 | HVAC – Mini Split, Tankless WH & Relocations | 1,363.36 | 5,140.00 | 0.00 | **6,503.36** | 36 |
| 21 | Insulation & Air Sealing | 1,493.80 | 1,590.64 | 0.00 | **3,084.44** | 44 |
| 22 | Drywall – New Addition & Existing Bedroom | 5,428.35 | 3,647.35 | 255.00 | **9,330.70** | 159 |
| 23 | Interior Finish Carpentry, Painting & Flooring | 5,540.30 | 7,291.28 | 0.00 | **12,831.58** | 162 |
| 24 | Master Bathroom – Custom Tile Shower & Finishes | 3,017.90 | 4,136.60 | 0.00 | **7,154.50** | 88 |
| 25 | Existing Hall Bath Mod, Bedroom Remodel & Closeout | 2,484.80 | **-4,199.00** | 0.00 | **-1,714.20** | 72 |

**Top three by dollar:** Framing ($14,008) → Interior Finish/Paint/Flooring ($12,832) → Roof Framing & Roofing ($9,652).
**Top three by labor hours:** Interior Finish (162 hr) → Drywall (159 hr) → Framing (146 hr).

## Allowances

The CSV itself does NOT enumerate line-item allowances — those live only in scope.md's "Material Allowance Schedule." The CSV appears to have already absorbed most allowances into section material totals. Allowances the schedule/procurement layer must track (from scope.md, cross-referenced):

- LVT flooring: $3.00/sqft
- Windows: $300 ea × 4 (3× 36"×60" DH + 1× transom)
- Interior doors: $250 ea (prehung) — 1 unit
- Pocket door systems: $400 ea — 2 units
- Recessed lights: $25 ea, up to 18 fixtures
- 72" double vanity: $1,000
- Faucets: $150 ea × 2
- Vanity lights: $100 ea × 2
- Commode: $250
- Shower valve & trim: $250
- Tile (walls): $3.00/sqft
- Tile (floor mosaic): $6.00/sqft
- Waterproofing / setting materials: $500
- Mirrors: $150 ea × 2
- Mini-split: $2,500 (appears embedded in row 20 HVAC material $5,140)
- Exterior door: $500
- Guest bath shower system pan & walls: **$1,000** — this is the hall bath acrylic shower kit; likely embedded in row 25's -$4,199 material line as a small credit-net figure.

**Optional packages (NOT in CSV grand total — must be added via CO if selected):**
- Closet & Cabinet System: **$7,000** allowance (labor + materials)
- Tankless Water Heater package: **$6,500** allowance (labor + materials). NOTE: CSV row 20 title says "Tankless WH" but scope treats tankless as an OPTIONAL package. Ambiguity — see Notes.

## Silent omissions (scope items with NO matching CSV row)

Cross-referenced against `inputs/scope.md`. These scope items are NOT line-itemed as their own CSV section (may be silently absorbed into a broader section, or dropped):

1. **Septic / TDEC coordination** — scope calls out "Coordinate and complete septic inspection with TDEC," feasibility of septic relocation, and grinder pump evaluation. No CSV section for TDEC permit, septic work, or grinder pump. Scope disclaims cost ("not included, will be addressed via change order"), so the CSV correctly omits BUT the PM interview must confirm whether TDEC inspection labor is buried in row 10 (general conditions, 56 hr) or truly absent.
2. **Heat pump relocation** — scope says "Relocate existing heat pump and electrical disconnect." No dedicated section — presumably folded into row 11 (demo/site work, 56 hr) and/or row 20 (HVAC, 36 hr). Not visible as its own line.
3. **Electrical disconnect relocation** — same as above; folded into row 11 or row 18.
4. **Existing gas WH vent extension through new roof** — scope explicitly requires this. No CSV line. Likely absorbed into row 15 (roof) or row 19 (plumbing). Should NOT trigger `procurement.tank` / `plumbing.tank_set` — existing tank stays (Rule 4H exemption).
5. **Elevator shaft framing + 30A dedicated circuit** — scope says frame 4'×4' shaft + rough-in 30A. Row 14 title mentions "Elevator Shaft" so framing is likely in — but no dedicated line item confirms 30A circuit labor. Confirm via interview.
6. **Interior doors (4 total: 1 prehung + 2 pocket + 1 other)** — no dedicated CSV row. Absorbed into row 23 (interior finish, 162 hr).
7. **Waterproofing membrane + shower niche + bench** — scope lists all three specifically for master bath. Row 24 total $7,154 covers "Custom Tile Shower & Finishes"; item counts not itemized.
8. **Concealed roof tie-in contingency** — scope discusses tie-in from new 3/12 into existing 6/12 with "additional structural modifications not included." No line item for contingency buffer. Schedule-only risk.
9. **Backhoe / equipment rental** — scope quotes backhoe at $1,100/wk. Row 12 has $1,950 equipment cost (excavation) which likely covers ~2 weeks. Confirm.
10. **Debris removal multiple dump runs** — scope references "multiple dump runs" at $450 each. Row 11 has $220 equipment cost — that's ~half of a single trailer dump. Likely under-priced OR most dump runs sit in a different row.
11. **Selections / customer allowance package selections** — no CSV row for pre-con selections coordination.
12. **Final cleaning** — scope closeout mentions "Perform final cleaning." Absorbed into row 25 (which is NEGATIVE — see Notes).
13. **Punch list / closeout returns** — no dedicated line beyond row 25's negative aggregate.
14. **Insulation of hall bath window infill** — scope for hall bath mod says "Install insulation, drywall, and finish" at the removed window. Absorbed into row 21 (44 hr addition insulation) and row 22 drywall — not itemized separately.

## Notes (anomalies, negative rows, credits)

### 🚨 Major anomaly — scope total vs CSV total mismatch

**Scope quotes "Total Investment: $173,850" — CSV grand total is $100,778.92 — a delta of $73,071 (72.5%).**

This blows past the 5% threshold in rule `scope_vs_csv_total_reconciliation` (company rule). An interview question MUST be emitted asking the PM to reconcile. Candidate explanations:
- Scope figure includes contingency / soft costs / margin not reflected in labor+material+equipment breakdown
- Scope figure includes both optional packages ($7,000 closet + $6,500 tankless = $13,500) — still leaves ~$60k unexplained
- CSV may be missing entire scope areas (see Silent omissions #1, #2, #5)
- Scope may include a markup/OH layer not in the CSV
- CSV template was populated with "detail rows only" per the CSV header note — perhaps a totals/markup tab from the original .xlsx is missing from the CSV export

This is the single most important item for the PM interview.

### 🚨 Row 25 is NEGATIVE (row 25: "Existing Hall Bath Mod, Bedroom Remodel & Closeout — Section total: -$1,714.20", material -$4,199.00, labor +$2,484.80, 72 hr)

Rule triggers warning #8 (section_total < 0 with labor_hours > 40). The -$4,199 material line is a credit / return, likely reflecting:
- Removed/salvage credit for the existing tub-shower combo
- Bulk material offset for the acrylic shower kit ($1,000 allowance is in the positive direction)
- Or a spreadsheet template artifact where a subtract-from-prior-bid line was baked in

The 72 labor hours are REAL (hall bath acrylic shower swap + window infill + bedroom repaint + closeout tasks). Do NOT interpret negative section_total as "no work here." Per company dev_rules Section 12, keep decomposition modest but non-empty. PM must clarify what the -$4,199 credit represents.

### Tankless water heater ambiguity

CSV row 20 title says "HVAC – Mini Split, Tankless WH & Relocations" implying tankless is BAKED IN. Scope's "Optional Package – Tankless Water Heater: $6,500 allowance" implies it's OPTIONAL and NOT in base price. Row 20 material total is $5,140 — with mini-split at $2,500 allowance, that leaves ~$2,640 for tankless materials + relocations, which is LESS than the $6,500 optional package. **Interpretation:** CSV row 20 title is aspirational; the tankless package is NOT priced in at the $6,500 level. Existing gas WH stays (scope: "Extend existing gas water heater vent through new roof"). Confirm with PM.

### Row 12 equipment cost ($1,950) — likely mini-ex + backhoe rental for excavation. Consistent with scope's $1,100/wk backhoe rate.

### Row 14 (Framing) at 146 hours and $14,008 aligns with dev_rules Example (labor_hours=146, crew=3 → ~6d split into basement walls / floor system / exterior walls / interior walls / roof / sheathing).

### Row 22 (Drywall) at 159 hours and $9,331 aligns with dev_rules editor "typical addition drywall (consolidated): 9–11 days total." Row title "New Addition & Existing Bedroom" implies drywall is already CONSOLIDATED for retrofit + addition — matches editor rule.

### Row 19 (Plumbing) at only 40 hours is LIGHT for a scope with master bath rough-in + W/D relocation + vent stack extension. Dev rule for plumbing rough on master-bath jobs is 4d × 2 crew = 64 hr baseline, plus tank vent + W/D relocation. 40 hours suggests the CSV is aggressive on plumbing — Rule `plumbing_rough_min_duration` still requires ≥ 4d × 2 crew in the TaskGraph regardless of what the CSV allocates. Flag for PM.

### Row 20 (HVAC) at 36 hours seems reasonable for mini-split rough (0.5d × 1) + install (1d × 1) + heat pump relocation (1d × 2) + tankless coordination. But if tankless is really in scope, hours are also light.

### Row 18 (Electrical) at 78 hours covers subpanel + rough + finish + elevator 30A + 12 recessed + vanity lights + fan/light + relocated switch + all outlets. Reasonable envelope.

### CSV template note (rows 1-8 header): "Use this workbook as a locked template. Populate detail rows only; preserve formulas, tabs, and section order." — implies the CSV as delivered is only the Summary tab; detail tabs (which might explain the scope-vs-CSV gap) are not in the export.
