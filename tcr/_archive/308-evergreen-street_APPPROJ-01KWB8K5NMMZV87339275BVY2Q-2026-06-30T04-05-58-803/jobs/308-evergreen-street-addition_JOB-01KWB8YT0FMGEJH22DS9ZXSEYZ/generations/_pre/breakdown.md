---
generation_kind: intel_gather_v1
artifact: breakdown_pre
derived_from:
  - path: _projects/308-evergreen-street_APPPROJ-01KWB8K5NMMZV87339275BVY2Q/jobs/308-evergreen-street-addition_JOB-01KWB8YT0FMGEJH22DS9ZXSEYZ/inputs/files/308_Evergreen_Addition.xlsx - Summary (1).csv.txt
    sha256: c936d98fafac090e05c29bef7398fa04614394c69cf5793fb284d2147ae64d6f
  - path: _projects/308-evergreen-street_APPPROJ-01KWB8K5NMMZV87339275BVY2Q/jobs/308-evergreen-street-addition_JOB-01KWB8YT0FMGEJH22DS9ZXSEYZ/inputs/scope.md
    sha256: cd479bfac8ead63c5439c8d4f8e8fa5c0af3af616a7f95321b42774ecebd81a6
last_verified_at: 2026-06-30T03:26:48Z
---

## Project totals

- Labor: $45,167.59 (breakdown.csv L2)
- Material: $52,171.33
- Equipment: $3,440.00
- **Grand Total: $100,778.92** — note: scope.md states a customer-facing total of $173,850 (scope, Material Allowance Schedule). Large gap; breakdown is the trade-cost rollup, scope total likely includes markup/margin/GC.
- Labor hours total: 1,287.00

## Trade / section totals (labor / material / equipment / section_total / hours)

- General Conditions, Permitting & Pre-Construction: $2,316.08 / $2,130.00 / $0 / $4,446.08 / 56h (breakdown.csv L10)
- Selective Demolition & Site Work: $1,982 / $2,040 / $220 / $4,242 / 56h
- Excavation, Foundation – Footings & Slab: $2,698.60 / $2,416.18 / $1,950 / $7,064.78 / 78h
- Structural Modifications – LVL Beam & Shoring: $2,117.80 / $2,422 / $0 / $4,539.80 / 60h
- Framing – Floor System, Walls & Elevator Shaft: $5,037.50 / $8,850.05 / $120 / $14,007.55 / 146h
- Roof Framing, Sheathing & Roofing System: $3,319.80 / $5,997.50 / $335 / $9,652.30 / 96h
- Exterior Finishes – Siding, Trim & Gutters: $2,474.70 / $2,696.61 / $560 / $5,731.31 / 72h
- Windows, Exterior Door & Weatherproofing: $1,493.80 / $2,172 / $0 / $3,665.80 / 44h
- Electrical – 100A Subpanel, Rough-In & Finish: $3,042 / $3,680.13 / $0 / $6,722.13 / 78h
- Plumbing – Rough-In, Master Bath & W/D Relocation: $1,356.80 / $2,160 / $0 / $3,516.80 / 40h
- HVAC – Mini Split, Tankless WH & Relocations: $1,363.36 / $5,140 / $0 / $6,503.36 / 36h
- Insulation & Air Sealing: $1,493.80 / $1,590.64 / $0 / $3,084.44 / 44h
- Drywall – New Addition & Existing Bedroom: $5,428.35 / $3,647.35 / $255 / $9,330.70 / 159h
- Interior Finish Carpentry, Painting & Flooring: $5,540.30 / $7,291.28 / $0 / $12,831.58 / 162h
- Master Bathroom – Custom Tile Shower & Finishes: $3,017.90 / $4,136.60 / $0 / $7,154.50 / 88h
- **Existing Hall Bath Mod, Bedroom Remodel & Closeout: $2,484.80 / -$4,199.00 / $0 / -$1,714.20 / 72h** — negative material total = strong anomaly signal (see Notes below)

## Allowances (from scope, Material Allowance Schedule L92-110)

- LVT flooring: $3.00/sqft
- Windows: $300 each (4 windows total)
- Interior doors: $250 each (4 doors)
- Pocket door systems: $400 each (2 systems assumed)
- Recessed lights: $25 each, up to 18 fixtures (scope lists ~12 per electrical section)
- Vanity (72"): $1,000
- Faucets: $150 each
- Vanity lights: $100 each
- Commode: $250
- Shower valve & trim: $250
- Tile (walls): $3.00/sqft
- Tile (floor mosaic): $6.00/sqft
- Waterproofing/setting materials: $500
- Mirrors: $150 each
- Mini-split: $2,500 (HVAC section also lists this)
- Exterior door: $500
- Guest bath shower system (pan + walls): $1,000
- Optional — Closet & cabinet system: $7,000 (NOT in main breakdown — opt-in package)
- Optional — Tankless WH replacement: $6,500 (NOT in main breakdown — opt-in package)
- Debris removal: $450 per 7'x14' dump trailer run
- Backhoe usage: $1,100/week

## Silent omissions (in scope, NOT in CSV)

- **TDEC septic permit fee** — scope L24-27 mentions $500 TDEC permit fee implicitly via "Coordinate and complete septic inspection with TDEC" but breakdown has NO `permit.tdec_septic` line nor a $500 line item. PM Interview must confirm septic vs city sewer; if septic, schedule needs `permit.tdec_septic` task (per job_types/addition/rules/tdec_septic_permit_offset.md).
- **Grinder pump system** — scope mentions as change-order candidate, no CSV line (expected — explicitly excluded from base contract).
- **Septic relocation / new tank + leach field** — scope mentions as change-order candidate, no CSV line (expected — explicitly excluded).
- **Existing main service amperage check** — scope assumes existing main service can support new 100A subpanel, but no `prep.amperage_check` task or line item exists. Addition rules MANDATE this check (`addition_rules.md` § Existing electrical service).
- **Elevator equipment** — explicitly excluded (only shaft framing + 30A circuit are in scope). Correctly absent from CSV.
- **Tankless WH** — Optional Package only; not in primary CSV trade lines despite HVAC section name reading "HVAC – Mini Split, Tankless WH & Relocations". The section material+labor totals likely include only the relocation/vent extension work for the EXISTING tank, not a tankless install. PM should confirm.
- **Concealed-roof-tie-in discovery buffer / change-order reserve** — scope acknowledges tie-in risk ("Roof tie-in assumes standard integration; additional structural modifications not included") but no contingency line. Standard TCR practice per addition_rules.md.
- **Cabinets** — no cabinet/casework section in CSV beyond the 72" vanity allowance. Master bath has vanity; primary bedroom remodel does NOT include built-in closet system (separate Optional Package at $7,000). Confirms scope's separation of bedroom vs closet packages.
- **Septic system test fee ($500) and soil scientist** — not budgeted in CSV. If TDEC required, must be carried as change order or PM contingency.

## Notes / anomalies

- **Negative section total ($-1,714.20) on "Existing Hall Bath Mod, Bedroom Remodel & Closeout"** — section has $2,484.80 labor + $-4,199.00 material. The negative material is almost certainly a credit/offset (e.g. customer-supplied materials, salvage credit, or a deliberate "subtract-from-bid" line). Per dev_rules edge-case 12, labor_hours = 72h is large; the negative is NOT a small punch-list credit. PM Interview should explain — likely a credit for the existing tub/shower not being installed by TCR, or for customer-supplied acrylic shower system.
- **Section labels combine multiple scopes** — e.g. one section covers Hall Bath Modification + Bedroom Remodel + Closeout. Decomposition will need to split these for the TaskGraph (retrofit hall bath vs primary bedroom retrofit vs project-wide closeout).
- **No separate "rough inspections" or "final inspections" section** — inspection labor is presumably absorbed into General Conditions. Stage B should confirm.
- **General Conditions hours: 56h** — at general crew rates that's ~7 working days of PM time, which is light for a 3-month addition. Typical PM admin/walkthrough/coordination ranges higher; flag for review.
- **Plumbing section: only 40h** — Will's nominal (per editor_rules "plumbing rough-in 4d × 2 crew" = 64h minimum for a master bath + W/D relocation + vent stacks). 40h could mean the breakdown sized rough at 3 days × 2 = 48h with finish folded in, but it's borderline tight per Rule 4H / plumbing duration heuristic.
- **HVAC section: 36h / $5,140 material** — material-heavy because of mini-split equipment cost. Mini-split rough should be 0.5d/1 person = 4h, install = 1d/1 person = 8h. The 36h leaves ~24h for "relocations" (existing HVAC components) — plausible.
- **Drywall section: 159h / 3-person crew → ~6.6 days** if you took it raw, but consolidated drywall for "addition + retrofit + basement storage" is expected to land at 9-11 working days per editor_rules. Stage B should reconcile via duration heuristic.
- **Roof system: 96h** — for a small addition with ~300 sqft of shingles. Editor_rules cap shingles at 1 day, so most of 96h is framing the new gable + tie-in + dry-in package, not roofing itself.
