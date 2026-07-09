---
generation_kind: intelligence_rebuild_v2
stage: extract_plans
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWHNZ9SX3T48DZS1YPB87SRA/jobs/308-evergreen-street-addition_JOB-01KWHP1G1HG8C26X6GPS0EXGBR/inputs/files/3725 SIMONS 012226.pdf.txt
  - _projects/308-evergreen-street_APPPROJ-01KWHNZ9SX3T48DZS1YPB87SRA/jobs/308-evergreen-street-addition_JOB-01KWHP1G1HG8C26X6GPS0EXGBR/inputs/scope.md
---

# Plans extraction — Simons Addition (dated 01/22/26, Greyscale Design)

Sheets provided (5 total):
- p.1 — Cover / title
- p.2 — Left & Back Elevations (1/4" = 1'-0")
- p.3 — Right Elevation (1/4" = 1'-0")
- p.4 — Floor Plan (1/4" = 1'-0"), with Window Schedule + Door Schedule
- p.5 — Roof Plan (1/4" = 1'-0")

Note on address discrepancy: the drawing title block reads **"647 AA Deakins Rd., Jonesborough, TN 37659"** (plans p.1-p.5) — but the job/project is named "308 Evergreen Street." The Deakins address appears to be Greyscale Design's designer (Rebecca Lineberry, NCIDQ) office address, not the site. Sheet titles say "SIMONS ADDITION" throughout, matching the scope's "Simons Addition." Treat as designer address; verify with PM if uncertain.

## Structural decisions

- **Addition footprint 30' × 10' → 295 SF per floor, 590 SF total** (plans p.4). Confirms scope's "approximately 30' × 10' two-story addition." Sheet also labels: "1ST FLOOR ADDITION = 295 / BASEMENT ADDITION = 295 / TOTAL ADDITION AREA = 590."
- **Two-story vertical stack:** basement addition below, primary-suite floor above (plans p.4). Floor-to-floor dimensions on elevations: 8'-0" ceiling + 1'-0" floor system + 8'-0" ceiling (plans p.2, p.3).
- **Gable roof, stick-frame implied.** Roof Plan (plans p.5) shows a NEW 3/12 gable tying into the EXISTING 6/12 roof via valleys ("V") and ridges ("R"). Multiple valleys shown — roof tie-in geometry is non-trivial. Scope says "truss OR rafter framed, determined during design phase" — no truss callout on the roof plan, so stick-frame default per company belief `stick_frame_default_for_small_additions` (small footprint, 30' span but 10' depth, well under 24' rafter span).
- **LVL beam location NOT dimensioned on floor plan.** Scope specifies "(1) engineered LVL beam (3-ply 14") spanning approx. 15'-6" to open existing load-bearing wall including temporary shoring" — plans p.4 does not annotate this beam location or the load path above. Verify with PM which existing wall opens.
- **Elevator shaft ~4' × 4'** shown on floor plan (plans p.4) labeled "ELEV. 4'-0" × 4'-0"" on both basement and upper level. Aligned vertically between floors, positioned at the addition/existing house tie-in area. Scope says "framing only" + 30A circuit rough-in.
- **Ceiling height 8'-0"** confirmed on both floors (plans p.2, p.3) — matches CSV metadata line "Ceiling Height, 8."
- **Foundation:** no foundation detail sheet included in these 5 pages. Scope says continuous 12"×12" footings + 4" slab, no CMU walls. Basement level shown as fully-enclosed conditioned space (plans p.4) — the "basement" is at-grade storage under the addition, not a below-grade basement. Confirms monolithic-foundation-eligible per company default.

## Retrofit indicators (existing conditions the plans expose)

- **Existing house shown on floor plan** (plans p.4) with labels: EXISTING GARAGE, EXISTING LOUNGE, EXISTING LIVING, EXISTING KIT (kitchen), DINING, COVERED DECK, FRONT PORCH, BDRM. 2, BEDRM. 3. Addition wraps onto one side/rear of the existing footprint.
- **Existing hall bath** (labeled "BTH. 2" on plans p.4) sits between BDRM. 2 and BEDRM. 3 in the existing house — window is being removed and reframed (scope), plans show a "NEW SHWR." callout in the hall bath (plans p.4) confirming the acrylic shower swap location.
- **Existing windows relocated:** plans p.2 (back elevation) and p.4 (floor plan) show "EXISTING WINDOW, RELOCATED" callouts in two places — one on back elevation, one at primary-bedroom exterior wall on floor plan. Two existing windows are being pulled and reinstalled elsewhere. Scope does NOT explicitly enumerate window relocation labor (only 4 NEW windows).
- **Existing door relocated:** floor plan (plans p.4) shows "RELOCATED DOOR" callout. Scope mentions only "(1) new exterior door" and "(4) interior doors total" — the relocated door is a separate labor item not called out.
- **Existing dryer vent relocation:** plans p.4 labels "RELOCATE DRYER VENT." Scope confirms W/D relocation with roof venting.
- **Existing brick to match:** elevations (plans p.2, p.3) call out "NEW BRICK TO MATCH EXISTING" on lower-level (basement) exterior. Note this conflicts with scope's exterior finish spec — see Discrepancies.
- **Existing chimney** shown on roof plan (plans p.5) — labeled "CHIMNEY" adjacent to the existing 6/12 roof. New roof integrates around it; no chimney modification called out in scope, but flashing tie-in at chimney is implicit.
- **Existing roof slope 6/12, existing soffit depth "unverified"** — plans p.5 carries the note "CONTRACTOR TO VERIFY EXISTING ROOF SLOPES AND SOFFIT DEPTH BEFORE CONSTRUCTION." Retrofit signal — dimensions not guaranteed.
- **Existing plumbing / venting / septic / HVAC locations "unverified"** — plans p.4 carries the note "CONTRACTOR TO VERIFY LOCATION OF EXISTING PLUMBING, VENTING, SEPTIC TANK, AND HVAC BEFORE CONSTRUCTION." Direct field-verification risk gate.

## Things plans show scope doesn't mention

- **Two existing windows are being RELOCATED** (plans p.2 back elevation, plans p.4 floor plan). Scope only lists (4) NEW windows and window relocation labor is not enumerated as a distinct line. Add to plumbing/framing/exterior labor scoping.
- **One existing door is being RELOCATED** (plans p.4 — "RELOCATED DOOR"). Scope's door schedule counts (4) interior doors + (1) new exterior door but does not identify the relocated existing door as separate.
- **Door schedule on plans p.4 lists 5 doors, not 4:**
  - A — 32" × 1-3/8" panel door, QTY 2
  - B — 30" × 1-3/8" panel door, QTY 1
  - C — 28" × 1-3/8" panel door, QTY 1
  - D — 36" × 1-3/4" exterior metal door, QTY 1
  - **Total = 5 doors** (4 interior + 1 exterior). Scope says "(4) interior doors total" — plans show 4 interior (A×2 + B + C) which matches, but scope also says "(1) pre-hung interior doors and (2) pocket door systems" (that's only 3 accounted for). Pocket doors are NOT annotated on plans p.4 — no pocket-door symbols visible. Reconcile with PM: which of A/B/C are pocket doors vs. pre-hung?
- **Window schedule on plans p.4 lists only 2 windows, not 4:**
  - 01 — 3'0" × 1'0" TRANSOM, QTY 1
  - 02 — 3'0" × 3'0" D.H. (double-hung), QTY 1
  - **Total = 2 new windows**. Scope says "(4) windows including (3) 36" × 60" and (1) transom." Major discrepancy — see Discrepancies below.
- **Master bath layout details** (plans p.4): shows HIS / HERS split vanities, LINEN closet, bench in shower, "RTRN." (return / possibly linen return niche), and dedicated water-closet compartment. Scope mentions 72" double vanity + shower with bench + niche — plans confirm bench and add a linen closet not called out in scope.
- **Primary bedroom shows a bench detail** (plans p.4). Not in scope.
- **Multiple valleys in the roof tie-in** (plans p.5) — the new 3/12 gable meets the existing 6/12 roof at 3+ valleys and 2+ ridges. Scope says "roof tie-in assumes standard integration; additional structural modifications not included" — the tie-in geometry looks non-trivial. Concealed-conditions risk elevated.
- **Two separate STORAGE areas** on plans p.4: "STORAGE" labeled in the addition upper level AND "STORAGE" labeled in the basement addition. Scope covers both (basement storage finish + "outlet in upstairs storage") but doesn't dimension them.
- **Bench detail in primary bathroom** shown as a callout (plans p.4). Scope covers it ("Install shower niche and bench").
- **A "BENCH" callout appears in the primary bedroom area too** (plans p.4) — separate from the shower bench. Possibly built-in seating not in scope.

## Discrepancies (explicit scope-vs-drawings contradictions)

1. **Window count: scope says 4, plans schedule shows 2.** Scope: "(4) windows including (3) 36" × 60" and (1) transom window." Plans p.4 window schedule: 1× transom (3'0"×1'0") + 1× D.H. (3'0"×3'0") = 2. Elevations (plans p.2, p.3) show "NEW WINDOW" callouts in at least 3 locations — hard to reconcile visually. The window schedule quantity totals under-count vs. scope AND vs. what elevations show. **Requires PM reconciliation.**

2. **Window sizes: scope says 36" × 60", plans schedule says 36" × 36" (3'0" × 3'0" D.H.).** Scope allowance is for "(3) 36" × 60"" windows. Plans p.4 window 02 is only 3'0" × 3'0" (36" × 36"). If the plans are authoritative the windows are smaller than the scope allowance covers — material cost is lower but scope commits to a size. **Reconcile.**

3. **Exterior siding vs brick: scope says vinyl siding, plans say brick + lap siding.** Scope: "Install vinyl siding to match existing as closely as possible." Elevations (plans p.2, p.3) explicitly label "NEW LAP SIDING" AND "NEW BRICK TO MATCH EXISTING" — brick on the basement level, lap siding on the upper level. Existing house is presumably brick lower / siding upper. Scope makes NO mention of brick masonry work. **Major cost/scope gap** — brick is a masonry trade, not siding. Verify with PM whether brick is in scope (change order?) or plans need to be updated.

4. **Roof shingles: scope says architectural asphalt, plans say "match existing."** Scope: "Install architectural asphalt shingle roofing system most similar to existing." Plans p.2 labels "NEW SHINGLES TO MATCH EXISTING." Not a hard contradiction — but "match existing" on plans is stricter than "most similar to" in scope.

5. **Pocket doors not shown on floor plan.** Scope: "(2) pocket door systems." Plans p.4 door schedule lists 4 interior doors as standard panel doors (A×2, B, C) — no pocket-door symbol or callout. If pocket doors are correct per scope, the plans need to identify which locations get pocket-door hardware (wall depth requirements differ).

6. **Elevator shaft: scope calls it "future," plans show it dimensioned and located on both levels.** Scope: "Frame (1) future elevator shaft approximately 4' × 4'. Elevator system not included." Plans p.4 shows "ELEV. 4'-0" × 4'-0"" on both basement and upper floor. Plans treat it as an active build element; scope treats it as framing-only. Not a contradiction, but confirms the shaft is being built now.

7. **Grinder pump / septic:** neither shown on plans. Scope raises septic feasibility and grinder pump as change-order items ("Costs associated with septic relocation, replacement, or grinder system are not included"). Plans p.4 note: "CONTRACTOR TO VERIFY LOCATION OF EXISTING PLUMBING, VENTING, SEPTIC TANK, AND HVAC BEFORE CONSTRUCTION." Confirms this is an open item, not a plans-side answer.

8. **Tankless water heater vent path:** scope says "Extend existing gas water heater vent through new roof system per code." Plans p.5 (roof plan) does NOT show a vent penetration for the WH. Verify vent routing intersects the new roof geometry.
