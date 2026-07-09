---
generation_kind: intel_gather_v1
artifact: scope_pre
derived_from:
  - path: _projects/308-evergreen-street_APPPROJ-01KWB8K5NMMZV87339275BVY2Q/jobs/308-evergreen-street-addition_JOB-01KWB8YT0FMGEJH22DS9ZXSEYZ/inputs/scope.md
    sha256: cd479bfac8ead63c5439c8d4f8e8fa5c0af3af616a7f95321b42774ecebd81a6
  - path: _projects/308-evergreen-street_APPPROJ-01KWB8K5NMMZV87339275BVY2Q/jobs/308-evergreen-street-addition_JOB-01KWB8YT0FMGEJH22DS9ZXSEYZ/inputs/files/scope.pdf.txt
    sha256: dc0f25f16699a66e0be27bb9547e854af53e59b3d9422fccd48c6f1b320e8b5f
  - path: _projects/308-evergreen-street_APPPROJ-01KWB8K5NMMZV87339275BVY2Q/jobs/308-evergreen-street-addition_JOB-01KWB8YT0FMGEJH22DS9ZXSEYZ/manifest.json
    sha256: db1e41017c0709e42fa0ce919c85270e53a3c469c05799e951f3ab0a3899d05a
last_verified_at: 2026-06-30T03:26:48Z
---

## Customer & job

- Customer: 308 Evergreen Street (manifest.json)
- Project slug: 308-evergreen-street; job_type: `addition` (manifest.json)
- Drawings authored by Greyscale Design, LLC — Rebecca Lineberry, NCIDQ (plans cover sheet)
- Project name in breakdown: "Simons Addition – 30'x10' Two-Story + Bedroom Remodel" (breakdown.csv L3)

## Footprint

- Two-story addition ~30' × 10' tying into existing structure (scope L1-4)
- 1st-floor addition: 295 sqft; basement addition: 295 sqft; total new addition area: 590 sqft (plans, floor plan L29-31)
- Overall workbook footprint SF: 789 (breakdown.csv L6) — includes retrofit areas (hall bath, primary bedroom remodel)
- Ceiling height: 8'-0" both levels (plans elevations); workbook ceiling height: 8 (breakdown.csv L7)
- 1'-0" rim/band visible at ceiling joint per elevations (plans, all three elevation sheets)

## Foundation

- Continuous 12" × 12" concrete footings around addition perimeter (scope, Foundation section)
- 4" gravel base + vapor barrier + reinforcement (rebar OR wire mesh)
- 4" concrete slab with smooth finish
- NO CMU or full-height foundation wall system (scope explicitly excludes)
- Implies monolithic footing+slab pour (matches editor_rules default)

## Framing

- Basement-level walls: 2x4 @ 16" O.C. (scope, Framing section)
- Floor system above: dimensional lumber OR engineered members sized per span
- Glued + fastened subfloor
- LVL beam: (1) 3-ply 14" spanning approx. 15'-6" to open existing load-bearing wall, with temporary shoring (scope)
- Exterior + interior walls: 2x4 @ 16" O.C.
- Roof: new gable, **truss OR rafter framed, determined during design phase** (scope, Roof System) — ambiguous, defaults to stick-frame per addition rules
- Roof pitch: 3/12 tying into existing 6/12 (scope; confirmed in plans roof plan)
- Plans roof plan shows multiple valleys (V) and ridges (R) at the tie-in (plans, sheet 5)
- Synthetic underlayment, drip edge, flashing, ridge vent
- Architectural asphalt shingles to match existing
- Frame (1) future elevator shaft ~4' × 4' (elevator system NOT included)

## MEP highlights

- **HVAC:** (1) ductless mini-split system, $2,500 budget (scope, HVAC). Existing HVAC components relocated as required.
- **Plumbing:** full rough-in (supply/waste/vent), quarter-turn shutoffs at all fixtures. Master bath: 2 lavs, 1 toilet, 1 custom shower w/ dual valve diverter. W/D relocation including water/drain/roof venting. Vent stacks extended through roof. Existing gas water heater stays — only its vent is extended through the new roof (scope, Selective Demolition + Plumbing).
- **Tankless WH option** (Optional Package, $6,500 allowance) — primary scope keeps existing tank.
- **Electrical:** (1) new 100A subpanel; full rough-in + trim-out; (12) recessed lights ($25 each); (2) vanity lights; (1) bathroom vent fan/light; outlets in storage/closet per code; (1) dedicated 120V/30A circuit for FUTURE elevator. GFCI/AFCI per code. Assumes existing main service can support new subpanel.
- **Septic / sewer:** scope explicitly calls out TDEC septic inspection coordination, feasibility of relocating septic / new tank+leach field, AND grinder pump system option — all costs explicitly excluded, change-order candidates (scope, Pre-Construction & Design Phase L24-32).

## Finishes

- **Flooring:** LVT throughout designated areas, $3.00/sqft allowance
- **Drywall:** Level 3 finish (3 coats, sanded) on all new + affected walls/ceilings. Primer + 2 finish coats paint.
- **Trim:** 5-1/4" MDF or finger-jointed pine baseboard; 2-1/4" casing
- **Interior doors:** (4) total — assume (1) pre-hung + (2) pocket door systems; types/locations TBD design phase
- **Master bath:** custom tile shower ~7' × 4', waterproofing, tile walls + mosaic tile floor; shower niche + bench; dual valve diverter; 72" double vanity; (2) faucets/mirrors/vanity lights; commode; exhaust fan/light vented to exterior
- **Tile allowances:** walls $3.00/sqft; floor mosaic $6.00/sqft; waterproofing/setting $500
- **Primary bedroom remodel** (~12'5" × 16'): framing modified, drywall + Level 3 finish, prime + paint, new LVT, full trim package
- **Basement storage finish:** framed + drywall walls, Level 3 finish, painted, single light fixture, concrete floor remains unfinished

## Special features

- **Customer early item candidate — hall bath acrylic shower swap.** Scope (Existing Hall Bathroom Modification): remove tub/shower combo, $1,000 pan+walls allowance, install acrylic shower, reuse existing valve/trim, PVC trim, minor patching + repaint. Matches the canonical "customer early item" pattern in addition_rules.md L289 (308 example explicitly cited). PM Interview should confirm whether this is a pre-demo early item.
- **Retrofit hall bath work:** remove existing window + frame opening, insulate, drywall + finish — separate from the shower swap (per addition_rules Rule 4V two-bucket pattern).
- **Future elevator shaft:** 4' × 4' framing only + 30A circuit rough-in. Will coordinates with 101 Mobility if homeowner requests. Elevator equipment NOT in scope.
- **Existing heat pump + electrical disconnect relocation** required (scope, Selective Demolition L37-38) — must run BEFORE main demo per addition_rules.
- **Existing gas WH vent extended through new roof** — note: existing tank STAYS, this is a vent extension only (scope, Selective Demolition L39). DO NOT emit `procurement.tank` / `plumbing.tank_set` (per editor_rules Tank-set scope condition).
- **Septic uncertainty (TDEC):** scope mentions TDEC coordination, septic relocation feasibility, grinder pump option — but all marked as change-order candidates. PM Interview must confirm: (a) is home on septic vs city sewer, (b) does adding master bath fixture trigger TDEC capacity issue.
- **Concealed roof tie-in:** new 3/12 gable into existing 6/12 — high change-order risk per addition_rules concealed-roof-tie-in section.
- **Sawcut + remove existing concrete walkway, remove railroad ties** as part of site work (scope, Selective Demolition).
- **Roof plan shows chimney near tie-in zone** (plans, sheet 5) — verify clearances during framing.
