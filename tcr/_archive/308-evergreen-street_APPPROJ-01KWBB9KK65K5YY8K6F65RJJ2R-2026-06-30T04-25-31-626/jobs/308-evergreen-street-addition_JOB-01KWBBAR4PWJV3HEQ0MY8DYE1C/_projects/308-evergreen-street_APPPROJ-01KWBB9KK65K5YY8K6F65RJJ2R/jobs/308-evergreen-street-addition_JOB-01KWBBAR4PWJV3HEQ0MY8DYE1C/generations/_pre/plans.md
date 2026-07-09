---
generation_kind: intel_gather_v1
artifact: plans_pre
derived_from:
  - path: _projects/308-evergreen-street_APPPROJ-01KWBB9KK65K5YY8K6F65RJJ2R/jobs/308-evergreen-street-addition_JOB-01KWBBAR4PWJV3HEQ0MY8DYE1C/inputs/files/3725 SIMONS 012226.pdf.txt
    sha256: 728d5090fe11df16e226dcadd85c52a4e5edf9ade2e4dbcdd0771fd9e0ccae6b
  - path: _projects/308-evergreen-street_APPPROJ-01KWBB9KK65K5YY8K6F65RJJ2R/jobs/308-evergreen-street-addition_JOB-01KWBBAR4PWJV3HEQ0MY8DYE1C/inputs/scope.md
    sha256: cd479bfac8ead63c5439c8d4f8e8fa5c0af3af616a7f95321b42774ecebd81a6
last_verified_at: 2026-06-30T04:08:07Z
---

## Drawing set (5 sheets)

- Sheet 01: Left + Back elevations
- Sheet 02: Right elevation
- Sheet 03: Floor plan (1st floor addition + basement addition)
- Sheet 04: Roof plan
- Designer: Rebecca Lineberry, NCIDQ — Greyscale Design, LLC (501-548-2885)
- Plan date: Jan 22, 2026
- Sheet header titled "3725 SIMONS / 647 AA DEAKINS RD, JONESBOROUGH, TN 37659" — **NOTE address mismatch** with job slug "308 Evergreen Street" (manifest.json customer) — confirm correct site address (plans sheet header vs manifest.json)
- Standard disclaimer: "CONTRACTOR TO VERIFY ALL DIMENSIONS BEFORE CONSTRUCTION" (every sheet)

## Structural decisions (from plans)

- Roof slope new = 3/12 (S3); existing = 6/12 (S6) — confirmed in roof plan
- Roof tie-in includes **multiple valleys (V), ridges (R), and transitions (T)** — concealed roof tie-in geometry is non-trivial, not just simple gable abut
- Existing chimney shown on roof plan — must be navigated by new roof framing
- Elevator shaft labeled "ELEV. 4'-0"" on floor plan — 4' × 4' shaft confirmed (scope.md L55 corroborates)
- Floor-plan dimensions: addition is 29'-5" × 10'-0" (close to nominal 30'×10') with primary bedroom 8'-6.5" × 10'-0" sleeping zone visible
- Bedroom 3 visible 5'-1.5" × 8'-6.5" zone — possibly the basement layout side
- Primary bath shows HIS / HERS lavatory split + LINEN + BENCH + new shower (scope.md L122-129 corroborates)
- Bath 2 shown in addition plan
- 1st floor addition area: 295 sqft; basement addition area: 295 sqft; **total addition area: 590 sqft** (plan schedule)

## Window / door schedules (from plans)

- Window schedule:
  - 01: 3'0" × 1'0" transom — qty 1
  - 02: 3'0" × 3'0" double-hung — qty 1
  - Plus relocated existing windows (multiple, called out on elevations and floor plan)
- Door schedule:
  - A: 32" × 1-3/8" panel door — qty 2
  - B: 30" × 1-3/8" panel door — qty 1
  - C: 28" × 1-3/8" panel door — qty 1
  - D: 36" × 1-3/4" EXTERIOR METAL door — qty 1
- **Scope says (4) interior doors total + (1) new exterior door**; plans show 4 interior (A×2 + B + C) + 1 exterior metal (D) — counts reconcile

## Retrofit indicators (visible in plans, OUTSIDE addition footprint)

- "Relocated existing window" called out on multiple elevations (Left, Back, Right) — existing windows are being removed and reinstalled in new locations
- "Relocate dryer vent" — corroborates scope.md L95 W/D relocation
- "Existing door" and "Relocated door" callouts in primary bedroom area — door swap within existing structure
- "EXISTING" structural callouts visible in floor plan showing the line where new addition meets existing house (garage, lounge, living, kit/dining, covered deck, front porch, basement storage labels)
- Existing hall bath (not the new master bath) is the retrofit zone for the acrylic shower swap + window infill (scope.md L141-149) — NOT explicitly drawn but implied by "existing" labels

## Things plans show that scope doesn't mention

- **Multiple roof valleys + ridges + transitions + an existing chimney** at the roof tie-in zone — scope.md L57-64 calls tie-in "standard integration" but the roof plan reveals it's geometrically complex (chimney navigation + multi-valley)
- **Scope L64:** "Roof tie-in assumes standard integration; additional structural modifications not included" — plans suggest this is a risk area (the chimney + multiple valleys may force structural touch)
- **Floor plan note:** "CONTRACTOR TO VERIFY LOCATION OF EXISTING PLUMBING, VENTING, SEPTIC TANK, AND HVAC BEFORE CONSTRUCTION" (sheet 03 note) — corroborates scope.md L13-14 + L97 about septic capacity assumption
- **Roof plan note:** "CONTRACTOR TO VERIFY EXISTING ROOF SLOPES AND SOFFIT DEPTH BEFORE CONSTRUCTION" (sheet 04 note) — additional verification ask beyond scope
- **HIS / HERS / LINEN / BENCH** specific labels in master bath layout — scope mentions bench + dual vanity but plans confirm split-zone layout
- **Front porch + covered deck + garage** labeled on existing-house side of floor plan — these are existing context, not new work, but help orient the addition placement
- **Brick + lap-siding mix** shown on elevations: addition exterior uses "NEW LAP SIDING" on upper portions and "NEW BRICK TO MATCH EXISTING" on lower band — scope.md L67 only says "vinyl siding to match existing" → **mismatch between scope (vinyl siding) and plans (lap siding + brick)** — material clarification needed
- **Elevations show "NEW SHINGLES TO MATCH EXISTING"** consistent with scope.md L60
