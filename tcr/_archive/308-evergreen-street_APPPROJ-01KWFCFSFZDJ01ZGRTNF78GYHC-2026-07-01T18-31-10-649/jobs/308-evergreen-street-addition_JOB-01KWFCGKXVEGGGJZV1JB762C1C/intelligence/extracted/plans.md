---
generation_kind: intelligence_rebuild_v2
stage: extract_plans
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWFCFSFZDJ01ZGRTNF78GYHC/jobs/308-evergreen-street-addition_JOB-01KWFCGKXVEGGGJZV1JB762C1C/inputs/files/3725 SIMONS 012226.pdf.txt
  - _projects/308-evergreen-street_APPPROJ-01KWFCFSFZDJ01ZGRTNF78GYHC/jobs/308-evergreen-street-addition_JOB-01KWFCGKXVEGGGJZV1JB762C1C/inputs/scope.md
---

# Plans extraction — Simons Addition (3725 SIMONS 012226)

Set prepared by **Rebecca Lineberry, NCIDQ / Greyscale Design, LLC** at 647 AA Deakins Rd, Jonesborough, TN 37659. Set dated **January 22, 2026**. Five sheets total: elevations (L/R + Back), Right elevation, Floor Plan, Roof Plan.

General plan notes (repeated on every sheet):
- "CONTRACTOR TO VERIFY ALL DIMENSIONS BEFORE CONSTRUCTION."
- "GREYSCALE DESIGN, LLC WILL NOT BE RESPONSIBLE FOR ERRORS IN DIMENSIONS OR CALCULATIONS ON DRAWINGS."
- Floor plan note: "CONTRACTOR TO VERIFY LOCATION OF EXISTING PLUMBING, VENTING, SEPTIC TANK, AND HVAC BEFORE CONSTRUCTION" (plans p.4).
- Roof plan note: "CONTRACTOR TO VERIFY EXISTING ROOF SLOPES AND SOFFIT DEPTH BEFORE CONSTRUCTION" (plans p.5).

These "verify before construction" notes are field-verification gates — every one of them is a potential change-order trigger.

## Structural decisions

- **Two-story addition, 30' × 10' footprint on each level.** Floor plan (plans p.4) states:
  - 1st floor addition: **295 sqft**
  - Basement addition: **295 sqft**
  - Total addition area: **590 sqft**
  This is smaller than the CSV "Overall Footprint SF: 789" figure — the ~200 sqft delta is the existing bedroom being remodeled, not new construction.
- **Wall heights:** 8'-0" floor-to-ceiling on both levels, with a **1'-0" band** (floor system depth) between levels shown on all three elevations (plans p.2, p.3). Total exterior wall stack ≈ 17'-0" above finished floor.
- **Roof:** New gable roof, 3/12 slope, tying into existing 6/12 (plans p.5). Ridge, valley, and transition points explicitly marked. Roof plan shows valleys where new 3/12 meets existing 6/12 — non-trivial tie-in geometry with at least 3 valleys (V) and multiple ridges (R) marked. New shingles specified "to match existing."
- **Elevator shaft** shown on floor plan (plans p.4) at 4'-0" × 4'-0", located between the two floors (labeled ELEV. on both levels). Framing only per scope; shaft carried through both floors.
- **LVL beam** (from scope) opens the existing load-bearing wall at the primary bedroom tie-in. Plans show the tie-in geometry: existing wall demoed at 15'-6" opening between the existing bedroom footprint and the new addition (approximate — plans p.4 dimensions in that zone read 10'-1" + 5'-9" = ~15'-10").
- **Primary bath layout** (plans p.4): dual-vanity ("HERS", "HIS") flanking a linen closet, custom shower with bench + return wall, separate WC. Bath 2 shown as separate. Walk-in closet ("PRMRY.") with bench.
- **Window / door schedules** (plans p.4):
  - Window 01: 3'0" × 1'0" **transom** — QTY 1
  - Window 02: 3'0" × 3'0" **D.H. (double-hung)** — QTY 1
  - Door A: 32" × 1-3/8" panel door — QTY 2
  - Door B: 30" × 1-3/8" panel door — QTY 1
  - Door C: 28" × 1-3/8" panel door — QTY 1
  - Door D: 36" × 1-3/4" **exterior metal door** — QTY 1

## Retrofit indicators (existing conditions the plans expose)

- **Two existing windows to be relocated**, both labeled "EXISTING WINDOW, RELOCATED" on the Left/Back elevations and floor plan (plans p.2, p.4). This is retrofit work: pull each existing window, patch original opening, cut new opening in relocated position, re-install. Not called out as its own scope line — bundled into "Exterior Finishes" and "Framing."
- **Existing door relocated** — the floor plan (plans p.4) shows a "RELOCATED DOOR" on the existing bedroom side and an "EXISTING DOOR" label near the addition tie-in.
- **Existing chimney** shown on roof plan (plans p.5). New roof geometry must integrate around the chimney; no re-flashing scope line, but the plan implies the new roof envelope butts against the existing chimney.
- **Existing bedroom (primary) tie-in wall** is load-bearing per LVL scope. Plans p.4 show the primary bedroom retrofit is directly adjacent to the new addition, sharing a demoed wall line.
- **Existing hall bath** (Bath 2 area on plans p.4) has a window that gets removed and infilled per scope. Plans show the "BTH. 2" location — the acrylic shower swap and window infill both occur here.
- **Existing brick, existing shingles, existing lap siding** — all three elevations (plans p.2, p.3) call out "NEW BRICK TO MATCH EXISTING," "NEW SHINGLES TO MATCH EXISTING," "NEW LAP SIDING." Match risk on all three. Scope says "vinyl siding to match existing as closely as possible" — see Discrepancies below (plans say lap; scope says vinyl).
- **Existing floor line / ceiling line** dimensions on the elevations imply the new 1st floor addition ties into existing finished floor elevation without a step. Field-verify.
- **Dryer vent** is called out on the floor plan (plans p.4): "RELOCATE DRYER VENT." Confirms the W/D relocation is inside the addition footprint.

## Things plans show scope doesn't mention

- **Covered deck** and **front porch** are drawn on the floor plan (plans p.4) as existing features flanking the addition. Not obviously in scope but the addition footprint abuts them — flashing/tie-in at those junctions is unaddressed in scope.
- **Garage, Living, Kit, Dining, Lounge** — the plan shows the entire existing house layout for context (plans p.4). Scope only names the primary bedroom / master bath / hall bath as the retrofit zones. The other existing rooms are unaffected per plans.
- **Bench in primary bath** and **linen closets (2)** — the plan shows a bench in the primary bath shower zone AND a return-wall bench, plus two linen closets ("LINEN" labels on plans p.4). Scope mentions the shower niche and bench but doesn't call out the two linen closets — cabinetry / built-in cost unclear.
- **Storage room** labeled on the addition (plans p.4) — the 1st floor addition includes a "STORAGE" room adjacent to the primary bedroom. Scope says "outlet in upstairs storage" so this is anticipated, but the room itself isn't described in the addition finish scope. Assume LVT + paint like the rest.
- **Window count discrepancy** — plans schedule (plans p.4) shows only **2 windows** (01 transom + 02 double-hung, QTY 1 each) PLUS the **2 relocated existing windows**. Scope says "(4) windows including (3) 36" × 60" and (1) transom window." See Discrepancies.
- **Door count discrepancy** — plans schedule (plans p.4) shows **5 doors** (2 × 32", 1 × 30", 1 × 28", 1 × 36" exterior metal). Scope says "(4) interior doors total" plus "(1) new exterior door." Count matches on total (4 int + 1 ext = 5) but the plans schedule doesn't distinguish pocket doors from pre-hung. Scope says "(2) pocket door systems" and "(1) pre-hung" — plans p.4 doesn't obviously label pocket vs hinged.
- **Roof plan complexity** — the roof plan (plans p.5) shows at least 3 valleys, multiple ridges, and slope-transition points. This is NOT a simple shed or single-gable — it's a multi-hip gable interlaced with the existing 6/12 roof. Scope treats it as "standard integration" — plans imply the tie-in is more complex than a straight gable-to-gable connection.

## Discrepancies (explicit scope-vs-drawings contradictions)

1. **Siding material — vinyl vs lap.** Scope says "Install **vinyl siding** to match existing as closely as possible." Elevations (plans p.2, p.3) label the new siding as "**NEW LAP SIDING**." Lap can be vinyl, fiber cement, or wood — ambiguous. If existing house is wood/fiber cement lap and scope commits to vinyl, the match is going to be poor. **Interview question candidate.**

2. **Window count — 4 (scope) vs 2 new + 2 relocated (plans).** Scope: "(4) windows including (3) 36" × 60" and (1) transom." Plans schedule (plans p.4): only 2 new windows drawn (a 3'×1' transom + a 3'×3' DH), with 2 additional "EXISTING WINDOW, RELOCATED" units. The scope's "(3) 36" × 60"" does not appear anywhere in the plans schedule. Either the scope is over-counting new windows OR the plans schedule is incomplete. **Direct contradiction — must resolve.**

3. **Window sizes — scope says 36" × 60" (5'-0" tall), plans show 3'-0" × 3'-0" (D.H.) and 3'-0" × 1'-0" (transom).** The plans' new D.H. window is nowhere near 36" × 60". Scope's material allowance schedule budgets "Windows: $300 each" — that price won't buy a 36" × 60" DH regardless.

4. **Roof tie-in complexity.** Scope: "Roof tie-in assumes standard integration; additional structural modifications not included." Roof plan (plans p.5) shows a multi-valley, mixed 3/12 + 6/12 geometry with an existing chimney to work around. This is NOT a standard integration by any reasonable read — it's a change-order risk waiting to happen. Scope acknowledges this generically but the drawings make the risk concrete.

5. **Truss vs rafter — deferred in both.** Scope: "truss or rafter framed, determined during design phase." Plans (plans p.5) show the roof plan geometry (slopes, valleys, ridges) but no framing plan indicating truss or stick. Design phase hasn't resolved this. Given the multi-valley tie-in and the existing chimney to work around, stick-frame is highly likely — supports company belief `stick_frame_default_for_small_additions` (footprint 590 sqft new, well under 800 sqft threshold).

6. **Elevator shaft location.** Scope: "Frame (1) future elevator shaft approximately 4' × 4'." Plans p.4 show the shaft at 4'-0" × 4'-0" — consistent. No discrepancy, but plans confirm shaft carries through BOTH the basement addition and the 1st floor addition. Scope wording is silent on which levels — plans resolve.

7. **Septic / grinder pump — plan says verify, scope says change-order.** Floor plan note (plans p.4): "CONTRACTOR TO VERIFY LOCATION OF EXISTING PLUMBING, VENTING, SEPTIC TANK, AND HVAC BEFORE CONSTRUCTION." Scope defers septic relocation, replacement, and grinder pump to change orders. Plans don't show a septic tank location. **Pre-construction TDEC verification is a hard prerequisite before excavation.**

8. **CSV total vs scope Total Investment.** Not a drawings issue directly, but worth noting cross-reference: scope states **Total Investment: $173,850**. CSV grand total: **$100,778.92**. ~$73k gap (~42%). This is the mandatory reconciliation-question trigger per company rule `scope_vs_csv_total_reconciliation` — flagged here because the drawings don't resolve it either way, and any scope-add revealed by drawings (extra windows, complex roof tie-in, brick match) could partially explain the gap.
