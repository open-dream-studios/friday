---
generation_kind: intel_breakdown_v1
artifact: breakdown_pre
derived_from:
  - path: inputs/files/308_Evergreen_Addition.xlsx - Summary (1).csv.txt
    sha256: c936d98fafac090e05c29bef7398fa04614394c69cf5793fb284d2147ae64d6f
  - path: inputs/scope.md
    sha256: cd479bfac8ead63c5439c8d4f8e8fa5c0af3af616a7f95321b42774ecebd81a6
last_verified_at: 2026-06-30T06:55:00Z
---

# Breakdown Extract — 308 Evergreen Street Addition

## Project Totals
- **Labor Cost:** $45,167.59
- **Material Cost:** $52,171.33
- **Equipment Cost:** $3,440.00
- **Grand Total:** $100,778.92

## Trade Totals (by section)

- **General Conditions, Permitting & Pre-Construction:** $4,446.08 (Labor: $2,316.08 | Material: $2,130.00 | Equipment: $0.00)
- **Selective Demolition & Site Work:** $4,242.00 (Labor: $1,982.00 | Material: $2,040.00 | Equipment: $220.00)
- **Excavation, Foundation – Footings & Slab:** $7,064.78 (Labor: $2,698.60 | Material: $2,416.18 | Equipment: $1,950.00)
- **Structural Modifications – LVL Beam & Shoring:** $4,539.80 (Labor: $2,117.80 | Material: $2,422.00 | Equipment: $0.00)
- **Framing – Floor System, Walls & Elevator Shaft:** $14,007.55 (Labor: $5,037.50 | Material: $8,850.05 | Equipment: $120.00)
- **Roof Framing, Sheathing & Roofing System:** $9,652.30 (Labor: $3,319.80 | Material: $5,997.50 | Equipment: $335.00)
- **Exterior Finishes – Siding, Trim & Gutters:** $5,731.31 (Labor: $2,474.70 | Material: $2,696.61 | Equipment: $560.00)
- **Windows, Exterior Door & Weatherproofing:** $3,665.80 (Labor: $1,493.80 | Material: $2,172.00 | Equipment: $0.00)
- **Electrical – 100A Subpanel, Rough-In & Finish:** $6,722.13 (Labor: $3,042.00 | Material: $3,680.13 | Equipment: $0.00)
- **Plumbing – Rough-In, Master Bath & W/D Relocation:** $3,516.80 (Labor: $1,356.80 | Material: $2,160.00 | Equipment: $0.00)
- **HVAC – Mini Split, Tankless WH & Relocations:** $6,503.36 (Labor: $1,363.36 | Material: $5,140.00 | Equipment: $0.00)
- **Insulation & Air Sealing:** $3,084.44 (Labor: $1,493.80 | Material: $1,590.64 | Equipment: $0.00)
- **Drywall – New Addition & Existing Bedroom:** $9,330.70 (Labor: $5,428.35 | Material: $3,647.35 | Equipment: $255.00)
- **Interior Finish Carpentry, Painting & Flooring:** $12,831.58 (Labor: $5,540.30 | Material: $7,291.28 | Equipment: $0.00)
- **Master Bathroom – Custom Tile Shower & Finishes:** $7,154.50 (Labor: $3,017.90 | Material: $4,136.60 | Equipment: $0.00)
- **Existing Hall Bath Mod, Bedroom Remodel & Closeout:** -$1,714.20 *NET CREDIT* (Labor: $2,484.80 | Material: -$4,199.00 | Equipment: $0.00)

## Allowances

- **Mini Split System:** $2,500 (per scope; line item in HVAC trade)
- **LVT Flooring:** $3.00/sqft (per scope; included in Interior Finish Carpentry)
- **Recessed Lights:** $25 each, up to 12 fixtures budgeted in Electrical
- **Windows:** $300 each (scope allocates 4 windows; reflected in Windows/Weatherproofing trade)
- **Vanity (72"):** $1,000 (per scope; reflected in Master Bathroom trade)
- **Faucets:** $150 each (scope specifies 2; reflected in Master Bathroom)
- **Vanity Lights:** $100 each (scope specifies 2; reflected in Electrical)
- **Commode:** $250 (per scope; reflected in Master Bathroom)
- **Tile (Walls):** $3.00/sqft (per scope; reflected in Master Bathroom)
- **Tile (Floor Mosaic):** $6.00/sqft (per scope; reflected in Master Bathroom)
- **Waterproofing/Setting Materials:** $500 (per scope; reflected in Master Bathroom)
- **Mirrors:** $150 each (scope specifies 2; reflected in Master Bathroom)
- **Exterior Door:** $500 (per scope; reflected in Windows/Weatherproofing)
- **Guest Bath Shower pan and walls:** $1,000 (per scope; reflected in Existing Hall Bath Mod credit line)
- **Interior Doors:** $250 each (scope allocates 4 doors; allocation not transparent in CSV)
- **Pocket Door Systems:** $400 each (scope allocates 2 systems; allocation not transparent in CSV)

## Optional Packages (Not in Main Total)

- **Closet & Cabinet System:** $7,000 (labor + materials)
- **Tankless Water Heater:** $6,500 (labor + materials)

## Silent Omissions (Scope Items Missing from Breakdown)

These scope-named features have no direct cost line in the CSV trade breakdown, suggesting they may be absorbed into larger categories or requiring clarification:

1. **Primary Bedroom Remodel** (~12'5" x 16') — scope lists framing modifications, drywall, paint, flooring, trim. Bedroom costs appear distributed across Drywall + Interior Finish Carpentry trades, but no isolated "Bedroom Remodel" line item. *Question: Is bedroom work fully captured, or missing labor detail?*

2. **Basement Storage Finish** — scope specifies frame, drywall, Level 3 finish, paint, lighting. No explicit "Basement Storage" line. Likely absorbed into Framing + Drywall trades, but unclear if lighting is included. *Question: Are all basement storage finishes costed?*

3. **Elevator Shaft Framing** — scope calls for framing only + rough-in 30A circuit. Framing appears in "Framing – Floor System, Walls & Elevator Shaft" trade; electrical rough-in should be in Electrical trade, but no breakdown. *Question: Is elevator shaft electrical fully allocated?*

4. **Interior Door Installation** — scope lists 4 doors (1 pre-hung, 2 pocket systems). Scope provides allowances ($250 each, $400 pocket), but CSV does not show a separate interior-door cost line. Door costs are likely embedded in "Interior Finish Carpentry" but not isolated. *Question: What is the actual door labor + material allocation within that line?*

5. **Permitting** — scope lists as general condition; CSV line "General Conditions, Permitting & Pre-Construction" bundles all three. Permit costs not isolated. *Question: What is the assumed permit cost for this scope?*

## Notes on Data Quality

- **Negative Material Cost (L17):** "Existing Hall Bath Mod, Bedroom Remodel & Closeout" shows -$4,199.00 material. This is a net credit, likely reflecting salvage value or value of removed fixtures. *Need confirmation: Is this true credit or data entry error?*

- **Labor Hours Total:** CSV shows 1,287 hours across all trades. At $70/hr base rate with differentials, this appears reasonable for a 789 SF addition over estimated duration. *Validation: Does $45,167.59 labor cost ÷ 1,287 hours account correctly for $70 base + differentials?*

- **Equipment Cost Distribution:** $3,440 equipment split across 6 trades (demo, excavation, framing, roofing, exterior, drywall). Largest: Excavation $1,950 (backhoe assumed). *Question: Is equipment cost forecast adequate for all trades listed in scope?*

- **HVAC Line Includes Mini Split + Tankless WH:** Scope budgets Mini Split at $2,500 and offers Tankless WH as optional $6,500. HVAC trade total is $6,503.36, suggesting mini split is in base scope and tankless is optional upsell. *Confirmation needed: Does $6,503.36 = mini split only, or does it include other HVAC relocation costs?*

