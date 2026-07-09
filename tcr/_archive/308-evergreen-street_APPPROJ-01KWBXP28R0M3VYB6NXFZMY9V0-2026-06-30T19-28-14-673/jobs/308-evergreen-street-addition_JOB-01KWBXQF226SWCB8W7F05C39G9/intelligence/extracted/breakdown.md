---
generation_kind: intelligence_rebuild_v2
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWBXP28R0M3VYB6NXFZMY9V0/jobs/308-evergreen-street-addition_JOB-01KWBXQF226SWCB8W7F05C39G9/inputs/files/308_Evergreen_Addition.xlsx - Summary (1).csv.txt
  - _projects/308-evergreen-street_APPPROJ-01KWBXP28R0M3VYB6NXFZMY9V0/jobs/308-evergreen-street-addition_JOB-01KWBXQF226SWCB8W7F05C39G9/inputs/scope.md
---

# Extracted — breakdown CSV (Simons Addition Summary, Tankless WH variant)

## Header metadata (CSV rows 1-9)

- **Variant**: "Two-Story Addition + Bedroom Remodel – Cost Breakdown (Incl. Tankless WH Option)" (row 1) — this priced sheet INCLUDES the tankless option even though scope L167-169 lists it as optional
- **Source scope** anchor: Simons_Addition_Scope_v2.txt (row 4)
- **Footprint**: 789 sqft listed (row 7) — DOES NOT match scope's ~600 sqft (~30×10 × 2 floors); see Discrepancies
- **Ceiling height**: 8 ft (row 8)
- **Grand Total**: $100,778.92 (Labor $45,167.59 / Material $52,171.33 / Equipment $3,440.00) (rows 2-5)
- Total labor hours: **1,287.00**

## Trade totals (CSV rows 11-27)

| Section | Labor $ | Material $ | Equip $ | Total $ | Labor hrs |
|---|---:|---:|---:|---:|---:|
| General Conditions, Permitting & Pre-Con | 2,316.08 | 2,130.00 | 0 | 4,446.08 | 56 |
| Selective Demolition & Site Work | 1,982.00 | 2,040.00 | 220 | 4,242.00 | 56 |
| Excavation, Foundation – Footings & Slab | 2,698.60 | 2,416.18 | 1,950 | 7,064.78 | 78 |
| Structural Modifications – LVL Beam & Shoring | 2,117.80 | 2,422.00 | 0 | 4,539.80 | 60 |
| Framing – Floor System, Walls & Elevator Shaft | 5,037.50 | 8,850.05 | 120 | 14,007.55 | 146 |
| Roof Framing, Sheathing & Roofing System | 3,319.80 | 5,997.50 | 335 | 9,652.30 | 96 |
| Exterior Finishes – Siding, Trim & Gutters | 2,474.70 | 2,696.61 | 560 | 5,731.31 | 72 |
| Windows, Exterior Door & Weatherproofing | 1,493.80 | 2,172.00 | 0 | 3,665.80 | 44 |
| Electrical – 100A Subpanel, Rough-In & Finish | 3,042.00 | 3,680.13 | 0 | 6,722.13 | 78 |
| Plumbing – Rough-In, Master Bath & W/D Relocation | 1,356.80 | 2,160.00 | 0 | 3,516.80 | 40 |
| **HVAC – Mini Split, Tankless WH & Relocations** | 1,363.36 | 5,140.00 | 0 | 6,503.36 | 36 |
| Insulation & Air Sealing | 1,493.80 | 1,590.64 | 0 | 3,084.44 | 44 |
| Drywall – New Addition & Existing Bedroom | 5,428.35 | 3,647.35 | 255 | 9,330.70 | 159 |
| Interior Finish Carpentry, Painting & Flooring | 5,540.30 | 7,291.28 | 0 | 12,831.58 | 162 |
| Master Bathroom – Custom Tile Shower & Finishes | 3,017.90 | 4,136.60 | 0 | 7,154.50 | 88 |
| **Existing Hall Bath Mod, Bedroom Remodel & Closeout** | 2,484.80 | **-4,199.00** | 0 | **-1,714.20** | 72 |

## Allowances (from scope, NOT line-itemized in CSV)

- LVT flooring $3.00/sqft (scope L185)
- Windows $300 each (scope L186)
- Interior doors $250 each, pocket door $400 each (scope L187-188)
- Recessed lights $25 each, up to 18 (scope L189)
- 72" vanity $1,000 (scope L190)
- Faucets $150 each, vanity lights $100 each, mirrors $150 each, commode $250 (scope L191-194)
- Tile walls $3.00/sqft, mosaic floor $6.00/sqft, waterproofing/setting $500 (scope L196-198)
- Mini-split $2,500 (scope L200)
- Exterior door $500 (scope L201)
- Hall bath shower pan + walls $1,000 (scope L202)

## Silent omissions (scope items NOT visibly broken out in CSV section list)

- **No TDEC septic permit line** despite scope L26-27 mandating TDEC inspection — likely lumped into "General Conditions, Permitting & Pre-Con" 56 hrs, but cannot be confirmed from summary granularity
- **No septic relocation / leach field / grinder pump** — explicit change-order exclusions per scope L29-30
- **No service-upgrade scope** — scope assumes existing main service can support new 100A subpanel (scope L83); amperage-check task required pre-construction
- **No elevator system** — scope L49, L161 confirms framing + 30A circuit only
- **No closet & cabinet system** — optional package $7,000 (scope L163-165), NOT in CSV totals; this is the $100,778.92 base price WITHOUT the closet upgrade
- **No standalone tankless WH line** — tankless is the variant chosen (header row 1), absorbed into HVAC line ($5,140 material includes $2,500 mini-split + ~$2,640 tankless equipment per scope L200, L168)
- **No siding "brick to match existing" line** — plans (L25, 32, 35) show "NEW BRICK TO MATCH EXISTING" but scope L62 lists only vinyl siding and CSV lumps both in "Exterior Finishes" 72 hrs

## Notes / anomalies

- **Negative section total** "Existing Hall Bath Mod, Bedroom Remodel & Closeout" at **-$1,714.20** (row 27) — labor $2,484.80, equipment $0, material **-$4,199.00**. Labor hrs 72.
  - The negative material line is a CREDIT — most likely subtracting overlap with prior bid lines (e.g. drywall material already covered in "Drywall – New Addition & Existing Bedroom" 159 hrs, paint material already in "Interior Finish Carpentry, Painting & Flooring" 162 hrs). Per dev_rules L562-567, with `section_total < 0` and `labor_hours > 24` this is a scope-ambiguity warning, not a credit-only line — 72 real labor hours still need decomposition.
  - 72 labor hrs covers: hall bath retrofit (window infill, acrylic shower swap, drywall patch, paint), existing primary bedroom remodel, AND closeout. Three distinct work streams compressed into one section.
- **Drywall hours unusually high** at 159 hrs (largest section by labor) — consistent with the editor-rule consolidation pattern: addition + retrofit bedroom + retrofit hall bath + basement storage drywall rolled into ONE block per editor_rules drywall consolidation guidance.
- **HVAC labor only 36 hrs** for mini-split + tankless WH + relocations — consistent with editor_rules mini-split=1d/1person + 0.5d/1person rough + small tankless install.
- **Plumbing labor only 40 hrs** — at default crew 2 × 8 hrs/day = 2.5 days, BELOW the 4-day floor in editor_rules L138-142 ("master bath, 2+ bath fixtures, W/D relocation"). Scope explicitly has master bath + W/D relocation. Per rule 4H/editor_rules tank-set, **plumbing rough-in must be ≥ 4 working days × 2 crew = 64 labor hrs**. Breakdown allocates 40 hrs which is short — task graph generation will need to expand to the rule floor with a warning.
- **Equipment cost $3,440 total**: $1,950 in foundation (likely backhoe + form rental), $560 in exterior, $220 in demo, $335 in roofing, $120 in framing, $255 in drywall — no equipment line for site_prep dumpster or porta-john (likely absorbed into "Selective Demolition & Site Work" $220 or assumed within hourly burden).

## Discrepancies vs scope

- **Footprint**: CSV header 789 sqft vs scope "30×10" ~600 sqft (two floors). 789 closer to 30×13 or 30×10 + retrofit bedroom (~12'5"×16' ≈ 200 sqft existing primary bedroom area being remodeled within scope). Possible explanation: footprint counts BOTH new addition floors (~600) + retrofit primary bedroom (~200). PM should confirm.
- **Tankless WH variant**: CSV explicitly priced WITH tankless option, but scope L167-169 lists it as optional package. Treat as confirmed-in for this priced version unless PM Interview overrides.
