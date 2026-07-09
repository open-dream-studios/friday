---
generation_kind: task_graph_v2
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWEEYTBJZXYA3GZMYAM45QX4/jobs/308-evergreen-street-addition_JOB-01KWEEZXTM9DFGBQGSDK40SE57/intelligence/facts.md
  - _projects/308-evergreen-street_APPPROJ-01KWEEYTBJZXYA3GZMYAM45QX4/jobs/308-evergreen-street-addition_JOB-01KWEEZXTM9DFGBQGSDK40SE57/intelligence/confirmed.md
  - _projects/308-evergreen-street_APPPROJ-01KWEEYTBJZXYA3GZMYAM45QX4/jobs/308-evergreen-street-addition_JOB-01KWEEZXTM9DFGBQGSDK40SE57/intelligence/applicable_rules.json
  - _projects/308-evergreen-street_APPPROJ-01KWEEYTBJZXYA3GZMYAM45QX4/jobs/308-evergreen-street-addition_JOB-01KWEEZXTM9DFGBQGSDK40SE57/intelligence/extracted/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KWEEYTBJZXYA3GZMYAM45QX4/jobs/308-evergreen-street-addition_JOB-01KWEEZXTM9DFGBQGSDK40SE57/intelligence/extracted/breakdown.md
  - _projects/308-evergreen-street_APPPROJ-01KWEEYTBJZXYA3GZMYAM45QX4/jobs/308-evergreen-street-addition_JOB-01KWEEZXTM9DFGBQGSDK40SE57/intelligence/extracted/plans.md
  - _projects/308-evergreen-street_APPPROJ-01KWEEYTBJZXYA3GZMYAM45QX4/jobs/308-evergreen-street-addition_JOB-01KWEEZXTM9DFGBQGSDK40SE57/manifest.json
  - _projects/308-evergreen-street_APPPROJ-01KWEEYTBJZXYA3GZMYAM45QX4/jobs/308-evergreen-street-addition_JOB-01KWEEZXTM9DFGBQGSDK40SE57/interview/round-1.md
last_verified_at: "2026-07-01T09:26:32.140Z"
---

# Task graph — 308 Evergreen Street addition

60 tasks. Two-story 30'×10' addition (~590 SF added), basement storage,
primary bedroom + master bath + walk-in closet remodel + hall bath retrofit.
1,287 total labor hours per CSV; stick-frame roof, no trusses, no tankless,
no brick veneer, no septic replacement.

Critical path is starred (★) below.

## Phase 0 — Pre-construction (backward-scheduled from on-site start)

T1. **checkpoint.selections_finalized** — Selections finalized checkpoint —
    Duration 0d / Trade pm / Depends on ∅ / pre-construction offset 15wd,
    lead-up 5wd. Rule 4P (mandatory, separate from equipment_confirmed).

T2. **checkpoint.equipment_confirmed** — Equipment confirmed checkpoint —
    Duration 0d / Trade pm / Depends on ∅ / pre-construction offset 10wd,
    lead-up 3wd. Rule 4P (mandatory; gates mini-split, subpanel, ext door, LVL).

T3. **general.permitting** — Permit walk-in + issuance — Duration 1d /
    Trade pm / Depends on ∅ / pre-construction offset 15wd, lead-up 2wd.
    Rule 4A (work, NOT lead_time).

T4. **general.tdec_septic_acknowledgment** — TDEC septic permit
    acknowledgment (no septic work) — Duration 1d / Trade pm /
    Depends on ∅ / pre-construction offset 30cd. Existing septic adequate
    (confirmed.md q.septic_grinder_direction).

## Phase 1 — Procurement + permits (3-task pattern per Rule 4R)

T5. **procurement.windows.order** — Order windows (1 transom + 1 DH per
    plans) — Duration 1d / Trade pm / Depends on T1.

T6. **procurement.windows.wait** — Wait ~21cd — Duration 0d / lead_time /
    Depends on T5.

T7. **procurement.windows.arrived** — Windows arrived — Milestone /
    Depends on T6.

T8. **procurement.lvl.order** — Order LVL beam (3-ply 14" × 15'-6") —
    Duration 1d / Depends on T2.

T9. **procurement.lvl.wait** — Wait ~14cd — Duration 0d / lead_time /
    Depends on T8.

T10. **procurement.lvl.arrived** — LVL arrived — Milestone / Depends on T9.

T11. **procurement.panel.order** — Order 100A subpanel — Duration 1d /
     Depends on T2.

T12. **procurement.panel.wait** — Wait ~14cd — Duration 0d / lead_time /
     Depends on T11.

T13. **procurement.panel.arrived** — Subpanel arrived — Milestone /
     Depends on T12.

T14. **procurement.minisplit.order** — Order mini-split — Duration 1d /
     Depends on T2.

T15. **procurement.minisplit.wait** — Wait ~14cd — Duration 0d /
     lead_time / Depends on T14.

T16. **procurement.minisplit.arrived** — Mini-split arrived — Milestone /
     Depends on T15.

T17. **procurement.tile.order** — Order custom master-bath tile —
     Duration 1d / Depends on T1.

T18. **procurement.tile.wait** — Wait ~21cd — Duration 0d / lead_time /
     Depends on T17.

T19. **procurement.tile.arrived** — Tile arrived — Milestone /
     Depends on T18.

T20. **procurement.lvt.order** — Order LVT flooring (stock) — Duration
     1d / Depends on T1.

T21. **procurement.lvt.wait** — Wait ~7cd — Duration 0d / lead_time /
     Depends on T20.

T22. **procurement.lvt.arrived** — LVT arrived — Milestone / Depends on T21.

## Phase 2 — On-site execution

### Site prep + customer early item (Rule 4V — two buckets)

T23. **site_prep.heat_pump_relocation** — Relocate existing heat pump +
     electrical disconnect — Duration 1d / Trade hvac / Crew 2 / Depends on
     T3 / lead-up 2wd. Rule 4K (≥3wd before demo).

T24. **customer_early.hall_bath_acrylic_shower_swap** — Hall bath acrylic
     shower swap (Day-1 early item, off critical path) — Duration 2d /
     Trade plumbing / Crew 2 / Depends on T3. Rule 4V bucket 1.

### Demo + foundation

T25. **demo.selective** — Selective demolition + site work (saw-cut
     walkway, remove railroad ties, dump runs) — Duration 3d / Trade demo /
     Crew 3 / Depends on T23 (FS+3wd per Rule 4K). CSV row 12: 56 hrs.

T26. **excavation.footings** — Excavate for footings + slab — Duration 2d /
     Trade excavation / Crew 2 / Depends on T25. CSV row 13: 78 hrs.

T27. ★ **foundation.monolithic_pour** — Monolithic footings + slab pour —
     Duration 2d / Trade concrete / Crew 3 / Depends on T26. Rule 4B
     monolithic (no CMU per scope.md L45).

T28. **inspect.foundation** — Foundation inspection — Duration 0.5d /
     Trade inspector / Depends on T27 / lead-up 1wd.

### Framing

T29. ★ **framing.floor_system** — Floor system + subfloor —
     Duration 2d / Trade framing / Crew 3 / Depends on T28.

T30. ★ **framing.lvl_install** — Install 3-ply 14" LVL beam + shoring —
     Duration 2d / Trade framing / Crew 3 / Depends on T29 + T10 (LVL
     arrived). CSV row 14: 60 hrs.

T31. ★ **framing.exterior_walls** — Frame exterior + interior 2×4 walls +
     elevator shaft — Duration 3d / Trade framing / Crew 3 / Depends on T30.
     CSV row 15 balance; elevator shaft folded in (breakdown silent
     omission #3).

T32. ★ **framing.roof** — Frame 3/12 gable + tie-in to existing 6/12
     (stick-frame, no trusses) — Duration 3d / Trade framing / Crew 3 /
     Depends on T31. Rule 4Q + belief stick_frame_default.

T33. **framing.roof_tie_in_discovery** — Roof tie-in discovery buffer
     (concealed 3/12→6/12 seam + chimney) — Duration 1d / Trade framing /
     Crew 2 / Depends on T32 SS. Concealed-conditions risk hedge.

### Roofing + windows (Rule 4I/4J: MEPs gate on underlayment + windows, NOT dried_in)

T34. **roofing.sheathing** — Roof sheathing — Duration 1d / Trade
     roofing / Crew 3 / Depends on T32.

T35. ★ **roofing.underlayment** — Synthetic underlayment + drip edge +
     temp dry-in — Duration 1d / Trade roofing / Crew 2 / Depends on T34.
     Rule 4I/4J MEP gate.

T36. **windows.install** — Install windows + exterior door + WRB
     flashing — Duration 2d / Trade windows_doors / Crew 2 / Depends on
     T32 + T7 / can_overlap_with T35. Rule 4I.

T37. **milestone.dried_in** — Dried-in — Milestone / Depends on T35 + T36.
     Informational; MEPs already gated by T35+T36 per Rule 4I/4J.

T38. **roofing.shingles** — Architectural shingles + flashing + ridge
     vent — Duration 2d / Trade roofing / Crew 3 / Depends on T35.

T39. **roofing.fascia_soffit_gutters** — Fascia + vinyl soffit + gutters —
     Duration 2d / Trade roofing / Crew 2 / Depends on T38.

### MEP rough (Rule 4G: mini-split LAST → plumbing → electrical → mini-split line-set)

T40. ★ **plumbing.rough** — Plumbing rough-in (master bath, W/D, vent
     stack through roof) — Duration 4d / Trade plumbing / Crew 2 /
     Depends on T35 + T36. Rule 4H SKIP (existing WH stays);
     plumbing_rough_min_duration overrides CSV's 2.5d to 4d hard floor.

T41. ★ **electrical.rough** — Electrical rough-in (subpanel, 12 recessed,
     30A elevator circuit) — Duration 4d / Trade electrical / Crew 2 /
     Depends on T40 + T13. Rule 4G order.

T42. **hvac.minisplit_lineset_rough** — Mini-split line-set rough (in-wall
     run) — Duration 0.5d / Trade hvac / Crew 1 / Depends on T41 + T16.
     Rule 4G LAST.

### Bundled rough inspection (Rule 4C — one inspector, one day, all trades)

T43. ★ **inspect.rough_bundled** — Bundled rough inspection (framing +
     plumbing + electrical + HVAC) — Duration 1d / Trade inspector /
     Depends on T42 / lead-up 1wd. Rule 4C.

T44. **general.punch_buffer_rough** — Punch buffer after rough
     (fix + re-inspect if needed) — Duration 2d / Trade general / Crew 2 /
     Depends on T43. Rule 4D.

### Insulation + exterior finish (can parallelize with MEP)

T45. **insulation.install** — Insulation R13/R30/R30 + air sealing —
     Duration 2d / Trade insulation / Crew 2 / Depends on T44. CSV row 22:
     44 hrs.

T46. **inspect.insulation** — Insulation inspection — Duration 0.5d /
     Trade inspector / Depends on T45 / lead-up 1wd.

T47. **exterior.siding_trim** — Vinyl siding + trim (NO brick veneer) —
     Duration 4d / Trade siding / Crew 2 / Depends on T36 + T39 /
     can_overlap_with T40, T41, T45. CSV row 17 (72 hrs).

### Drywall + interior finish (Rule 4N: 2-trade cap; Rule 4E/4F: paint 2-phase; Rule 4L: flooring→trim)

T48. ★ **drywall.hang_finish** — Drywall hang + tape + Level 3 finish
     (consolidated: addition + primary bedroom + basement) — Duration
     10d / Trade drywall / Crew 3 / Depends on T46. CSV row 23: 159 hrs.

T49. **paint.phase_1** — Paint phase 1 (primer + ceilings) — Duration 2d /
     Trade paint / Crew 2 / Depends on T48. Rule 4E/4F.

T50. ★ **tile.master_bath** — Master bath tile (waterproofing, walls,
     mosaic floor, niche + bench) — Duration 5d / Trade tile / Crew 2 /
     Depends on T49 + T19. CSV row 25: 88 hrs.

T51. **flooring.install** — LVT flooring (addition + primary bedroom) —
     Duration 3d / Trade flooring / Crew 2 / Depends on T49 + T22 /
     can_overlap_with T50. Rule 4L (flooring precedes trim).

T52. **electrical.finish** — Electrical finish/trim-out (fixtures,
     devices, dimmers) — Duration 2d / Trade electrical / Crew 2 /
     Depends on T49. Rule 4L: after paint_1 primer.

T53. **plumbing.finish** — Plumbing finish (72" vanity, faucets, toilet,
     shower valve trim) — Duration 2d / Trade plumbing / Crew 2 /
     Depends on T50 + T51.

T54. **hvac.minisplit_install** — Mini-split install (head + outdoor
     unit + commissioning) — Duration 1d / Trade hvac / Crew 1 /
     Depends on T52. Rule 4N: staggered AFTER electrical.finish to hold
     2-trade interior cap.

T55. **trim.install** — Interior trim + baseboard + casing + interior
     doors (2 pocket + pre-hung remainder) — Duration 3d / Trade
     trim_carpentry / Crew 2 / Depends on T51. Rule 4L.

T56. ★ **paint.phase_2** — Paint phase 2 (wall finish + trim paint +
     touch-ups) — Duration 2d / Trade paint / Crew 2 / Depends on
     T55 + T53 + T54 + T50. Rule 4E/4F: predecessors include EVERY
     finish trade.

### Hall bath retrofit bucket (Rule 4V bucket 2)

T57. **hall_bath.window_infill_patch** — Hall bath window infill +
     insulation + drywall + repaint — Duration 2d / Trade general /
     Crew 2 / Depends on T48 / can_overlap_with T49. Rule 4V retrofit
     bucket (separate from T24 Day-1 early item).

## Phase 3 — Closeout

T58. ★ **closeout.punch_final_clean** — Punch list + final clean + final
     walkthrough — Duration 3d / Trade cleanup / Crew 2 / Depends on
     T56 + T57.

T59. **inspect.final** — Final inspection (building + electrical +
     plumbing + HVAC) — Duration 1d / Trade inspector / Depends on T58 /
     lead-up 1wd.

T60. **milestone.substantial_completion** — Substantial completion —
     Milestone / Depends on T59. Triggers final invoice + balance due.

## Critical path (12 tasks, ★ above)

foundation.monolithic_pour → framing.floor_system → framing.lvl_install →
framing.exterior_walls → framing.roof → roofing.underlayment →
plumbing.rough → electrical.rough → inspect.rough_bundled →
drywall.hang_finish → tile.master_bath → paint.phase_2 →
closeout.punch_final_clean.

Nominal working-day sum on the critical path ≈ **43 wd** on-site (before
lags/buffers/exterior siding parallelization). Add pre-construction offset
(15 wd back-schedule for permits/selections, 30 cd TDEC) and this reads
as a **~11-week on-site window** — consistent with the 1,287 labor-hour
budget at typical 2-crew average.

## Warnings & assumptions

See `task_graph.json` — 16 `warnings[]` entries (Rule 4H skip, Rule 4Q
truss skip, plumbing hard-floor override, row-26 negative, Rule 4V two-
bucket, window schedule authority, brick drop, closet package out,
interior door verification, roof tie-in risk, Rule 4N cap, Rule 4C
bundled, Rule 4A permits, TDEC offset, elevator silent-omission,
CSV-vs-contract dollar reconciliation) and 9 `assumptions[]` entries.
