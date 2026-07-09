---
generation_kind: intel_breakdown_v1
artifact: breakdown_pre
derived_from:
  - path: inputs/files/308_Evergreen_Addition.xlsx - Summary (1).csv.txt
    sha256: c936d98fafac090e05c29bef7398fa04614394c69cf5793fb284d2147ae64d6f
  - path: inputs/scope.md
    sha256: cd479bfac8ead63c5439c8d4f8e8fa5c0af3af616a7f95321b42774ecebd81a6
last_verified_at: 2026-06-30T06:22:00Z
---

# 308 Evergreen Street Addition — Cost Breakdown Extract

## Trade Totals (from CSV breakdown)

- **General Conditions, Permitting & Pre-Construction**: $4,446.08
- **Selective Demolition & Site Work**: $4,242.00
- **Excavation, Foundation – Footings & Slab**: $7,064.78
- **Structural Modifications – LVL Beam & Shoring**: $4,539.80
- **Framing – Floor System, Walls & Elevator Shaft**: $14,007.55
- **Roof Framing, Sheathing & Roofing System**: $9,652.30
- **Exterior Finishes – Siding, Trim & Gutters**: $5,731.31
- **Windows, Exterior Door & Weatherproofing**: $3,665.80
- **Electrical – 100A Subpanel, Rough-In & Finish**: $6,722.13
- **Plumbing – Rough-In, Master Bath & W/D Relocation**: $3,516.80
- **HVAC – Mini Split, Tankless WH & Relocations**: $6,503.36
- **Insulation & Air Sealing**: $3,084.44
- **Drywall – New Addition & Existing Bedroom**: $9,330.70
- **Interior Finish Carpentry, Painting & Flooring**: $12,831.58
- **Master Bathroom – Custom Tile Shower & Finishes**: $7,154.50
- **Existing Hall Bath Mod, Bedroom Remodel & Closeout**: -$1,714.20 *(credit/offset)*

**Grand Total**: $100,778.92  
**Labor**: $45,167.59  
**Material**: $52,171.33  
**Equipment**: $3,440.00  

## Labor Summary

**Total Labor Hours**: 1,287.00 hours  
**Blended Average Labor Rate**: ~$35.07/hr (gross total ÷ hours)  
*Note: Scope specifies $70/hr base + differentials ($15 teamlead, $30 electrical/HVAC, $40 plumbing); this average reflects mix.*

## Material Allowances (from scope, with CSV references)

- **LVT Flooring**: $3.00/sqft (scope L161) — included in "Interior Finish Carpentry, Painting & Flooring" (L24, $7,291.28 material)
- **Windows**: $300 each × 4 units = $1,200 (scope L162) — included in "Windows, Exterior Door & Weatherproofing" (L18, $2,172.00 material)
- **Interior Doors**: $250 pre-hung × 1 + $400 pocket door × 2 = $1,050 (scope L163–164) — included in drywall/finish sections
- **Recessed Lights**: $25 × 12 = $300 (scope L165) — included in "Electrical" (L19, $3,680.13 material)
- **Vanity (72")**: $1,000 (scope L166) — included in "Master Bathroom" (L25, $4,136.60 material)
- **Faucets**: $150 × 2 = $300 (scope L167) — included in plumbing/bathroom sections
- **Mini Split**: $2,500 (scope L176) — included in "HVAC – Mini Split, Tankless WH & Relocations" (L21, $5,140.00 material)
- **Exterior Door**: $500 (scope L177) — included in "Windows, Exterior Door & Weatherproofing" (L18)
- **Guest Bath Shower system pan/walls**: $1,000 (scope L178) — included in "Existing Hall Bath Mod" (L26)
- **Tile (Walls)**: $3.00/sqft (scope L172) — included in "Master Bathroom – Custom Tile Shower & Finishes" (L25, $4,136.60)
- **Tile (Floor Mosaic)**: $6.00/sqft (scope L173) — included in Master Bath line
- **Waterproofing/Setting Materials**: $500 (scope L174) — included in Master Bath line
- **Mirrors**: $150 × 2 = $300 (scope L175) — included in Master Bath line
- **Commode**: $250 (scope L169) — included in Master Bath line
- **Shower Valve & Trim**: $250 (scope L170) — included in plumbing or Master Bath

## Silent Omissions (scope items with no discrete CSV line)

1. **Backhoe Usage**: Scope L197 states "$1,100/wk" but no CSV line item. May be zero-duration assumption or included in "Selective Demolition & Site Work" (L12).

2. **Debris Removal Dump Trailer**: Scope L196 specifies "$450 per removal" with "multiple dump runs" mentioned (scope L38). This cost structure does not appear as discrete line in CSV; likely absorbed into "Selective Demolition & Site Work" (L12, $4,242.00).

3. **Closet & Cabinet System (Optional)**: Scope L180–182 lists "$7,000 allowance (labor + materials)" for custom shelving/rods. **NOT included in CSV total** — this is an optional add-on.

4. **Tankless Water Heater (Optional)**: Scope L183–185 lists "$6,500 allowance (labor + materials)" for removal of existing WH + tankless install. Title of CSV (L1) mentions "Incl. Tankless WH Option" but detailed breakdown line 21 "HVAC – Mini Split, Tankless WH & Relocations" shows $5,140.00 material cost, suggesting **tankless may be partially costed in HVAC material but full allowance ($6,500) is not explicitly called out**. Requires clarification.

5. **Interior Trim Detail**: Scope L114 lists "Install casing: 2-1/4" profile" and L113 "Install baseboard: 5-1/4" MDF or finger-jointed pine". No separate allowance line; assumed bundled into "Interior Finish Carpentry, Painting & Flooring" (L24).

6. **Paint Finish**: Scope L110–111 specifies "Apply primer and (2) coats of finish paint" and "Level 3 drywall finish". Labor and materials are embedded in drywall (L23) and finish carpentry (L24) sections; no separate paint allowance line.

7. **Elevator Shaft Rough-In**: Scope L154 mentions "rough-in electrical for 30 amp circuit" but electrical subpanel labor (L19) includes "Electrical – 100A Subpanel, Rough-In & Finish" at $3,042 labor + $3,680.13 material. Confirm if elevator 30A circuit is fully accounted for.

## Anomalies & Flags

1. **Negative Material Credit (L26)**: "Existing Hall Bath Mod, Bedroom Remodel & Closeout" shows -$4,199.00 material cost. This is unusual and suggests either:
   - A material credit (e.g., salvage value, reuse of existing fixture).
   - A data entry error or reversal.
   - **Recommendation**: Confirm the nature of this credit before finalizing purchase orders.

2. **Equipment Cost Concentration**: $1,950.00 of the total $3,440 equipment budget (56.6%) is allocated to "Excavation, Foundation – Footings & Slab" (L13), likely for excavator/compactor rental. Other trades show minimal or zero equipment. Verify equipment rental schedule.

3. **Low Electrical Labor Cost**: Line 19 "Electrical – 100A Subpanel, Rough-In & Finish" shows only $3,042 labor for approximately 78 hours of work (implied from section total / rate). At $70/hr base + $30 electrical differential = $100/hr, expected labor would be ~$7,800. This gap suggests either:
   - Electrical labor is under-estimated.
   - Electrical differentials are not applied as stated in scope.
   - **Recommendation**: Cross-check against hourly detail or scope rates.

4. **HVAC Labor Underestimation**: Line 21 "HVAC – Mini Split, Tankless WH & Relocations" shows $1,363.36 labor for 36 hours. At $100/hr (base + differential), this should be ~$3,600. Same pattern as electrical.
   - **Recommendation**: Verify HVAC labor hours and rates.

5. **Plumbing Labor (L20)**: "Plumbing – Rough-In, Master Bath & W/D Relocation" shows $1,356.80 labor for 40 hours. At $110/hr (base + plumbing differential), expected ~$4,400. Again, appears under-budgeted.
   - **Recommendation**: Confirm plumbing labor hours and wage structure alignment.

6. **Total Labor Hours (1,287) vs. Scope Estimate**: Scope does not provide an explicit total labor hour target for comparison. The 1,287 hours at blended $35.07/hr ≈ $45,167.59 labor cost. Verify this is reasonable for a 30'×10' two-story addition with full MEP systems.

7. **Title Reference to Tankless WH**: CSV title (L1) mentions "Incl. Tankless WH Option" but the optional tankless package in scope (L183–185) is listed separately with a $6,500 allowance. If the CSV total of $100,778.92 is meant to include tankless, the $6,500 should be explicitly in the breakdown. Current material cost for HVAC (L21) is $5,140, which does not align with the full $6,500 optional allowance. **Clarify whether tankless is included in base cost or is truly optional.**

---

## Summary for Stage B

**Total Project Cost (CSV)**: $100,778.92  
**Optionals Not Included**: Closet & Cabinet System ($7,000) + Tankless WH allowance clarity needed  
**Total if Both Optionals Included**: ~$113,778.92 (pending tankless clarification)

**Confidence Level**: Medium. Trade-level cost structure is clear, but labor rate alignment, optional package treatment, and negative material credit require field verification before commitment.

Key next steps:
1. Confirm backhoe/equipment rental schedule.
2. Validate electrical and HVAC labor hours against scope technical requirements.
3. Clarify tankless water heater treatment (included vs. optional).
4. Investigate negative material credit in line 26.
5. Verify basement storage, drywall finish levels, and trim package are fully costed.
