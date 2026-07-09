---
generation_kind: daily_schedule_v2
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWFF6ZQ82D651FWRN1RBJA72/jobs/308-evergreen-street-addition_JOB-01KWFF8CWBQKYGA4Z64XF143EY/generations/task_graph.json
  - _projects/308-evergreen-street_APPPROJ-01KWFF6ZQ82D651FWRN1RBJA72/jobs/308-evergreen-street-addition_JOB-01KWFF8CWBQKYGA4Z64XF143EY/generations/schedule.json
  - _projects/308-evergreen-street_APPPROJ-01KWFF6ZQ82D651FWRN1RBJA72/jobs/308-evergreen-street-addition_JOB-01KWFF8CWBQKYGA4Z64XF143EY/intelligence/confirmed.md
  - _projects/308-evergreen-street_APPPROJ-01KWFF6ZQ82D651FWRN1RBJA72/jobs/308-evergreen-street-addition_JOB-01KWFF8CWBQKYGA4Z64XF143EY/intelligence/applicable_rules.json
last_verified_at: "2026-07-01T18:54:41.671Z"
---

# Daily schedule — 308 Evergreen Street Addition

On-site window: **2026-07-01 (Wed) → 2026-10-05 (Mon)** — 68 working days across 14 calendar weeks. Pre-construction runway starts 2026-06-10 (Wed), 15 working days ahead of Day 1.

## Pre-construction runway (T-weeks)

Runway anchored on the two longest pre-con offsets (both 15 working days) plus their lead-up windows. All items complete by 2026-06-30, one working day before on-site kickoff.

- **T-3w (Wed 2026-06-10):** `permit.building` — Building permit application + issuance (pm; dev_rules §4A, 15wd offset, 2wd lead-up).
  - Preparing: application packet + plans set assembled, fee cut, submitted to Washington Co. TN permit office.
- **T-3w (Wed 2026-06-10):** `prep.tdec_septic_inspection` — TDEC septic inspection, capacity confirmation only (pm; 15wd offset, 2wd lead-up).
  - Preparing: schedule TDEC inspector, pull septic as-built if available. *(existing septic stays — inspection-only per confirmed round 1 q.sewer_septic_direction)*
- **T-3w (Wed 2026-06-10):** `prep.amperage_check` — Existing service amperage check before panel order (electrical; 15wd offset, 2wd lead-up, `_company/rules/service_amperage_check.md`).
  - Preparing: electrician site visit scheduled; verify existing panel size to gate 100A subpanel order + mini-split load.
- **T-3w (Wed 2026-06-10):** `checkpoint.selections_finalized` — finishes, tile, LVT, vanity, fixtures (milestone; dev_rules §4P, 15wd offset, 5wd lead-up).
  - Preparing (T-4w window, 2026-06-03 → 2026-06-09): design meeting, allowance walk with customer, tile + LVT + vanity picks locked, fixture SKUs recorded. Gates tile / doors / windows orders.
- **T-2w (Wed 2026-06-17):** `checkpoint.equipment_confirmed` — mini-split, subpanel, exterior door, vanity spec sheets confirmed (milestone; dev_rules §4P, 10wd offset, 5wd lead-up).
  - Preparing (2026-06-10 → 2026-06-16): pull spec sheets from suppliers, confirm cut dimensions, sign off. Gates mini-split / subpanel / doors orders.
- **T-1w:** slack week for any pre-con slip absorption before Day 1.

Long-lead procurement fires as soon as its upstream checkpoint hits; the earliest on-site-adjacent order (LVL) drops 2026-07-07 (on-site Day 5) since LVL doesn't wait on either checkpoint.

## On-site Day 1 → Day 68

_Format: `Day N (Weekday YYYY-MM-DD)` · active tasks (trade). Critical-path days marked with ★. `[off-site]` = procurement events (order placed / arrival) that do not consume field labor but anchor gates._

**Day 1 (Wed 2026-07-01)** ★ — `early.acrylic_shower_swap` (plumbing, 1d) · `prep.relocate_heat_pump` (hvac, 1d). Two-bucket customer-early kickoff per dev_rules §4V; heat pump also relocated Day 1 to open the 3-wd lag before demo (§4K).
Day 2 (Thu 2026-07-02) — idle on-site: 3-wd cure/setback lag between heat pump relocation and demo (§4K).
Day 3 (Fri 2026-07-03) — idle on-site: lag continues.
_(Sat 2026-07-04 — Independence Day observance; no work.)_
Day 4 (Mon 2026-07-06) — idle on-site: lag tail; PM should use this day to stage demo dumpster + backhoe.
**Day 5 (Tue 2026-07-07)** ★ — `site.demo` day 1 of 2 (demo, 3 crew): sawcut walkway, remove railroad ties, clear site. `procurement.lvl.order` [off-site] (pm) — LVL 3-ply 14" placed with supplier, 7–14 cal-d wait begins.
**Day 6 (Wed 2026-07-08)** ★ — `site.demo` day 2 (demo).
**Day 7 (Thu 2026-07-09)** ★ — `foundation.excavate` day 1 of 2 (excavation, 2 crew). Backhoe on site.
**Day 8 (Fri 2026-07-10)** ★ — `foundation.excavate` day 2 (excavation).
> Preparing: schedule TN foundation inspector for Monday's pre-pour walk (lead_up_working_days=1 for `inspect.foundation`).
**Day 9 (Mon 2026-07-13)** ★ — `foundation.footings_slab_pour` day 1 of 2 (concrete, 3 crew): monolithic 12×12 footings + 4" slab. **`inspect.foundation`** (inspector, SS with pour, 0.5d).
> ⚠ PM required on site.
`procurement.doors.order` [off-site] (pm) — 3× pre-hung panel + 1× pocket door frame + 1 exterior door placed; 10 cal-d wait.
**Day 10 (Tue 2026-07-14)** ★ — `foundation.footings_slab_pour` day 2 (concrete).
Day 11 (Wed 2026-07-15) — idle on-site: 3-wd slab-cure lag before LVL install begins.
Day 12 (Thu 2026-07-16) — idle on-site: cure lag continues; LVL still in supplier lead-time.
Day 13 (Fri 2026-07-17) — idle on-site: cure lag tail; LVL wait ends today.
**Day 14 (Mon 2026-07-20)** ★ — `structural.lvl_install` day 1 of 2 (framing, 3 crew): 3-ply 14" LVL + temp shoring, open existing bearing wall. `procurement.lvl.arrived` [off-site] milestone. `procurement.windows.order` [off-site] (pm) — 2 new windows (3'×3' DH + 3'×1' transom) placed with 18 cal-d wait.
**Day 15 (Tue 2026-07-21)** ★ — `structural.lvl_install` day 2 (framing).
**Day 16 (Wed 2026-07-22)** ★ — `framing.floor_system` day 1 of 2 (framing, 3 crew): glued & fastened subfloor.
**Day 17 (Thu 2026-07-23)** ★ — `framing.floor_system` day 2 (framing).
**Day 18 (Fri 2026-07-24)** ★ — `framing.walls` day 1 of 5 (framing, 3 crew): exterior + interior walls both levels, elevator shaft + pocket-door frame rough-in. `procurement.doors.arrived` [off-site] milestone — pocket-door frame on site, hard gate satisfied.
**Day 19 (Mon 2026-07-27)** ★ — `framing.walls` day 2 (framing).
**Day 20 (Tue 2026-07-28)** ★ — `framing.walls` day 3 (framing) · `framing.tie_in_discovery` day 1 of 2 (framing, SS+2 overlap per `retrofit_tie_in_discovery`): chimney envelope, 3/12↔6/12 tie-in, window/door relocation framing.
**Day 21 (Wed 2026-07-29)** ★ — `framing.walls` day 4 (framing) · `framing.tie_in_discovery` day 2 (framing).
**Day 22 (Thu 2026-07-30)** ★ — `framing.walls` day 5 (framing).
**Day 23 (Fri 2026-07-31)** ★ — `framing.roof` day 1 of 3 (framing, 3 crew): stick-frame 3/12 gable tying to existing 6/12 (no truss — belief `stick_frame_default_for_small_additions`). `procurement.subpanel.order` [off-site] (pm) — 100A subpanel released; amperage check pre-req satisfied.
**Day 24 (Mon 2026-08-03)** ★ — `framing.roof` day 2 (framing).
**Day 25 (Tue 2026-08-04)** ★ — `framing.roof` day 3 (framing).
**Day 26 (Wed 2026-08-05)** ★ — `roofing.sheathing` (framing, 3 crew, 1d): roof sheathing + wall WRB.
**Day 27 (Thu 2026-08-06)** ★ — `roofing.underlayment` (roofing, 2 crew, 1d): synthetic underlayment + drip edge + temp dry-in. Unlocks windows/MEPs (§4I) and siding (`siding_starts_at_underlayment`).
**Day 28 (Fri 2026-08-07)** ★ — `windows.install` day 1 of 2 (windows_doors, 2 crew): install 2 new + relocate 2 existing + set exterior door. `roofing.shingles` day 1 of 2 (roofing, 2 crew, same crew as underlayment — serialized per `roof_and_siding_same_crew`). `procurement.windows.arrived` [off-site] milestone.
**Day 29 (Mon 2026-08-10)** ★ — `windows.install` day 2 (windows_doors). `roofing.shingles` day 2 (roofing): architectural shingles, valleys, chimney cricket, ridge vent.
**Day 30 (Tue 2026-08-11)** ★ — `milestone.dried_in` (pm, informational). `siding.install` day 1 of 3 (siding, 2 crew — same crew as roof, serialized): vinyl lap, ALL exterior (no brick veneer per round 1 q.brick_veneer_scope). ★ `plumbing.rough` day 1 of 4 (plumbing, 2 crew): supply/waste/vent, master bath, W/D relocate, gas WH vent extension.
**Day 31 (Wed 2026-08-12)** ★ — `siding.install` day 2 (siding). `exterior.trim_gutters` (siding, 2 crew, SS+1 overlap): fascia, soffit, seamless gutters. ★ `plumbing.rough` day 2 (plumbing).
**Day 32 (Thu 2026-08-13)** ★ — `siding.install` day 3 (siding). ★ `plumbing.rough` day 3 (plumbing). ★ `electrical.rough` day 1 of 3 (electrical, 2 crew, SS+2 from plumbing per §4N): subpanel install, receptacles, lighting, 30A elevator circuit. `procurement.subpanel.arrived` [off-site] milestone.
**Day 33 (Fri 2026-08-14)** ★ — ★ `plumbing.rough` day 4 (plumbing). ★ `electrical.rough` day 2 (electrical).
**Day 34 (Mon 2026-08-17)** ★ — ★ `electrical.rough` day 3 (electrical).
> Preparing: schedule TN bundled rough inspector for Tuesday (lead_up_working_days=1 for `inspect.rough_bundled`, dev_rules §4C).
**Day 35 (Tue 2026-08-18)** ★ — ★ `hvac.mini_split_rough` (hvac, 1 crew, 0.5d): line-set + condensate, LAST in MEP sequence per §4G. **`inspect.rough_bundled`** day 1 of 1 (inspector, 1d): framing + plumbing + electrical + HVAC bundled.
> ⚠ PM required on site.
**Day 36 (Wed 2026-08-19)** ★ — **`inspect.rough_bundled`** wraps (paperwork; end date 08-19). ★ `punch.rough_buffer` day 1 of 2 (general): address any red-tags before insulation.
**Day 37 (Thu 2026-08-20)** ★ — ★ `punch.rough_buffer` day 2 (general).
**Day 38 (Fri 2026-08-21)** ★ — ★ `insulation.install` day 1 of 2 (insulation, 2 crew): R13 walls, R30 attic, R30 floor + air seal. `procurement.tile.order` [off-site] (pm) — master bath tile + waterproofing released with 14 cal-d wait.
**Day 39 (Mon 2026-08-24)** ★ — ★ `insulation.install` day 2 (insulation).
> Preparing: schedule TN insulation inspector for Tuesday (lead_up_working_days=1 for `inspect.insulation`); drywall crew calendared per belief `drywall_soft_schedule`.
**Day 40 (Tue 2026-08-25)** ★ — **`inspect.insulation`** (inspector, 0.5d).
> ⚠ PM required on site.
**Day 41 (Wed 2026-08-26)** ★ — ★ `drywall.hang_finish` day 1 of 6 (drywall, 3 crew): hang + 3-coat compound + sand to L3.
**Day 42 (Thu 2026-08-27)** ★ — ★ `drywall.hang_finish` day 2 (drywall).
**Day 43 (Fri 2026-08-28)** ★ — ★ `drywall.hang_finish` day 3 (drywall).
**Day 44 (Mon 2026-08-31)** ★ — ★ `drywall.hang_finish` day 4 (drywall).
**Day 45 (Tue 2026-09-01)** ★ — ★ `drywall.hang_finish` day 5 (drywall).
**Day 46 (Wed 2026-09-02)** ★ — ★ `drywall.hang_finish` day 6 (drywall).
**Day 47 (Thu 2026-09-03)** ★ — ★ `paint.phase_1` day 1 of 2 (paint, 2 crew): primer + ceilings per dev_rules §4E.
**Day 48 (Fri 2026-09-04)** ★ — ★ `paint.phase_1` day 2 (paint).
_(Mon 2026-09-07 — Labor Day; no work.)_
**Day 49 (Tue 2026-09-08)** ★ — `hall_bath.finish` day 1 of 2 (general, 2 crew — off critical path, float 10d): window infill, insulate, drywall patch, PVC trim, repaint (round 1 q.hall_bath_acrylic_shower_timing: acrylic swap was Day 1). ★ `master_bath.tile_shower` day 1 of 4 (tile, 2 crew): waterproof + wall tile + mosaic floor + niche + bench. `procurement.tile.arrived` [off-site] milestone.
**Day 50 (Wed 2026-09-09)** ★ — `hall_bath.finish` day 2 (general). ★ `master_bath.tile_shower` day 2 (tile).
**Day 51 (Thu 2026-09-10)** ★ — ★ `master_bath.tile_shower` day 3 (tile). `procurement.mini_split.order` [off-site] (pm) — mini-split released with 7–14 cal-d wait.
**Day 52 (Fri 2026-09-11)** ★ — ★ `master_bath.tile_shower` day 4 (tile).
**Day 53 (Mon 2026-09-14)** ★ — ★ `flooring.lvt` day 1 of 2 (flooring, 2 crew): LVT throughout ($3/sqft). Precedes trim per §4L.
**Day 54 (Tue 2026-09-15)** ★ — ★ `flooring.lvt` day 2 (flooring).
**Day 55 (Wed 2026-09-16)** ★ — ★ `trim.install` day 1 of 3 (trim_carpentry, 2 crew): 5-1/4" base + 2-1/4" casing + hang 3 panel + 1 pocket door.
**Day 56 (Thu 2026-09-17)** ★ — ★ `trim.install` day 2 (trim_carpentry).
**Day 57 (Fri 2026-09-18)** ★ — ★ `trim.install` day 3 (trim_carpentry).
**Day 58 (Mon 2026-09-21)** ★ — ★ `electrical.finish` day 1 of 2 (electrical, 2 crew): devices, ~12 recessed, vanity lights, fan/light, GFCI/AFCI. `plumbing.finish` day 1 of 2 (plumbing, 2 crew, float 1d): 72" double vanity, 2 faucets, commode, shower valve trim.
**Day 59 (Tue 2026-09-22)** ★ — ★ `electrical.finish` day 2 (electrical). `plumbing.finish` day 2 (plumbing).
**Day 60 (Wed 2026-09-23)** ★ — ★ `hvac.mini_split_install` (hvac, 1 crew, 1d): head + condenser + commissioning per §4G. `procurement.mini_split.arrived` [off-site] milestone.
**Day 61 (Thu 2026-09-24)** ★ — ★ `paint.phase_2` day 1 of 3 (paint, 2 crew): finish coats (2) + trim touch-up, gates on ALL finish trades (§4E/4F).
**Day 62 (Fri 2026-09-25)** ★ — ★ `paint.phase_2` day 2 (paint).
**Day 63 (Mon 2026-09-28)** ★ — ★ `paint.phase_2` day 3 (paint).
> Preparing: schedule TN final inspector for Tuesday (lead_up_working_days=1 for `inspect.final`).
**Day 64 (Tue 2026-09-29)** ★ — **`inspect.final`** (inspector, 1d): building + electrical + plumbing + HVAC final, bundled.
> ⚠ PM required on site.
**Day 65 (Wed 2026-09-30)** ★ — ★ `punch.closeout` day 1 of 3 (general, 2 crew): punch list.
**Day 66 (Thu 2026-10-01)** ★ — ★ `punch.closeout` day 2 (general): final cleaning.
**Day 67 (Fri 2026-10-02)** ★ — ★ `punch.closeout` day 3 (general): customer walkthrough with Will.
**Day 68 (Mon 2026-10-05)** ★ — ★ `milestone.substantial_completion` (pm) — balance due per scope terms.

## Critical-path days

Critical-path tasks (from `task_graph.json.critical_path[]` and `schedule.json.critical_path[]`). Any slip = total-project slip.

- **Day 1 (2026-07-01):** `prep.relocate_heat_pump` — opens the 3-wd lag before demo can start.
- **Days 5–6 (2026-07-07 → 07-08):** `site.demo` — 2 crew-days, gates excavation.
- **Days 7–8 (2026-07-09 → 07-10):** `foundation.excavate` — gates the pour.
- **Days 9–10 (2026-07-13 → 07-14):** `foundation.footings_slab_pour` — critical pour day; carries 3-wd cure lag afterward.
- **Days 14–15 (2026-07-20 → 07-21):** `structural.lvl_install` — LVL arrival gates this; opens bearing wall.
- **Days 16–17 (2026-07-22 → 07-23):** `framing.floor_system`.
- **Days 18–22 (2026-07-24 → 07-30):** `framing.walls` — 5 crew-days, densest framing block; pocket-door frame installed here.
- **Days 23–25 (2026-07-31 → 08-04):** `framing.roof` — stick-frame gable + tie-in.
- **Day 26 (2026-08-05):** `roofing.sheathing`.
- **Day 27 (2026-08-06):** `roofing.underlayment` — dry-in gate; unlocks windows + MEPs + siding.
- **Days 28–29 (2026-08-07 → 08-10):** `windows.install` — critical for MEP unblock.
- **Days 30–33 (2026-08-11 → 08-14):** `plumbing.rough` — 4 crew-days at hard rule floor (round 1 q.plumbing_rough_labor_floor).
- **Days 32–34 (2026-08-13 → 08-17):** `electrical.rough` — SS+2 stagger from plumbing.
- **Day 35 (2026-08-18):** `hvac.mini_split_rough` — LAST in MEP sequence + rough inspection first day.
- **Days 35–36 (2026-08-18 → 08-19):** `inspect.rough_bundled` — one inspector, one day, all trades.
- **Days 36–38 (2026-08-19 → 08-21):** `punch.rough_buffer` — 2-wd buffer before insulation.
- **Days 38–40 (2026-08-21 → 08-25):** `insulation.install` + `inspect.insulation` — soft-schedule gate for drywall crew.
- **Days 41–46 (2026-08-26 → 09-02):** `drywall.hang_finish` — 6-day block; longest single critical task.
- **Days 47–48 (2026-09-03 → 09-04):** `paint.phase_1`.
- **Days 49–52 (2026-09-08 → 09-11):** `master_bath.tile_shower` — 4-day tile block gating flooring.
- **Days 53–54 (2026-09-14 → 09-15):** `flooring.lvt`.
- **Days 55–57 (2026-09-16 → 09-18):** `trim.install`.
- **Days 58–59 (2026-09-21 → 09-22):** `electrical.finish`.
- **Day 60 (2026-09-23):** `hvac.mini_split_install`.
- **Days 61–63 (2026-09-24 → 09-28):** `paint.phase_2` — every finish trade must be complete first (§4E/4F).
- **Day 64 (2026-09-29):** `inspect.final`.
- **Days 65–67 (2026-09-30 → 10-02):** `punch.closeout`.
- **Day 68 (2026-10-05):** `milestone.substantial_completion`.

## Totals

- **On-site working days:** 68 (2026-07-01 → 2026-10-05, Mon-Fri, minus 2026-07-04 Independence Day observance and 2026-09-07 Labor Day)
- **Calendar weeks (on-site):** ≈14.3 wks
- **Signed-to-handoff weeks:** pre-con runway 3 wks + on-site 14.3 wks ≈ **17.3 weeks** from checkpoint kickoff (2026-06-10) to substantial completion (2026-10-05). If signed contract precedes checkpoint kickoff by any margin, add that to the front.

## Assumptions baked in (revisit when violated)

- **Roof is stick-framed, no truss procurement.** *(round 1 q.interior_doors_pocket_vs_panel context + belief `stick_frame_default_for_small_additions`; scope was ambiguous "truss OR rafter" and the 295 sqft/level × ~10 ft span defaults to stick.)* If wrong, add a 14–28 cal-d truss procurement chain ahead of `framing.roof` — Days 23–25 slip right by that lead time.
- **Existing septic stays; TDEC inspection only.** *(round 1, q.sewer_septic_direction: "Existing septic stays; TDEC inspection only (confirms capacity)".)* If wrong (septic install or grinder pump required), rule `tdec_septic_permit_offset` fires with 30-wd pre-con offset + 42-cal-d permit wait — pre-con runway blows out to ≥8 weeks and Day 1 shifts.
- **Existing gas water heater remains; tankless Optional Package not elected.** *(round 1, q.tankless_water_heater_election: "Not elected — keep existing gas WH; only vent extension".)* If wrong, `plumbing.tank_set` returns and plumbing.rough duration bumps; Day 30–33 block widens.
- **Brick veneer is out — 100% vinyl lap siding.** *(round 1, q.brick_veneer_scope: "the design was updated, all cladding is vinyl lap siding".)* If wrong, add masonry crew days between `windows.install` and `siding.install` — Day 30 siding start delays and roof/siding same-crew serialization no longer applies cleanly.
- **Hall-bath acrylic shower swap runs Day 1 as customer-early.** *(round 1, q.hall_bath_acrylic_shower_timing: "Customer-requested early item — acrylic shower swap runs Day 1 before demo".)* If wrong (customer OK with mid-job hall-bath work), the two-bucket collapses and Day 1 loses its off-critical work — no schedule slip, but plumbing crew Day 1 vanishes.
- **Interior doors: 3 pre-hung panel + 1 pocket door (hall-bath entry).** *(round 1, q.interior_doors_pocket_vs_panel: "3 pre-hung panel + 1 pocket".)* If wrong (more pockets, or all panel), `procurement.doors.order` line items shift and Day 18 pocket-frame gate on `framing.walls` may not exist.
- **Plumbing rough floored to 4 crew-days × 2 = 64 hrs.** *(round 1, q.plumbing_rough_labor_floor: "Reprice CSV plumbing labor to Will's nominal — 4d × 2 crew = 64 hrs" per company rule `plumbing_rough_min_duration`.)* If wrong (CSV's 40 hrs stands), Day 33 collapses and `electrical.rough` SS+2 shifts left by 1 wd — the whole finish tail slides earlier by that day.
