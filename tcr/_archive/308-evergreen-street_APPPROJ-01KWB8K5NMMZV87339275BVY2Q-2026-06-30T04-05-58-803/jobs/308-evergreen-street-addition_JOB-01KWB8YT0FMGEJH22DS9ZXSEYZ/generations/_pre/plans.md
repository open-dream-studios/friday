---
generation_kind: intel_gather_v1
artifact: plans_pre
derived_from:
  - path: _projects/308-evergreen-street_APPPROJ-01KWB8K5NMMZV87339275BVY2Q/jobs/308-evergreen-street-addition_JOB-01KWB8YT0FMGEJH22DS9ZXSEYZ/inputs/files/3725 SIMONS 012226.pdf.txt
    sha256: 728d5090fe11df16e226dcadd85c52a4e5edf9ade2e4dbcdd0771fd9e0ccae6b
last_verified_at: 2026-06-30T03:26:48Z
---

## Source

- Greyscale Design, LLC drawings — dated 01/22/2026 — Rebecca Lineberry, NCIDQ (cover sheet)
- 5 sheets: cover, left+back elevations, right elevation, floor plan, roof plan
- All sheets carry standard disclaimer: "CONTRACTOR TO VERIFY ALL DIMENSIONS BEFORE CONSTRUCTION"

## Structural decisions visible in plans

- **2-story massing:** 8'-0" basement level, 1'-0" rim/band, 8'-0" first-floor level — confirmed all three elevation sheets
- **New 3/12 gable roof** tying into existing 6/12 — roof plan shows multiple ridge (R) and valley (V) markers at the tie-in (sheet 5)
- **Floor plan (sheet 4):** addition footprint dimensions — 29'-5" depth × 10'-0" width on each floor. Notes "295 / 295 / 590" — 1st-floor addition area / basement addition area / total addition area
- **Master bath layout (sheet 4):** dual lav vanity (HIS/HERS labeled), separate water closet, custom shower with bench + RTRN (return), linen storage. Confirms scope's master bath fixture count (2 lavs, 1 toilet, 1 shower) and 72" vanity.
- **Primary bedroom (sheet 4):** ~10'-1" × 5'-9" × 4'-0" approximate dimensions noted, plus existing relocated windows on two walls. Bedroom retrofit confirmed.
- **Elevator shaft (sheet 4):** drawn as ELEV. 4'-0" × 4'-0", in plan with adjacent linen closet. **Located inside the new addition footprint** — Signal C (spatial ambiguity per dev_rules § 9) resolves to NEW CONSTRUCTION, not retrofit.
- **Hall bath (BTH. 2 on sheet 4):** small, located in the existing structure portion of the floor plan. New shower called out as "NEW SHWR." with new window opening. Confirms hall bath = retrofit zone.
- **Window schedule (sheet 4):** 01 = 3'0" × 1'0" TRANSOM (1 ea); 02 = 3'0" × 3'0" D.H. (1 ea). Scope mentions "(3) 36" x 60" and (1) transom" but drawings only show 1 DH + 1 transom — **discrepancy between scope and drawings on window count**.
- **Door schedule (sheet 4):** A = 32" × 1-3/8" panel door (2 ea); B = 30" × 1-3/8" panel door (1 ea); C = 28" × 1-3/8" panel door (1 ea); D = 36" × 1-3/4" exterior metal door (1 ea). Total 5 interior + 1 exterior — scope says "4 interior doors total" — **discrepancy** between scope and door schedule.

## Retrofit indicators in plans

- **Hall bath (BTH. 2) sits in the EXISTING structure**, not in the new addition footprint — sheet 4 floor plan. Retrofit work (window replacement, acrylic shower swap) is physically outside the addition envelope. Two-bucket pattern (Rule 4V) applies.
- **"RELOCATED EXISTING WINDOW"** annotations appear at multiple locations on elevations (left + back) and floor plan — indicates existing windows being moved as part of the tie-in. Adds light retrofit demo/reframe scope not necessarily itemized in CSV.
- **"EXISTING DOOR"** kept and a new door added in the bedroom 3 area (sheet 4) — retrofit reframe at door opening.
- **Existing chimney shown near tie-in on roof plan** (sheet 5, faint annotation near top) — confirms scope's note about extending existing gas WH vent through new roof. Verify clearances during framing.
- **"CONTRACTOR TO VERIFY LOCATION OF EXISTING PLUMBING, VENTING, SEPTIC TANK, AND HVAC BEFORE CONSTRUCTION"** (sheet 4 floor plan) — explicit drawing-level confirmation that septic tank location is unknown and must be field-verified. Strengthens TDEC-uncertainty flag.
- **"RELOCATE DRYER VENT"** call-out on floor plan — confirms W/D relocation scope, drives plumbing vent stack and exterior wall penetration coordination.
- **Drawings call out "NEW BRICK TO MATCH EXISTING"** on elevations (left, back, right) — scope says "vinyl siding to match existing as closely as possible" — **discrepancy**: drawings call for brick veneer at lower level + lap siding above, scope assumes vinyl siding throughout. Material cost + labor implications.

## Things plans show that scope doesn't mention

- **Lap siding + brick combination** on exterior elevations — scope assumes vinyl siding only. Brick adds masonry trade (not in CSV trade totals).
- **"NEW SHINGLES TO MATCH EXISTING"** call-out on left elevation — confirms architectural asphalt to match, consistent with scope.
- **Multiple "RELOCATED EXISTING WINDOW"** call-outs across elevations (at least 2 visible on left+back) — labor to remove + reseat existing windows in new wall framing, not separately budgeted in CSV.
- **Existing covered deck + front porch + garage** shown on the existing structure side of the floor plan — confirms project does NOT touch these, but the existing covered deck is adjacent to the addition footprint and may affect access/staging.
- **Bedroom 3 retrofit:** plans show "BDRM. 3" on existing side with new closet partition + new door + relocated existing window — retrofit framing/finishing work that may be folded into scope's "Primary Bedroom Remodel" section but addresses a different bedroom (Bedroom 3, not the primary). PM Interview should confirm whether bedroom 3 modifications are in scope or out of scope.
- **Closet storage layout** on sheet 4 — His/Hers walk-in closet shown with bench, return, linen. Confirms scope's note about coordinating with the Optional Closet & Cabinet System package ($7,000 allowance).
- **No structural details / framing plan** in the drawings supplied — LVL beam location, header sizes, foundation reinforcement details NOT in this drawing set. Implies a separate structural drawing set or engineer-stamped framing plan expected. PM Interview should confirm whether a stamped structural set exists.

## Discrepancies summary (high-priority for Stage B)

- **Window count:** scope says 4 windows (3 × 36"×60" DH + 1 transom); drawings show only 2 (1 DH 3'×3' + 1 transom). Either scope is over-counted or drawings are incomplete.
- **Door count:** scope says 4 interior doors; door schedule shows 5 interior + 1 exterior.
- **Siding material:** scope says vinyl siding; drawings call for brick (lower level) + lap siding (upper). Significant material/trade implications.
- **Bedroom scope:** plans label both a "Primary Bedroom" remodel area AND "BDRM. 3" with new partition — scope's "Primary Bedroom Remodel (~12'5" × 16')" section may not cover bedroom 3 work.
