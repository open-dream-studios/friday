# Project Execution Plan — Simons Addition (30'x10' Two-Story + Bedroom Remodel)

## Snapshot
- **Customer:** Simons (primary contact John; brother Tony is secondary point of contact per PM notes)
- **Scope:** 30'x10' two-story addition (basement storage + expanded primary bedroom + master bath) plus existing bedroom remodel and hall bath retrofit; ~789 sf footprint
- **Pre-construction start:** 2026-08-28 (TDEC septic permit fires)
- **On-site start:** 2026-10-12
- **Substantial completion:** 2026-12-28
- **Will's final walkthrough:** 2027-01-07
- **Contract value:** $100,778.92 ($45,167.59 labor / $52,171.33 materials / $3,440.00 equipment)
- **Total labor hours:** 1,287

## Critical path
The dominant gate is `permit.tdec_septic` — a 42-day calendar lead pinned to 2026-08-28. Miss that start and everything downstream slides day-for-day.

1. `permit.tdec_septic` — 2026-08-28 → 2026-10-09 (42 cal days)
2. `general.site_setup` — 2026-10-12 (0.5 d)
3. `prep.heat_pump_relocate` — 2026-10-12 → 2026-10-13 (1 d)
4. `demo.selective` — 2026-10-13 → 2026-10-15 (2 d)
5. `excavation.dig` — 2026-10-15 → 2026-10-19 (2 d)
6. `foundation.form_and_prep` — 2026-10-19 → 2026-10-20 (1.5 d)
7. `inspect.footing` — 2026-10-22 (0.5 d)
8. `foundation.monolithic_pour` — 2026-10-22 → 2026-10-23 (1 d)
9. `foundation.cure` — 2026-10-23 → 2026-10-27 (2 cal days)
10. `framing.floor_system` — 2026-10-27 → 2026-10-29 (2 d)
11. `framing.exterior_walls` — 2026-10-29 → 2026-11-04 (4 d)
12. `framing.roof` — 2026-11-04 → 2026-11-09 (3 d)
13. `framing.sheathing` — 2026-11-09 → 2026-11-10 (1.5 d)
14. `roofing.underlayment` — 2026-11-11 (1 d)
15. `plumbing.tank_set` — 2026-11-12 (0.5 d)
16. `plumbing.rough_in` — 2026-11-12 → 2026-11-17 (3 d)
17. `electrical.rough_in` — 2026-11-13 → 2026-11-18 (3 d)
18. `inspect.rough_bundled` — 2026-11-19 (0.5 d)
19. `buffer.post_rough_inspection` — 2026-11-20 → 2026-11-23 (2 cal days)
20. `insulation.install` — 2026-11-24 → 2026-11-25 (1.5 d)
21. `inspect.insulation` — 2026-11-30 (0.5 d)
22. `drywall.consolidated` — 2026-12-01 → 2026-12-08 (6 d)
23. `paint.phase_1` — 2026-12-09 (1 d)
24. `tile.shower_substrate` — 2026-12-10 → 2026-12-11 (2 d)
25. `tile.shower_set` — 2026-12-14 → 2026-12-16 (3 d)
26. `tile.grout_seal` — 2026-12-18 (1 d)
27. `plumbing.finish` — 2026-12-21 → 2026-12-22 (2 d)
28. `paint.phase_2` — 2026-12-23 (1 d)
29. `milestone.substantial_completion` — 2026-12-28
30. `closeout.pm_walkthrough` — 2026-12-28 (0.5 d)
31. `closeout.punch_list` — 2026-12-28 → 2026-12-30 (2 d)
32. `closeout.final_clean` — 2026-12-30 → 2026-12-31 (1 d)
33. `inspect.final_bundled` — 2027-01-05 (0.5 d)
34. `closeout.wills_walkthrough` — 2027-01-07 (0.5 d)

**Dominant gates:** TDEC septic (6-week lead, no float), footing inspection, bundled rough MEP inspection, insulation inspection, bundled final inspection. Any inspection slip pushes substantial completion.

## Phases

### Pre-Construction
**Dates:** 2026-08-28 → 2026-10-09

PM's job here is to lock TDEC septic in motion immediately, get customer selections closed by 2026-09-21, verify main service can accept the 100A subpanel, pull the walk-in permit three weeks out, and confirm demo/roof equipment reservations two weeks out. Tony gets a call 2026-10-08. Nothing on-site until this phase closes.

- `permit.tdec_septic` fires 2026-08-28 — this is the zero-float task; call TDEC day one.
- `general.permitting` walk-in 2026-09-21 (TCR gets same-day ~90%).
- `prep.amperage_check` 2026-09-21 — result must be in hand before `order.subpanel` fires.
- `checkpoint.selections_finalized` 2026-09-21 — tile, paint, fixtures, LVP, vanity locked. This gates five procurement chains.
- `checkpoint.equipment_confirmed_demo` and `checkpoint.equipment_confirmed_roof` on 2026-09-28.
- `pm.call_tony` on 2026-10-08 (2 days pre-start, per PM notes).

### Procurement & Long Leads
**Dates:** 2026-10-12 → 2026-11-02 (windows land last; drives dried-in)

Ten procurement chains fire off day-of on-site start. PM is chasing tracking numbers, confirming delivery windows, and staging materials. Windows are the constraining procurement — 21 supplier days land them 2026-11-02, which is exactly when framing wants them.

- `checkpoint.windows_arrived` 2026-11-02 — gates `windows.install`; only 0.5 days of float.
- `checkpoint.lvl_arrived` 2026-10-26 — gates `structural.install_lvl`.
- `checkpoint.subpanel_arrived` 2026-10-22 — gates `electrical.rough_in`.
- `checkpoint.tankless_arrived` 2026-10-22 — gates `plumbing.tank_set` (which precedes plumbing rough).
- `checkpoint.minisplit_arrived`, `checkpoint.tile_arrived` (10-29), `checkpoint.vanity_arrived`, `checkpoint.fixtures_arrived`, `checkpoint.flooring_arrived`, `checkpoint.shower_glass_arrived` — all land by 2026-10-29.
- Handoff into Site Prep is `general.site_setup` on the same 2026-10-12 day.

### Site Prep
**Dates:** 2026-10-12 → 2026-10-13

Kickoff day. Site protection and temp fencing go in the morning, then HVAC hits the yard to relocate the existing heat pump and disconnect box that sit inside the new footprint. This has to close before demo swings — no exceptions.

- `equipment.dumpster_arrive` day of demo (2026-10-12).
- `general.site_setup` complete 2026-10-12.
- `prep.heat_pump_relocate` complete 2026-10-13 — heat pump to new pad, disconnect re-mounted.

### Demolition & Protection
**Dates:** 2026-10-13 → 2026-10-16

Selective demo of the existing wall for addition tie-in plus hall bath demo — 3-person crew, 2 days. Then bearing wall gets exposed to open the LVL subchain. PM watches the demo like a hawk to document any concealed conditions the moment they show up.

- `demo.selective` 2026-10-13 → 2026-10-15.
- `demo.expose_bearing_wall` 2026-10-15 → 2026-10-16 (has 51 float days — non-critical, sequence with framing).

### Structural & Shell
**Dates:** 2026-10-15 → 2026-11-18

Longest phase. Excavation → monolithic foundation prep → footing inspection → pour → cure → floor system → two-story exterior walls + elevator shaft → roof frame → sheathing → underlayment → windows → shingles → WRB. Dried-in target 2026-11-13. Siding runs concurrent from 2026-11-13 to 2026-11-18. Windows have only 0.5 days of float — if 11-02 delivery slips a day, framing waits.

- `inspect.footing` 2026-10-22 (bundled with slab prep for monolithic pour).
- `foundation.cure` 2 cal days before floor system starts.
- `roof.concealed_buffer` — 3-day discovery window running concurrent with `framing.roof`. Document rafter conditions day 1.
- `milestone.dried_in` 2026-11-13 (shingles + windows + WRB). Interior comfort unlocks; MEPs already started upstream.
- Elevator shaft is framed only — 4x4 opening with 120V/30A stubbed. Verify no scope creep.

### Rough Trades
**Dates:** 2026-11-12 → 2026-11-18

Tank set first (per Rule 4H), then plumbing rough-in leads, electrical stacks in SS+1, mini-split line set slides in behind electrical. Two interior trades cap holds. PM enforces the sequence and keeps drywall staging clear.

- `plumbing.tank_set` 2026-11-12.
- `plumbing.rough_in` 2026-11-12 → 2026-11-17.
- `electrical.rough_in` 2026-11-13 → 2026-11-18 (subpanel + recessed + elevator dedicated circuit).
- `hvac.minisplit_rough` 2026-11-16.

### Rough Inspections
**Dates:** 2026-11-19 → 2026-11-23

One inspector, one bundled visit covering framing + rough MEPs, then a 2-day punch buffer for trades to correct. Zero float here — a red-tag pushes everything downstream.

- `inspect.rough_bundled` 2026-11-19.
- `buffer.post_rough_inspection` runs through the Thanksgiving week (holidays 2026-11-26 and 2026-11-27 already baked into the calendar).

### Insulation & Drywall
**Dates:** 2026-11-24 → 2026-12-09

Batts + air sealing → insulation inspection → consolidated drywall block (addition + existing bedroom + hall bath patch, 6 days) → paint phase 1 (prime + ceiling finish coat, same day). Paint order must be placed and delivered before 12-09.

- `inspect.insulation` 2026-11-30 — gates drywall start.
- `drywall.consolidated` 2026-12-01 → 2026-12-08.
- `paint.phase_1` 2026-12-09.

### Interior Finishes
**Dates:** 2026-12-09 → 2026-12-28

Master bath tile sequence (substrate → set → grout, 3 discrete blocks with cure gaps), LVP flooring, trim carpentry, vanity install, retrofit hall bath repaint and hallway switch patch. Paint phase 2 is the last work task — gates on every finish trade including the retrofit paint.

- `tile.shower_substrate` → `tile.shower_set` → `tile.grout_seal` (12-10 through 12-18, tile critical path).
- `flooring.install` 2026-12-14 → 2026-12-15.
- `trim.install` 2026-12-16 → 2026-12-18.
- `cabinets.install` (vanity) 2026-12-16.
- `retrofit.hall_bath_repaint` and `retrofit.hallway_switch_patch` land 2026-12-09.
- `paint.phase_2` 2026-12-23.
- `milestone.substantial_completion` 2026-12-28.

### Finish Trades
**Dates:** 2026-12-10 → 2026-12-22

Electrical finish → mini-split install → plumbing finish → shower glass install. Serialized to preserve 2-trade interior cap per Rule 4N.

- `electrical.finish` 2026-12-10 → 2026-12-11.
- `hvac.minisplit_install` 2026-12-14 (after electrical finish per Rule 4N).
- `plumbing.finish` 2026-12-21 → 2026-12-22.
- `shower.glass_install` 2026-12-21.

### Closeout
**Dates:** 2026-12-28 → 2027-01-07

PM walkthrough → punch list work → final clean → bundled final inspection → Will's walkthrough. Christmas holidays (12-24/25/26) already handled by calendar; final inspection lands 2027-01-05 with 2-day lag from final clean.

- `closeout.pm_walkthrough` 2026-12-28.
- `closeout.punch_list` 2026-12-28 → 2026-12-30.
- `closeout.final_clean` 2026-12-30 → 2026-12-31.
- `inspect.final_bundled` 2027-01-05.
- `closeout.wills_walkthrough` 2027-01-07 — Will's personal customer handoff; last task on schedule.

## Long-lead procurement

| Task | Lead | Order-by | Arrival gate | Consumer |
|---|---|---|---|---|
| `permit.tdec_septic` | 42 cal | 2026-08-28 | 2026-10-09 | `general.site_setup`, `excavation.dig` |
| `order.windows` → `wait.windows` | 21 cal | 2026-10-12 | `checkpoint.windows_arrived` 2026-11-02 | `windows.install` (0.5 d float — TIGHT) |
| `order.lvl` → `wait.lvl` | 14 cal | 2026-10-12 | `checkpoint.lvl_arrived` 2026-10-26 | `structural.install_lvl` |
| `order.subpanel` → `wait.subpanel` | 10 cal | 2026-10-12 (after amperage check) | `checkpoint.subpanel_arrived` 2026-10-22 | `electrical.rough_in` |
| `order.tankless` → `wait.tankless` | 10 cal | 2026-10-12 | `checkpoint.tankless_arrived` 2026-10-22 | `plumbing.tank_set` (critical path) |
| `order.minisplit` → `wait.minisplit` | 10 cal | 2026-10-12 | `checkpoint.minisplit_arrived` 2026-10-22 | `hvac.minisplit_install` |
| `order.tile` → `wait.tile` | 18 cal | 2026-10-12 (after selections) | `checkpoint.tile_arrived` 2026-10-29 | `tile.shower_substrate` |
| `order.vanity` → `wait.vanity` | 14 cal | 2026-10-12 | `checkpoint.vanity_arrived` 2026-10-26 | `cabinets.install` |
| `order.fixtures` → `wait.fixtures` | 10 cal | 2026-10-12 | `checkpoint.fixtures_arrived` 2026-10-22 | `plumbing.finish` |
| `order.flooring` → `wait.flooring` | 10 cal | 2026-10-12 | `checkpoint.flooring_arrived` 2026-10-22 | `flooring.install` |
| `order.paint` | short | 2026-10-12 | delivered before 12-09 | `paint.phase_1` |
| `order.shower_glass` → `wait.shower_glass` | 10 cal | 2026-10-12 | `checkpoint.shower_glass_arrived` 2026-10-22 | `shower.glass_install` |

## Inspections

| Task | Date | Gates | Pre-inspection prep |
|---|---|---|---|
| `inspect.footing` | 2026-10-22 | `foundation.monolithic_pour` | Footings formed, gravel + vapor + rebar placed, slab prep complete (monolithic). Call inspector day prior. |
| `inspect.rough_bundled` | 2026-11-19 | `buffer.post_rough_inspection` → insulation | All three rough MEPs plus framing ready simultaneously. Walk site with each trade the afternoon of 11-18 — nail plates on, straps set, no unsupported wire, tank set stubbed. |
| `inspect.insulation` | 2026-11-30 | `drywall.consolidated` | Batts full-depth in all cavities, air-sealing complete at penetrations, top plates sealed. Camera-walk the site 11-25. |
| `inspect.final_bundled` | 2027-01-05 | `closeout.wills_walkthrough` | Punch list clean, final clean done, all trades' finals ready in one bundled visit. GFCI/AFCI verified, plumbing tested, mini-split running, subpanel labeled. |

## Risk register

- [ ] **TDEC septic delay** — Zero float. If TDEC misses 42-day turn, on-site start slides day-for-day. PM must confirm application received and log expected date within week 1 of pre-construction.
- [ ] **Windows delivery slip** — Only 0.5 days of float on `windows.install`. PM confirms shipping status by 2026-10-26 and again 2026-10-30. Any slip past 11-02 stalls framing.
- [ ] **Concealed roof tie-in** — 3/12 new pitch tying into existing 6/12; saddle detail being produced by Tri-State (John Beaver PE) by 7/22. PM documents existing rafter conditions on day 1 of `framing.roof` (2026-11-04). Any concealed condition triggers change-order fast — buffer of 3 days is baked in but not unlimited.
- [ ] **Subpanel amperage fails** — If `prep.amperage_check` shows existing service can't accept subpanel, service upgrade change order fires before contract lock. PM must not release `order.subpanel` until amperage check clean.
- [ ] **Weather on shell** — Roofing (2026-11-11 → 2026-11-12) and siding (2026-11-13 → 2026-11-18) fall mid-November. No weather days modeled. Watch 7-day forecast starting 2026-11-05; add tarps/buffer if wet week.
- [ ] **Hall bath return-to-stock timing** — $4,199 credit hinges on existing tub/tile/vanity/mirror/hardware returning cleanly to Ferguson. Coordinate return before demo swings.
- [ ] **Elevator shaft scope drift** — Framed only per contract. 4x4 opening + 120V/30A stubbed. Confirm with John there's no expectation of additional shaft work.
- [ ] **Tony contact** — PM notes require Tony call 2 days pre-start. Missed call = customer trust hit. Calendar it now for 2026-10-08.
- [ ] **Selections slip past 2026-09-21** — Five procurement chains gated on selections. A one-day slip is one-day slip on tile/vanity/fixtures/flooring/paint arrival.
- [ ] **Thanksgiving compression** — `buffer.post_rough_inspection` straddles 2026-11-26/27 holidays. Trades disappear the last week of November — get punch corrections closed by 2026-11-25.

## PM daily runsheet

### Day 1 (2026-10-12)
- Kick off site protection with GC crew (`general.site_setup`).
- Confirm dumpster on site (`equipment.dumpster_arrive`).
- Confirm HVAC crew arrival for heat pump relocation.
- Place all 10 procurement orders same morning (`order.windows`, `order.lvl`, `order.subpanel`, `order.minisplit`, `order.tankless`, `order.tile`, `order.vanity`, `order.fixtures`, `order.flooring`, `order.paint`, `order.shower_glass`).
- Log all supplier confirmation numbers.
- Verify TDEC final permit in hand from pre-con.
- Photo baseline: full property exterior, staging area, existing HVAC location, existing hall bath.

### Day of `inspect.rough_bundled` (2026-11-19)
- Walk all four scopes AM before inspector arrives: framing (nail plates, straps, headers), plumbing (tank set, vents, DWV, supply, pressure test), electrical (box heights, staples, subpanel bonding, elevator circuit), HVAC (line set, condensate).
- Confirm rough drawings on site for inspector.
- Confirm concealed roof tie-in documentation ready in case of question.
- Trades on-call for immediate corrections.
- After inspection: brief each trade on any callouts; schedule punch work into the 2-day buffer.

### Substantial completion (2026-12-28)
- Walk full site with customer AM (`closeout.pm_walkthrough`).
- Produce written punch list; assign trade + due date to each item.
- Confirm all finish materials/paint touch-up kits staged for punch crew.
- Trigger `closeout.punch_list` PM.
- Calendar `inspect.final_bundled` for 2027-01-05 with inspector (schedule now to protect date).
- Prep Will's walkthrough packet (warranty docs, 1-year drywall crack callback note, maintenance sheet for mini-split and tankless) for 2027-01-07.