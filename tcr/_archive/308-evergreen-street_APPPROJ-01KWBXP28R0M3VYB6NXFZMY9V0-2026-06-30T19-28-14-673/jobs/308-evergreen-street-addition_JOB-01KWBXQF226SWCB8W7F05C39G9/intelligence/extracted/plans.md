---
generation_kind: intelligence_rebuild_v2
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWBXP28R0M3VYB6NXFZMY9V0/jobs/308-evergreen-street-addition_JOB-01KWBXQF226SWCB8W7F05C39G9/inputs/files/3725 SIMONS 012226.pdf.txt
  - _projects/308-evergreen-street_APPPROJ-01KWBXP28R0M3VYB6NXFZMY9V0/jobs/308-evergreen-street-addition_JOB-01KWBXQF226SWCB8W7F05C39G9/inputs/scope.md
---

# Extracted — 3725 SIMONS 012226.pdf (Greyscale Design architectural drawings)

Drawing set: 5 pages — left/back elevations (p1), right elevation (p2), floor plan (p3), roof plan (p4), title page (p0). Designer: Rebecca Lineberry NCIDQ, Greyscale Design LLC. Dated 01/22/26.

## Structural decisions

- **Footprint figures from p3 (FLOOR PLAN)**: "1ST FLOOR ADDITION 295", "BASEMENT ADDITION 295", "TOTAL ADDITION AREA 590" sqft (plans p3) — matches scope ~30×10 × 2 floors. CSV's 789 sqft includes ~200 sqft of existing-primary-bedroom retrofit area on top of the new footprint.
- **Roof system (p4 ROOF PLAN)**: gable form, slopes "12 S" / "12 6" markings indicating new 3/12 transitions tying into existing 6/12 ridge (R = ridge; S = slope; V = valley; T = transition).
  - Multiple valleys (V) indicate the new roof intersects the existing roof at multiple points → multi-valley tie-in increases concealed-condition surface area.
  - "CHIMNEY" noted on roof plan — possible vent/flue routing through new roof envelope.
- **Roof tie-in into existing 6/12** with note "CONTRACTOR TO VERIFY EXISTING ROOF SLOPES AND SOFFIT DEPTH BEFORE CONSTRUCTION" (p4) — explicitly flags field verification required, change-order risk per addition_rules concealed-roof-tie-in.
- **Elevator shaft placement**: floor plan labels "ELEV. 4'-0" × 4'-0"" — appears WITHIN the new addition footprint (between PRIMARY BEDROOM and HERS closet on the addition side). Plans RESOLVE the elevator location ambiguity → NOT a retrofit.
- **LVL beam location**: not explicitly drawn but implied by floor plan opening between existing house and new addition. Scope L45-47 confirms 3-ply 14" LVL spanning ~15'-6".

## Floor plan rooms (p3) — addition vs existing

**Inside addition footprint (NEW)**:
- PRIMARY BEDROOM (with note "EXISTING WINDOW, RELOCATED")
- PRMRY BTH (master bath with custom shower, dual vanity HERS/HIS, niche/bench)
- HERS closet, HIS closet, LINEN
- ELEV. shaft (4'-0" × 4'-0")
- STORAGE (basement-level)
- NEW SHWR location with NEW WINDOW

**Existing house (RETROFIT)**:
- BDRM. 2, BEDRM. 3 — labeled but NOT in addition objective; these are existing bedrooms
- BTH. 2 (hall bath) with notes: "RELOCATED EXISTING WINDOW", "NEW TRANSOM WINDOW", "EXISTING DOOR"
- GARAGE, LOUNGE, LIVING, KIT/DINING, COVERED DECK, FRONT PORCH — pre-existing, not in scope
- HALLWAY (where switch relocation from scope L78 occurs)

## Retrofit indicators (Signal A / B / C per addition_rules)

- **Signal A (area mismatch)**: BDRM 2, BEDRM 3, BTH 2 all named in plans but NOT in addition objective. Hall bath modification confirmed retrofit. Bedroom 2 and Bedroom 3 do not appear in any scope work line — likely fully existing, untouched.
- **Signal A**: Primary Bedroom retrofit (scope L131) of ~12'5"×16' existing primary bedroom — plans show the new primary bedroom of the addition; the SCOPED "primary bedroom remodel" refers to the EXISTING primary bedroom in the original house. Need PM clarification of which bedroom is being remodeled — the existing one being decommissioned/repurposed, or the addition primary itself.
- **Signal B (word "existing")**: plans contain "EXISTING DOOR", "RELOCATED EXISTING WINDOW" (×3 callouts) — confirms existing-house window relocation per scope L62-63.
- **Signal C (spatial ambiguity)**: scope's "(1) outlet in upstairs storage" (L75) — plans p3 show STORAGE only at basement level inside addition footprint, but scope says "upstairs storage" — possible second-floor storage area not explicitly drawn, OR scope text typo. PM confirmation needed.
- **Signal C**: scope's "future elevator shaft" RESOLVED by plans (inside addition).

## Things plans show that scope doesn't mention

- **NEW BRICK to match existing** on left, back, and right elevations (plans p1-p2) — scope L62 only mentions vinyl siding, not brick. Elevations show NEW BRICK on the lower portion (basement level) and NEW LAP SIDING on the upper portion (second-floor level). This is a MATERIAL ADDITION not priced anywhere obvious in the CSV; "Exterior Finishes – Siding, Trim & Gutters" $5,731 likely needs to cover both — see Discrepancies.
- **Multiple RELOCATED EXISTING WINDOWS** (3+ callouts across elevations + floor plan) — scope says only "(4) windows" NEW; relocated existing windows are additional installation labor not separately quantified.
- **NEW TRANSOM window in BTH 2 (hall bath)** — plans p3 — adds to window install count beyond the addition's 4 new units. Scope L146 only mentions removing the existing hall bath window and framing the opening — adding a new transom in its place is a plans-only detail.
- **Multiple doors** in plan schedule (5 total: 32"×2, 30"×1, 28"×1, 36" exterior×1) — scope L117-118 totals (4) interior doors. Plans show: A=32" panel ×2, B=30" panel ×1, C=28" panel ×1, D=36" exterior metal ×1.
- **Window schedule lists only 2 windows** (1 transom 3'×1', 1 DH 3'×3') — scope L63 lists (3) 36"×60" DH + (1) transom = 4 windows. Plans schedule + relocated-existing markings imply: 1 new transom in hall bath, 1 new DH in addition, + relocated existing windows that the scope counted as "new" for procurement purposes. Significant count discrepancy.
- **Door D** (36" exterior metal) — scope L64 says "up to (1) new exterior door"; matches.

## Discrepancies (explicit scope vs drawings contradictions)

1. **Brick vs siding**: plans elevations explicitly call out "NEW BRICK TO MATCH EXISTING" on basement-level walls of the addition. Scope L62 says only vinyl siding ("most similar to existing"). Plans contradict scope: addition is brick-on-basement + lap-siding-on-second-floor. PM must confirm — pricing in CSV may not include masonry labor (no separate masonry line; 72 hrs in "Exterior Finishes – Siding, Trim & Gutters" likely insufficient for brick veneer per editor_rules ~150 brick/day productivity).
2. **Window count**: scope (4 new) vs plan schedule (2 new) vs floor plan callouts (≥1 new transom + ≥1 new DH + ≥3 relocated existing) — uncertain how many windows TCR procures vs reuses. Procurement count must be resolved before `order.windows` lead-time decision.
3. **Door count**: scope (4 interior) vs plans (5 doors total, 4 interior + 1 exterior). Likely reconciles if scope's "(4) interior" excludes the exterior door counted separately at L64.
4. **Footprint discrepancy resolved by plans**: plans confirm 590 sqft new addition; CSV 789 sqft figure most likely includes the ~200 sqft existing primary-bedroom remodel area within the 789 total.
5. **Storage location**: scope says "upstairs storage" (L75) — plans only show STORAGE at basement level. Either scope typo, or undrawn upstairs storage area. PM should clarify.

## Field-verification notes called out on plans

- p3 floor plan: "CONTRACTOR TO VERIFY LOCATION OF EXISTING PLUMBING, VENTING, SEPTIC TANK, AND HVAC BEFORE CONSTRUCTION" — flags concealed-condition risk for plumbing rough-in.
- p4 roof plan: "CONTRACTOR TO VERIFY EXISTING ROOF SLOPES AND SOFFIT DEPTH BEFORE CONSTRUCTION" — flags concealed roof tie-in change-order risk.
- All pages: "CONTRACTOR TO VERIFY ALL DIMENSIONS BEFORE CONSTRUCTION" + designer disclaimer.

## Constraints to feed forward

- Roof tie-in is multi-valley (V markings on p4) → concealed-condition risk is HIGHER than a single-valley tie-in; addition_rules concealed-roof-tie-in buffer applies with ≥3-day buffer.
- Plumbing verification note + scope's "extend vent stacks through roof" + W/D relocation + master bath = full 4-day × 2-crew plumbing rough-in floor applies (per dev_rules 4H / editor_rules L138).
- Elevator location resolved (inside addition footprint) → no spatial-ambiguity question for the elevator shaft.
