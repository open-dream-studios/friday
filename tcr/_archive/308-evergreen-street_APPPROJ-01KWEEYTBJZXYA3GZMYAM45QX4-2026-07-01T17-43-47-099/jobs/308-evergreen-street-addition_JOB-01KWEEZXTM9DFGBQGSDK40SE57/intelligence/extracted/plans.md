---
generation_kind: intelligence_rebuild_v2
stage: extract_plans
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWEEYTBJZXYA3GZMYAM45QX4/jobs/308-evergreen-street-addition_JOB-01KWEEZXTM9DFGBQGSDK40SE57/inputs/files/3725 SIMONS 012226.pdf.txt
  - _projects/308-evergreen-street_APPPROJ-01KWEEYTBJZXYA3GZMYAM45QX4/jobs/308-evergreen-street-addition_JOB-01KWEEZXTM9DFGBQGSDK40SE57/inputs/scope.md
---

# Plans extraction — Simons Addition (drawing set dated 01/22/26)

Drawing set is 5 pages by Greyscale Design, LLC (Rebecca Lineberry,
NCIDQ), address on drawings reads 647 AA Deakins Rd, Jonesborough, TN
37659 — this is the DESIGNER's address, not the project address. The
job folder slug says "308 Evergreen Street" and the scope PDF is titled
"308 Evergreens Scope." Flagging in Discrepancies below.

Pages:
- p.1 — cover
- p.2 — Left & Back elevations
- p.3 — Right elevation
- p.4 — Floor Plan + window/door schedules
- p.5 — Roof Plan

## Structural decisions

- **Roof geometry — NEW gable roof at 3/12 slope tying into existing
  6/12** (plans p.5, confirmed by scope). Roof plan page shows a
  ridge, two slopes marked "12 S / 3" and "12 S / 6", three valleys
  ("V"), and multiple ridges ("R") where the new gable meets the
  existing 6/12 roof. Existing chimney is called out on the roof plan
  and must be worked around.
- **Wall heights** (plans pp.2–3): both floors are drawn at **8'-0"
  floor-to-ceiling**, with **1'-0"** between finished ceiling of
  lower level and finished floor of upper level (i.e. floor system
  depth). This matches typical dimensional-lumber floor framing depth
  and confirms scope's "basement-level storage + second-floor
  expansion."
- **Addition footprint = 295 sqft per floor × 2 floors = 590 sqft
  TOTAL addition area** (plans p.4, explicit callout: "295 / 295 /
  590 — 1ST FLOOR ADDITION / BASEMENT ADDITION / TOTAL ADDITION
  AREA"). Scope says "approximately 30' x 10'" which would be 300 sqft
  — plans call it 295. Effectively the 30×10 approximation. Small
  addition footprint under 800 sqft → stick-frame default per company
  belief `stick_frame_default_for_small_additions` applies unless PM
  confirms otherwise.
- **Roof span for new gable is ≤ 10 ft** (the narrow addition
  dimension is 10'-0"; gable ridge runs along the 30' dimension).
  Well under the 24 ft truss-trigger threshold. **No trusses needed
  — stick-frame the roof.**
- **Elevator shaft** shown on floor plan p.4 (labeled "ELEV." with
  "4'-0" × 4'-0" callouts on both floors). Located between the
  Primary Bath / Hers / His closet area and the storage side —
  vertically aligned on both floors as required for a shaft. Framing
  only per scope.
- **LVL beam location** — plans do not explicitly dimension the LVL
  location. Scope calls out (1) 3-ply 14" LVL spanning ~15'-6" to
  open an existing load-bearing wall. Floor plan p.4 shows an
  existing wall being opened between the Primary Bedroom and the
  new addition area (interior demarcation between "EXISTING" and
  "LINE OF NEW ADDITION"). This is the load-bearing wall the LVL
  replaces.
- **Roof tie-in is CONCEALED at the existing 6/12 roof** (plans p.5
  + scope). New 3/12 ties into existing 6/12 — pitch change means
  the tie-in point must be exposed before final rafter/valley
  dimensions are known. Standard TCR "concealed roof tie-in" risk.

## Retrofit indicators (existing conditions the plans expose)

- **Hall bath ("BTH. 2" on p.4) is an EXISTING room being modified.**
  Floor plan shows the hall bath with a **new shower** (labeled "NEW
  SHWR."), a relocated door, and the existing window called out for
  removal (scope: "Remove existing window and frame opening. Install
  insulation, drywall, and finish"). Hall bath does NOT sit inside
  the new addition footprint — it's clearly on the existing-house
  side of the "LINE OF NEW ADDITION" boundary drawn on p.4.
- **Bedroom 3 is EXISTING** — labeled on p.4 with the note
  "EXISTING" nearby. Two existing windows in Bedroom 3 are being
  **relocated** (called out on elevations pp.2–3: "EXISTING WINDOW
  RELOCATED" appears twice on the back elevation, once on the left).
- **Primary Bedroom (~12'5" × 16')** — scope says "Primary Bedroom
  Remodel" of the existing bedroom; plans p.4 show this room
  labeled and it sits on the existing-house side, connected to the
  new master bath / closet expansion.
- **Existing door being relocated** (schedule on p.4 shows "A/B/C/D"
  doors, and one existing door is called "RELOCATED DOOR" on plan).
- **Existing chimney** is present on the roof plan (p.5, small
  callout) — new roof framing must dodge/tie around it.
- **Existing plumbing, venting, septic tank, and HVAC location** —
  p.4 carries the explicit note *"CONTRACTOR TO VERIFY LOCATION OF
  EXISTING PLUMBING, VENTING, SEPTIC TANK, AND HVAC BEFORE
  CONSTRUCTION."* This is a retrofit-heavy indicator; PM must
  physically locate these before any excavation.
- **Existing gas water heater stays** — scope says "Extend existing
  gas water heater vent through new roof system." Plans p.5 (roof
  plan) show the new roof geometry but do not explicitly locate the
  vent penetration; PM to field-locate. **No new tank in scope**
  (unless optional Tankless WH Allowance is exercised → then
  procurement + tank_set apply per Rule 4H).
- **Existing heat pump + electrical disconnect** — scope says
  "Relocate existing heat pump and electrical disconnect." Plans
  don't show the current heat pump location; verification required
  in the field. Triggers Rule 4K (heat pump relocation BEFORE demo,
  in `site_prep`).
- **Dryer vent relocation** — floor plan p.4 has the callout
  "RELOCATE DRYER VENT" near the primary bath area. Consistent with
  scope's W/D relocation.

## Things plans show scope doesn't mention

- **Bedroom 2 ("BDRM. 2") appears on the floor plan p.4** — but scope
  never lists Bedroom 2 as a scope area. It sits on the existing side
  near the entry from the primary suite. It appears to be an
  UNTOUCHED existing room shown for context only. Confirm with PM
  that no work is happening in Bedroom 2. If any drywall/paint/
  flooring touches it, it's an addition retrofit not accounted for.
- **Existing "STORAGE" area is labeled inside the new addition
  footprint on p.4** — this is the "basement-level storage" from
  scope, so consistent — but plans also show a second "STORAGE"
  label upstairs (near Bedroom 3), which is likely existing. Verify.
- **Existing house program shown on p.4**: GARAGE, LOUNGE, LIVING,
  KIT (kitchen), DINING, COVERED DECK, FRONT PORCH. These are
  context labels only — no scope work in any of them. If any
  demo/patch bleeds into these areas, out of scope.
- **Bench + return ("BENCH" + "RTRN.") called out in the primary
  bath layout** on p.4 — scope mentions a shower bench and niche
  but plans show more detail on placement. Non-material but
  confirms tile work location.
- **Linen closets** — plans p.4 show TWO "LINEN" closets on the
  upstairs level (one in the primary suite hall, one in the primary
  bath). Scope doesn't specifically enumerate linen closets or
  their trim/shelving — assume included in general trim/paint
  scope. Flag if custom shelving expected (optional Closet & Cabinet
  package covers primary closet, not linen).
- **Door schedule specifies four doors** (p.4): A = 32"×1-3/8" panel
  (×2), B = 30"×1-3/8" panel (×1), C = 28"×1-3/8" panel (×1),
  D = 36"×1-3/4" **exterior metal door** (×1). Scope says "(4)
  interior doors total" and "(1) new exterior door." Plans confirm
  1 exterior + 3 interior panel doors, plus a **relocated existing
  door** = 4 door leaves total, but only 3 are NEW interior doors
  in the schedule, not 4. Scope's "(1) pre-hung interior + (2)
  pocket doors = 3 interior" reconciles with the schedule (A, B, C
  = 3 interior panel doors). **Plans show NO pocket doors** — all
  three interior doors on the schedule are panel doors. Scope says
  pocket doors are used; plans don't reflect that. Discrepancy
  (see below).
- **Window schedule specifies only TWO new windows** (p.4): 01 =
  3'0"×1'0" transom (×1), 02 = 3'0"×3'0" double-hung (×1). Scope
  says "(4) windows including (3) 36"×60" and (1) transom" — that
  is a MATERIAL discrepancy. See Discrepancies section.
- **Roof plan shows ridge/valley/transition annotations** ("R", "V",
  "S", "T") — the "T" (transition) callout suggests a specific
  transition detail at the pitch change from 3/12 to 6/12. Scope
  glosses this as "standard integration" but plans hint at a
  detail worth field-verifying (plans p.5).
- **NEW BRICK to match existing** appears on left AND back
  elevations (plans pp.2–3). Scope's exterior finishes section only
  mentions "vinyl siding to match existing" and doesn't call out
  brick veneer. Plans show new brick at the base of the addition
  walls (below the siding transition line). **This is a real
  scope-vs-plans discrepancy** — see below.
- **Ridge vent** callouts on the roof plan are consistent with scope,
  but the roof plan p.5 shows **multiple ridges** (the new gable's
  ridge plus the tie-in ridge with the existing) — flag if the
  siding/roofing crew hasn't priced multiple ridge terminations.

## Discrepancies (explicit scope-vs-drawings contradictions)

1. **Window count and sizes.** Scope says "(4) windows including (3)
   36"×60" and (1) transom window" (scope.md, Exterior Finishes).
   Plans p.4 window schedule lists only **(1) transom 3'0"×1'0"** and
   **(1) double-hung 3'0"×3'0"** = 2 NEW windows. The elevations
   pp.2–3 show two **"EXISTING WINDOW RELOCATED"** callouts plus one
   or two "NEW WINDOW" callouts and the transom. Best reconciliation:
   scope's "(4) windows" = 2 new units + 2 relocated existing units;
   scope's "(3) 36"×60"" is wrong — plans show only one 3'0"×3'0"
   (36"×36", not 36"×60") new double-hung. **Material discrepancy —
   size and count both differ.** Procurement task must reflect what
   plans show, not scope. PM to confirm before ordering windows
   (21-cal-d lead time per company editor rules).

2. **Brick veneer at addition base.** Elevations pp.2–3 label "NEW
   BRICK TO MATCH EXISTING" at the base of the addition. Scope
   Exterior Finishes only lists vinyl siding + WRB + sheathing — no
   brick, no brick labor, no brick material. If the existing home
   has a brick water-table / wainscot and the addition must match,
   there's an unpriced masonry sub-scope. **Flag for PM interview:
   is brick actually installed or is this a design intent the PM
   discussed dropping?**

3. **Interior door types.** Scope says "(2) pocket door systems"
   plus "(1) pre-hung interior door." Plans door schedule (p.4)
   lists three interior doors (A×2, B, C) all as **"PANEL DOOR"** —
   no pocket door callouts. Either the schedule is understating
   what's built (pocket doors are still panel doors, and the pocket
   hardware isn't shown on schedule) OR the scope over-promised
   pocket doors. Pocket door systems have a $400 allowance in scope
   — real cost. PM to confirm.

4. **Address on drawings vs. job.** Drawings cover-sheet header
   reads "647 AA DEAKINS RD, JONESBOROUGH, TN 37659" (repeated on
   every page). Job folder slug and scope title say "308 Evergreen
   Street" / "308 Evergreens." Either the drawings are stamped with
   the DESIGNER's address (most likely — Rebecca Lineberry's studio
   address) or these drawings are for the wrong site. Confirm with
   PM at interview that these drawings are indeed for 308 Evergreen.
   If yes, ignore the header; if no, entire generation is against
   the wrong drawing set.

5. **Roof plan pitch transition detail.** Scope calls the tie-in
   "standard integration; additional structural modifications not
   included." Plans p.5 explicitly show a **transition ("T")**
   callout at the pitch change and multiple valleys. "Standard"
   integration language in scope is a change-order hedge — plans
   show enough complexity (3/12 → 6/12 pitch change, multiple
   valleys, existing chimney nearby) that the concealed-tie-in risk
   is real. Consistent with company rule set; flag for PM to open
   the tie-in ceiling early during framing.

6. **Roof/truss decision.** Scope says "truss or rafter framed,
   determined during design phase" — but plans p.5 don't specify.
   Company belief `stick_frame_default_for_small_additions` applies
   (small addition, span < 24 ft) → stick-frame default, NO
   procurement.trusses task. PM to confirm at interview.
