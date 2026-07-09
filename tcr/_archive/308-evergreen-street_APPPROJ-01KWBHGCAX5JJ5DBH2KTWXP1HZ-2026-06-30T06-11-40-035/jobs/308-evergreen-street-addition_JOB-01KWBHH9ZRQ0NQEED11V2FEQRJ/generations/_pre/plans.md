---
generation_kind: intel_plans_v1
artifact: plans_pre
derived_from:
  - path: _projects/308-evergreen-street_APPPROJ-01KWBHGCAX5JJ5DBH2KTWXP1HZ/jobs/308-evergreen-street-addition_JOB-01KWBHH9ZRQ0NQEED11V2FEQRJ/inputs/files/3725 SIMONS 012226.pdf.txt
    sha256: 728d5090fe11df16e226dcadd85c52a4e5edf9ade2e4dbcdd0771fd9e0ccae6b
  - path: _projects/308-evergreen-street_APPPROJ-01KWBHGCAX5JJ5DBH2KTWXP1HZ/jobs/308-evergreen-street-addition_JOB-01KWBHH9ZRQ0NQEED11V2FEQRJ/inputs/scope.md
    sha256: cd479bfac8ead63c5439c8d4f8e8fa5c0af3af616a7f95321b42774ecebd81a6
last_verified_at: 2026-06-30T06:00:00Z
---

# Plans Interpretation — 308 Evergreen Street Addition (Simons)

**Source drawings:** 3725 SIMONS 012226.pdf (5 sheets, dated January 22, 2026)
**Designer:** Rebecca Lineberry, NCIDQ — Greyscale Design, LLC
**Sheet inventory:**
- Sheet 1 of 5: Title sheet (cover / project info)
- Sheet 2 of 5 (labeled "02 A"): Left and Back Elevations
- Sheet 3 of 5 (labeled "03 A"): Right Elevation
- Sheet 4 of 5 (labeled "04 A"): Floor Plan (1/4" = 1'-0")
- Sheet 5 of 5 (labeled "05 A"): Roof Plan (1/4" = 1'-0")

---

## Structural decisions

- **Two-story addition footprint:** Plans confirm 30' × 10' footprint. Area schedule on floor plan reads: 1st floor addition = 295 sqft, basement addition = 295 sqft, total addition area = 590 sqft. (Note: scope says "30' x 10'" = 300 sqft — plans show 295 sqft per level, likely due to wall thickness deductions. Immaterial to scheduling.)
- **LVL beam location:** Scope references a single 3-ply 14" LVL spanning approx. 15'-6" to open an existing load-bearing wall. The floor plan shows an interior span labeled "14'-0"" in the area between the existing structure and the new addition, consistent with the LVL location. The beam spans the wall shared between the existing primary bedroom zone and the new addition corridor. Exact bearing points must be field-verified per drawing note.
- **Elevator shaft:** Plans show two "ELEV." markers on the floor plan, each labeled "4'-0" × 4'-0"". One appears on the lower level (basement area) and one on the upper floor plan. The shaft straddles the addition footprint boundary. Framing-only scope per contract; no elevator system included.
- **Two-story floor-to-floor heights:** Elevations show 8'-0" floor-to-ceiling on both stories, with a 1'-0" floor system depth between levels, for a total of ~17'-0" above grade at the wall line plus the roof structure above.
- **Roof pitch mismatch / tie-in:** Roof plan confirms the new addition carries a 3/12 gable pitch tying into the existing 6/12 roof. The roof plan uses valley (V) and transition (T) callouts at the intersection. This is a complex tie-in and the drawing note explicitly states "CONTRACTOR TO VERIFY EXISTING ROOF SLOPES AND SOFFIT DEPTH BEFORE CONSTRUCTION." High risk of concealed-condition change orders at the tie-in.
- **Roof plan legend:** R = Ridge, S = Slope, V = Valley, T = Transition. Multiple valley lines shown at the new/existing junction.
- **Chimney:** Roof plan labels a chimney in the existing structure near the tie-in zone. No chimney work is in scope, but its proximity to the new ridge/valley junction is a coordination point.
- **Window locations (floor plan, Sheet 4):**
  - Window 01: 3'0" × 1'0" transom — 1 unit — located at the front/left elevation of the addition (confirmed by back elevation sheet)
  - Window 02: 3'0" × 3'0" D.H. (double-hung) — 1 unit — located on the right side elevation
  - Two existing windows shown as "RELOCATED" on left/back elevation (Sheet 2). These are existing windows being moved, not new windows.
- **Door locations (floor plan, Sheet 4 — Door Schedule):**
  - Door A: 32" × 1-3/8" panel door — qty 2
  - Door B: 30" × 1-3/8" panel door — qty 1
  - Door C: 28" × 1-3/8" panel door — qty 1
  - Door D: 36" × 1-3/4" exterior metal door — qty 1
- **Existing windows relocated (Sheets 2 & 4):** Two existing windows labeled "EXISTING WINDOW RELOCATED" appear on the left/back elevation and on the floor plan. These windows are being moved as part of opening the existing wall for the addition — scope does not explicitly describe window relocation work (only "remove existing window and frame opening" for the hall bath, and "relocate existing HVAC and electrical disconnect" for site prep). This is a structural coordination item.
- **Dryer vent relocation:** Floor plan (Sheet 4) explicitly labels "RELOCATE DRYER VENT" — consistent with scope plumbing section describing W/D relocation.
- **New shower:** Floor plan labels "NEW SHWR." in the primary bath area, within the addition footprint — confirms custom tile shower location.
- **Return bench (BTH. 2):** Floor plan shows "RTRN. BENCH" in what appears to be a secondary bathroom area labeled "BTH. 2." This area ("BDRM. 2," "BEDRM. 3," "BTH. 2") appears to be in the EXISTING structure zone, not the new addition footprint. See Retrofit Indicators below.
- **Brick lower level on elevations:** Sheet 2 (Left/Back elevations) and Sheet 3 (Right elevation) show "NEW BRICK TO MATCH EXISTING" at the lower level of the addition on at least two elevation faces, above which new lap siding is shown. Scope says "vinyl siding" throughout. This is a materials discrepancy — see Discrepancies section.

---

## Retrofit indicators

These features appear in the plans in areas that sit outside the primary addition footprint (the 30' × 10' two-story addition). Each is a candidate for a separate retrofit component in the TaskGraph.

- **BDRM. 2 / BEDRM. 3 (Sheet 4 — Floor Plan):** The floor plan labels "BDRM. 2" and "BEDRM. 3" in what reads as the existing house footprint, adjacent to but not within the new addition boundary. These room labels plus associated door references (Door A, Door C) indicate rooms in the existing structure that may require framing modification, drywall, and finish work. Signal B (word "existing" context) + Signal C (spatial ambiguity — rooms not clearly inside the 30'×10' addition). **Retrofit candidate: existing bedroom area modification.**
- **BTH. 2 (Sheet 4 — Floor Plan):** A second bathroom labeled "BTH. 2" with a "RTRN. BENCH" annotation is shown on the floor plan in what appears to be an existing area adjacent to the addition. The new master bath (PRIMARY BTH.) is clearly within the addition footprint. BTH. 2 is likely the existing hall bathroom described in scope as "Existing Hall Bathroom Modification." Signal A (area mismatch — addition objective is primary bedroom/bath/closet; BTH. 2 is a secondary bath not in the addition). Signal B ("existing"). **Retrofit candidate: hall bath modification — separate component, runs independently of new addition.**
- **Relocated existing windows (Sheets 2 & 4):** Two windows labeled "EXISTING WINDOW RELOCATED" on the back/left elevation are in the existing structure wall that is being integrated with the addition. Relocating these windows is work on the existing structure, not new construction. Signal B ("existing"). **Retrofit candidate: existing window relocation — framing and refit work in existing wall.**
- **Hallway switch relocation (scope reference, Signal C):** Scope describes "Relocate (1) existing switch in hallway including drywall patch, priming, and painting." This is existing-area electrical work. Not explicitly called out on plans (electrical not on these sheets), but confirmed by scope. **Retrofit candidate: hallway electrical patch work.**
- **Primary bedroom remodel area (scope + floor plan):** Scope calls out "Primary Bedroom Remodel (~12'5" × 16')" as a named existing-room modification. The floor plan shows the "PRIMARY BEDROOM." label with dimensions within or adjacent to the addition footprint boundary. Given the LVL beam opens the existing load-bearing wall, part of the primary bedroom framing modification IS tied to the new addition. However, the full bedroom remodel (drywall, LVT, trim, paint) is a retrofit of an existing room. **Partial retrofit: structural portion is new-construction-tied; finish portion is retrofit.**
- **Basement storage (floor plan / scope):** Floor plan shows "STORAGE" in the basement area. Scope confirms "Basement Storage Finish: Frame and drywall walls. Apply Level 3 finish and paint. Install lighting fixture. Concrete floor remains unfinished." The basement storage is below the new addition — part of the addition footprint — and is new construction, NOT a retrofit of existing space. No retrofit flag here.

---

## Things plans show that scope doesn't mention

1. **Brick veneer at lower level on at least two elevation faces.** Sheets 2 and 3 (Left/Back and Right elevations) show "NEW BRICK TO MATCH EXISTING" at the base level of the addition. Scope describes only "vinyl siding to match existing as closely as possible" and "sheathing and WRB." No masonry work is mentioned in the scope at all. This is a potentially significant omission — brick veneer work (masonry sub, material lead time, tie-in to foundation) is very different from vinyl siding.

2. **Only 2 windows in the window schedule (not 4).** Plans' Window Schedule on Sheet 4 lists only two window types: Window 01 (3'0" × 1'0" transom, qty 1) and Window 02 (3'0" × 3'0" D.H., qty 1). That is 2 new windows total. Scope says "(4) windows including (3) 36" × 60" and (1) transom window." The plans schedule does not show (3) 36"×60" windows — only one 3'0"×3'0" D.H. (which is 36"×36", not 36"×60") and one transom. This is a count and dimension discrepancy that could affect procurement.

3. **Existing windows being relocated (not just removed/framed).** Plans clearly label two windows "EXISTING WINDOW RELOCATED" on the back elevation. Scope does not describe window relocation work in the existing walls — it only mentions removing and framing the hall bath window. Relocating existing windows requires framing modification in the existing wall, which may be a scope gap.

4. **"RTRN. BENCH" in BTH. 2.** Floor plan shows a return bench in the secondary bathroom. Scope does not describe a bench in the hall bath modification section — only an acrylic shower swap. If this bench is part of the hall bath work, it's unscoped.

5. **Multiple valleys and transitions at roof tie-in (Sheet 5).** The roof plan shows 3+ valley intersections (V callouts) at the new-to-existing roof junction. The scope says "Roof tie-in assumes standard integration; additional structural modifications not included." The complexity visible in the roof plan (multiple valleys, 3/12 meeting 6/12 at chimney proximity) is beyond a simple ridge tie-in. This is a change-order risk not surfaced in the scope narrative.

6. **Chimney proximity to new ridge.** Roof plan (Sheet 5) shows an existing chimney in the existing structure where the new addition ties in. Chimney flashing integration and any required code separation are not mentioned in scope. This is a field-verification item.

7. **Door count confirmation:** Plans show 5 doors total (A×2, B×1, C×1, D×1 = 5). Scope says "install (4) interior doors total" plus "(1) new exterior door" = 5. Plans align on total count but note Door A appears twice (qty 2), which is consistent. The exterior metal door (D) = Door D in plans matches scope's "up to (1) new exterior door."

---

## Discrepancies

1. **Brick veneer vs. vinyl siding on lower level (CRITICAL).**
   - Scope (line 67): "Install vinyl siding to match existing as closely as possible."
   - Plans (Sheet 2 — Left/Back Elevation, Sheet 3 — Right Elevation): "NEW BRICK TO MATCH EXISTING" at the lower portion of the addition walls on multiple faces; lap siding shown only at the upper story.
   - Impact: If plans govern, masonry work is required. This requires a masonry sub, brick material procurement (lead time), and integration with the foundation/slab edge. Significant cost and schedule delta vs. vinyl siding throughout.

2. **Window count and dimensions — scope vs. plans.**
   - Scope (line 68): "(4) windows including (3) 36" × 60" and (1) transom window."
   - Plans (Sheet 4 — Window Schedule): 2 windows total — Window 01: 3'0"×1'0" transom (1 unit), Window 02: 3'0"×3'0" D.H. (1 unit). No 36"×60" windows listed.
   - The "36" × 60"" scope windows are neither shown in the window schedule nor consistent with the 3'0"×3'0" D.H. on plans. Either the plans are not fully coordinated with the final window selections, or the scope window count is wrong.
   - Impact: Procurement quantities and sizes drive lead time and cost. PM must reconcile before ordering.

3. **Addition footprint area: scope "30' × 10'" vs. plans "295 sqft per floor."**
   - Minor: 30'×10' = 300 sqft; plans show 295 sqft per level. Likely wall thickness deduction. No scheduling impact, but contractor should use 295 sqft as the working area for material takeoffs.

4. **Roof framing method: "truss or rafter framed — determined during design phase."**
   - Scope (line 57): "Construct new gable roof system (truss or rafter framed, determined during design phase)."
   - Plans (Sheet 5): Roof plan shows ridge, slope, valley, and transition annotations — consistent with stick framing (rafter framing). No truss layout indicators are present. The 3/12 over a 10'-wide span with complex valley tie-ins is consistent with stick framing.
   - Conclusion: Plans support stick-frame default. No `procurement.trusses` task needed per Rule 4Q and the company belief on small additions under 800 sqft / spans under 24'.

5. **Existing window relocation not in scope demolition section.**
   - Scope demolition section describes saw-cutting walkway, removing railroad ties, relocating heat pump and electrical disconnect — but does NOT mention relocating the two existing windows shown on plans.
   - These window relocations are structural modifications to the existing wall and should be in scope (or clarified as a change order).
