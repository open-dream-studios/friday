---
generation_kind: intel_plans_v1
artifact: plans_pre
derived_from:
  - path: inputs/files/3725 SIMONS 012226.pdf.txt
    sha256: 728d5090fe11df16e226dcadd85c52a4e5edf9ade2e4dbcdd0771fd9e0ccae6b
  - path: inputs/scope.md
    sha256: cd479bfac8ead63c5439c8d4f8e8fa5c0af3af616a7f95321b42774ecebd81a6
last_verified_at: 2026-06-30T07:00:00Z
---

# Plans Interpretation — 308 Evergreen Street Addition (Simons)

**Drawings source:** `3725 SIMONS 012226.pdf` (5 sheets, dated January 22, 2026)
**Designer:** Greyscale Design LLC / Rebecca Lineberry, NCIDQ
**Addition footprint:** 590 sqft total (295 sqft basement + 295 sqft 1st floor, each 30'×10' per floor plan sheet 03-A)

---

## Structural decisions

- **LVL beam:** Plans confirm a load-bearing wall opening requiring structural intervention, consistent with the scope's "3-ply 14" LVL spanning approx. 15'-6"." The floor plan (sheet 03-A) shows the interior wall separating the addition from existing living space with a 14'-0" dimension annotated — the beam load path runs across this line. Temporary shoring is required before demo of that wall section.
- **Two-story addition confirmed:** Sheet 03-A annotates distinct `BASEMENT ADDITION` (295 sqft) and `1ST FLOOR ADDITION` (295 sqft) areas. Basement-level walls frame up to support a floor system carrying the primary bedroom/bathroom/closet suite above.
- **Floor system span:** Sheet 03-A shows the addition width at 10'-0" and overall run of 29'-5". Dimensional lumber or engineered members per scope; no truss framing shown for the floor.
- **Roof pitch conflict visible in plans:** Sheet 04-A (Roof Plan) annotates the NEW roof at `12/3` (3:12) slope and shows `V` (valley) intersections where the new 3:12 ties into existing. The existing roof is shown at `6/12`. Multiple ridge (`R`) and valley (`V`) points are annotated. The note reads *"CONTRACTOR TO VERIFY EXISTING ROOF SLOPES AND SOFFIT DEPTH BEFORE CONSTRUCTION."* This is a non-trivial tie-in — valley framing at two different pitches requires careful field measurement before roof framing begins.
- **Chimney noted on roof plan:** Sheet 04-A shows `CHIMNEY` near the addition footprint. Exact relationship to the new roof is not dimensioned in the extracted text. Field verification needed to confirm clearance and any required chase/flashing at the tie-in.
- **Elevator shaft framing:** Sheet 03-A shows two elevator shaft positions annotated `ELEV. 4'-0"` on both the basement and 1st floor plan, confirming the 4'×4' rough shaft footprint called out in scope. The shaft appears to run through both floors (basement through 1st floor addition), which establishes a vertical structural opening that must be framed continuously through both levels.

---

## Retrofit indicators

Areas or features visible in the drawings that sit **outside** the confirmed addition footprint (primary bedroom, master bathroom, walk-in closet, basement storage). Each is a potential retrofit — independent of new-construction dependencies.

- **Existing Hall Bathroom (BTH. 2) — sheet 03-A:** Labeled `BTH. 2` on the floor plan. The plan shows `NEW SHWR.` inside this existing bath space, and `RELOCATED EXISTING WINDOW` annotations adjacent to it. This bathroom is **outside** the new addition footprint. The scope confirms this is an existing hall bath modification (window removal/infill + acrylic shower system). **Retrofit signal B (uses "existing") + Signal A (area mismatch — hall bath is not in the addition objective list).** The acrylic shower swap is explicitly a customer-requested early item per scope and must be treated as `early.acrylic_shower_swap` in `site_prep / customer_early_items`. The window-infill and drywall/repaint work go in a separate `hall_bath_mod` retrofit component.
- **Primary Bedroom Remodel (BDRM context on sheet 03-A):** The primary bedroom remodel (~12'5" × 16') is called out in scope and exists as an existing-area modification. The floor plan shows the existing bedroom footprint adjacent to the new addition, with a `RELOCATED DOOR` annotation on the shared wall. This is a retrofit of the existing bedroom, not part of the new 295 sqft 1st-floor addition area. **Retrofit signal B ("existing") + Signal A (area mismatch from new-construction perspective).** Framing modifications and drywall patching here are distinct from new-construction framing.
- **Bedroom 2 / Bedroom 3 labels on sheet 03-A:** The plan shows `BDRM. 2` and `BEDRM. 3` labels that appear to reference existing rooms adjacent to the addition. These are labeled but not described as work areas in the scope — they are shown for context/orientation only. No retrofit flag required; confirmed context rooms.
- **Relocated windows on left and back elevations (sheet 02-A):** `EXISTING WINDOW RELOCATED` appears twice on the Left Elevation (sheet 02-A), and once on the Back Elevation. Window relocation involves modifying existing exterior walls — work that is outside the new addition footprint walls. **Retrofit signal B ("existing") + Signal A.** This work should be in a separate retrofit component, not bundled with new window installs.
- **RELOCATE DRYER VENT annotation (sheet 03-A):** Explicitly annotated on the floor plan. The dryer vent relocation is in the existing structure, not within the new addition perimeter. **Retrofit signal B.** This is consistent with the scope's "washer and dryer relocation" plumbing work — confirm with PM whether this is W/D unit relocation (new plumbing rough-in) or vent extension only.
- **Existing switch relocation in hallway (scope only, not directly visible in plans):** Scope calls out relocating one existing switch in the hallway with drywall patch, priming, and painting. Not visible in extracted plan text, but the hallway is outside the addition footprint. **Retrofit signal A.** Minor but should be in its own electrical retrofit task.
- **Basement storage area labeled `STORAGE` (sheet 03-A):** The floor plan shows a `STORAGE` label within the basement addition footprint. Scope confirms basement storage finish is part of scope. This IS inside the addition footprint — not a retrofit. Included for clarity; no retrofit flag.

---

## Things plans show that scope doesn't mention

- **Brick veneer on lower level exterior (sheets 02-A and 03-A):** The Left Elevation (sheet 02-A) clearly annotates `NEW BRICK TO MATCH EXISTING` on the lower (basement) level on both left and back elevations. The Right Elevation (sheet 03-A label: sheet 02-A) also shows `NEW BRICK TO MATCH EXISTING`. **The scope says only "Install vinyl siding to match existing."** The plans differentiate: lower level = brick veneer, upper level = lap siding. Brick masonry subcontractor, brick procurement, and brick installation time are not modeled in the scope or breakdown. This is a significant gap — brick is a slow-productivity trade (~150 brick/day) and materials need time to source a matching unit.
- **New exterior door visible on back elevation (sheet 02-A):** `NEW DOOR` is annotated on the Back Elevation. The scope mentions "Install up to (1) new exterior door." Plans confirm one exterior door location. Consistent — no gap, but placement is on the back/left elevation per drawings.
- **Window count discrepancy — floor plan shows 2 windows in window schedule vs. scope's 4:** The Window Schedule on sheet 03-A lists only:
  - `01` — 3'0" × 1'0" Transom (qty: 1)
  - `02` — 3'0" × 3'0" D.H. (qty: 1)
  That's 2 distinct window types on the schedule. The scope states `(4) windows including (3) 36" × 60" and (1) transom window`. The extracted floor plan text may be incomplete (image-heavy PDF; some window annotations may not have been captured in text extraction). The scope's count (4) should be treated as authoritative, but the PM must verify the window schedule against the full drawing set — the extracted text may be missing window tags 03 and 04.
- **72" dimension annotation on floor plan (sheet 03-A):** Annotated near the BTH. 2 / Primary Bath zone. Likely the 72" double vanity rough-in width. Consistent with scope ("Install 72" double vanity"). Not a gap but confirms the vanity placement is within the master bath area.
- **`RTRN. BENCH` noted on floor plan (sheet 03-A):** A return bench is annotated within what appears to be the primary bath or closet area. Scope mentions "Install shower niche and bench" for the custom tile shower. This is consistent but the "return bench" label may indicate a specific L-shaped bench configuration that the tile installer should plan for.
- **Roof plan shows multiple valleys (sheet 04-A):** Three `V` (valley) annotations and three `R` (ridge) annotations are shown. The scope notes "roof tie-in assumes standard integration; additional structural modifications not included." The number of valleys increases complexity — each valley requires custom valley flashing and potential rafter modification at the intersection. PM should review with the roofing sub before assuming 1-day shingle completion.
- **`HIS` and `HERS` closet labels (sheet 03-A):** The primary bedroom closet area is labeled with `HIS` and `HERS` zones and a `LINEN` closet. The scope's walk-in closet references this but doesn't describe the dual-zone layout. Relevant for the optional closet/cabinet system ($7,000 allowance) if selected — framer needs to know the partition configuration before closing drywall.
- **`LOUNGE`, `LIVING`, `KIT, DINING`, `COVERED DECK`, `FRONT PORCH`, `GARAGE` labels on sheet 03-A:** These are existing spaces shown for orientation. No scope work is called out in them. Not a gap; context only.

---

## Discrepancies

1. **Exterior finish material — lower level brick vs. scope's vinyl siding (CRITICAL):**
   - **Scope (line 67):** "Install vinyl siding to match existing as closely as possible."
   - **Plans (sheet 02-A, Left + Back Elevations):** `NEW BRICK TO MATCH EXISTING` on lower-level walls; `NEW LAP SIDING` on upper-level walls.
   - **Impact:** Brick masonry work is not priced in the breakdown (no masonry section in the CSV). If drawings govern, a masonry subcontractor and brick procurement need to be added. If scope governs (vinyl throughout), the elevation drawings are aspirational or from an earlier design revision. PM must resolve before framing closes — once sheathing is up, the exterior finish decision is locked.

2. **Window schedule count — 2 types in drawings vs. 4 windows in scope:**
   - **Scope (line 68):** "Install (4) windows including (3) 36" × 60" and (1) transom window."
   - **Plans (sheet 03-A, Window Schedule):** Lists only 2 window entries (transom + 3'×3' DH). The 36"×60" windows (scope's primary count of 3) do not appear in the extracted window schedule text.
   - **Impact:** Likely an extraction artifact (image-based schedule not fully captured in text). Scope count of 4 should govern for procurement. Verify the complete window schedule with the full PDF before ordering.

3. **Roof framing method — scope says "TBD during design phase," plans show stick-framed gable:**
   - **Scope (line 57):** "Construct new gable roof system (truss or rafter framed, determined during design phase)."
   - **Plans (sheet 04-A, Roof Plan):** The roof plan shows ridges, valleys, and slopes consistent with rafter/stick framing (no truss layout grid shown). The 3:12 slope tying into an existing 6:12 at multiple valley points is not a standard parallel-chord truss scenario — it strongly implies stick framing.
   - **Impact:** Stick framing is the correct default per TCR rules (addition under 800 sqft, roof span ~10'). No `procurement.trusses` task needed. This resolves the scope ambiguity — treat as stick frame.

4. **Two relocated existing windows on elevation vs. scope's "install (4) new windows":**
   - **Plans (sheet 02-A, Left + Back Elevations):** `EXISTING WINDOW RELOCATED` appears twice. These are existing windows being moved within the existing structure, not new window installs.
   - **Scope:** Does not explicitly call out window relocations — only new window installation is mentioned.
   - **Impact:** Window relocation work (framing, patching, header modification in existing walls) is a retrofit task not captured in the scope's window section. PM should confirm whether this is included in the framing or demo sections of the breakdown, or if it requires a separate change order.

5. **Dryer vent direction — `RELOCATE DRYER VENT` on plans vs. scope's W/D relocation:**
   - **Plans (sheet 03-A):** Explicitly shows `RELOCATE DRYER VENT` annotation on the floor plan.
   - **Scope (line 95):** "Install washer and dryer relocation including water, drain, and roof venting."
   - **Impact:** Consistent in intent. The dryer vent must route through the new roof system. The plumbing/HVAC rough-in task must include this vent penetration coordination with roofing. No structural gap, but sequencing note: vent rough-in must happen before roofing shingles are installed.

6. **Chimney on roof plan — not mentioned in scope:**
   - **Plans (sheet 04-A):** `CHIMNEY` labeled on the roof plan within or adjacent to the new roofing area.
   - **Scope:** No mention of chimney work, flashing, or clearance.
   - **Impact:** The chimney may require new step flashing and counter-flashing where the new roof meets it. If the chimney is within the new addition's roof footprint, this is a roofing scope item not captured in the breakdown. PM must field-verify chimney location relative to addition before roof framing begins.
