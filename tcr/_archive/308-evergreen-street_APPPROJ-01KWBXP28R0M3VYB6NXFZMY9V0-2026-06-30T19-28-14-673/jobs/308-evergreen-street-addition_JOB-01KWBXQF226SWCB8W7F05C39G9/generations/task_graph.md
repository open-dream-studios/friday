---
generation_kind: task_graph_v2
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWBXP28R0M3VYB6NXFZMY9V0/jobs/308-evergreen-street-addition_JOB-01KWBXQF226SWCB8W7F05C39G9/intelligence/facts.md
  - _projects/308-evergreen-street_APPPROJ-01KWBXP28R0M3VYB6NXFZMY9V0/jobs/308-evergreen-street-addition_JOB-01KWBXQF226SWCB8W7F05C39G9/intelligence/confirmed.md
  - _projects/308-evergreen-street_APPPROJ-01KWBXP28R0M3VYB6NXFZMY9V0/jobs/308-evergreen-street-addition_JOB-01KWBXQF226SWCB8W7F05C39G9/intelligence/applicable_rules.json
  - _projects/308-evergreen-street_APPPROJ-01KWBXP28R0M3VYB6NXFZMY9V0/jobs/308-evergreen-street-addition_JOB-01KWBXQF226SWCB8W7F05C39G9/intelligence/extracted/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KWBXP28R0M3VYB6NXFZMY9V0/jobs/308-evergreen-street-addition_JOB-01KWBXQF226SWCB8W7F05C39G9/intelligence/extracted/breakdown.md
  - _projects/308-evergreen-street_APPPROJ-01KWBXP28R0M3VYB6NXFZMY9V0/jobs/308-evergreen-street-addition_JOB-01KWBXQF226SWCB8W7F05C39G9/intelligence/extracted/plans.md
last_verified_at: "2026-06-30T17:07:29.893Z"
---

# Task graph — 308 Evergreen addition

Two-story 30×10 addition (~590 sqft new) + retrofit of existing primary bedroom + hall bath modification. Brick lower / vinyl lap upper, tankless WH, mini-split HVAC, custom master-bath tile shower, monolithic foundation, stick-frame gable roof tying into existing 6/12.

**Total tasks: 38.** Pre-construction 4 · Procurement 5 · On-site 28 · Closeout 1.

**Anchor date:** on-site start = 2026-08-24 (TDEC application targets 2026-07-07 submit + 6-wk turnaround + 1-wk buffer).

Critical path marked **[CP]**.

## Pre-construction (offset back from 2026-08-24)

- **T1. permit.tdec_septic** — Duration: 42 cal-d lead_time / Trade: general / Depends on: — / Notes: TDEC septic permit, 6-wk lead from 2026-07-07 submit. `pre_construction_offset_working_days: 30`. **[CP]**
- **T2. permit.building_walk_in** — Duration: 1 d work / Trade: pm / Depends on: — / Notes: building permit walk-in. `pre_construction_offset_working_days: 15, lead_up_working_days: 2`.
- **T3. checkpoint.selections_finalized** — Duration: 0 d milestone / Trade: pm / Depends on: — / Notes: LVT, tile, vanity, fixtures, doors, paint colors all locked. `pre_construction_offset_working_days: 15, lead_up_working_days: 5`. Gates the 5 procurement chains below.
- **T4. prep.amperage_check** — Duration: 0.5 d work / Trade: electrical / Depends on: — / Notes: verify existing main service can support new 100A subpanel. `pre_construction_offset_working_days: 15`. Must clear before contract sign.

## Procurement (5 long-lead items)

- **T5. procurement.windows** — Duration: 14 cal-d lead / Trade: windows_doors / Depends on: T3 / Notes: 2 stock vinyl (1 transom + 1 DH) per drawing schedule.
- **T6. procurement.lvl** — Duration: 10 cal-d lead / Trade: framing / Depends on: — / Notes: 3-ply 14" LVL (~15'-6" span), standard stock.
- **T7. procurement.brick** — Duration: 14 cal-d lead / Trade: masonry / Depends on: T3 / Notes: General Shale "brick to match existing" via Builders FirstSource.
- **T8. procurement.tank** — Duration: 10 cal-d lead / Trade: plumbing / Depends on: T3 / Notes: tankless WH (customer signed $6,500 option).
- **T9. procurement.tile_master_bath** — Duration: 14 cal-d lead / Trade: tile / Depends on: T3 / Notes: master-bath tile + setting materials.

## On-site execution

### Customer-early + site prep + demo

- **T10. early.acrylic_shower_swap** — 1 d / plumbing / no deps / Day-1 customer early item — keeps homeowner showering through construction. Off CP.
- **T11. prep.heat_pump_relocate** — 1 d / hvac / no deps / dev_rules 4K: relocate before main demo, FS lag 3 working days into T12.
- **T12. demo.expose_and_clear** — 2 d / demo / Depends on: T11 (FS+3) / Saw-cut walkway, remove railroad ties, expose bearing wall, dump runs. **[CP]**

### Structural + foundation + framing

- **T13. structural.lvl_install** — 2 d / framing / Depends on: T12, T6 / Temp shoring + LVL set + remove shoring (one block).
- **T14. concrete.foundation_monolithic** — 1 d / concrete / Depends on: T12 / Single-pour monolithic per dev_rules 4B; footing + slab + inspection same day. **[CP]**
- **T15. framing.floor_system** — 2 d / framing / Depends on: T14 (FS+2 cure), T13 / New floor bears on LVL.
- **T16. framing.walls_and_shaft** — 5 d / framing / Depends on: T15 / Basement 2×4 walls + exterior + interior + 4'×4' elevator shaft framing. **[CP]**
- **T17. framing.roof** — 4 d / framing / Depends on: T16 / Stick-frame gable tying 3/12 new into existing 6/12. Multi-valley tie-in — concealed-condition buffer modeled as FS lag 3 cal-d on T18. **[CP]**

### Roofing, windows, exterior

- **T18. roofing.underlayment** — 1 d / roofing / Depends on: T17 (FS+3 buffer) / Synthetic underlayment + drip edge + ridge vent. Gates MEPs + windows per addition_rules MEP-gating.
- **T19. windows.install** — 1 d / windows_doors / Depends on: T17, T5 / 4I: install IMMEDIATELY after roof framed (NOT after dried-in). Parallel with T18.
- **T20. roofing.shingles** — 2 d / roofing / Depends on: T18 / Architectural asphalt + fascia + soffit + gutters.
- **T21. exterior.brick_veneer** — 4 d / masonry / Depends on: T19, T7 / Bristol Brick crew, basement-level walls.
- **T22. exterior.vinyl_lap** — 3 d / siding / Depends on: T19 / Vinyl lap second floor. Parallel with T21.

### MEP rough + bundled inspection

- **T23. plumbing.rough_in** — 4 d / plumbing / Depends on: T18, T19, T8 / Tank set (tankless) + supply/waste/vent for master bath + W/D relocate + vent stacks through roof. Expanded from 40 hrs breakdown to 64-hr rule floor (4H + editor_rules). **[CP]**
- **T24. electrical.rough_in** — 1.5 d / electrical / Depends on: T18, T19, T4 / 100A subpanel + recessed lights + outlets + 30A elevator + hall switch relocate. Overlaps T23.
- **T25. hvac.minisplit_rough** — 0.5 d / hvac / Depends on: T24 / Line-set + electrical penetration. Mini-split LAST per 4G.
- **T26. inspect.rough_bundled** — 1 d / inspector / Depends on: T23, T24, T25 / Bundled per 4C: single inspector, single day, all trades. `lead_up_working_days: 1`. **[CP]**

### Insulation + drywall

- **T27. insulation** — 1 d / insulation / Depends on: T26 (FS+2 punch buffer per 4D) / R13 walls, R30 attic, R30 floor.
- **T28. drywall.consolidated** — 10 d / drywall / Depends on: T27 / Largest section (159 breakdown hrs). Covers addition + retrofit primary bedroom + hall bath patch + basement storage in ONE block per editor_rules drywall-consolidation. **[CP]**

### Interior finishes (paint two-phase, tile, LVT, trim, electrical/HVAC finish)

- **T29. paint.phase_1** — 1 d / paint / Depends on: T28 / Primer walls + ceilings AM, ceiling finish coat PM same day (4E).
- **T30. tile.shower_full** — 6 d / tile / Depends on: T29, T9 / Substrate → install → grout/seal (compressed). Custom 7×4 shower + mosaic floor + niche/bench + dual-valve diverter. **[CP]**
- **T31. flooring.lvt** — 3 d / flooring / Depends on: T29 / LVT throughout addition + existing primary bedroom retrofit. Parallel with T30. (4L: flooring → trim ordering.)
- **T32. electrical.finish** — 2.5 d / electrical / Depends on: T29 / Trim recessed lights, switches/outlets, vanity lights, dimmers. (4L: electrical.finish → paint_1, not paint_2.)
- **T33. hvac.minisplit_install** — 1 d / hvac / Depends on: T32 / Head install + commissioning. 4N + 4G: FS-after electrical.finish (mini-split LAST).
- **T34. trim.carpentry** — 3 d / trim_carpentry / Depends on: T31 / 5-1/4" base + 2-1/4" casing + doors + plumbing finish + cabinet/vanity set.

### Retrofit components (separate from new construction)

- **T35. retrofit.existing_primary_bedroom** — 2 d / trim_carpentry / Depends on: T34 / EXISTING original-house primary bedroom remodel — final trim + touch-ups (framing handled in T16, drywall in T28, LVT in T31).
- **T36. retrofit.hall_bath_mod** — 3 d / drywall / Depends on: T28 / Window infill + drywall patch + paint + PVC trim. Parallel with T29/T30/T31. SEPARATE Component from T10's acrylic shower swap per 4V two-bucket pattern.

### Final paint + closeout

- **T37. paint.phase_2** — 1 d / paint / Depends on: T34, T30, T32, T33, T35, T36, T21, T22, T20 / Wall finish coats + cut-ins + touch-ups. ALL finish trades are predecessors per 4E + 4F. **[CP]**
- **T38. milestone.substantial_completion** — 0 d milestone / pm / Depends on: T37 ONLY / 4F: paint.phase_2 is sole predecessor. **[CP]**

## Critical path summary

T1 (TDEC anchor) → T12 → T14 → T16 → T17 → T23 → T26 → T28 → T30 → T37 → T38.

The schedule is gated by (a) TDEC permit lead (42 cal-d from 2026-07-07), (b) framing → roofing → MEP gating chain, (c) the 10-day consolidated drywall block, (d) the 6-day master-bath tile shower, and (e) the two-phase paint converging on substantial completion.

## Warnings + assumptions

See `task_graph.json` `warnings[]` and `assumptions[]` for the structured list (10 each). Highlights:

- TDEC anchor is 2026-08-24 — any submit slip past 2026-07-07 slides the on-site start day-for-day.
- Plumbing rough-in expanded from breakdown 40 hrs to rule-floor 64 hrs — cost ledger should reconcile.
- Brick CO is paperwork-only; no vinyl-only fallback variant carried.
- Bristol Brick advance notice (3-4 wk) is a PM operational item, not modeled as a separate task.
- checkpoint.equipment_confirmed (offset-10) is intentionally folded into checkpoint.selections_finalized (offset-15) to keep task count in budget; if HVAC equipment / exterior door / vanity / LVT slip into long-lead at selections, PM must add explicit procurement tasks.
