# Project Execution Plan — Simons Addition (30'×10' Two-Story Bedroom)

## Snapshot
- **Customer:** John Simons (brother Zach — call day before on-site start)
- **Project:** 30'×10' two-story addition — basement storage below, primary bedroom + master bath + walk-in closet above; future 4'×4' elevator shaft framed
- **Pre-construction start:** 2026-08-28
- **On-site start:** 2026-10-12
- **Substantial completion:** 2026-12-23
- **Final walkthrough / project end:** 2027-01-06
- **On-site duration:** ~12 working weeks
- **Contract value:** $100,778.92 (labor $45,167.59 / materials $52,171.33 / equipment $3,440.00 / 1,287 labor hours)

## Critical path

The chain runs day-1 site setup → demo → foundation → framing → dry-in → rough plumbing → rough inspection → drywall → tile → plumbing finish → paint 2 → punch → final inspection → Will's walkthrough. There is no float on this spine.

| # | Task | Date | Duration |
|---|------|------|----------|
| 1 | `equipment.dumpster_arrive` | 2026-10-12 | 0.5 d |
| 2 | `general.site_setup` | 2026-10-12 | 0.5 d |
| 3 | `prep.heat_pump_relocate` | 2026-10-13 | 1 d |
| 4 | `demo.walkway_and_obstructions` | 2026-10-16 | 1 d |
| 5 | `demo.expose_bearing_wall` | 2026-10-19 | 1 d |
| 6 | `demo.haul_out` | 2026-10-20 | 0.5 d |
| 7 | `equipment.mini_ex_arrive` | 2026-10-20 | 0.5 d |
| 8 | `excavation.dig` | 2026-10-21 → 10-22 | 2 d |
| 9 | `foundation.form_and_prep` | 2026-10-23 → 10-26 | 1.5 d |
| 10 | `inspect.footing` | 2026-10-27 | 0.5 d |
| 11 | `foundation.monolithic_pour` | 2026-10-28 | 1 d |
| 12 | `foundation.cure` | 2026-10-29 → 10-30 | 2 d cure |
| 13 | `framing.floor_system` | 2026-11-02 → 11-03 | 2 d |
| 14 | `framing.exterior_walls` | 2026-11-04 → 11-06 | 3 d |
| 15 | `framing.roof` | 2026-11-09 → 11-11 | 3 d |
| 16 | `framing.sheathing` | 2026-11-12 | 1 d |
| 17 | `windows.install` | 2026-11-12 → 11-13 | 2 d |
| 18 | `roofing.underlayment` | 2026-11-13 | 1 d |
| 19 | `plumbing.tank_set` | 2026-11-16 | 0.5 d |
| 20 | `plumbing.rough_in` | 2026-11-16 → 11-19 | 3 d |
| 21 | `inspect.rough_bundled` | 2026-11-20 | 0.5 d |
| 22 | `buffer.post_rough_inspection` | 2026-11-23 → 11-24 | 2 d |
| 23 | `insulation.install` | 2026-11-25 | 1 d |
| 24 | `inspect.insulation` | 2026-12-01 | 0.5 d |
| 25 | `equipment.drywall_dumpster` | 2026-12-01 | 0.5 d |
| 26 | `drywall.consolidated` | 2026-12-02 → 12-08 | 5 d |
| 27 | `paint.phase_1` | 2026-12-09 | 1 d |
| 28 | `tile.shower_substrate` | 2026-12-10 → 12-11 | 1.5 d |
| 29 | `tile.shower_walls_floor` | 2026-12-11 → 12-16 | 3 d |
| 30 | `tile.grout_seal` | 2026-12-17 → 12-18 | 1 d |
| 31 | `plumbing.finish` | 2026-12-18 → 12-21 | 1.5 d |
| 32 | `paint.phase_2` | 2026-12-22 | 1 d |
| 33 | `milestone.substantial_completion` | 2026-12-23 | — |
| 34 | `closeout.pm_walkthrough` | 2026-12-23 | 0.5 d |
| 35 | `closeout.punch_list_work` | 2026-12-23 → 12-29 | 2 d |
| 36 | `closeout.final_clean` | 2026-12-29 → 12-30 | 1 d |
| 37 | `inspect.final_bundled` | 2027-01-04 | 0.5 d |
| 38 | `closeout.wills_walkthrough` | 2027-01-06 | 0.5 d |

> ⚠ **TDEC septic permit gates excavation.** `permit.tdec_septic` has only 7 days of float — must be submitted by 2026-08-28 or excavation slips and the entire critical path shifts.

> ⚠ **Rough MEP → bundled inspection is the pinch.** `plumbing.rough_in` (2026-11-16 → 11-19) sits on zero-float. Any slip past 11-19 pushes `inspect.rough_bundled` and cascades through drywall, tile, and closeout.

> ⚠ **Tile chain dominates the finish half.** From 12-10 (substrate) to 12-18 (grout) is a zero-float 6-working-day block that feeds plumbing finish and shower-glass template. Waterproofing must be Kerdi/Wedi — no substitutions.

## Phases

### Pre-Construction
**Dates:** 2026-08-28 → 2026-10-09

PM's job is to lock down the two long fuses that decide whether we start on time: the TDEC septic permit (6-week window, submit day one) and customer selections. Verify existing service supports the new 100A subpanel before contract binds. All 2-week-out equipment checkpoints hit 2026-09-28 — one Monday, all confirmations logged.

- `permit.tdec_septic` — apply 2026-08-28, gates `excavation.dig`
- `prep.amperage_check` — 2026-09-21, must pass before contract sign
- `checkpoint.selections_finalized` — 2026-09-21 (tile, vanity, flooring, paint colors)
- `general.permitting` — building permit walk-in 2026-09-21
- `general.pre_construction_walkthrough` — with customer 2026-09-28
- `checkpoint.equipment_confirmed_demo` / `_excavation` / `_roof` / `_drywall` — all 2026-09-28

> ⚠ **TDEC contact by 2026-08-31 or the schedule breaks.** ~42 calendar-day review + zero cushion after that.

### Procurement & Long Leads
**Dates:** 2026-10-12 (orders placed day-1 on-site) → 2027-01-05 (shower glass last)

All orders except shower glass go out the morning of 2026-10-12 — short-job pattern, order everything up front against use-date. Windows (21 d), LVL (14 d), subpanel/mini-split/tankless/flooring (10 d) arrive in the 10-22 → 11-02 window, cleanly ahead of their consumer tasks. Tile ships 11-02, in time for 12-10 substrate. Shower glass is templated only after tile grout/seal on 12-18.

- All order tasks placed 2026-10-12: `order.windows`, `order.lvl`, `order.subpanel`, `order.minisplit`, `order.tankless`, `order.tile`, `order.vanity`, `order.flooring`, `order.paint`
- Arrivals: subpanel/mini-split/tankless/flooring 10-22, LVL/vanity 10-26, windows/tile 11-02
- `order.shower_glass_template` 2026-12-18 → `checkpoint.shower_glass_arrived` 2027-01-05

> 📦 **Windows & tile arrive 2026-11-02** — confirm site-ready 11-01. Windows feed `windows.install` on 11-12; tile feeds `tile.shower_substrate` on 12-10.

### Site Prep
**Dates:** 2026-10-12 → 2026-10-13

Day-1 is dumpster + site protection + call Zach in the morning. Heat pump and electrical disconnect relocate on 10-13 — both must clear before main demo (2-day lag). The customer-requested acrylic shower swap in the hall bath happens the same day so John has a working shower through the build.

- `equipment.dumpster_arrive` 2026-10-12
- `general.site_setup` 2026-10-12 — dust barriers, floor protection, staging
- `prep.heat_pump_relocate` + `prep.electrical_disconnect_relocate` 2026-10-13
- `early.acrylic_shower_swap` 2026-10-13 (customer early item — do NOT bundle into interior finish phase)

> 👷 **Day-1 on site: 2026-10-12.** Called Zach 10-09 (Friday) per customer note.

### Demolition & Protection
**Dates:** 2026-10-16 → 2026-10-20

Saw-cut walkway + RR ties + obstructions on 10-16, expose the load-bearing wall for the LVL on 10-19, haul out 10-20. Retrofit hall-bath window infill demo runs alongside on 10-19 — separate component, does not gate new addition.

- `demo.walkway_and_obstructions` 2026-10-16
- `demo.expose_bearing_wall` 2026-10-19
- `demo.hall_bath_window` 2026-10-19 (retrofit — 43-day float)
- `demo.haul_out` 2026-10-20

> 👷 **Framing shell raise Monday 2026-11-02** — floor system starts, exterior walls up by 11-06.

### Structural & Shell
**Dates:** 2026-10-20 → 2026-11-19

The heavy phase. Mini-ex on site 10-20, dig 10-21/22, form + rebar 10-23/26, footing inspection 10-27, monolithic pour 10-28, 2-day cure. Framing 11-02 → 11-11. LVL subchain (temp shoring 10-20, install 10-26/27, remove 10-28) runs independently of new-addition framing — do not tie the two crews together. Roof sheathing + windows on 11-12, underlayment 11-13, shingles 11-16. Dried-in milestone 11-17 → siding/trim/gutter block 11-17 → 11-19 (same crew, continuous).

- `excavation.dig` 2026-10-21 → 10-22
- `foundation.form_and_prep` 2026-10-23 → 10-26
- `inspect.footing` 2026-10-27
- `foundation.monolithic_pour` 2026-10-28 (one pour, footings + slab together)
- `structural.install_lvl` 2026-10-26 → 10-27 (parallel with foundation cure)
- `framing.floor_system` → `framing.exterior_walls` → `framing.elevator_shaft` (SS+1) → `framing.roof` → `framing.sheathing`
- `windows.install` 2026-11-12 → 11-13
- `roofing.underlayment` 11-13, `roofing.shingles` 11-16
- `milestone.dried_in` 2026-11-17
- `exterior.siding_trim_gutters` 2026-11-17 → 11-19

> ⚠ **Concealed roof tie-in to existing 6/12 pitch.** 3-day change-order buffer built in (`roof.concealed_buffer`). PM: document existing conditions with photos day 1 of `framing.roof` (2026-11-09).

> 👷 **Dried-in 2026-11-17** — building is weather-tight, interior work can commit.

### Rough Trades
**Dates:** 2026-11-16 → 2026-11-19

E/P/M rough starts as soon as building is weatherproof (underlayment + windows). Tankless sets first on 11-16 morning, plumbing rough stubs into it same day and runs 3 days. Electrical rough (with new 100A subpanel + dedicated 30A elevator circuit) runs 11-16 → 11-18 in parallel. Mini-split line-set is a half-day on 11-16. WH vent extension through the new roof 11-17.

- `plumbing.tank_set` 2026-11-16 (before rough-in per Will's rule)
- `plumbing.rough_in` 2026-11-16 → 11-19 (critical path)
- `electrical.rough_in` 2026-11-16 → 11-18
- `hvac.minisplit_rough` 2026-11-16
- `hvac.wh_vent_extend` 2026-11-17

### Rough Inspections
**Dates:** 2026-11-20 → 2026-11-24

One inspector, one day, all four inspections bundled per rule 4C. Two-day punch buffer 11-23/24 handles anything flagged.

- `inspect.rough_bundled` 2026-11-20
- `buffer.post_rough_inspection` 2026-11-23 → 11-24

> ⚠ **Bundled rough inspection is a hard gate.** Fail = 2-day punch consumes buffer, any second re-inspect pushes drywall and cascades through Christmas.

### Insulation & Drywall
**Dates:** 2026-11-25 → 2026-12-09

Insulation 11-25 (Wednesday before Thanksgiving), inspection 12-01 (first working day after the 11-26/27 holiday). Dumpster swap 12-01, then consolidated 5-day hang/tape/sand block 12-02 → 12-08 (addition + hall bath patch in one pass). Paint phase 1 (primer + ceiling finish) 12-09.

- `insulation.install` 2026-11-25
- `inspect.insulation` 2026-12-01
- `equipment.drywall_dumpster` 2026-12-01
- `drywall.consolidated` 2026-12-02 → 12-08
- `paint.phase_1` 2026-12-09

> ⚠ **Thanksgiving eats 11-26/27.** Insulation inspection cannot happen until 12-01 — do NOT try to squeeze it in on 11-25.

### Interior Finishes
**Dates:** 2026-12-10 → 2026-12-22

Tile chain owns the critical path here. Substrate + Kerdi/Wedi 12-10/11, tile 12-11 → 12-16, grout/seal 12-17/18. Flooring 12-11 → 12-15 in parallel (2.5-day float). Trim 12-15 → 12-17, vanity 12-15, retrofit hallway switch relocate 12-09 (right after drywall). Paint phase 2 on 12-22 is the last interior task — gates on every finish trade.

- `tile.shower_substrate` → `tile.shower_walls_floor` → `tile.grout_seal`
- `flooring.install` 2026-12-11 → 12-15
- `trim.install` 2026-12-15 → 12-17
- `cabinets.vanity_install` 2026-12-15
- `retrofit.hallway_switch_relocate` 2026-12-09
- `retrofit.hall_bath_window_infill` (runs 2026-10-19, parked ready)
- `paint.phase_2` 2026-12-22
- `milestone.substantial_completion` 2026-12-23

> 👷 **Substantial completion 2026-12-23** — home is functionally usable. Customer walkthrough for punch list same day.

### Finish Trades
**Dates:** 2026-12-10 → 2027-01-05

Electrical finish 12-10/11 (12 recessed + vanity lights + outlets + dimmers), then mini-split install 12-14 (staggered after electrical per rule 4N — keeps interior at ≤2 concurrent trades). Plumbing finish 12-18 → 12-21 after cabinets + flooring + tile grout. Shower glass templated 12-18 → fab through Christmas holidays → install 2027-01-05.

- `electrical.finish` 2026-12-10 → 12-11
- `hvac.minisplit_install` 2026-12-14
- `plumbing.finish` 2026-12-18 → 12-21
- `glazing.shower_install` 2027-01-05

### Closeout
**Dates:** 2026-12-23 → 2027-01-06

Walkthrough + punch on 12-23, final clean 12-29/30 (spanning Christmas holidays 12-24/25/26), final bundled inspection 2027-01-04 (E/P/M + final building, one inspector), Will's personal walkthrough 2027-01-06.

- `closeout.pm_walkthrough` 2026-12-23
- `closeout.punch_list_work` 2026-12-23 → 12-29
- `closeout.final_clean` 2026-12-29 → 12-30
- `inspect.final_bundled` 2027-01-04
- `closeout.wills_walkthrough` 2027-01-06

> 👷 **Will's final walkthrough 2027-01-06** — project ends here; CO + handoff.

## Long-lead procurement

| Item | Task | Lead time | Order by | Arrives | Consumer |
|------|------|-----------|----------|---------|----------|
| TDEC septic permit | `permit.tdec_septic` | 42 cal d | 2026-08-28 | 2026-10-09 | `excavation.dig` |
| Windows + ext. door (stock) | `order.windows` → `wait.windows` | 21 cal d | 2026-10-12 | 2026-11-02 | `windows.install` (11-12) |
| LVL beam (3-ply 14") | `order.lvl` → `wait.lvl` | 14 cal d | 2026-10-12 | 2026-10-26 | `structural.install_lvl` (10-26) |
| 100A subpanel | `order.subpanel` → `wait.subpanel` | 10 cal d | 2026-10-12 | 2026-10-22 | `electrical.rough_in` (11-16) |
| Mini-split unit | `order.minisplit` → `wait.minisplit` | 10 cal d | 2026-10-12 | 2026-10-22 | `hvac.minisplit_install` (12-14) |
| Tankless WH | `order.tankless` → `wait.tankless` | 10 cal d | 2026-10-12 | 2026-10-22 | `plumbing.tank_set` (11-16) |
| Vanity + fixtures | `order.vanity` → `wait.vanity` | 14 cal d | 2026-10-12 | 2026-10-26 | `cabinets.vanity_install` (12-15) |
| Flooring (LVP) | `order.flooring` → `wait.flooring` | 10 cal d | 2026-10-12 | 2026-10-22 | `flooring.install` (12-11) |
| Tile (custom) | `order.tile` → `wait.tile` | 21 cal d | 2026-10-12 | 2026-11-02 | `tile.shower_substrate` (12-10) |
| Paint | `order.paint` | short lead | 2026-10-12 | — | `paint.phase_1` (12-09) |
| Shower glass | `order.shower_glass_template` → `wait.shower_glass` | 10 cal d from template | template 2026-12-18 | 2027-01-05 | `glazing.shower_install` (01-05) |

> 📦 **Order-day: 2026-10-12** — all long-leads go out Monday morning of on-site week 1.

> 📦 **LVL & vanity arrive 2026-10-26** — LVL is critical to `structural.install_lvl` same day.

> 📦 **Windows & tile arrive 2026-11-02** — coordinate site delivery, protect tile from framing debris.

> 📦 **Shower glass templates 2026-12-18, arrives 2027-01-05** — holiday fab window; confirm fabricator's Christmas schedule at template.

## Inspections

| Inspection | Date | Gates | Pre-inspection prep |
|------------|------|-------|---------------------|
| `inspect.footing` | 2026-10-27 | `foundation.monolithic_pour` | Forms set, gravel, vapor, rebar in place; call inspector 10-26 |
| `inspect.rough_bundled` (E/P/M + framing) | 2026-11-20 | `insulation.install` | All rough MEPs pressure-tested; framing complete; call inspector 11-19; single inspector, single day |
| `inspect.insulation` | 2026-12-01 | `drywall.consolidated` | Insulation + air sealing complete; call inspector 11-25 (before Thanksgiving) |
| `inspect.final_bundled` (E/P/M + final building) | 2027-01-04 | `closeout.wills_walkthrough` | Final clean done; all finish trades signed off; call inspector 12-30 |

> ⚠ **Bundled inspections are the whole game.** Any failure = a re-visit day + potential critical-path slide. Walk each inspection prep with the lead employee 24 h prior.

## Risk register

> ⚠ **TDEC septic is the single hardest external gate.** Submit 2026-08-28. Only 7 days of float. If it lags, excavation slides and the entire on-site schedule moves.

> ⚠ **Confirm septic vs. city sewer at contract.** If home is on city sewer, drop `permit.tdec_septic` and pick up 6 weeks. If on septic, confirm option (relocate / new tank / grinder pump) — all costs excluded from contract, will be a change order.

> ⚠ **100A subpanel assumes existing service can carry the load.** `prep.amperage_check` on 2026-09-21 must confirm before contract binds. If service is short → new main service = major change order.

> ⚠ **Concealed roof tie-in to existing 6/12 pitch.** Buffer of 3 days built in but not much more. Document existing rafter/framing conditions with photos before covering.

> ⚠ **Weather window.** On-site 2026-10-12 → 2027-01-06 lands foundation + shell in Oct-Nov (OK) but interior finish through late Dec (indoor, OK) with siding block in mid-Nov. Watch forecasts 11-09 → 11-19; siding crew needs a dry stretch.

> ⚠ **Interior 2-trade cap.** Mini-split install is deliberately staggered after electrical finish. Do NOT let PM allow tile + electrical + HVAC + flooring on the same day — schedule enforces 2 trades max inside.

> ⚠ **Drawings gap on deck + brick veneer.** A-02 shows multi-level deck and brick veneer at addition base that are NOT in the CSV breakdown. Raise with customer BEFORE contract sign — either add scope + cost or exclude in writing.

> ⚠ **Elevator shaft location assumed inside addition footprint.** No drawing. Confirm with customer before `framing.exterior_walls` starts 2026-11-04.

> ⚠ **Truss vs. stick-frame TBD in scope.** Defaulted to stick-frame (~300 sqft roof, small enough). Confirm before ordering LVL / framing package.

> ⚠ **Christmas holidays consume 12-24/25/26 + 12-31 wobble.** Punch list and final clean straddle the holiday — verify subs and inspector availability 12-15.

> ⚠ **Hall bath section is a scope credit (-$1,714.20).** Not extra scope — a scope reduction. Do NOT let it drift back into a full remodel via change orders.

> ⚠ **Water heater ambiguity: scope PDF says vent-only for existing tank; breakdown header says tankless.** Currently modeled as BOTH — existing gas WH vent extension AND new tankless install. Confirm with customer 2026-08-28 and adjust before ordering.

## PM daily runsheet

### Day-1 checklist (Monday 2026-10-12)
- Call Zach (John's brother) by phone before 8:00 AM — customer note requires day-before contact, do it Friday 10-09 as well
- Confirm 25% deposit received and cleared
- Confirm signed contract in hand
- Dumpster on site (arrives day-of)
- Site protection + dust barriers + floor protection installed by noon
- All 9 procurement orders placed by end of day: windows, LVL, subpanel, mini-split, tankless, vanity, flooring, tile, paint
- Verify TDEC septic status (should be in review since 2026-08-28)
- Send Monday weekly-update email to John (start-of-week template + week 1 plan)

> 👷 **On-site start: 2026-10-12.** First customer touchpoint since the pre-con walkthrough 09-28.

> 📦 **All long-lead orders placed today.** Log confirmation numbers to job folder.

### Day of first major inspection — Rough Bundled (Friday 2026-11-20)
- Call inspector Thursday 11-19 to confirm morning slot
- All rough plumbing pressure-tested and holding
- All rough electrical boxes labeled, home runs to subpanel dressed
- Mini-split line set secured and labeled
- Framing straps and hangers all installed and visible
- Ladder + light at each inspection point
- Lead employee on site as inspector escort
- Photo record of everything about to be covered (behind-drywall warranty file)

### Substantial completion checklist (Wednesday 2026-12-23)
- Paint phase 2 dry; walk every room
- Punch list generated with customer during walkthrough — logged same day
- Photo record of finished spaces before punch trades come back
- Confirm final inspection scheduled for 2027-01-04
- Confirm shower glass template happened 12-18 and fab is on track for 01-05 install
- Send progress payment invoice (25% at completion tranche)
- Customer expectation set: they can begin using the addition; punch list + closeout continues through 01-06

> 👷 **Substantial completion — home is usable today.** Customer sees it as "done."

Handoff completes 2027-01-06 at Will's personal walkthrough — 1-year labor warranty starts that day.