---
generation_kind: task_graph_v1
depends_on:
  - _schemas/task_graph.schema.md
  - _company/rules/dev_rules.md
  - _company/rules/editor_rules.md
  - _company/rules/pep_rules.md
  - _company/beliefs/_examples/stick_frame_default_for_small_additions.md
  - _company/knowledge/308_evergreen_wills_audit_transcript.md
  - _company/knowledge/_examples/wills_voice.md
  - job_types/addition/rules/addition_rules.md
  - job_types/addition/rules/tdec_septic_permit_offset.md
  - job_types/addition/beliefs/stick_frame_default_for_small_additions.md
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/manifest.json
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/inputs/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/inputs/files/308_scope.pdf.txt
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/inputs/files/308_Evergreen_Addition.xlsx - Summary (1).csv.txt
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/beliefs/initial.md
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/beliefs/interview-2026-06-26T20-55-11-049.md
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/beliefs/interview-2026-06-26T21-02-50-651.md
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/beliefs/interview-2026-06-26T21-10-42-369.md
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/beliefs/interview-2026-06-26T21-18-26-782.md
last_verified_at: "2026-06-26T21:59:16.409Z"

---

# 308 Evergreen Street — Task Graph (narrative)

Companion to `task_graph.json` (94 tasks across 10 phases). The structured graph is the contract; this narrative consolidates the 94 atomic tasks into 28 high-level work bars for the PM's mental model. Every id below appears verbatim in the JSON. The deterministic CPM scheduler turns the JSON into dated tasks — this narrative does NOT assign dates.

**Critical path (marked `[CP]`)** runs: TDEC (PC anchor, 42 cal-d) → on-site Day 1 site setup → demo chain → excavation → foundation chain (form, inspect, monolithic pour, cure) → framing chain (basement walls → floor → exterior walls → roof) → underlayment → plumbing rough (4-day floor) → bundled inspection + punch buffer → insulation → drywall (11d consolidated) → paint phase 1 → tile shower chain (substrate → install → grout) → shower glass template + 10-cal-d fab + install → paint phase 2 → substantial completion → closeout → Will's walkthrough.

## Pre-construction (anchors backward from on-site start day 0)

T1. **Permit walk-in** — `general.permitting` · 1d / general / no predecessors / PC offset 15 wd. 1-day same-day walk-in per Will's audit; 3 weeks before on-site as a safety buffer.

T2. **TDEC septic eval [CP anchor]** — `permit.tdec_septic` · 42 cal-d `lead_time` / PC offset 30 wd. 6-week TDEC window per addition_rules; gates `excavation.dig`. Clock starts at contract signing (Round 2) — on-site start is FLOATING until contract signs.

T3. **Amperage check** — `prep.amperage_check` · 0.5d / electrical / PC offset 15 wd. Verifies existing main service can support new 100A subpanel. CO trigger if insufficient.

T4. **Selections finalized checkpoint** — `checkpoint.selections_finalized` · milestone / PC offset 15 wd, lead-up 5 wd. Gates tile, paint, LVT, vanity, vanity_fixtures, interior_doors, exterior_door, minisplit procurement chains. Still TBD per Round 2: vanity, faucets, mirrors, vanity lights, mini-split aesthetic, interior + exterior door styles.

T5. **Equipment-confirmed-demo checkpoint** — `checkpoint.equipment_confirmed_demo` · milestone / PC offset 10 wd, lead-up 2 wd. PM confirms dumpster, concrete saw, mini-ex, scaffolding reserved.

## Procurement (long-lead chains, install-date-driven)

T6. **Windows chain** — `order.windows` (0.5d) → `wait.windows` (21 cal-d) → `checkpoint.windows_arrived` → gates `windows.install`. Stock 3× 36"×60" DH + transom per Round 1.

T7. **LVL chain** — `order.lvl` → `wait.lvl` (14 cal-d) → `checkpoint.lvl_arrived` → gates `structural.install_lvl`. Standard 3-ply 14" per Round 1.

T8. **Subpanel chain** — `order.subpanel` → `wait.subpanel` (14 cal-d) → `checkpoint.subpanel_arrived` → gates `electrical.subpanel_install`.

T9. **Mini-split chain** — `order.minisplit` (FS after `milestone.dried_in` + `checkpoint.selections_finalized`) → `wait.minisplit` (14 cal-d) → `checkpoint.minisplit_arrived` → gates `hvac.minisplit_install`. Mechanical equipment ordered at dried-in per editor rules.

T10. **Tile chain [special order]** — `order.tile` (FS after selections_finalized) → `wait.tile` (14 cal-d) → `checkpoint.tile_arrived` → gates `tile.shower_substrate`. Per Round 4: special-order wall + mosaic tile combo, 14-day full 3-task chain.

T11. **Finish materials (collapsed 1-day orders)** — `order.paint`, `order.lvt`, `order.vanity`, `order.vanity_fixtures`, `order.interior_doors`, `order.exterior_door`. Each FS after `checkpoint.selections_finalized`. Stock 7-day suppliers — collapsed per Rule 4R exception.

## On-site execution (day 0 = on-site start)

T12. **Site setup + customer early item [CP]** — `general.site_setup` (1d / general) + `equipment.dumpster_arrive` + `equipment.demo_machines_arrive` running parallel Day 1. **`early.acrylic_shower_swap`** (1d / plumbing) runs Day 1 in parallel — customer-requested hall bath shower swap so homeowner has a working shower during construction (Rule 4V bucket #1). All depend on `general.site_setup`.

T13. **Prep work before demo** — `prep.heat_pump_relocate` (1d / hvac) + `prep.electrical_disconnect_relocate` (0.5d / electrical), both Day 1. Demo gated 2-wd FS lag behind them (Rule 4K).

T14. **Demolition [CP]** — `demo.protection` (1d / demo) → `demo.selective_demo` (3d / demo, includes hall bath window removal) → `demo.haul_out` (1d / demo). Separate `demo.expose_bearing_wall` (1d / demo) opens existing 2nd-story load-bearing wall for LVL retrofit — runs in parallel from `demo.protection`.

T15. **Excavation [CP]** — `excavation.dig` (2d / excavation, crew 2 + mini-ex) · FS after `demo.haul_out` AND `permit.tdec_septic`.

T16. **Foundation chain [CP]** — `foundation.form_and_prep` (1.5d / concrete, crew 4) → `inspect.footing` (0.5d / inspector, FS lag 1) → `foundation.monolithic_pour` (1d / concrete, crew 4 — footings + slab same day per Rule 4B) → `foundation.cure` (2 cal-d `lead_time`).

T17. **Framing chain [CP]** — `framing.basement_walls` (2d) → `framing.floor_system` (2d, depends ONLY on basement walls per Will's audit) → `framing.exterior_walls` (3d) → `framing.interior_walls` (2d, SS lag 1 with exterior) → `framing.roof` (3d stick-frame per Round 2) → `framing.sheathing` (1d). All `framing` trade, crew 3.

T18. **LVL retrofit sub-chain** — `structural.temp_shoring` (0.5d) → `structural.install_lvl` (1d, FS after `checkpoint.lvl_arrived`) → `structural.remove_temp_shoring` (0.5d). Independent of new framing per Will's audit; runs in parallel. `framing.elevator_shaft` (1d) is also independent retrofit, FS after `demo.haul_out`.

T19. **Concealed roof tie-in buffer** — `roof.concealed_buffer` (3 cal-d `lead_time`, SS lag 1 after `framing.roof`). PM accepted this buffer in Round 1; opens existing ceiling early on Day 1 of roof framing to surface CO conditions.

T20. **Roofing + windows + dried-in [CP partial]** — `roofing.underlayment` (1d / roofing, crew 3) → `roofing.shingles` (1d, up to 6,000 sqft/day per Will). `windows.install` (2d / windows_doors, FS after `framing.roof` AND `checkpoint.windows_arrived` AND `order.exterior_door`) runs in PARALLEL with underlayment per Rule 4J. `milestone.dried_in` fires after both underlayment + windows.

T21. **Exterior siding bundle** — `siding.install` (3d) → `siding.trim_fascia_soffit_gutters` (2d). Same-crew block; runs in parallel with interior MEPs (exterior trades don't count against 2-interior-trade cap).

T22. **MEP rough trades [CP partial]** — Order per Rule 4G for mini-split jobs (plumbing → electrical → mini-split):
- `plumbing.rough_in` (4d / plumbing, crew 2 — Will's nominal floor per `plumbing_rough_min_duration` rule) · FS after `roofing.underlayment` + `windows.install`. NO tank-set predecessor (existing WH stays per Round 1).
- `electrical.rough_in` (1.5d / electrical, crew 2) · SS lag 1 with plumbing.
- `electrical.subpanel_install` (1d / electrical, crew 1 — Will's audit override on crew/duration) · FS after `checkpoint.subpanel_arrived` + `prep.amperage_check`.
- `hvac.minisplit_rough` (0.5d / hvac, crew 1) · FS after plumbing + electrical (mini-split LAST per Rule 4G).

T23. **Bundled rough inspection + punch buffer [CP]** — `inspect.rough_bundled` (0.5d / inspector, FS lag 1 after all rough trades) covers electrical + plumbing + mini-split line set + framing in ONE inspector visit per Rule 4C. `buffer.post_rough_inspection` (2 wd `lead_time`) follows per Rule 4D.

T24. **Insulation chain [CP]** — `equipment.insulation_material_arrival` (0.5d, same day as bundled inspection) → `insulation.air_seal` (0.5d) → `insulation.install` (1d, R13 walls + R30 attic + R30 floor) → `inspect.insulation` (0.5d, FS lag 1). Hall bath retrofit work consolidated: `retrofit.hall_bath_window_infill_framing` (0.5d / framing) → `retrofit.hall_bath_insulation` (0.5d, SS with insulation install).

T25. **Drywall consolidated [CP]** — `drywall.consolidated` (11d / drywall, crew 3). One block covering addition + existing primary bedroom retrofit + hall bath window-infill patch + basement storage finish. Hang + tape + sand + prime with internal cure days baked in. Multi-zone bump per editor_rules guidance.

T26. **Paint Phase 1 [CP]** — `paint.phase_1` (1d / paint, crew 2) · FS after `drywall.consolidated` + `order.paint`. Primer walls+ceilings AM + ceiling finish coat PM same day per Will's standard. Gates flooring, electrical finish, tile substrate.

T27. **Master bath tile chain [CP]** — `tile.shower_substrate` (1d, FS after paint.phase_1 + `checkpoint.tile_arrived`) → `tile.shower_install` (5d / tile, crew 2 — 88h / 2 crew = 5.5d rounded; wall tile + mosaic floor + niche + bench) → `tile.grout_seal` (1.5d).

T28. **Shower glass chain [CP]** — `shower.glass_template` (0.5d / glazing, FS after `tile.grout_seal`) → `wait.shower_glass` (10 cal-d `lead_time`) → `shower.glass_install` (0.5d / glazing). Per Round 4: frameless 3/8" tempered glass door + return panel.

T29. **Other interior finishes (parallel cluster)** —
- `flooring.install` (3d / flooring) · FS after `paint.phase_1` + `tile.shower_substrate` + `order.lvt` (Rule 4L).
- `vanity.install` (0.5d / cabinets) · FS after `flooring.install` + `paint.phase_1` + `order.vanity`.
- `trim.install` (3d / trim_carpentry) · FS after `flooring.install` + `order.interior_doors` (Rule 4L: trim gates on flooring, NOT paint).
- `electrical.finish` (2.5d / electrical) · FS after `paint.phase_1` (Rule 4L).
- `plumbing.finish` (2d / plumbing) · FS after `vanity.install` + `flooring.install` + `tile.grout_seal` + `order.vanity_fixtures`.
- `hvac.minisplit_install` (1d / hvac, crew 1) · FS after drywall + paint.phase_1 + `checkpoint.minisplit_arrived` + `electrical.finish` (Rule 4N stagger — preserves 2-trade interior cap).
- `retrofit.hall_bath_repaint` (0.5d / paint) · FS after `drywall.consolidated` + `paint.phase_1` (Rule 4V bucket #2 — same area as early item but different timing window).

T30. **Paint Phase 2 + Substantial Completion [CP]** — `paint.phase_2` (1d / paint) · FS after EVERY finish trade per Rule 4F: trim, flooring, vanity, tile grout, plumbing finish, electrical finish, mini-split install, shower glass install, hall bath repaint. LAST work task on site. `milestone.substantial_completion` is FS-after paint.phase_2 ONLY per Rule 4F.

T31. **Closeout [CP]** — `closeout.client_walkthrough` (0.5d / general — PM + signed punch list) → `closeout.punch_list_returns` (2d) → `closeout.final_clean` (1d / cleanup) → `inspect.final_bundled` (0.5d / inspector — all finals + final building in ONE visit per Rule 4M) → `milestone.co_handoff`.

T32. **Will's walkthrough [closeout final]** — `closeout.wills_walkthrough` (0.5d / general, FS lag 1 after `inspect.final_bundled`). The actual end of the project from TCR's standpoint per addition_rules.

## Reading the structured graph

- All ids above appear in `task_graph.json`; consult that file for trade, crew_size, duration_days, lead_time_days, lead_up_working_days, pre_construction_offset_working_days, and the complete depends_on list per task.
- Critical-path tasks listed `[CP]` are the longest sequential chain. Other tasks float either in parallel (LVL sub-chain, elevator shaft, siding bundle, hall bath retrofit) or backward-pulled by their consumers (all procurement chains).
- Warnings + assumptions block at the bottom of the JSON enumerates open risks (concealed roof tie-in, selections still TBD, TDEC clock floating, hall bath retrofit two-bucket pattern, drywall consolidation, etc.) and judgment calls the agent made (stick-frame default, monolithic foundation, 4d plumbing floor, 11d drywall, HVAC stagger).
- Two atomic patterns repeated throughout: (a) procurement 3-task chain `order.X` → `wait.X` → `checkpoint.X_arrived` per Rule 4R, and (b) two-bucket pattern for hall bath per Rule 4V — `early.acrylic_shower_swap` (Day 1, site_prep) is SEPARATE from `retrofit.hall_bath_window_infill_framing` / `retrofit.hall_bath_insulation` / `retrofit.hall_bath_repaint` (mid-job, interior_finishes / hall_bath_mod).
