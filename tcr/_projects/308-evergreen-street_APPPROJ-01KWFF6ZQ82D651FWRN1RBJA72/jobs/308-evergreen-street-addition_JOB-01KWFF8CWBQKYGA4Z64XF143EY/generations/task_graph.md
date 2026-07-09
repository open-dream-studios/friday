---
generation_kind: task_graph_v2
last_verified_at: "2026-07-01T18:47:46.357Z"
rendered_by: server_a1/taskGraphMdRenderer
---

# Task graph

61 tasks across 4 phases and 15 components. Critical path = 11 tasks (starred ★ below).

## Phase 0 — Pre-construction (pre-construction)

### Permits + checkpoints

T1. **permit.building** — Building permit application + issuance — Duration 1d / Trade pm / Crew 1 / Depends on ∅ / pre-construction offset 15wd, lead-up 2wd (rules: dev_rules.4A)
    Permit is 1d work task with 15-working-day pre-con offset per dev_rules §4A (NOT kind:lead_time).
T2. **prep.tdec_septic_inspection** — TDEC septic inspection (capacity confirmation only) — Duration 1d / Trade pm / Crew 1 / Depends on ∅ / pre-construction offset 15wd, lead-up 2wd (rules: job_types/addition/rules/tdec_septic_permit_offset.md, confirmed.md:q.sewer_septic_direction)
    Existing septic stays per PM round 1; TDEC inspection only, no install. tdec_septic_permit_offset does NOT fire for install work — inspection-only pre-con task.
T3. **prep.amperage_check** — Existing service amperage check (before panel order) — Duration 0.5d / Trade electrical / Crew 1 / Depends on ∅ / pre-construction offset 15wd, lead-up 2wd (rules: _company/rules/service_amperage_check.md)
    Adding 100A subpanel + mini-split — service_amperage_check rule requires prep.amperage_check in pre-con before panel order + rough.
T4. **checkpoint.selections_finalized** — Selections finalized (finishes, tile, LVT, vanity, fixtures) — Milestone / Trade pm / Depends on ∅ / pre-construction offset 15wd, lead-up 5wd (rules: dev_rules.4P, _company/rules/editor_rules.md)
    Rule 4P — selections_finalized checkpoint mandatory in pre_construction, 15-day offset, 5-day lead-up. Downstream consumers: tile order, vanity, LVT, doors.
T5. **checkpoint.equipment_confirmed** — Equipment/spec sheets confirmed (mini-split, subpanel, exterior door, vanity) — Milestone / Trade pm / Depends on ∅ / pre-construction offset 10wd, lead-up 5wd (rules: dev_rules.4P)
    Rule 4P — equipment_confirmed is a SEPARATE checkpoint from selections_finalized, 10-day offset. Downstream: mini-split order, subpanel order, exterior door order.

## Phase 1 — Procurement + permits (pre-construction)

### Long-lead procurement

T6. **procurement.windows.order** — Order (2) new windows (3'×3' D.H. + 3'×1' transom) — Duration 0.5d / Trade pm / Crew 1 / Depends on [object Object] (rules: dev_rules.4R, confirmed.md:q.window_count_and_relocation)
    Rule 4R 3-task procurement pattern. PM confirmed 2 new windows (relocate 2 existing separately).
T7. **procurement.windows.wait** — Window lead-time wait (stock ~14–21 cal-d) — Duration 0d / Trade general / Depends on [object Object] (rules: dev_rules.4R, _company/rules/editor_rules.md)
    Stock window lead 14–21 cal-d per editor_rules; mid-range 18d.
T8. **procurement.windows.arrived** — Windows on-site — Milestone / Trade general / Depends on [object Object] (rules: dev_rules.4R)
    Completes 3-task procurement chain; gates windows.install.
T9. **procurement.lvl.order** — Order 3-ply 14" LVL (~15'-6" span) — Duration 0.5d / Trade pm / Crew 1 / Depends on ∅ (rules: dev_rules.4R)
    LVL is long-lead; 3-task pattern.
T10. **procurement.lvl.wait** — LVL lead-time wait (7–14 cal-d) — Duration 0d / Trade general / Depends on [object Object] (rules: dev_rules.4R)
    Editor_rules LVL supplier ~7–14 cal-d.
T11. **procurement.lvl.arrived** — LVL on-site — Milestone / Trade general / Depends on [object Object] (rules: dev_rules.4R)
    Gates structural.lvl_install.
T12. **procurement.mini_split.order** — Order ductless mini-split (~$2,500) — Duration 0.5d / Trade pm / Crew 1 / Depends on [object Object] (rules: dev_rules.4R)
    3-task pattern; equipment_confirmed gates mini-split spec sheet.
T13. **procurement.mini_split.wait** — Mini-split lead-time wait (7–14 cal-d) — Duration 0d / Trade general / Depends on [object Object] (rules: dev_rules.4R)
    Editor_rules mini-split 7–14 cal-d.
T14. **procurement.mini_split.arrived** — Mini-split on-site — Milestone / Trade general / Depends on [object Object] (rules: dev_rules.4R)
    Gates hvac.mini_split_install.
T15. **procurement.subpanel.order** — Order 100A subpanel — Duration 0.5d / Trade pm / Crew 1 / Depends on [object Object], [object Object] (rules: dev_rules.4R, _company/rules/service_amperage_check.md)
    3-task pattern; amperage check must precede panel order per service_amperage_check.
T16. **procurement.subpanel.wait** — Subpanel lead-time wait (7–14 cal-d) — Duration 0d / Trade general / Depends on [object Object] (rules: dev_rules.4R)
    Editor_rules subpanel 7–14 cal-d.
T17. **procurement.subpanel.arrived** — Subpanel on-site — Milestone / Trade general / Depends on [object Object] (rules: dev_rules.4R)
    Gates electrical.rough.
T18. **procurement.tile.order** — Order master bath tile (wall + mosaic floor) + waterproofing — Duration 0.5d / Trade pm / Crew 1 / Depends on [object Object] (rules: dev_rules.4R)
    Tile can be 14–21 cal-d if custom, 7 if stock; treat as long-lead.
T19. **procurement.tile.wait** — Tile lead-time wait (14 cal-d) — Duration 0d / Trade general / Depends on [object Object] (rules: dev_rules.4R)
    Editor_rules tile lead.
T20. **procurement.tile.arrived** — Tile on-site — Milestone / Trade general / Depends on [object Object] (rules: dev_rules.4R)
    Gates master_bath.tile_shower.
T21. **procurement.doors.order** — Order 3× pre-hung panel doors + 1× pocket door frame + 1 exterior door — Duration 0.5d / Trade pm / Crew 1 / Depends on [object Object], [object Object] (rules: dev_rules.4R, confirmed.md:q.interior_doors_pocket_vs_panel)
    PM confirmed 3 panel + 1 pocket; standard 7–14 cal-d. Pocket-door frame needed during framing.
T22. **procurement.doors.wait** — Door lead-time wait (10 cal-d) — Duration 0d / Trade general / Depends on [object Object] (rules: dev_rules.4R)
    Editor_rules doors 7–14 cal-d.
T23. **procurement.doors.arrived** — Doors on-site (pocket frame gates framing) — Milestone / Trade general / Depends on [object Object] (rules: dev_rules.4R, confirmed.md:q.interior_doors_pocket_vs_panel)
    Pocket door frame installed during framing per PM answer; hard gate.

## Phase 2 — On-site execution

### Customer early items

T24. **early.acrylic_shower_swap** — Hall bath acrylic shower swap (Day 1, customer-early) — Duration 1d / Trade plumbing / Crew 2 / Depends on ∅ (rules: dev_rules.4V, confirmed.md:q.hall_bath_acrylic_shower_timing)
    Rule 4V — customer-requested early item; Day 1, off critical path, SEPARATE bucket from mid-job hall bath retrofit. PM confirmed customer needs working shower.

### Prep work before demo

T25. **prep.relocate_heat_pump** — Relocate existing heat pump + electrical disconnect (before demo) — Duration 1d / Trade hvac / Crew 2 / Depends on ∅ (rules: job_types/addition/rules/addition_rules.md)
    dev_rules §4K: heat pump relocation in prep_work_before_demo, ≥3 working days before demo.

### Site prep + demo

T26. ★ **site.demo** — Selective demo — sawcut walkway, remove railroad ties, clear site — Duration 2d / Trade demo / Crew 3 / Depends on [object Object], [object Object] (rules: _company/rules/editor_rules.md)
    Site work per breakdown row 2 (56 labor hrs) — 2 crew-days × 3 crew. Follows heat pump relocation by 3d per §4K.

### Excavation + foundation

T27. **foundation.excavate** — Excavate for footings + slab — Duration 2d / Trade excavation / Crew 2 / Depends on [object Object]
    Row 3 breakdown 78 hrs across excavate + foundation; ~2d excavate.
T28. ★ **foundation.footings_slab_pour** — Monolithic pour — 12×12 perimeter footings + 4" slab (gravel/VB/rebar) — Duration 2d / Trade concrete / Crew 3 / Depends on [object Object] (rules: dev_rules.4B)
    Rule 4B — monolithic foundation default; footings + slab same pour (scope confirms slab-on-grade, no CMU/full-height wall).
T29. **inspect.foundation** — Foundation inspection (pre-pour footing / post-slab) — Duration 0.5d / Trade inspector / Crew 1 / Depends on [object Object], lead-up 1wd (rules: _company/rules/editor_rules.md)
    TN inspection prior to pour; SS overlap coordinates with pour day.

### Structural / LVL

T30. ★ **structural.lvl_install** — LVL beam install + temporary shoring (open existing bearing wall) — Duration 2d / Trade framing / Crew 3 / Depends on [object Object], [object Object]
    Row 4 breakdown 60 hrs; LVL 3-ply 14" @ ~15'-6" per scope. 3-day lag after slab pour for cure.

### Framing

T31. **framing.floor_system** — Frame floor system + subfloor (glued & fastened) — Duration 2d / Trade framing / Crew 3 / Depends on [object Object]
    Row 5 breakdown 146 hrs total framing; floor system first sub-phase.
T32. ★ **framing.walls** — Frame exterior + interior walls (both levels), incl. elevator shaft + pocket door frame — Duration 5d / Trade framing / Crew 3 / Depends on [object Object], [object Object] (rules: job_types/addition/beliefs/stick_frame_default_for_small_additions.md, confirmed.md:q.interior_doors_pocket_vs_panel)
    Stick-frame default (295 sqft/level, 10ft span). Pocket door frame rough-in during framing per PM answer.
T33. **framing.tie_in_discovery** — Retrofit tie-in discovery + framing (chimney, 3/12↔6/12, window/door relocation) — Duration 2d / Trade framing / Crew 3 / Depends on [object Object] (rules: job_types/addition/rules/retrofit_tie_in_discovery.md)
    Rule fires: existing chimney inside new roof envelope + 3/12↔6/12 tie-in + 2 relocated windows + relocated door. SS+2 overlap with walls.
T34. ★ **framing.roof** — Frame new gable roof (stick, 3/12) + tie-in to existing 6/12 — Duration 3d / Trade framing / Crew 3 / Depends on [object Object], [object Object] (rules: dev_rules.4Q, job_types/addition/beliefs/stick_frame_default_for_small_additions.md)
    Rule 4Q — stick-frame default (no procurement.trusses). Row 6 breakdown 96 hrs total roof; framing ~3d of it.

### Roof + exterior

T35. **roofing.sheathing** — Roof sheathing + WRB on walls — Duration 1d / Trade framing / Crew 3 / Depends on [object Object]
    Sheathing bridges framing → roofing / siding.
T36. ★ **roofing.underlayment** — Synthetic underlayment + drip edge + temporary dry-in — Duration 1d / Trade roofing / Crew 2 / Depends on [object Object] (rules: dev_rules.4I, job_types/addition/rules/siding_starts_at_underlayment.md)
    Rule 4I/4J: windows install + MEPs gated on roofing.underlayment (not milestone.dried_in). siding_starts_at_underlayment: siding can start here too.
T37. **windows.install** — Install 2 new windows + relocate 2 existing + install exterior door — Duration 2d / Trade windows_doors / Crew 2 / Depends on [object Object], [object Object] (rules: dev_rules.4I, confirmed.md:q.window_count_and_relocation)
    Rule 4I — windows.install after roofing.underlayment. +1d added for window relocation labor per PM.
T38. **roofing.shingles** — Architectural shingles + flashing + chimney cricket + ridge vent — Duration 2d / Trade roofing / Crew 2 / Depends on [object Object] / Can overlap with siding.install, exterior.trim_gutters (rules: _company/beliefs/roof_and_siding_same_crew.md)
    Same 2–3 person crew handles roof + siding; serialize by default. Multi-valley + chimney per plans.
T39. **siding.install** — Vinyl lap siding — ALL exterior (no brick veneer) — Duration 3d / Trade siding / Crew 2 / Depends on [object Object], [object Object] / Can overlap with exterior.trim_gutters (rules: confirmed.md:q.brick_veneer_scope, job_types/addition/rules/siding_starts_at_underlayment.md, _company/beliefs/roof_and_siding_same_crew.md)
    PM confirmed all vinyl lap siding (brick veneer OUT). Same crew as roofing → serialize.
T40. **exterior.trim_gutters** — Fascia, vinyl soffit, seamless gutters — Duration 1d / Trade siding / Crew 2 / Depends on [object Object]
    Row 7 breakdown 72 hrs total exterior — trim/gutter tail overlaps with siding tail.
T41. **milestone.dried_in** — Dried-in milestone (roof + windows + WRB complete) — Milestone / Trade pm / Depends on [object Object], [object Object]
    Informational milestone; MEPs gated on underlayment+windows per §4I not this.

### MEP rough-in

T42. ★ **plumbing.rough** — Plumbing rough-in (supply/waste/vent, master bath, W/D relocate, gas WH vent ext.) — Duration 4d / Trade plumbing / Crew 2 / Depends on [object Object], [object Object] (rules: dev_rules.4G, confirmed.md:q.plumbing_rough_labor_floor, confirmed.md:q.tankless_water_heater_election)
    Rule 4G mini-split HVAC → MEP order plumbing → electrical → mini-split. Repriced to hard floor: 4d × 2 crew = 64 hrs per plumbing_rough_min_duration. NO tank_set (existing gas WH stays per rule 4H; only vent extension).
T43. **electrical.rough** — Electrical rough — subpanel install, receptacles, lighting, 30A elevator circuit — Duration 3d / Trade electrical / Crew 2 / Depends on [object Object], [object Object] / Can overlap with plumbing.rough (rules: dev_rules.4G, dev_rules.4N)
    §4G: mini-split HVAC → plumbing → electrical → mini-split. §4N: stagger by 2 days SS to keep ≤2 trades concurrent.
T44. **hvac.mini_split_rough** — Mini-split rough (line-set, condensate) — Duration 0.5d / Trade hvac / Crew 1 / Depends on [object Object] (rules: dev_rules.4G)
    §4G mini-split rough = 0.5d/1 person, LAST in MEP rough sequence.
T45. ★ **inspect.rough_bundled** — Bundled rough inspection (framing + plumbing + electrical + HVAC) — Duration 1d / Trade inspector / Crew 1 / Depends on [object Object], [object Object], [object Object], [object Object], lead-up 1wd (rules: dev_rules.4C)
    Rule 4C — rough inspections BUNDLED (one inspector, one day, all trades).
T46. **punch.rough_buffer** — Post-rough punch buffer — Duration 2d / Trade general / Crew 1 / Depends on [object Object] (rules: dev_rules.4D)
    Rule 4D — 2-day punch buffer after rough inspection.

### Insulation + drywall

T47. **insulation.install** — Insulation — R13 walls, R30 attic, R30 floor + air seal — Duration 2d / Trade insulation / Crew 2 / Depends on [object Object] (rules: _company/rules/editor_rules.md)
    Row 12 breakdown 44 hrs. Material staged same day as insulation inspection per editor rules.
T48. **inspect.insulation** — Insulation inspection — Duration 0.5d / Trade inspector / Crew 1 / Depends on [object Object], lead-up 1wd (rules: _company/beliefs/drywall_soft_schedule.md)
    Drywall soft-schedule: drywall crew committed only after insulation inspection is calendared.
T49. ★ **drywall.hang_finish** — Drywall hang + 3-coat compound + sand to L3 (addition + primary bedroom + hall bath) — Duration 6d / Trade drywall / Crew 3 / Depends on [object Object] (rules: _company/beliefs/drywall_soft_schedule.md)
    Row 13 breakdown 159 hrs; ~6d × 3 crew. L3 finish + primer prep per scope.

### Interior finishes

T50. **paint.phase_1** — Paint phase 1 — primer + ceilings — Duration 2d / Trade paint / Crew 2 / Depends on [object Object] (rules: dev_rules.4E)
    Rule 4E/4F — paint ALWAYS two phases. Phase 1 = primer + ceiling after drywall.
T51. **flooring.lvt** — LVT flooring throughout ($3/sqft) — Duration 2d / Trade flooring / Crew 2 / Depends on [object Object], [object Object] (rules: dev_rules.4L)
    Rule 4L — flooring precedes trim (NOT paint→trim).
T52. **trim.install** — Trim carpentry — 5-1/4" base + 2-1/4" casing + hang doors (3 panel + 1 pocket) — Duration 3d / Trade trim_carpentry / Crew 2 / Depends on [object Object], [object Object] (rules: dev_rules.4L, confirmed.md:q.interior_doors_pocket_vs_panel)
    Rule 4L — flooring → trim. Row 14 162 hrs across trim + paint2.
T53. **electrical.finish** — Electrical finish (devices, recessed lights ~12, vanity lights, fan/light, GFCI/AFCI) — Duration 2d / Trade electrical / Crew 2 / Depends on [object Object] (rules: dev_rules.4L)
    Rule 4L — electrical finish before paint_1... wait, actually 4L says electrical finish → paint_1. Here electrical finish runs after trim but BEFORE paint_2 so paint_2 covers device cutouts.
T54. **plumbing.finish** — Plumbing finish (72" double vanity, 2 faucets, commode, shower valve trim) — Duration 2d / Trade plumbing / Crew 2 / Depends on [object Object], [object Object] / Can overlap with electrical.finish
    Vanity, faucets, commode, shower trim after tile + trim.
T55. **hvac.mini_split_install** — Mini-split install (head + condenser set + commissioning) — Duration 1d / Trade hvac / Crew 1 / Depends on [object Object], [object Object] (rules: dev_rules.4G)
    §4G mini-split install = 1d/1 person, after electrical finish.
T56. ★ **paint.phase_2** — Paint phase 2 — wall finish coats (2 coats) + trim touch-up — Duration 3d / Trade paint / Crew 2 / Depends on [object Object], [object Object], [object Object], [object Object], [object Object], [object Object] (rules: dev_rules.4E, dev_rules.4F)
    Rule 4E/4F — paint_2 predecessors MUST include EVERY finish trade (trim, elec finish, plumbing finish, hvac install, tile, hall bath finish).

### Master bath

T57. **master_bath.tile_shower** — Master bath custom tile shower (waterproof, wall tile, mosaic floor, niche, bench) — Duration 4d / Trade tile / Crew 2 / Depends on [object Object], [object Object]
    Row 15 breakdown 88 hrs. Tile after paint_1 so ceilings/primer set; before flooring.

### Hall bath retrofit finish

T58. **hall_bath.finish** — Hall bath finish — remove window/infill, insulate, drywall patch, PVC trim, repaint — Duration 2d / Trade general / Crew 2 / Depends on [object Object] / Can overlap with master_bath.tile_shower, flooring.lvt (rules: dev_rules.4V)
    Rule 4V two-bucket: acrylic swap ran Day 1 (early), remainder mid-job here. Reuses valve/trim installed on Day 1.

## Phase 3 — Closeout

### Closeout + punch

T59. **inspect.final** — Final inspection (building + electrical + plumbing + HVAC) — Duration 1d / Trade inspector / Crew 1 / Depends on [object Object], lead-up 1wd (rules: _company/rules/editor_rules.md)
    TN final inspections bundled per editor rules.
T60. ★ **punch.closeout** — Punch list + final cleaning + customer walkthrough — Duration 3d / Trade general / Crew 2 / Depends on [object Object] (rules: job_types/addition/rules/addition_rules.md)
    Addition playbook — Will's walkthrough + final clean + punch.
T61. **milestone.substantial_completion** — Substantial completion — Milestone / Trade pm / Depends on [object Object]
    Final marker; balance due per scope terms.

## Critical path (11 tasks, ★ above)

T26 site.demo → T28 foundation.footings_slab_pour → T30 structural.lvl_install → T32 framing.walls → T34 framing.roof → T36 roofing.underlayment → T42 plumbing.rough → T45 inspect.rough_bundled → T49 drywall.hang_finish → T56 paint.phase_2 → T60 punch.closeout

Nominal on-site working-day sum on the critical path ≈ **32 wd** (before lag/buffer/parallelization adjustments the CPM engine applies).

## Warnings & assumptions

See `task_graph.json` — **10** warnings entries, **15** assumptions.

_This file is auto-rendered from `task_graph.json` by server_a1._
_Edit the JSON, not this file — regenerating will overwrite any changes here._
