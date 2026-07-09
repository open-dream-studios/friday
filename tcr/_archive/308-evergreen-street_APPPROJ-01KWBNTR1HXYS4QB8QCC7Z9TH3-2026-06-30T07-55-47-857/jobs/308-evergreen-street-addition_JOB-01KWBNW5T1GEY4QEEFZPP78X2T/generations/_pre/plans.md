---
generation_kind: intel_plans_v1
artifact: plans_pre
derived_from:
  - path: inputs/files/3725 SIMONS 012226.pdf.txt
    sha256: 728d5090fe11df16e226dcadd85c52a4e5edf9ade2e4dbcdd0771fd9e0ccae6b
  - path: inputs/scope.md
    sha256: cd479bfac8ead63c5439c8d4f8e8fa5c0af3af616a7f95321b42774ecebd81a6
last_verified_at: 2026-06-30T07:30:00Z
---

# Plans Interpretation — 308 Evergreen Street Addition (Simons)

**Drawings package:** "3725 SIMONS 012226.pdf" — 5 sheets, dated January 22, 2026. Designer: Rebecca Lineberry, NCIDQ / Greyscale Design LLC. Project address per drawings: 647 AA Deakins Rd, Jonesborough TN 37659 (field address). Sheet titles: (1) Title/Cover, (2) Left & Back Elevations, (3) Right Elevation, (4) Floor Plan, (5) Roof Plan.

---

## Structural decisions

- **LVL beam span and configuration:** Scope calls for one (1) engineered LVL beam (3-ply 14") spanning approximately 15'-6" to open an existing load-bearing wall. The floor plan (Sheet 4) shows the addition connecting to the existing structure with an open wall at the first-floor living/lounge zone. The LVL loads the floor system above (second-floor addition). This is a real load-bearing modification — temporary shoring is explicitly required before beam install.

- **Two-story addition footprint:** Sheet 4 shows the addition as 30' wide × 10' deep. Floor plan confirms two levels: basement addition (295 sqft) and 1st-floor addition (295 sqft) = 590 sqft total addition area. The plan labels these explicitly: "1ST FLOOR ADDITION," "BASEMENT ADDITION," "TOTAL ADDITION AREA 590."

- **Roof tie-in geometry (Sheet 5):** New gable roof at 3/12 pitch ties into existing 6/12. The roof plan shows valleys (V) at both intersections of new and existing roof systems. Multiple ridge lines (R) are labeled. A chimney is also shown on the existing roof. This is a complex tie-in — valley cuts at two points, pitch transition from 3/12 new to 6/12 existing. This is NOT a simple shed-roof add-on; it requires careful rafter-to-rafter integration at the valleys.

- **Roof pitch note (Sheet 5):** "CONTRACTOR TO VERIFY EXISTING ROOF SLOPES AND SOFFIT DEPTH BEFORE CONSTRUCTION." This is an explicit drawing-level flag — concealed condition risk at the tie-in.

- **Floor plan confirmed two elevator shaft locations (Sheet 4):** Two "ELEV." labels appear on the floor plan, each showing a 4'-0" × 4'-0" shaft. One appears at the basement level, one on the upper floor. This aligns with scope (one future elevator shaft), but the placement of TWO "ELEV." indicators on separate floors of the plan is consistent with a single through-shaft extending vertically.

- **Structural floor system:** Plan shows "BDRM. 2" and "BEDRM. 3" labeled in the existing house footprint on the floor plan. The addition adds the primary bedroom, primary bath, hers/his walk-in closets, and linen on the upper floor. The basement level shows storage and garage areas in the existing structure adjacent to the new addition basement.

- **Existing windows relocated (Sheet 2 & 4):** Left/Back elevation (Sheet 2) labels two existing windows as "EXISTING WINDOW RELOCATED." Floor plan (Sheet 4) also shows "RELOCATED EXISTING WINDOW" and "EXISTING WINDOW, RELOCATED" at two positions on the existing structure adjacent to the addition. These are structural modifications to the existing house — the openings must be framed in or resized.

---

## Retrofit indicators

These are areas or features visible in the drawings that sit **outside** the new addition footprint (primary bedroom, master bath, walk-in closet, basement storage addition). Each is a retrofit candidate requiring its own component in the TaskGraph.

1. **Existing Hall Bathroom (BTH. 2) — Sheet 4, Floor Plan.** The floor plan labels "BTH. 2" within the existing house footprint, clearly outside the 30'×10' addition boundary. The plan shows "NEW SHWR." in BTH. 2, confirming a new shower is being installed in an existing bathroom. Signal B ("existing") + Signal C (new feature inside existing area). This is the hall bath modification called out in scope — a retrofit, NOT part of the new addition.

2. **Relocated existing windows — Sheets 2 & 4.** Two "EXISTING WINDOW RELOCATED" callouts appear on the Left/Back elevations and floor plan. These windows are in the existing structure walls adjacent to (but outside) the addition footprint. Relocating/infilling existing window openings in the existing house is retrofit work. Signal A (area outside addition) + Signal B ("existing").

3. **Bedroom 2 and Bedroom 3 (BDRM. 2, BEDRM. 3) — Sheet 4, Floor Plan.** These are labeled in the existing house footprint. While the primary bedroom remodel is in scope (scope explicitly names "Primary Bedroom Remodel"), the drawings show at least two additional bedrooms (Bdrm 2, Bedrm 3) that are part of the existing house. Any work described in scope touching these rooms (e.g. "Primary Bedroom Remodel ~12'5" × 16'") is retrofit of existing space. Signal A (outside addition footprint).

4. **Dryer vent relocation — Sheet 4, Floor Plan.** "RELOCATE DRYER VENT" is explicitly labeled on the floor plan. The dryer vent appears to be in the existing living area / laundry zone, not inside the new addition footprint. Scope confirms W/D relocation. This is existing-area plumbing/mechanical work — retrofit. Signal B ("relocate" = existing) + Signal C (location not explicitly within addition).

5. **Existing door relocated — Sheet 4, Floor Plan.** "RELOCATED DOOR" appears on the floor plan in the existing structure, adjacent to the addition connection point. Framing patch/modification of an existing doorway opening is retrofit work. Signal B ("relocated") + Signal A (in existing footprint).

6. **Chimney — Sheet 5, Roof Plan.** A chimney is shown on the existing roof plan, clearly in the existing house portion. No chimney work is mentioned in scope. This is noted for completeness — confirm with PM whether any chimney flashing or integration work is needed at the roof tie-in.

---

## Things plans show that scope doesn't mention

- **Brick veneer on lower level (Sheets 2 & 3 — Left/Back/Right Elevations):** All three exterior elevation sheets label "NEW BRICK TO MATCH EXISTING" at the lower-level (basement/foundation level) of the new addition. The scope (line 67) says only "Install vinyl siding to match existing as closely as possible." The drawings show a mixed exterior: **lap siding above, brick veneer below** — two different exterior finish materials, not one. Scope does not mention brick veneer at all. This is a discrepancy with cost implications (see Discrepancies section).

- **Window schedule is 2 windows total, not 4:** Sheet 4 Window Schedule lists only:
  - Window 01: 3'0" × 1'0" Transom — Qty: 1
  - Window 02: 3'0" × 3'0" D.H. (double-hung) — Qty: 1
  Total = **2 windows** on the schedule. Scope says "Install (4) windows including (3) 36" × 60" and (1) transom window." The drawings schedule 2 windows; scope calls for 4. The floor plan also references "NEW WINDOW" at two locations. This is a significant discrepancy — either the window schedule is incomplete or the scope is over-counting.

- **Door schedule shows 5 doors (4 interior + 1 exterior):** Sheet 4 Door Schedule:
  - A: 32" × 1-3/8" Panel Door — Qty: 2 (interior)
  - B: 30" × 1-3/8" Panel Door — Qty: 1 (interior)
  - C: 28" × 1-3/8" Panel Door — Qty: 1 (interior)
  - D: 36" × 1-3/4" Exterior Metal Door — Qty: 1
  Total = 4 interior doors + 1 exterior door. Scope says "(4) interior doors total" and "up to (1) new exterior door" — this matches. No discrepancy on door count, but the door schedule gives specific sizes the scope doesn't detail.

- **Return bench in Primary Bathroom (Sheet 4):** The floor plan labels "RTRN. BENCH" in the primary bathroom area. Scope mentions a "shower niche and bench" in the master bathroom section — this appears to be the bench referenced, but the drawing label "RTRN." suggests a return/corner bench configuration. Not a discrepancy, but a design detail the scheduler should be aware of (slightly more complex tile work).

- **Linen closets (×2) — Sheet 4:** Two "LINEN" labels appear on the floor plan — one in the primary bath/closet zone (addition footprint) and one in the existing hall area. The addition-side linen is part of the new build. The existing-side linen modification (if any) would be retrofit. Scope does not specifically call out linen closet work.

- **"HIS" and "HERS" closets explicitly planned — Sheet 4:** Floor plan labels separate "HIS" and "HERS" closet areas within the new primary suite footprint. Scope says "walk-in closet" (singular). The drawings show two distinct closet zones. The optional closet/cabinet system package ($7,000 allowance) likely covers both. PM should confirm scope of finish work in these spaces.

- **Chimney in existing roof (Sheet 5):** Existing chimney shown on roof plan. Not mentioned anywhere in scope. May require flashing integration at or near the new roof tie-in zone. Low risk unless chimney is near the valley cut points.

- **"72" vanity" label on floor plan (Sheet 4):** "72"" annotation appears on the floor plan at the primary bathroom — consistent with scope's "72" double vanity." This confirms the vanity size and placement are drawn, not ambiguous.

- **Note on Sheet 4:** "*CONTRACTOR TO VERIFY LOCATION OF EXISTING PLUMBING, VENTING, SEPTIC TANK, AND HVAC BEFORE CONSTRUCTION" — this is a formal drawing-level caution. Especially relevant given scope's septic feasibility study requirement (TDEC inspection).

---

## Discrepancies

1. **CRITICAL — Exterior finish material mismatch (Sheets 2 & 3 vs. scope line 67):**
   - **Scope says:** "Install vinyl siding to match existing as closely as possible."
   - **Plans show:** "NEW BRICK TO MATCH EXISTING" at the lower level (basement level / foundation zone) of the addition on the Left, Back, and Right elevations. "NEW LAP SIDING" is shown above the brick on those same elevations.
   - **Impact:** The drawings prescribe a two-material exterior: brick veneer below + lap siding above. Scope prices only vinyl siding. Brick veneer is materially more expensive and a different trade (masonry vs. siding). The cost breakdown section "Exterior Finishes – Siding, Trim & Gutters" likely does NOT include brick masonry. This is a potential change-order item or a scope error. **PM must resolve before exterior work begins.**

2. **Window count mismatch (Sheet 4 Window Schedule vs. scope line 68):**
   - **Scope says:** 4 windows: (3) 36" × 60" and (1) transom window.
   - **Plans show:** Window Schedule lists only 2 windows: one 3'×1' transom and one 3'×3' double-hung. The scope's three 36"×60" windows do not appear in the drawing schedule.
   - **Impact:** Either the window schedule is preliminary/incomplete (possible — this is a design-phase drawing set), or the scope over-counts windows. The floor plan shows "NEW WINDOW" at two locations and "NEW TRANSOM WINDOW" at one location, suggesting possibly 3 new windows total in the addition — still one short of scope's 4. **PM should reconcile window count against final construction drawings before ordering.**

3. **Roof framing method ambiguity (scope vs. scope vs. drawings):**
   - **Scope says:** "Construct new gable roof system (truss or rafter framed, determined during design phase)."
   - **Plans show:** Roof plan (Sheet 5) does not resolve truss vs. stick-frame — it only shows the geometry (ridges, valleys, slopes). The roof plan shows a 3/12 new pitch tying into a 6/12 existing with multiple valley intersections. The addition footprint is 30'×10' (300 sqft of roof), which per TCR rules is clearly within stick-frame territory (under 800 sqft, span <24 ft). **Ruling: stick-frame default applies. No trusses procurement task needed unless PM confirms otherwise.**

4. **Scope mentions "4 windows" but drawings window schedule shows only 2 sizes/types scheduled:** See item 2 above. Additionally, scope calls for "(3) 36"×60"" but drawings show "3'0"×3'0" D.H." (36"×36") as the only double-hung. The sizes don't match (scope 36"×60" vs. drawings 36"×36"). This is a real dimension discrepancy beyond just count. **Flag for PM — verify final window specs before ordering.**

5. **Addition address vs. project address:**
   - **Job context:** Project labeled "308 Evergreen Street."
   - **Drawings say:** "647 AA Deakins Rd, Jonesborough TN 37659."
   - **Scope says:** "308 Evergreens Scope" with no street address given.
   - **Impact:** Drawings and project label use different addresses. This may indicate the drawings package is from a different project file (interior designer's reference address). PM should verify the drawings are the correct set for 308 Evergreen Street before construction begins. Low risk if the designer confirms, but worth a formal check.
