---
generation_kind: intel_gather_v1
artifact: breakdown_pre
derived_from:
  - path: _projects/308-evergreen-street_APPPROJ-01KWBB9KK65K5YY8K6F65RJJ2R/jobs/308-evergreen-street-addition_JOB-01KWBBAR4PWJV3HEQ0MY8DYE1C/inputs/files/308_Evergreen_Addition.xlsx - Summary (1).csv.txt
    sha256: c936d98fafac090e05c29bef7398fa04614394c69cf5793fb284d2147ae64d6f
  - path: _projects/308-evergreen-street_APPPROJ-01KWBB9KK65K5YY8K6F65RJJ2R/jobs/308-evergreen-street-addition_JOB-01KWBBAR4PWJV3HEQ0MY8DYE1C/inputs/scope.md
    sha256: cd479bfac8ead63c5439c8d4f8e8fa5c0af3af616a7f95321b42774ecebd81a6
last_verified_at: 2026-06-30T04:08:07Z
---

## Project totals

- Labor: $45,167.59 (1,287 labor hours)
- Material: $52,171.33
- Equipment: $3,440.00
- **Grand Total: $100,778.92** (CSV L1-5)
- Note: scope.md `Total Investment` line states $173,850 — **discrepancy of ~$73k** vs CSV grand total (scope.md L179 vs breakdown.csv totals)
- Title flag: CSV header reads "Incl. Tankless WH Option" — tankless appears to be priced IN this breakdown (CSV L1)

## Section totals (each = labor + material + equipment)

- General Conditions, Permitting & Pre-Construction: **$4,446.08** (56 lh)
- Selective Demolition & Site Work: **$4,242.00** (56 lh, $220 equip)
- Excavation, Foundation – Footings & Slab: **$7,064.78** (78 lh, $1,950 equip)
- Structural Modifications – LVL Beam & Shoring: **$4,539.80** (60 lh)
- Framing – Floor System, Walls & Elevator Shaft: **$14,007.55** (146 lh, $120 equip)
- Roof Framing, Sheathing & Roofing System: **$9,652.30** (96 lh, $335 equip)
- Exterior Finishes – Siding, Trim & Gutters: **$5,731.31** (72 lh, $560 equip)
- Windows, Exterior Door & Weatherproofing: **$3,665.80** (44 lh)
- Electrical – 100A Subpanel, Rough-In & Finish: **$6,722.13** (78 lh)
- Plumbing – Rough-In, Master Bath & W/D Relocation: **$3,516.80** (40 lh)
- HVAC – Mini Split, Tankless WH & Relocations: **$6,503.36** (36 lh) — tankless WH bundled here
- Insulation & Air Sealing: **$3,084.44** (44 lh)
- Drywall – New Addition & Existing Bedroom: **$9,330.70** (159 lh, $255 equip)
- Interior Finish Carpentry, Painting & Flooring: **$12,831.58** (162 lh)
- Master Bathroom – Custom Tile Shower & Finishes: **$7,154.50** (88 lh)
- Existing Hall Bath Mod, Bedroom Remodel & Closeout: **-$1,714.20** (72 lh) — **NEGATIVE** (likely credit / template offset)

## Material allowances (per scope, not separately broken out in CSV)

- LVT flooring: $3.00/sqft (scope.md L161)
- Windows: $300 each (scope.md L162)
- Interior doors: $250 each (scope.md L163)
- Pocket door systems: $400 each (scope.md L164)
- Recessed lights: $25 each, up to 18 fixtures (scope.md L165)
- Vanity (72"): $1,000 (scope.md L166)
- Faucets: $150 each (scope.md L167)
- Vanity lights: $100 each (scope.md L168)
- Commode: $250 (scope.md L169)
- Shower valve & trim: $250 (scope.md L170)
- Tile walls: $3.00/sqft (scope.md L172)
- Tile floor mosaic: $6.00/sqft (scope.md L173)
- Waterproofing/setting materials: $500 (scope.md L174)
- Mirrors: $150 each (scope.md L175)
- Mini-split: $2,500 (scope.md L176)
- Exterior door: $500 (scope.md L177)
- Guest bath shower pan + walls: $1,000 (scope.md L178)

## Optional packages (NOT in base CSV totals)

- Custom Closet & Cabinet System: $7,000 allowance — labor + materials (scope.md L180-182)
- Tankless Water Heater: $6,500 allowance — labor + materials, utility upgrades excluded (scope.md L184-186) — **conflicts with CSV title claim that tankless is included**

## Silent omissions (in scope but NO matching CSV line)

- **Septic / TDEC / grinder pump:** scope.md L25-30 explicitly defers cost via change order — correctly NOT in CSV but Stage B should confirm this stayed a CO
- **Optional Closet & Cabinet System ($7,000):** no CSV line — opt-in not selected for this priced quote
- **Optional Tankless WH ($6,500):** CSV title implies included, but no separate "tankless" line — appears folded into HVAC section ($6,503 HVAC total) — **needs verification**
- **Elevator system (motor / cab):** correctly excluded per scope.md L55 (framing + circuit only)
- **Truss procurement:** roof framing method "truss OR rafter" undetermined — no separate truss procurement line (consistent with stick-frame default for small addition)

## Notes / weird lines

- Hall Bath Mod / Bedroom Remodel / Closeout section: **negative $1,714** with 72 labor hours — section_total < 0 with labor_hours > 40 triggers dev_rule warning #8 (scope ambiguity / template offset). The labor hours are real but materials show -$4,199 (likely a credit from template).
- HVAC section is **$6,503** with only 36 labor hours — high material cost ($5,140) is consistent with mini-split + tankless WH unit cost bundled.
- Plumbing section labor only 40 hours (~5 working days at 1 crew, ~2.5 working days at 2 crew) — appears LOW for master bath + W/D relocation + vent stack work (editor rules note ≥4d × 2 crew floor for any job with master bath / W/D relocation — confirm with PM).
- Framing section bundles "Floor System, Walls & Elevator Shaft" into one $14k line — elevator shaft framing not separately priced.
- Drywall section bundles "New Addition & Existing Bedroom" together (159 lh) — consistent with editor_rules consolidation guidance.
- Equipment costs concentrated in Excavation ($1,950 — backhoe/mini-ex), Siding ($560 — scaffold), Roofing ($335), Demo ($220), Drywall ($255), Framing ($120). Total $3,440.
