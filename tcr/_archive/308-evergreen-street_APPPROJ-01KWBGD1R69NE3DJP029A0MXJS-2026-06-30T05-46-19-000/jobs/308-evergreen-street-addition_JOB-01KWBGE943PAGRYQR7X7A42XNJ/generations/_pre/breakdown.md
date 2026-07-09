---
generation_kind: intel_breakdown_v1
artifact: breakdown_pre
derived_from:
  - path: inputs/files/308_Evergreen_Addition.xlsx - Summary (1).csv.txt
    sha256: c936d98fafac090e05c29bef7398fa04614394c69cf5793fb284d2147ae64d6f
  - path: inputs/scope.md
    sha256: cd479bfac8ead63c5439c8d4f8e8fa5c0af3af616a7f95321b42774ecebd81a6
last_verified_at: 2026-06-30T05:36:13Z
---

# Cost Breakdown Summary — 308 Evergreen Street Addition

**Project Total:** $100,778.92 (Labor: $45,167.59 | Materials: $52,171.33 | Equipment: $3,440.00)  
**Total Labor Hours:** 1,287.00

---

## Trade Labor Cost Distribution

- **General / Permits & Pre-Construction:** $2,316.08 (56 hrs)
- **Demolition & Site Work:** $1,982.00 (56 hrs)
- **Excavation & Foundation:** $2,698.60 (78 hrs)
- **Structural Modifications (LVL & Shoring):** $2,117.80 (60 hrs)
- **Framing (Floor, Walls, Elevator Shaft):** $5,037.50 (146 hrs)
- **Roof Framing & Roofing:** $3,319.80 (96 hrs)
- **Exterior Finishes (Siding, Trim, Gutters):** $2,474.70 (72 hrs)
- **Windows & Exterior Doors:** $1,493.80 (44 hrs)
- **Electrical (Subpanel, Rough-In, Finish):** $3,042.00 (78 hrs)
- **Plumbing (Rough-In, Master Bath, W/D Relocation):** $1,356.80 (40 hrs)
- **HVAC (Mini-Split, Relocations):** $1,363.36 (36 hrs)
- **Insulation & Air Sealing:** $1,493.80 (44 hrs)
- **Drywall (Addition & Bedroom Retrofit):** $5,428.35 (159 hrs)
- **Interior Finish (Carpentry, Painting, Flooring):** $5,540.30 (162 hrs)
- **Master Bathroom (Custom Tile Shower):** $3,017.90 (88 hrs)
- **Hall Bath Mod & Closeout:** $2,484.80 (72 hrs)

---

## Material Allowances & Notable Items (from scope.md)

- **LVT Flooring:** $3.00/sqft throughout addition + bedroom remodel + basement storage
- **Windows:** $300 each (4 total: 3 @ 36"×60" DH + 1 transom)
- **Mini-Split HVAC Unit:** $2,500 budget
- **Tile (Wall):** $3.00/sqft; **Tile (Floor Mosaic):** $6.00/sqft
- **Tile Waterproofing/Setting Materials:** $500
- **Vanity (72" double):** $1,000
- **Faucets:** $150 each (2 for master bath)
- **Vanity Lights:** $100 each (2 for master bath)
- **Shower Valve & Trim:** $250
- **Guest Bath Acrylic Shower Pan & Walls:** $1,000 allowance
- **Exterior Door:** $500
- **Mirrors:** $150 each (2 for master bath)
- **Recessed Lights:** $25 each (up to 12 in scope, estimated)
- **Interior Doors:** $250 each (pre-hung); Pocket Doors: $400 each (2 systems planned)

**Optional Packages (NOT included in totals):**
- Closet & Cabinet System: $7,000 allowance
- Tankless Water Heater: $6,500 allowance

---

## Silent Omissions & Scope-CSV Gaps

1. **Elevator Shaft Framing & Rough-In** — Scope specifies "4' × 4' elevator shaft, framing only, rough-in 30A circuit from subpanel" but the CSV "Framing" section (L15) label mentions elevator shaft parenthetically. Confirm whether the 146 labor hours include a discrete shaft task or if it's bundled into general wall framing. **Action:** Verify with PM during scope deep-dive.

2. **Septic/Grinder Pump System** — Scope pre-construction states "costs associated with septic relocation, replacement, or grinder system are NOT included and will be addressed via change order." Correctly absent from CSV. No action needed unless scope changes.

3. **Tankless Water Heater** — Scope mentions existing gas WH with extended vent; tankless upgrade is optional ($6,500 allowance). Not in base CSV. Clarify customer intent before scheduling procurement tasks.

---

## Notable Line-Item Issues & Questions

- **Hall Bath Mod Section (L26) — Negative Material Credit:** Material cost is −$4,199.00, indicating credit/return of existing fixtures. Labor $2,484.80 + equipment $0 − material credit = net section −$1,714.20. Likely driven by demolition credit (removal of existing tub/shower combo). **Verify:** does this offset apply to other sections or stand alone?

- **Plumbing Labor Hours (40):** Low for scope including master bath rough (4-day nominal per Will's rule), W/D relocation, vent extensions, and quarter-turn shutoffs. Breakdown shows only 40 hrs ≈ 5 days at $70/hr with +$40/hr plumbing differential. **Question:** is the scope missing detail on fixture counts, or is the labor estimate conservative? Task graph must verify against Will's plumbing_rough_min_duration rule (≥ 4 working days × 2 crew).

- **Equipment Allocation:** Only $3,440 total equipment spread across 6 sections: excavation ($1,950 = mini-ex), framing ($120), roof ($335), exterior ($560), drywall ($255). Missing dumpster / haul cost despite demolition scope mentioning "multiple dump runs" and debris removal. **Flag:** confirm hauling method (single dumpster vs. daily trailer runs).

- **Structural Modifications (LVL):** 60 labor hours for 3-ply 14" LVL spanning ~15'-6", including temporary shoring and removal. Reasonable but monitor against site conditions (existing framing strength, shoring clearances).

---

## Summary for Stage B (Scope Deep-Dive & Assumptions)

- ✅ **Well-formed CSV** with clear section boundaries and line-item totals.
- ⚠️ **Scope ambiguities to confirm:** elevator shaft decomposition, plumbing labor adequacy, dumpster/haul method, tankless WH customer decision.
- 🚩 **Negative material credit in Hall Bath** — understand the offset before task scheduling.
- ✅ **No obvious labor-cost inconsistencies** aside from plumbing hours (flagged above).
- ✅ **Equipment costs reasonable** for demolition + excavation scope; confirm dumpster billing model.
