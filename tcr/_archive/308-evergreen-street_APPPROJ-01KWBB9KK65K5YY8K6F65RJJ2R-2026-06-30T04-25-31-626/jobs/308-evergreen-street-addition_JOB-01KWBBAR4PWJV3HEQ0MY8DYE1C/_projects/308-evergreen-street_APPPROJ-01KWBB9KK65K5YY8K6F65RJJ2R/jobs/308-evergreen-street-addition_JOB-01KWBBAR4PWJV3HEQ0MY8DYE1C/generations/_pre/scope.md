---
generation_kind: intel_gather_v1
artifact: scope_pre
derived_from:
  - path: _projects/308-evergreen-street_APPPROJ-01KWBB9KK65K5YY8K6F65RJJ2R/jobs/308-evergreen-street-addition_JOB-01KWBBAR4PWJV3HEQ0MY8DYE1C/inputs/scope.md
    sha256: cd479bfac8ead63c5439c8d4f8e8fa5c0af3af616a7f95321b42774ecebd81a6
  - path: _projects/308-evergreen-street_APPPROJ-01KWBB9KK65K5YY8K6F65RJJ2R/jobs/308-evergreen-street-addition_JOB-01KWBBAR4PWJV3HEQ0MY8DYE1C/inputs/files/scope.pdf.txt
    sha256: dc0f25f16699a66e0be27bb9547e854af53e59b3d9422fccd48c6f1b320e8b5f
  - path: _projects/308-evergreen-street_APPPROJ-01KWBB9KK65K5YY8K6F65RJJ2R/jobs/308-evergreen-street-addition_JOB-01KWBBAR4PWJV3HEQ0MY8DYE1C/manifest.json
    sha256: 3baf255e53b0135efdbd747a977a13d1a1f999d5e77b4e3c928fd7d865f664c8
last_verified_at: 2026-06-30T04:08:07Z
---

## Customer & job

- Customer / address: 308 Evergreen Street (manifest.json `customer`)
- job_type: `addition` (manifest.json)
- Project label: "Simons Addition – 30'x10' Two-Story + Bedroom Remodel" (breakdown.csv L3)

## Footprint

- Addition footprint: 30' × 10' two-story (scope.md L3)
- 1st floor addition: 295 sqft; basement addition: 295 sqft; total NEW addition area: 590 sqft (plans floor-plan schedule)
- Overall jobsite footprint (incl. retrofit areas): 789 sqft (breakdown.csv header)
- Ceiling height: 8' (breakdown.csv header; confirmed in elevations)
- Floors: 2 (basement storage below + master suite above)

## Foundation

- Continuous 12" × 12" concrete footings around addition perimeter (scope.md L40)
- 4" gravel base under slab + vapor barrier + rebar/wire mesh reinforcement (scope.md L41-43)
- 4" concrete slab, smooth finish (scope.md L44)
- NO CMU / no full-height foundation walls (scope.md L45) — monolithic-compatible default

## Framing

- All walls (basement, exterior, interior): 2x4 lumber @ 16" O.C. (scope.md L47, L54)
- Floor system above basement: dimensional or engineered members, sized per span (scope.md L48-49)
- LVL beam: (1) 3-ply 14" engineered LVL, ~15'-6" span, opens existing load-bearing wall, requires temp shoring (scope.md L51-53)
- Roof: new gable system, 3/12 pitch tying into existing 6/12 (scope.md L57-58)
- Roof framing method: "truss or rafter framed, determined during design phase" — UNDETERMINED in scope (scope.md L57)
- Roofing: architectural asphalt shingles + synthetic underlayment + drip edge + flashing + ridge vent (scope.md L60-61)
- Exterior: sheathing + WRB + vinyl siding + fascia + vinyl soffit + seamless gutters (scope.md L62, L66-67)

## MEP highlights

- HVAC: (1) ductless mini-split system, $2,500 budget (scope.md L99); existing HVAC components relocated as required (scope.md L100)
- Existing heat pump relocation REQUIRED before demo (scope.md L36)
- Existing electrical disconnect relocation REQUIRED before demo (scope.md L36)
- Plumbing: full rough-in (supply/waste/vent); master bath: 2 lavs, 1 toilet, 1 custom shower w/ dual-valve diverter; W/D relocation with water/drain/roof vent; extend vent stacks through roof (scope.md L89-96)
- Water heater: scope EXTENDS existing gas WH vent through new roof (scope.md L37) — existing WH STAYS in base scope
- Optional Tankless WH package: $6,500 allowance for tankless install + venting (scope.md L184-185) — separate from base
- Electrical: (1) new 100A subpanel; full rough + finish; ~12 recessed lights @ $25 each; 2 vanity lights; 1 bath fan/light; outlets per spec; GFCI/AFCI per code; dedicated 120V/30A circuit for future elevator (scope.md L73-85)
- Assumes existing main electrical service can support new 100A subpanel (scope.md L86) — NOT verified
- Septic: TDEC inspection + feasibility evaluation for septic relocation OR new septic OR grinder-pump-to-sewer; ALL costs explicitly excluded, addressed via CO (scope.md L25-30)

## Insulation

- R13 exterior walls; R30 attic/roof; R30 floor system between basement and living space (scope.md L103-105)

## Finishes

- Drywall: 3-coat L3 finish, sanded, ready for paint (scope.md L108-110)
- Paint: primer + 2 coats finish (scope.md L111)
- Flooring: LVT throughout, $3.00/sqft allowance (scope.md L112, L161)
- Trim: 5-1/4" MDF or finger-jointed pine baseboard; 2-1/4" casing profile (scope.md L113-114)
- Interior doors: (4) total — assume (1) pre-hung + (2) pocket-door systems; final locations TBD (scope.md L118-120)
- Master bath: custom tile shower ~7' × 4' w/ waterproofing + tile walls + mosaic tile floor + niche + bench + dual-valve diverter; 72" double vanity; 2 faucets/mirrors/lights; commode; bath fan/light vented to exterior (scope.md L122-129)
- Allowances: tile walls $3/sqft; tile floor mosaic $6/sqft; waterproofing $500; vanity $1,000; faucets $150/ea; mirrors $150/ea; commode $250; shower valve+trim $250; mini split $2,500; exterior door $500 (scope.md L172-178)

## Special features

- **Future elevator shaft (4' × 4'):** framing only + rough-in for dedicated 30A 120V circuit; elevator system NOT included; will coordinate with 101 Mobility if requested (scope.md L55, L85, L153-155)
- **Primary bedroom remodel (~12'5" × 16'):** modify framing, drywall L3, prime+paint, new LVT, full trim package (scope.md L130-135) — RETROFIT within existing footprint
- **Basement storage finish:** frame + drywall walls, L3 finish + paint, 1 lighting fixture, concrete floor stays unfinished (scope.md L136-140)
- **Existing hall bathroom modification:** remove existing window + frame opening + insulate/drywall/finish; remove tub/shower combo + install acrylic shower system ($1,000 allowance for pan+walls); reuse existing valve & trim; PVC trim; patch + repaint (scope.md L141-149) — RETROFIT + likely customer early item (acrylic shower swap)
- **Optional Closet & Cabinet System:** $7,000 allowance for custom shelving / rods / organization (scope.md L180-182) — opt-in
- **Optional Tankless WH:** $6,500 allowance for remove existing + install tankless + venting + connections; utility upgrades excluded (scope.md L184-186) — opt-in
- **Septic/sewer scope uncertainty:** TDEC inspection + feasibility for septic relocation / new septic / grinder pump — costs excluded, addressed via CO (scope.md L25-30)

## Explicit exclusions

- French drains, foundation waterproofing, drainage improvements (scope.md L151-152)
- Septic / grinder pump install (cost only — via CO) (scope.md L28-30)
- Rock excavation, unsuitable soil work (scope.md L16-18) — via CO
- Elevator system itself (scope.md L55)

## Pricing structure (notable rates)

- General hourly $70; teamlead +$15; electrical/HVAC +$30; plumbing +$40 (scope.md L188-192)
- Materials at cost +15%; subs at cost +30% (scope.md L193-195)
- Debris removal $450/dump; backhoe $1,100/wk (scope.md L196-197)
- Total Investment quoted in scope: $173,850 (scope.md L179) — NOTE discrepancy with breakdown.csv grand total $100,778.92
- Deposit: $20,000 (scope.md L199); weekly invoicing thereafter
