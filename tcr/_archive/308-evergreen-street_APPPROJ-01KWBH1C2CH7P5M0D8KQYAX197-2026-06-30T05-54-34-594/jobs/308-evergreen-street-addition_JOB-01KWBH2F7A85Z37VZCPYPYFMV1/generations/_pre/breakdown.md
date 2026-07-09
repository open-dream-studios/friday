---
generation_kind: intel_breakdown_v1
artifact: breakdown_pre
derived_from:
  - path: _projects/308-evergreen-street_APPPROJ-01KWBH1C2CH7P5M0D8KQYAX197/jobs/308-evergreen-street-addition_JOB-01KWBH2F7A85Z37VZCPYPYFMV1/inputs/files/308_Evergreen_Addition.xlsx - Summary (1).csv.txt
    sha256: c936d98fafac090e05c29bef7398fa04614394c69cf5793fb284d2147ae64d6f
  - path: _projects/308-evergreen-street_APPPROJ-01KWBH1C2CH7P5M0D8KQYAX197/jobs/308-evergreen-street-addition_JOB-01KWBH2F7A85Z37VZCPYPYFMV1/inputs/scope.md
    sha256: cd479bfac8ead63c5439c8d4f8e8fa5c0af3af616a7f95321b42774ecebd81a6
last_verified_at: 2026-06-30T05:47:02Z
---

# 308 Evergreens Addition — Breakdown Extraction

## Overview

- **Total Labor:** $45,167.59 (1,287 hours)
- **Total Material:** $52,171.33
- **Total Equipment:** $3,440.00
- **Grand Total:** $100,778.92
- **Footprint:** 789 SF (two-story addition + basement storage)

## Trade totals

- **General:** $4,446.08 (56 hours) — permitting, site setup, management
- **Demo:** $1,982.00 (56 hours) — selective demolition, haul-out, site prep
- **Excavation:** $2,698.60 + $1,950 equip (78 hours) — dig, site work
- **Concrete:** $2,698.60 (foundation) + $2,117.80 (structural mods) combined in section totals
- **Framing:** $5,037.50 (146 hours) + $2,117.80 (LVL structural, 60 hours) — floor, walls, roof framing, elevator shaft
- **Roofing:** included in "Roof Framing, Sheathing & Roofing System" $3,319.80 (96 hours)
- **Siding/Exterior:** $2,474.70 (72 hours) — vinyl siding, fascia, soffit, gutters
- **Windows & Doors:** $1,493.80 (44 hours) — 4 windows, 1 exterior door
- **Electrical:** $3,042.00 (78 hours) — subpanel, rough-in, finish, recessed lights
- **Plumbing:** $1,356.80 (40 hours) — rough-in, master bath, W/D relocation
- **HVAC:** $1,363.36 (36 hours) — mini-split install, relocations
- **Insulation:** $1,493.80 (44 hours) — wall, attic, floor insulation + air sealing
- **Drywall:** $5,428.35 (159 hours) — addition + bedroom remodel + basement storage
- **Paint:** included in "Interior Finish Carpentry, Painting & Flooring"
- **Flooring (LVT):** included in "Interior Finish Carpentry, Painting & Flooring"
- **Trim & Carpentry:** included in "Interior Finish Carpentry, Painting & Flooring" $5,540.30 (162 hours)
- **Tile & Shower:** $3,017.90 (88 hours) — master bath custom tile shower, waterproofing, bench, niche
- **Closeout & Credits:** $2,484.80 labor, -$4,199.00 material credit (72 hours) — hall bath mod, bedroom remodel finishes, punch list

## Material allowances & notes from scope

- **LVT Flooring:** $3.00/sqft budget (scope line 161)
- **Windows:** $300 each × 4 units (scope line 162)
- **Interior Doors:** $250 each × 4 units (scope line 163); note includes 2 pocket door systems @ $400 each (scope line 164)
- **Recessed Lights:** $25 each, up to 18 fixtures (scope line 165)
- **Vanity (72" double):** $1,000 (scope line 166)
- **Faucets:** $150 each (scope line 167)
- **Vanity Lights:** $100 each (scope line 168)
- **Commode:** $250 (scope line 169)
- **Shower Valve & Trim:** $250 (scope line 170)
- **Tile (Walls):** $3.00/sqft (scope line 172)
- **Tile (Floor Mosaic):** $6.00/sqft (scope line 173)
- **Waterproofing/Setting Materials:** $500 (scope line 174)
- **Mirrors:** $150 each (scope line 175)
- **Mini Split:** $2,500 (scope line 176)
- **Exterior Door:** $500 (scope line 177)
- **Guest Bath Shower Pan & Walls:** $1,000 allowance (scope line 178)

## Silent omissions — scope features NOT found in breakdown

1. **Closet & Cabinet System** (scope optional package, line 180–182) — "Design and installation of custom shelving, rods, and closet organization system. Allowance: $7,000 (labor and materials)." — NOT in the CSV breakdown; marked optional but should be clarified whether included or pending customer decision.

2. **Tankless Water Heater** (scope optional package, line 183–185) — "Remove existing water heater and install tankless system including venting and connections. Allowance: $6,500 (labor and materials)." — NOT in the CSV breakdown. Scope line 37 mentions "Extend existing gas water heater vent" which implies the existing tank stays. Confirm customer decision: keep existing tank + vent extension, or replace with tankless?

3. **Septic work** (scope lines 25–31) — Pre-construction tasks mention TDEC septic inspection, feasibility of relocation/replacement, and grinder pump evaluation, but scope explicitly excludes cost ("Costs associated with septic relocation, replacement, or grinder system are not included"). No breakdown line visible for these; confirm whether septic scope is a TBD change order.

4. **Elevator system** (scope lines 55, 153–155) — Scope includes framing the future shaft (4'×4') and rough-in electrical for 30A circuit, but "Elevator system not included." The breakdown includes elevator shaft framing in the "Framing – Floor System, Walls & Elevator Shaft" section (78 hours for framing, line 15 of CSV). Confirm that the elevator installation coordination cost/labor, if later needed, is NOT in this budget.

## Anomalies & questions

- **Negative material credit in closeout** (breakdown.csv L26): "Existing Hall Bath Mod, Bedroom Remodel & Closeout" shows Labor $2,484.80, Material -$4,199.00, Section Total -$1,714.20. This is a credit line (e.g., credit for reusing existing fixtures, removal of old vanity allowance overage, or material return). Clarify what drove the -$4,199 material credit to ensure it's correctly modeled in task graph labor/material split.

- **Mini-split budget vs. HVAC section** (scope line 176 vs. breakdown.csv L21): Scope budgets Mini Split at $2,500. The breakdown "HVAC – Mini Split, Tankless WH & Relocations" section shows Material $5,140.00. The $5,140 likely includes the mini-split unit ($2,500) plus relocation labor/materials and possibly equipment. Confirm that the $5,140 is intended for mini-split + relocations, and no separate tankless WH cost is embedded here (tankless is the optional package not in the base breakdown).

- **Plumbing hours seem light** (breakdown.csv L20): Plumbing – Rough-In, Master Bath & W/D Relocation shows only 40 hours. Scope includes: full rough-in (supply, waste, vent), 2 lavatory drains/supplies, 1 toilet, custom shower with dual valve, W/D relocation with roof vents, vent stack extension. TCR's rule (editor_rules.md) specifies plumbing rough-in for a master bath is **minimum 4 days × 2 crew** (which is 64 person-hours, or 32 8-hour working days at crew size 2). 40 hours = 5 working days at crew size 2. Flag for PM confirmation: is this realistic, or should it be higher?

- **Drywall hours high** (breakdown.csv L23): Drywall section shows 159 hours across "New Addition & Existing Bedroom." This rolls up hang, tape, mud, sand, prime across two areas (addition + bedroom retrofit + basement storage implied). Editor rules suggest ~9–11 working days for a typical addition's consolidated drywall (which is roughly 72–88 person-hours at 3-person crew). 159 hours = ~18.75 person-days at a 3-person crew, or ~19.875 person-days at 2-person crew. Higher than default but plausible for a multi-zone job (addition + retrofit + basement). Confirm crew size assumption.

- **Interior Finishes labor is substantial** (breakdown.csv L24): 162 hours for carpentry, painting, flooring. This is split across trim, paint phase 1, paint phase 2, and LVT flooring. Reasonable order-of-magnitude for a 789 SF footprint but verify that paint is decomposed into two phases (mandatory per TCR rules).

## Project context

- **Two-story addition** 30' × 10' with basement-level storage.
- **Scope includes:** New master suite (bedroom, bath, walk-in closet), primary bedroom remodel, basement storage finish, hall bath modification (acrylic shower swap).
- **Roof tie-in:** Scope calls out 3/12 gable roof tying into existing 6/12 — potential complexity; breakdow treats as standard integration.
- **Structural:** LVL beam (3-ply 14") spanning ~15'6" to open load-bearing wall + temporary shoring included.
- **HVAC:** Mini-split system (ductless).
- **Water heater:** Existing gas tank; scope extends vent through new roof. Tankless is optional (not in base breakdown).
- **Septic/Grinder:** Scope is TBD via change order; not in base.

