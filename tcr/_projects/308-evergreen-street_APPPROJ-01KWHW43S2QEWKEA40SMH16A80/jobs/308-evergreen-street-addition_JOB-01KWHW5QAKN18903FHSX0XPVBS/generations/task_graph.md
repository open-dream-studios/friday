---
generation_kind: task_graph_v2
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWHW43S2QEWKEA40SMH16A80/jobs/308-evergreen-street-addition_JOB-01KWHW5QAKN18903FHSX0XPVBS/manifest.json
  - _projects/308-evergreen-street_APPPROJ-01KWHW43S2QEWKEA40SMH16A80/jobs/308-evergreen-street-addition_JOB-01KWHW5QAKN18903FHSX0XPVBS/intelligence/manifest.json
  - _projects/308-evergreen-street_APPPROJ-01KWHW43S2QEWKEA40SMH16A80/jobs/308-evergreen-street-addition_JOB-01KWHW5QAKN18903FHSX0XPVBS/intelligence/facts.md
  - _projects/308-evergreen-street_APPPROJ-01KWHW43S2QEWKEA40SMH16A80/jobs/308-evergreen-street-addition_JOB-01KWHW5QAKN18903FHSX0XPVBS/intelligence/confirmed.md
  - _projects/308-evergreen-street_APPPROJ-01KWHW43S2QEWKEA40SMH16A80/jobs/308-evergreen-street-addition_JOB-01KWHW5QAKN18903FHSX0XPVBS/intelligence/applicable_rules.json
  - _projects/308-evergreen-street_APPPROJ-01KWHW43S2QEWKEA40SMH16A80/jobs/308-evergreen-street-addition_JOB-01KWHW5QAKN18903FHSX0XPVBS/intelligence/extracted/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KWHW43S2QEWKEA40SMH16A80/jobs/308-evergreen-street-addition_JOB-01KWHW5QAKN18903FHSX0XPVBS/intelligence/extracted/breakdown.md
  - _projects/308-evergreen-street_APPPROJ-01KWHW43S2QEWKEA40SMH16A80/jobs/308-evergreen-street-addition_JOB-01KWHW5QAKN18903FHSX0XPVBS/intelligence/extracted/plans.md
  - _schemas/task_graph.schema.md
last_verified_at: "2026-07-02T17:17:51.162Z"
rendered_by: server_a1/taskGraphMdRenderer
---

# Task graph

59 tasks across 11 phases and 27 components. Critical path = 8 tasks (starred ★ below).

## Phase 0 — Pre-construction (pre-construction)

### Permits + checkpoints

T1. **permit.building** — Pull building permit (walk-in) — Duration 1d / Trade pm / Crew 1 / Depends on ∅ / pre-construction offset 15wd, lead-up 2wd (rules: dev_rules:4A)
    Rule 4A: permit is 1-day walk-in `work` task with 15 working-day pre-construction offset. Not lead_time.
T2. **checkpoint.selections_finalized** — Selections finalized checkpoint — Milestone / Trade pm / Crew 1 / Depends on ∅ / pre-construction offset 15wd, lead-up 5wd (rules: dev_rules:4P)
    Rule 4P mandatory: selections_finalized locked 3 weeks (15 working days) before on-site start; anchors all finish-material procurement.
T3. **checkpoint.equipment_confirmed** — Equipment/appliance confirmed checkpoint (mini-split, vanity, exterior door, panel) — Milestone / Trade pm / Crew 1 / Depends on [object Object] / pre-construction offset 10wd, lead-up 3wd (rules: dev_rules:4P)
    Rule 4P: equipment_confirmed is SEPARATE from selections_finalized; gates HVAC equipment, vanity, exterior door, electrical panel orders (10-working-day offset).

### Septic + service verification

T4. **permit.tdec_septic** — TDEC septic inspection (existing septic — inspection only) — Duration 1d / Trade pm / Crew 1 / Depends on ∅ / pre-construction offset 30wd, lead-up 2wd (rules: job_types/addition/rules/tdec_septic_permit_offset)
    PM confirmed (round 1 q.septic_direction): keep existing septic, TDEC inspection only. Job-type rule tdec_septic_permit_offset requires 30 working-day pre-construction offset.
T5. **prep.amperage_check** — Verify existing main service supports new 100A subpanel — Duration 0.5d / Trade electrical / Crew 1 / Depends on ∅ / pre-construction offset 20wd, lead-up 1wd (rules: _company/rules/service_amperage_check)
    Scope assumes existing service supports new 100A subpanel; rule service_amperage_check requires verification BEFORE panel procurement + electrical rough.

## Phase 1 — Procurement + long-lead orders (pre-construction)

### Long-lead orders (3-task pattern)

T6. **procurement.windows.order** — Order windows (3× 36x60 DH + 1 transom) — Duration 1d / Trade pm / Crew 1 / Depends on [object Object] (rules: dev_rules:4R, editor_rules)
    Rule 4R 3-task pattern for stock windows (14-21 day lead per editor_rules).
T7. **procurement.windows.wait** — Windows lead time — Duration 0d / Trade pm / Depends on [object Object] (rules: dev_rules:4R)
    18 calendar-day wait (mid of 14-21 stock window lead).
T8. **procurement.windows.arrived** — Windows on site — Milestone / Trade pm / Depends on [object Object] (rules: dev_rules:4R)
    Arrival milestone gates windows.install.
T9. **procurement.subpanel.order** — Order 100A subpanel — Duration 1d / Trade pm / Crew 1 / Depends on [object Object], [object Object] (rules: _company/rules/service_amperage_check, dev_rules:4R)
    Panel order gated on amperage_check pass per service_amperage_check rule.
T10. **procurement.subpanel.wait** — Subpanel lead time — Duration 0d / Trade pm / Depends on [object Object] (rules: dev_rules:4R)
    10 calendar-day mid of 7-14 day subpanel lead per editor_rules.
T11. **procurement.subpanel.arrived** — Subpanel on site — Milestone / Trade pm / Depends on [object Object]
T12. **procurement.lvl_beam.order** — Order 3-ply 14" LVL beam (~15'-6") — Duration 1d / Trade pm / Crew 1 / Depends on [object Object] (rules: dev_rules:4R, editor_rules)
    3-task pattern; LVL 7-14 day standard lead.
T13. **procurement.lvl_beam.wait** — LVL beam lead time — Duration 0d / Trade pm / Depends on [object Object]
T14. **procurement.lvl_beam.arrived** — LVL beam on site — Milestone / Trade pm / Depends on [object Object]
T15. **procurement.minisplit.order** — Order ductless mini-split unit ($2,500) — Duration 1d / Trade pm / Crew 1 / Depends on [object Object] (rules: dev_rules:4R)
    Mini-split 7-14 day lead per editor_rules; gates on equipment_confirmed.
T16. **procurement.minisplit.wait** — Mini-split lead time — Duration 0d / Trade pm / Depends on [object Object]
T17. **procurement.minisplit.arrived** — Mini-split unit on site — Milestone / Trade pm / Depends on [object Object]

### Stock orders (collapsed)

T18. **procurement.stock_finishes** — Stock finish materials (LVT, tile, vanity, fixtures, interior + exterior doors) — Duration 1d / Trade pm / Crew 1 / Depends on [object Object] (rules: dev_rules:4R)
    Rule 4R exception: stock 7-day items collapse to 1-day order 1 week before install. PM confirmed 4 interior doors (2 pre-hung + 2 pocket), stock exterior door, no closet system, no tankless.

## Phase 2 — Site prep + customer early items

### Customer early items (Day 1)

T19. **early.hall_bath_shower** — Hall bath acrylic shower swap (customer early item — Day 1) — Duration 1d / Trade plumbing / Crew 2 / Depends on [object Object] (rules: dev_rules:4V)
    PM confirmed (round 1 q.customer_early_items): customer needs working shower during construction. Two-bucket pattern per Rule 4V: early item runs Day 1 off critical path; window-infill/repaint work stays in interior_finish as separate hall bath retrofit component. Reuses existing valve/trim (round 1 q.hall_bath_valve_reuse_confirmed) — no plumbing rough needed.

### Site mobilization + utility relocations

T20. **site.mobilization** — Site mobilization + staging — Duration 1d / Trade general / Crew 2 / Depends on [object Object]
    Standard mobilization: dump trailer, backhoe delivery, material staging.
T21. **site.relocate_hvac_disconnect** — Relocate existing heat pump + electrical disconnect (BEFORE demo) — Duration 1d / Trade electrical / Crew 2 / Depends on [object Object] (rules: dev_rules:4K)
    Rule 4K: heat pump + electrical disconnect relocations happen in site_prep phase, BEFORE demo — not in demo phase.

## Phase 3 — Demolition

### Selective demolition

T22. **demo.selective** — Selective demo (walkway saw-cut, railroad ties, site obstructions, hall bath tub/shower) — Duration 2d / Trade demo / Crew 3 / Depends on [object Object]
    Selective demo per scope: saw-cut walkway, remove railroad ties + obstructions, hall bath tub/shower demo. Heat pump + disconnect already relocated in site_prep.

## Phase 4 — Foundation + structural

### Foundation (monolithic)

T23. **foundation.excavation** — Excavate for footings + slab — Duration 2d / Trade excavation / Crew 2 / Depends on [object Object]
T24. ★ **foundation.monolithic_pour** — Set forms + rebar/mesh + monolithic pour (12x12 footings + 4" slab + vapor barrier) — Duration 2d / Trade concrete / Crew 4 / Depends on [object Object] (rules: dev_rules:4B)
    Rule 4B monolithic default: no CMU or full-height wall (scope explicit). Footings + slab poured same day.
T25. **inspect.foundation** — Foundation inspection — Duration 0.5d / Trade inspector / Crew 1 / Depends on [object Object], lead-up 1wd
T26. **foundation.slab_cure** — Slab cure (calendar wait) — Duration 0d / Trade concrete / Depends on [object Object]

### LVL beam + load-bearing wall open

T27. ★ **structural.lvl_install** — Install 3-ply 14" LVL beam + temporary shoring, open load-bearing wall — Duration 2d / Trade framing / Crew 3 / Depends on [object Object], [object Object]
    LVL beam opens existing load-bearing wall per scope; requires shoring and gates upper floor framing.

## Phase 5 — Framing

### Floor + walls framing

T28. **framing.floor_system** — Frame floor system + subfloor (glue + fasten) — Duration 2d / Trade framing / Crew 3 / Depends on [object Object]
T29. ★ **framing.walls** — Frame basement + exterior + interior walls (2x4 @ 16" OC) + elevator shaft — Duration 3d / Trade framing / Crew 3 / Depends on [object Object]
    Includes 4x4 future elevator shaft framing (framing only, no elevator system).

### Roof framing (stick-framed)

T30. ★ **framing.roof** — Stick-frame gable roof rafters (3/12 tie into existing 6/12) — Duration 3d / Trade framing / Crew 3 / Depends on [object Object] (rules: job_types/addition/beliefs/stick_frame_default_for_small_additions, dev_rules:4Q)
    PM confirmed (round 1 q.roof_framing_method): stick-framed rafters, lumber arrives day-of with framing crew. Belief stick_frame_default confirmed. Per Rule 4Q, NO procurement.trusses task.

### Tie-in discovery + retrofit framing

T31. **framing.tie_in_discovery** — Tie-in discovery (roof/framing/MEP existing conditions) — Duration 1d / Trade framing / Crew 2 / Depends on [object Object] (rules: job_types/addition/rules/retrofit_tie_in_discovery)
    Rule retrofit_tie_in_discovery: addition ties into existing at roof (3/12 into 6/12), primary bedroom framing, hall bathroom — SS with tie-in framing.
T32. **framing.retrofit_tie_in** — Retrofit framing at existing tie-ins (primary bedroom + hall bath window infill) — Duration 1d / Trade framing / Crew 2 / Depends on [object Object], [object Object] (rules: job_types/addition/rules/retrofit_tie_in_discovery)
    Framing modifications for primary bedroom + hall bath window infill.
T33. **inspect.framing** — Framing inspection — Duration 0.5d / Trade inspector / Crew 1 / Depends on [object Object], lead-up 1wd

## Phase 6 — Shell (roofing, windows, siding)

### Roofing

T34. **roofing.underlayment** — Roof sheathing + synthetic underlayment + drip edge + temp dry-in — Duration 2d / Trade roofing / Crew 3 / Depends on [object Object]
T35. **roofing.shingles** — Architectural shingles + flashing + ridge vent + fascia + soffit + gutters — Duration 3d / Trade roofing / Crew 3 / Depends on [object Object] (rules: _company/beliefs/roof_and_siding_same_crew)
    Same crew does roof then siding per TCR default; serial render.

### Windows + exterior door

T36. **windows.install** — Install 4 windows (3× 36x60 + 1 transom) + 1 exterior door — Duration 2d / Trade windows_doors / Crew 2 / Depends on [object Object], [object Object], [object Object] / Can overlap with roofing.shingles (rules: dev_rules:4J)
    Rule 4J: windows install runs immediately after roof framing, parallel with roofing underlayment. Exterior door PM confirmed stock (round 1 q.exterior_door_type).

### Siding + exterior finish

T37. **siding.install** — Sheathing + WRB + vinyl siding (match existing) + sealed penetrations — Duration 4d / Trade siding / Crew 3 / Depends on [object Object], [object Object], [object Object] (rules: job_types/addition/rules/siding_starts_at_underlayment, _company/beliefs/roof_and_siding_same_crew)
    Rule siding_starts_at_underlayment: siding may start once underlayment + windows in; same-crew belief keeps it after shingles.
T38. **milestone.dried_in** — Dried-in milestone — Milestone / Trade pm / Depends on [object Object], [object Object]

## Phase 7 — MEP rough + bundled inspection

### Plumbing rough

T39. ★ **plumbing.rough** — Plumbing rough (supply/waste/vent, master bath, W/D relocation, vent stacks + WH vent extension) — Duration 4d / Trade plumbing / Crew 2 / Depends on [object Object], [object Object] (rules: _company/rules/_examples/plumbing_rough_min_duration, dev_rules:4I, dev_rules:4G)
    4d floor per plumbing_rough_min_duration (master bath + W/D relocation + multiple branches). Gated on underlayment + windows, NOT dried-in (Rule 4I). Mini-split → plumbing FIRST per Rule 4G. WH vent extension included; existing WH stays per PM confirmation (round 1 q.tankless_option_elected) — no tank set task per Rule 4H.

### Electrical rough

T40. ★ **electrical.rough** — Electrical rough (100A subpanel, ~12 recessed, outlets, elevator 120V/30A circuit, switch relocation) — Duration 4d / Trade electrical / Crew 2 / Depends on [object Object], [object Object] (rules: dev_rules:4G, _company/rules/service_amperage_check)
    Rule 4G mini-split order: plumbing → electrical → mini-split. Panel install gated on amperage_check pass + subpanel arrived.

### HVAC rough (mini-split lineset)

T41. **hvac.rough_minisplit_lineset** — HVAC rough — mini-split lineset + relocate existing HVAC components — Duration 2d / Trade hvac / Crew 2 / Depends on [object Object] (rules: dev_rules:4G)
    Rule 4G: mini-split LAST in MEP rough order (plumbing → electrical → mini-split).

### Bundled rough inspection + punch buffer

T42. **inspect.rough_bundled** — Bundled rough inspection (framing + plumbing + electrical + HVAC) — Duration 1d / Trade inspector / Crew 1 / Depends on [object Object], [object Object], lead-up 1wd (rules: dev_rules:4C)
    Rule 4C: single inspector, single day, all trades bundled.
T43. **punch.rough_buffer** — Rough inspection punch buffer (2-day) — Duration 2d / Trade general / Crew 2 / Depends on [object Object] (rules: dev_rules:4D)
    Rule 4D: 2-day punch buffer after rough inspection.

## Phase 8 — Insulation, drywall, paint phase 1

### Insulation + drywall

T44. **insulation.install** — Insulation (R13 walls, R30 attic/roof, R30 floor) + air sealing — Duration 2d / Trade insulation / Crew 2 / Depends on [object Object]
T45. **inspect.insulation** — Insulation inspection — Duration 0.5d / Trade inspector / Crew 1 / Depends on [object Object], lead-up 1wd
T46. ★ **drywall.hang_finish** — Drywall hang + tape + Level 3 finish (addition + primary bedroom + basement storage + hall bath retrofit) — Duration 5d / Trade drywall / Crew 3 / Depends on [object Object] (rules: _company/beliefs/drywall_soft_schedule)
    Belief drywall_soft_schedule: soft-start behind inspect.insulation; consolidates across addition + primary bedroom + basement + hall bath retrofit.

### Paint phase 1 (primer + ceilings)

T47. **paint.phase_1** — Paint phase 1 — primer + ceilings — Duration 2d / Trade paint / Crew 2 / Depends on [object Object] (rules: dev_rules:4E, dev_rules:4F)
    Rule 4E/4F: paint is ALWAYS two phases. Phase 1 = primer + ceilings before finish trades.

## Phase 9 — Interior finish

### Tile + flooring

T48. **tile.master_bath** — Master bath tile — waterproofing + 7x4 custom shower walls + mosaic floor + niche + bench — Duration 4d / Trade tile / Crew 2 / Depends on [object Object]
T49. **flooring.lvt** — LVT flooring throughout (addition + primary bedroom) — Duration 3d / Trade flooring / Crew 2 / Depends on [object Object] / Can overlap with tile.master_bath (rules: dev_rules:4L)
    Rule 4L: flooring → trim (not paint → trim). LVT $3/sqft, stock.

### Trim + interior doors

T50. **trim.interior** — Interior trim (5-1/4" baseboard, 2-1/4" casing, 4 interior doors: 2 pre-hung + 2 pocket, caulk/fill/sand) — Duration 4d / Trade trim_carpentry / Crew 2 / Depends on [object Object] (rules: dev_rules:4L)
    Rule 4L: flooring → trim. PM confirmed (round 1 q.fourth_interior_door_type): 2 pre-hung + 2 pocket. Note: pocket door FRAMES are installed pre-drywall in framing.walls; casings/leaves install here.

### MEP finish (electrical trim, plumbing finish, mini-split install)

T51. **electrical.trim** — Electrical trim (~12 recessed lights, 2 vanity lights, bath fan/light, dimmers, devices, GFCI/AFCI) — Duration 2d / Trade electrical / Crew 2 / Depends on [object Object] / Can overlap with flooring.lvt (rules: dev_rules:4L)
    Rule 4L: electrical finish precedes paint_2 (not paint_1).
T52. **hvac.minisplit_install** — Mini-split head install + startup + commissioning — Duration 1d / Trade hvac / Crew 2 / Depends on [object Object], [object Object] (rules: dev_rules:4N)
    Rule 4N: stagger HVAC after electrical trim to avoid 3+ concurrent trades.
T53. **plumbing.finish** — Plumbing finish (2 lav sup/drain, toilet, custom shower dual-valve trim, 72" double vanity + 2 faucets, exhaust fan) — Duration 2d / Trade plumbing / Crew 2 / Depends on [object Object], [object Object] (rules: dev_rules:4H)
    Rule 4H: NO plumbing.tank_set — PM confirmed tankless not elected (round 1 q.tankless_option_elected); existing WH stays.

### Hall bath retrofit (window infill + repaint)

T54. **hall_bath.retrofit_finish** — Hall bath retrofit (window infill drywall/finish, PVC trim, patch + repaint) — Duration 2d / Trade general / Crew 2 / Depends on [object Object] (rules: dev_rules:4V)
    Rule 4V two-bucket: hall bath window-infill/repaint retrofit lives here, SEPARATE from Day-1 early shower swap in site_prep.

### Paint phase 2 (wall finish)

T55. ★ **paint.phase_2** — Paint phase 2 — wall finish coats (2 coats) after all finish trades — Duration 3d / Trade paint / Crew 2 / Depends on [object Object], [object Object], [object Object], [object Object], [object Object], [object Object] (rules: dev_rules:4E, dev_rules:4F)
    Rule 4E/4F: paint_2 predecessors include EVERY finish trade.

## Phase 10 — Closeout

### Punch, clean, final inspection

T56. **punch.list** — Punch list walk + fixes — Duration 3d / Trade general / Crew 2 / Depends on [object Object]
T57. **cleanup.final** — Final cleaning + debris removal — Duration 1d / Trade cleanup / Crew 2 / Depends on [object Object]
T58. **inspect.final** — Final inspection (building) — Duration 0.5d / Trade inspector / Crew 1 / Depends on [object Object], lead-up 1wd
T59. **milestone.substantial_completion** — Substantial completion — Milestone / Trade pm / Depends on [object Object]

## Critical path (8 tasks, ★ above)

T24 foundation.monolithic_pour → T27 structural.lvl_install → T29 framing.walls → T30 framing.roof → T39 plumbing.rough → T40 electrical.rough → T46 drywall.hang_finish → T55 paint.phase_2

Nominal on-site working-day sum on the critical path ≈ **26 wd** (before lag/buffer/parallelization adjustments the CPM engine applies).

## Warnings & assumptions

See `task_graph.json` — **14** warnings entries, **15** assumptions.

_This file is auto-rendered from `task_graph.json` by server_a1._
_Edit the JSON, not this file — regenerating will overwrite any changes here._
