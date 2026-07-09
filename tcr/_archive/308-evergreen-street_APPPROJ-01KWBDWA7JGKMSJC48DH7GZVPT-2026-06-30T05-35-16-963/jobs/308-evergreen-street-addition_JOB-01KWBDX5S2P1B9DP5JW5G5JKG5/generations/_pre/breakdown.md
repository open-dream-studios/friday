---
generation_kind: intel_gather_v1
artifact: breakdown_pre
derived_from:
  - path: _projects/308-evergreen-street_APPPROJ-01KWBDWA7JGKMSJC48DH7GZVPT/jobs/308-evergreen-street-addition_JOB-01KWBDX5S2P1B9DP5JW5G5JKG5/inputs/files/308_Evergreen_Addition.xlsx - Summary (1).csv.txt
    sha256: c936d98fafac090e05c29bef7398fa04614394c69cf5793fb284d2147ae64d6f
last_verified_at: 2026-06-30T05:00:00Z
---

## Trade Totals

All figures from breakdown CSV (L11-26). Labor hours per section.

| Section (CSV label) | Labor $ | Material $ | Equip $ | Total $ | Labor Hrs |
|---|---|---|---|---|---|
| General Conditions, Permitting & Pre-Construction | $2,316.08 | $2,130.00 | $0.00 | $4,446.08 | 56 |
| Selective Demolition & Site Work | $1,982.00 | $2,040.00 | $220.00 | $4,242.00 | 56 |
| Excavation, Foundation – Footings & Slab | $2,698.60 | $2,416.18 | $1,950.00 | $7,064.78 | 78 |
| Structural Modifications – LVL Beam & Shoring | $2,117.80 | $2,422.00 | $0.00 | $4,539.80 | 60 |
| Framing – Floor System, Walls & Elevator Shaft | $5,037.50 | $8,850.05 | $120.00 | $14,007.55 | 146 |
| Roof Framing, Sheathing & Roofing System | $3,319.80 | $5,997.50 | $335.00 | $9,652.30 | 96 |
| Exterior Finishes – Siding, Trim & Gutters | $2,474.70 | $2,696.61 | $560.00 | $5,731.31 | 72 |
| Windows, Exterior Door & Weatherproofing | $1,493.80 | $2,172.00 | $0.00 | $3,665.80 | 44 |
| Electrical – 100A Subpanel, Rough-In & Finish | $3,042.00 | $3,680.13 | $0.00 | $6,722.13 | 78 |
| Plumbing – Rough-In, Master Bath & W/D Relocation | $1,356.80 | $2,160.00 | $0.00 | $3,516.80 | 40 |
| HVAC – Mini Split, Tankless WH & Relocations | $1,363.36 | $5,140.00 | $0.00 | $6,503.36 | 36 |
| Insulation & Air Sealing | $1,493.80 | $1,590.64 | $0.00 | $3,084.44 | 44 |
| Drywall – New Addition & Existing Bedroom | $5,428.35 | $3,647.35 | $255.00 | $9,330.70 | 159 |
| Interior Finish Carpentry, Painting & Flooring | $5,540.30 | $7,291.28 | $0.00 | $12,831.58 | 162 |
| Master Bathroom – Custom Tile Shower & Finishes | $3,017.90 | $4,136.60 | $0.00 | $7,154.50 | 88 |
| Existing Hall Bath Mod, Bedroom Remodel & Closeout | $2,484.80 | **-$4,199.00** | $0.00 | **-$1,714.20** | 72 |
| **TOTALS** | **$45,167.59** | **$52,171.33** | **$3,440.00** | **$100,778.92** | **1,287** |

## Allowances

Per scope doc Material Allowance Schedule:

- **LVT Flooring:** $3.00/sqft
- **Windows:** $300 each × 4 = ~$1,200 implied
- **Interior Doors:** $250 each × 4 = ~$1,000 implied
- **Pocket Door Systems:** $400 each × 2 = ~$800 implied
- **Recessed Lights:** $25 each, up to 18 fixtures (scope says ~12 installed)
- **72" Double Vanity:** $1,000
- **Faucets:** $150 each × 2 = $300
- **Vanity Lights:** $100 each × 2 = $200
- **Commode:** $250
- **Shower Valve & Trim:** $250
- **Tile – Walls:** $3.00/sqft
- **Tile – Floor Mosaic:** $6.00/sqft
- **Waterproofing/Setting Materials:** $500
- **Mirrors:** $150 each × 2 = $300
- **Mini Split unit:** $2,500
- **Exterior Door:** $500
- **Guest Bath Shower system (pan + walls):** $1,000 (= hall bath acrylic shower)

## Silent Omissions

Features named in scope that have NO matching dedicated CSV section:

- **TDEC septic inspection / grinder pump evaluation** — scope L25-31 explicitly required pre-construction; no CSV line; costs are CO-only but the PM coordination task (site visit, inspector scheduling) is unaccounted
- **Closet & cabinet system** — optional package ($7,000 allowance); not in base CSV; may be added as CO
- **Tankless water heater** — optional package ($6,500 allowance); not in base CSV; breakdown CSV section title includes "Tankless WH" but base scope has only WH vent extension; HVAC section total includes $5,140 material (likely mini-split unit + HVAC relocation + possibly tankless — AMBIGUOUS)
- **Chimney integration/flashing** — visible on roof plan; no scope line; no CSV line
- **Primary bedroom remodel** — appears folded into "Existing Hall Bath Mod, Bedroom Remodel & Closeout" section (negative material cost) rather than its own section; unclear how bedroom costs are allocated
- **Basement storage finish** — likely rolled into framing/drywall sections; no dedicated CSV line for basement storage lighting or framing
- **Hall switch relocation** (electrical) — minor item called out in scope L81; likely in electrical section but not broken out
- **Elevator shaft electrical (30A circuit)** — likely in electrical section; not separately called out

## Notes

- **Negative section total:** "Existing Hall Bath Mod, Bedroom Remodel & Closeout" shows -$4,199.00 material cost and -$1,714.20 section total (CSV L26). This is a CREDIT or allowance deduction, not actual material cost. $2,484.80 labor hours (72 hrs) suggests real work is included. The negative material likely reflects a credit for removed fixtures (tub/shower combo) or a scope credit applied here. Stage B should clarify.
- **HVAC section title says "Tankless WH"** but base scope only includes WH vent extension (no new tank). $5,140 material in HVAC section is high for just mini-split + relocation — suggests tankless WH materials may already be priced in despite being "optional." Stage B should confirm.
- **Footprint discrepancy:** CSV header says 789 sqft overall footprint; plans show 590 sqft total addition area (295+295). The 199 sqft gap may represent primary bedroom remodel area or existing spaces being modified. Stage B should confirm what "789" represents.
- **Labor hours:** 1,287 total hours — large job. At 2 person average crew ~80 hrs/week, approximately 8+ weeks of on-site labor (raw math; actual schedule depends on parallel trades).
- **Grand total $100,778.92** vs. **scope total investment $173,850** — significant gap ($73K). Scope total likely includes markup, overhead, profit, and optional packages not in the cost breakdown CSV.
