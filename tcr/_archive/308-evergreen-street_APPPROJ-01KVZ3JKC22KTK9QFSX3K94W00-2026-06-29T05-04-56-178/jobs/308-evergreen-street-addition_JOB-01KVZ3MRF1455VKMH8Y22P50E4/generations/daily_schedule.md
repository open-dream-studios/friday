---
generation_kind: daily_schedule_v1
depends_on:
  - _company/rules/dev_rules.md
  - _company/rules/editor_rules.md
  - _company/rules/pep_rules.md
  - _company/beliefs/_examples/stick_frame_default_for_small_additions.md
  - _company/knowledge/308_evergreen_wills_audit_transcript.md
  - _company/knowledge/_examples/wills_voice.md
  - job_types/addition/rules/addition_rules.md
  - job_types/addition/rules/tdec_septic_permit_offset.md
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/manifest.json
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/inputs/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/inputs/files/308_scope.pdf.txt
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/inputs/files/308_Evergreen_Addition.xlsx - Summary (1).csv.txt
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/beliefs/initial.md
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/beliefs/interview-2026-06-26T20-55-11-049.md
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/beliefs/interview-2026-06-26T21-02-50-651.md
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/beliefs/interview-2026-06-26T21-10-42-369.md
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/beliefs/interview-2026-06-26T21-18-26-782.md
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/generations/task_graph.json
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/generations/task_graph.md
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/generations/schedule.json
last_verified_at: "2026-06-26T23:57:59.132Z"
---

# 308 Evergreen Street — Daily Schedule

Working-day calendar derived from `schedule.json`. On-site start = **Thu 2026-06-25 (Day 1)**. Final handoff = **Thu 2026-10-08 (Will's walkthrough)**. All dates verbatim from CPM. **Pre-construction is anchored on the TDEC septic permit (42 cal-d).**

---

## Pre-construction runway (T-weeks from on-site Day 1)

The TDEC septic evaluation is the longest pre-con item and the only one that's calendar-bound: per Round 2 interview, the 6-week clock starts at contract signing. Until the contract signs and TDEC kicks off, **on-site Day 1 floats**. The dates below assume TDEC kickoff on Wed 2026-05-13 (`permit.tdec_septic`, 42 cal-d → ends Wed 2026-06-24, gates `excavation.dig`).

| Week | Date | Pre-Con Task | Notes |
|---|---|---|---|
| **T-6 wk** | Wed May 13 | `permit.tdec_septic` 42-cal-d window opens | PM places call to TDEC same day as contract / deposit. CRITICAL — gates `excavation.dig` (Day 10). |
| T-5 wk | — | (TDEC processing) | PM monitors. Soil scientist visit + report come in within 1-2 weeks. |
| T-4 wk | — | (TDEC processing) | — |
| **T-3 wk** | Thu Jun 4 | `general.permitting` (1d, walk-in) | Per Will's audit, ~90% same-day approval. Lead-up 2 wd: assemble package Tue Jun 2 + Wed Jun 3. |
| T-3 wk | Thu Jun 4 | `general.pre_construction_walkthrough` (0.5d) | PM + homeowner verify tie-in points, existing dimensions. |
| T-3 wk | Thu Jun 4 | `prep.amperage_check` (0.5d, electrical) | Verify existing main supports new 100A subpanel. CO trigger if insufficient. Lead-up 1 wd. |
| **T-3 wk** | Thu Jun 4 | **`checkpoint.selections_finalized`** (milestone) | LAST chance for homeowner to lock vanity, faucets, mirrors, vanity lights, mini-split aesthetic, interior + pocket door styles, exterior door. 5-wd PM lead-up (Fri May 29 → Thu Jun 4): kick off → push → press → lock. Cascade-critical for tile (14-d), windows (21-d), exterior door, vanity, mini-split. |
| **T-2 wk** | Thu Jun 11 | **`checkpoint.equipment_confirmed_demo`** (milestone) | PM confirms dumpster, concrete saw, mini-ex, scaffolding reserved. 2-wd lead-up. |
| T-1 wk | Wed Jun 17 → Wed Jun 24 | (TDEC closeout window) | PM tracks soil scientist report, confirms septic feasibility before excavation Day 10. |
| **T-0** | Wed Jun 24 | `permit.tdec_septic` ends | Excavation gate cleared. |

---

## On-site Day 1 → Day N

`[CP]` = critical-path task (slip on this day = total project slip). **Bold INSPECTION lines** require PM physically on site per Will's audit. All dates from `schedule.json`.

### Site Prep + Demo (Days 1–9)

- **Day 1 (Thu Jun 25)** — `general.site_setup` (1d, general) [CP] · `order.windows`, `order.lvl`, `order.subpanel`, `order.tile`, `order.exterior_door`, `order.vanity`, `order.vanity_fixtures`, `order.interior_doors`, `order.paint`, `order.lvt` (PM places all on Day 1).
- **Day 2 (Fri Jun 26)** — `prep.heat_pump_relocate` (1d, hvac) [CP] · `prep.electrical_disconnect_relocate` (0.5d, electrical) · **`early.acrylic_shower_swap` (1d, plumbing)** — customer-requested early item, hall bath shower swap so homeowner has a working shower during construction · `equipment.dumpster_arrive` (0.5d) · `equipment.demo_machines_arrive` (0.5d, saw + mini-ex + skid steer + scaffolding).
- **Day 3 (Mon Jun 29)** — (2-wd buffer between prep work + demo per `addition_rules#heat_pump_relocate`).
- **Day 4 (Tue Jun 30)** — (buffer continues).
- **Day 5 (Wed Jul 1)** — `demo.protection` (1d, demo, crew 3) [CP] — floor protection + dust walls. 2-wd lead-up.
- **Day 6 (Thu Jul 2)** — `demo.selective_demo` Day 1/3 [CP] · `demo.expose_bearing_wall` (1d, demo) — independent LVL retrofit, opens existing 2nd-story load-bearing wall.
- **Day 7 (Fri Jul 3)** — `demo.selective_demo` Day 2/3 [CP] · `structural.temp_shoring` (0.5d, framing) — LVL retrofit sub-chain.
- **(Sat Jul 4 — Independence Day, off)**
- **Day 8 (Mon Jul 6)** — `demo.selective_demo` Day 3/3 [CP] — wraps walkway saw-cut + hall bath window removal.
- **Day 9 (Tue Jul 7)** — `demo.haul_out` (1d, demo, crew 2) [CP] · `retrofit.hall_bath_window_infill_framing` (0.5d, framing).

### Excavation + Foundation (Days 10–17)

- **Day 10 (Wed Jul 8)** — `excavation.dig` Day 1/2 (excavation, crew 2 + mini-ex) [CP] · `framing.elevator_shaft` (1d, framing) — independent retrofit, framing only · TDEC gate must be clear (`permit.tdec_septic` ended Wed Jun 24).
- **Day 11 (Thu Jul 9)** — `excavation.dig` Day 2/2 [CP] · `checkpoint.lvl_arrived` (milestone) · `structural.install_lvl` Day 1 (framing, crew 3) — gated on LVL arrival + temp shoring.
- **Day 12 (Fri Jul 10)** — `foundation.form_and_prep` Day 1/1.5 (concrete, crew 4) [CP] — form footings + gravel base + vapor barrier + rebar in ONE continuous task · `structural.install_lvl` finishes · `structural.remove_temp_shoring` (0.5d) — closes LVL sub-chain.
- **Day 13 (Mon Jul 13)** — `foundation.form_and_prep` Day 2/1.5 [CP] (last 0.5d).
- **Day 14 (Tue Jul 14)** — **INSPECTION: `inspect.footing` (0.5d, inspector) [CP]** — covers BOTH footing and slab prep (monolithic per Rule 4B). PM on site with camera + spray paint.
- **Day 15 (Wed Jul 15)** — `foundation.monolithic_pour` (1d, concrete, crew 4) [CP] — footings + 4" slab same day.
- **Days 16–17 (Thu Jul 16 → Fri Jul 17)** — `foundation.cure` (2 cal-d lead_time) [CP] — no on-site work.

### Framing (Days 18–27)

- **Day 18 (Mon Jul 20)** — `framing.basement_walls` Day 1/2 (framing, crew 3) [CP]. 2-wd lead-up.
- **Day 19 (Tue Jul 21)** — `framing.basement_walls` Day 2/2 [CP].
- **Day 20 (Wed Jul 22)** — `framing.floor_system` Day 1/2 [CP] — depends only on basement walls (LVL retrofit independent).
- **Day 21 (Thu Jul 23)** — `framing.floor_system` Day 2/2 [CP].
- **Day 22 (Fri Jul 24)** — `framing.exterior_walls` Day 1/3 [CP].
- **Day 23 (Mon Jul 27)** — `framing.exterior_walls` Day 2/3 [CP] · `framing.interior_walls` Day 1/2 (SS lag 1).
- **Day 24 (Tue Jul 28)** — `framing.exterior_walls` Day 3/3 [CP] · `framing.interior_walls` Day 2/2.
- **Day 25 (Wed Jul 29)** — `framing.roof` Day 1/3 (stick-frame 3/12 gable tying into existing 6/12) [CP]. **PM: OPEN existing ceiling at tie-in TODAY to surface any concealed conditions early — biggest CO risk on this job.**
- **Day 26 (Thu Jul 30)** — `framing.roof` Day 2/3 [CP] · `roof.concealed_buffer` opens (3 cal-d).
- **Day 27 (Fri Jul 31)** — `framing.roof` Day 3/3 [CP] · concealed buffer continues.

### Dried-in + MEPs (Days 28–37)

- **Day 28 (Mon Aug 3)** — `framing.sheathing` (1d) [CP] · `windows.install` Day 1/2 (windows_doors, crew 2) [CP] — immediately after roof framed per Rule 4J · concealed buffer closes.
- **Day 29 (Tue Aug 4)** — `roofing.underlayment` (1d, roofing, crew 3) [CP] · `windows.install` Day 2/2 [CP].
- **Day 30 (Wed Aug 5)** — `roofing.shingles` (1d) · **`milestone.dried_in`** fires · `plumbing.rough_in` Day 1/4 (plumbing, crew 2) [CP] · `electrical.subpanel_install` (1d, 1 person) · `siding.install` Day 1/3 (exterior, doesn't count vs. 2-trade interior cap) · `order.minisplit` (PM places — mechanical equipment ordered at dried-in per editor rules).
- **Day 31 (Thu Aug 6)** — `plumbing.rough_in` Day 2/4 [CP] · `electrical.rough_in` Day 1/1.5 (SS lag 1 with plumbing) · `siding.install` Day 2/3.
- **Day 32 (Fri Aug 7)** — `plumbing.rough_in` Day 3/4 [CP] · `electrical.rough_in` Day 2/1.5 · `siding.install` Day 3/3.
- **Day 33 (Mon Aug 10)** — `plumbing.rough_in` Day 4/4 [CP] · `siding.trim_fascia_soffit_gutters` Day 1/2.
- **Day 34 (Tue Aug 11)** — `hvac.minisplit_rough` (0.5d, 1 person — line set only) [CP] · `siding.trim_fascia_soffit_gutters` Day 2/2.
- **Day 35 (Wed Aug 12)** — **INSPECTION: `inspect.rough_bundled` (0.5d, ONE inspector) [CP]** — covers plumbing + electrical + HVAC line set + framing in ONE visit per Rule 4C. PM must be on site for the whole visit — photos, spray-paint flagged items, get verbal pass/fail same day. `equipment.insulation_material_arrival` (0.5d) — material staged for post-inspection install.
- **Days 36–37 (Thu Aug 13 → Fri Aug 14)** — `buffer.post_rough_inspection` (2 wd) [CP] — punch-list loop, trades return for fixes + re-inspect.

### Insulation + Drywall (Days 38–52)

- **Day 38 (Mon Aug 17)** — `insulation.air_seal` (0.5d, insulation) [CP] · `insulation.install` Day 1 (R13 walls + R30 attic + R30 floor) [CP] · `retrofit.hall_bath_insulation` (0.5d) — rolled in with main insulation crew.
- **Day 39 (Tue Aug 18)** — `insulation.install` Day 2 (finishes) [CP].
- **Day 40 (Wed Aug 19)** — **INSPECTION: `inspect.insulation` (0.5d) [CP]** — procedural, almost always passes. PM on site.
- **Day 41 (Thu Aug 20)** — `drywall.consolidated` Day 1/11 (drywall, crew 3) [CP] — single block: addition + existing primary bedroom + hall bath patch + basement storage finish. Hang → tape → sand → prime, cure days baked in. 2-wd lead-up. PM calls drywall crew when insulation inspection scheduled (not after it passes — gives 3-day-out target).
- **Days 42–52 (Fri Aug 21 → Thu Sep 3)** — `drywall.consolidated` Days 2–11 [CP] (Mon-Fri working days through Aug 21, 24-28, 31, Sep 1-3).

### Paint Phase 1 + Interior Finishes (Days 53–71)

- **Day 53 (Fri Sep 4)** — `paint.phase_1` (1d, paint, crew 2) [CP] — AM: primer walls + ceilings · PM: ceiling finish coat. Walls left in primer for downstream trades. Will's standard sequence — 1d covers everything.
- **(Mon Sep 7 — Labor Day, off)**
- **Day 54 (Tue Sep 8)** — `tile.shower_substrate` (1d, tile, crew 2) [CP] · `electrical.finish` Day 1/2.5 · `retrofit.hall_bath_repaint` (0.5d, paint). 2-trade interior count: tile + electrical (at cap; retrofit paint is brief touch-up).
- **Day 55 (Wed Sep 9)** — `tile.shower_install` Day 1/5 (master shower walls + mosaic floor + niche + bench) [CP] · `electrical.finish` Day 2/2.5 · `flooring.install` Day 1/3 (LVT throughout). 2-trade cap: tile + flooring (electrical finishes mid-day).
- **Day 56 (Thu Sep 10)** — `tile.shower_install` Day 2/5 [CP] · `electrical.finish` Day 3/2.5 (closes) · `flooring.install` Day 2/3 · `hvac.minisplit_install` Day 1 (1 person, gated on electrical.finish per Rule 4N HVAC stagger).
- **Day 57 (Fri Sep 11)** — `tile.shower_install` Day 3/5 [CP] · `flooring.install` Day 3/3 (closes) · `hvac.minisplit_install` Day 2 (finishes).
- **Day 58 (Mon Sep 14)** — `tile.shower_install` Day 4/5 [CP] · `vanity.install` (0.5d, cabinets) · `trim.install` Day 1/3 (base, casing, 4 interior doors).
- **Day 59 (Tue Sep 15)** — `tile.shower_install` Day 5/5 [CP] · `trim.install` Day 2/3.
- **Day 60 (Wed Sep 16)** — `tile.grout_seal` Day 1/1.5 [CP] · `trim.install` Day 3/3 (closes).
- **Day 61 (Thu Sep 17)** — `tile.grout_seal` Day 2/1.5 (finishes morning) [CP] · `shower.glass_template` (0.5d, glazing) — glass supplier templates AFTER grout sets [CP] · `plumbing.finish` Day 1 (faucets + toilet + dual-valve shower + W/D hookup).
- **Day 62 (Fri Sep 18)** — `wait.shower_glass` opens (10 cal-d fab) [CP] · `plumbing.finish` Day 2.
- **Days 63–67 (Mon Sep 21 → Fri Sep 25)** — `plumbing.finish` wraps (scheduled_end Mon Sep 21). Glass-fab wait continues. Critical path is idle on-site Wed Sep 23 → Tue Sep 29 awaiting glass — schedule no other work in master bath; finish walls in other zones stay in primer.
- **Days 68–69 (Mon Sep 28 → Tue Sep 29)** — wait.shower_glass closing window. PM confirms install scheduled for Wed.

### Closeout (Days 70–75)

- **Day 70 (Wed Sep 30)** — `shower.glass_install` (0.5d, glazing) [CP] · `paint.phase_2` Day 1/1 (paint, crew 2) [CP] — final walls cut-in + roll. LAST work task on site. Gated on EVERY finish trade per Rule 4F.
- **Day 71 (Thu Oct 1)** — `paint.phase_2` finishes [CP] · **`milestone.substantial_completion`** fires · `closeout.client_walkthrough` (0.5d) — PM walks through with homeowner using Will's punch-list SOP; customer SIGNS the punch list to lock it.
- **Day 72 (Fri Oct 2)** — `closeout.punch_list_returns` Day 1/2 [CP] — trades return for flagged items.
- **Day 73 (Mon Oct 5)** — `closeout.punch_list_returns` Day 2/2 [CP].
- **Day 74 (Tue Oct 6)** — `closeout.final_clean` (1d, cleanup, crew 2) [CP].
- **Day 75 (Wed Oct 7)** — **INSPECTION: `inspect.final_bundled` (0.5d, ONE inspector) [CP]** — all finals (electrical + plumbing + HVAC) + final building in ONE visit per Rule 4M. PM on site. `milestone.co_handoff` fires (Certificate of Occupancy).
- **Day 76 (Thu Oct 8)** — `closeout.wills_walkthrough` (0.5d) [CP] — Will's personal final touchpoint with the customer. **Project ends.**

---

## Critical-path days (slip = total project slip)

Per `schedule.json:critical_path` (39 tasks, 41% of graph):

1. **TDEC gate (T-6 wk → Wed Jun 24)** — `permit.tdec_septic`. Floats until contract signs.
2. **On-site Day 1 (Thu Jun 25)** — `general.site_setup`.
3. **Day 2 (Fri Jun 26)** — `prep.heat_pump_relocate`.
4. **Day 5 (Wed Jul 1)** — `demo.protection`.
5. **Days 6–8 (Thu Jul 2 → Mon Jul 6)** — `demo.selective_demo` (3d).
6. **Day 9 (Tue Jul 7)** — `demo.haul_out`.
7. **Days 10–11 (Wed Jul 8 → Thu Jul 9)** — `excavation.dig`.
8. **Days 12–13 (Fri Jul 10 → Mon Jul 13)** — `foundation.form_and_prep`.
9. **Day 14 (Tue Jul 14)** — **INSPECTION: footing**.
10. **Day 15 (Wed Jul 15)** — `foundation.monolithic_pour`.
11. **Days 16–17 (Thu Jul 16 → Fri Jul 17)** — `foundation.cure`.
12. **Days 18–19 (Mon Jul 20 → Tue Jul 21)** — `framing.basement_walls`.
13. **Days 20–21 (Wed Jul 22 → Thu Jul 23)** — `framing.floor_system`.
14. **Days 22–24 (Fri Jul 24 → Tue Jul 28)** — `framing.exterior_walls`.
15. **Days 25–27 (Wed Jul 29 → Fri Jul 31)** — `framing.roof` (highest-CO-risk single bar — concealed tie-in).
16. **Day 28 (Mon Aug 3)** — `framing.sheathing` + `windows.install` start.
17. **Day 29 (Tue Aug 4)** — `roofing.underlayment` + `windows.install` finish.
18. **Days 30–33 (Wed Aug 5 → Mon Aug 10)** — `plumbing.rough_in` (4d Will-nominal floor).
19. **Day 34 (Tue Aug 11)** — `hvac.minisplit_rough`.
20. **Day 35 (Wed Aug 12)** — **INSPECTION: rough bundled**.
21. **Days 36–37 (Thu Aug 13 → Fri Aug 14)** — `buffer.post_rough_inspection`.
22. **Days 38–39 (Mon Aug 17 → Tue Aug 18)** — `insulation.air_seal` + `insulation.install`.
23. **Day 40 (Wed Aug 19)** — **INSPECTION: insulation**.
24. **Days 41–52 (Thu Aug 20 → Thu Sep 3)** — `drywall.consolidated` (11d, multi-zone).
25. **Day 53 (Fri Sep 4)** — `paint.phase_1`.
26. **Day 54 (Tue Sep 8)** — `tile.shower_substrate`.
27. **Days 55–59 (Wed Sep 9 → Tue Sep 15)** — `tile.shower_install` (5d).
28. **Days 60–61 (Wed Sep 16 → Thu Sep 17)** — `tile.grout_seal` + `shower.glass_template`.
29. **Days 62–69 (Fri Sep 18 → Tue Sep 29)** — `wait.shower_glass` (10 cal-d fab).
30. **Day 70 (Wed Sep 30)** — `shower.glass_install` + `paint.phase_2` Day 1.
31. **Day 71 (Thu Oct 1)** — `paint.phase_2` finishes + substantial completion + client walkthrough.
32. **Days 72–73 (Fri Oct 2 → Mon Oct 5)** — `closeout.punch_list_returns`.
33. **Day 74 (Tue Oct 6)** — `closeout.final_clean`.
34. **Day 75 (Wed Oct 7)** — **INSPECTION: final bundled** + CO.
35. **Day 76 (Thu Oct 8)** — Will's walkthrough.

**Inspection days (PM mandatory on site, per Will's audit):** Tue Jul 14 (footing) · Wed Aug 12 (rough bundled) · Wed Aug 19 (insulation) · Wed Oct 7 (final bundled).

---

## Totals

- **On-site working days:** 76 (Thu Jun 25 → Thu Oct 8, weekends + Jul 4 + Sep 7 excluded).
- **On-site calendar weeks:** ~15.
- **Pre-construction window:** 6 cal weeks (TDEC anchor, Wed May 13 → Wed Jun 24).
- **Signed-to-handoff:** ~21 cal weeks (TDEC kickoff → Will's walkthrough).
- **Critical path:** 39 of 94 tasks (41% — reflow warning flags possible over-parallelization).
- **Substantial completion → Will's walkthrough:** 5 working days (Thu Oct 1 → Thu Oct 8).

---

## Assumptions baked in (revisit when violated)

1. **TDEC clock starts on contract signing.** Round 2 PM interview: clock has NOT started; on-site Day 1 is floating. If the homeowner doesn't sign by ~6 cal-weeks before the target Jun 25 start (i.e. by Wed May 13), Day 1 slips 1:1 with the signing delay. The PEP narrative should treat on-site Day 1 as a function of signing date, not a fixed calendar date.
2. **Stick-framed roof, no truss procurement.** ~300 sqft footprint / 10' max wall / 3/12 pitch all fit within sub-800 sqft / sub-24' default per `stick_frame_default_for_small_additions`. Lumber arrives day-of with framing crew. If design phase pivots to engineered trusses, add `procurement.trusses` chain (28–42 cal-d) and re-anchor.
3. **Monolithic foundation pour** — footings + 4" slab same day per Rule 4B. Single footing inspection covers both. If scope pivots to stem walls / CMU foundation (rare), split into separate pour + cure + slab inspection (~3 extra working days).
4. **Existing gas WH stays.** Tankless WH optional package NOT accepted (Round 1). No `procurement.tank`, no `plumbing.tank_set`. Plumbing rough-in proceeds with no tank predecessor. If the homeowner reverses course, insert tank-set sequence BEFORE rough-in (+0.5d).
5. **Selections lock on Thu Jun 4 (T-3 wk).** Round 2 PM interview: vanity, faucets, mirrors, vanity lights, mini-split aesthetic, interior + pocket door styles, exterior door all still TBD. If `checkpoint.selections_finalized` slips, the cascade hits: tile (14-d) and windows (21-d) push, and the 1-week-before-install delivery target per Will's universal rule cascades into the on-site schedule.
6. **Concealed roof tie-in 3-cal-d buffer absorbs typical CO.** Round 1: PM accepted the buffer. If exposed rafter conditions exceed the buffer (e.g. structural changes triggering a CO), Day 25 onwards slips — open the existing ceiling EARLY on Day 25 (`framing.roof` Day 1) to maximize buffer usage.
7. **Existing main electrical service supports 100A subpanel.** `prep.amperage_check` on Thu Jun 4 verifies this. If amperage is insufficient, a service upgrade CO triggers BEFORE contract signing — re-baseline the entire schedule.
8. **Hall bath two-bucket pattern holds.** `early.acrylic_shower_swap` on Day 2 is the homeowner's "working shower" promise — landing it Day 2 is non-negotiable. The window infill + drywall patch + repaint stay in their separate `interior_finishes / hall_bath_mod` bucket (Day 41 framing roll-in + Day 54 repaint).
