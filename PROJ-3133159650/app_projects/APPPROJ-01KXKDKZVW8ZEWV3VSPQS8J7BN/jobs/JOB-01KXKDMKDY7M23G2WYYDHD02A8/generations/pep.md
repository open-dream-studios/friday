# Project Execution Plan — Simons Addition (30×10 Two-Story Bedroom + Master Bath)

## Snapshot
- **Customer / project**: Simons Addition — 30'×10' two-story addition (789 sqft footprint, 8' ceilings), master bedroom + master bath + walk-in closet + basement storage, plus retrofit of existing hall bath and hallway.
- **Pre-construction start**: 2026-09-08 (TDEC septic filing)
- **On-site start**: 2026-10-12
- **Substantial completion**: 2027-02-03
- **Final walkthrough / handoff**: 2027-02-12
- **Duration**: ~17 working weeks on-site (~5 weeks pre-con)
- **Contract value**: $100,778.92 ($45,167.59 labor / $52,171.33 materials / $3,440.00 equipment)
- **Labor hours**: 1,287

## Critical path
The critical path runs late — it lives entirely in the finish end of the job, gated by shower-glass templating and fabrication. Everything upstream carries at least 0.5–1 day of float; the moment tile is grouted, the schedule goes tight and stays tight to handoff.

1. `wait.shower_glass` — shower glass fabrication — 2027-01-18 → 2027-01-27 (10 cal-d)
2. `checkpoint.shower_glass_arrived` — 2027-01-28
3. `plumbing.finish` — 2027-01-28 → 2027-01-29 (2 d)
4. `paint.phase_2` — 2027-02-01 → 2027-02-02 (2 d)
5. `milestone.substantial_completion` — 2027-02-03
6. `closeout.pm_walkthrough` — 2027-02-03 (1 d)
7. `closeout.punch_work` — 2027-02-04 → 2027-02-05 (2 d)
8. `closeout.final_clean` — 2027-02-08 (1 d)
9. `inspect.final_bundled` — 2027-02-10 (1 d, +1 d scheduling lag)
10. `closeout.wills_walkthrough` — 2027-02-12 (1 d)

> ⚠ **Shower-glass template date is the make-or-break gate.** If `tile.grout_seal` slips past 2027-01-14 the glass template slips, and every day of glass slip is a day of handoff slip. Templater must be booked the moment grout dries.

> ⚠ **TDEC septic (`permit.tdec_septic`) has only 10 days of float** and gates `excavation.dig`. Filed 2026-09-08, must clear by 2026-10-09. Any delay past mid-September cuts into the on-site start.

## Phases

### Pre-Construction
**2026-09-08 → 2026-10-09**
PM's job here is paperwork, procurement setup, and locking selections. TDEC septic filing goes out day one; permit walk-in and amperage check happen ~3 weeks before on-site. Selections must be signed off (`checkpoint.selections_finalized`) by 2026-09-21 or the whole long-lead cascade slides.
- `permit.tdec_septic` filed 2026-09-08
- `general.site_verification` 2026-09-14
- `general.permitting`, `prep.amperage_check`, `checkpoint.selections_finalized` all 2026-09-21
- `checkpoint.equipment_confirmed_demo` + `checkpoint.equipment_confirmed_foundation` 2026-09-28

> ⚠ **Amperage check gates the 100A subpanel order.** If existing service can't accept the sub, a service upgrade change order needs to be written and signed BEFORE 2026-10-12 mobilization.

### Procurement & Long Leads
**2026-10-12 → 2027-01-28**
All long-lead orders (windows, door, LVL, subpanel, mini-split, tankless, tile, flooring, vanity, paint) drop the day of on-site start. Shower glass templates late (post-tile) — that's the schedule-critical procurement item, not the early ones.
- Windows, exterior door, tile: order 2026-10-12, arrive 2026-11-03
- LVL, mini-split, tankless, vanity/fixtures: order 2026-10-12, arrive 2026-10-27
- Subpanel, flooring: order 2026-10-12, arrive 2026-10-22 → 2026-10-23
- Shower glass: template 2027-01-15, arrive 2027-01-28

### Site Prep
**2026-10-12 → 2026-10-14**
Dumpster lands 2026-10-12, then site setup, then the two prep moves (heat pump + electrical disconnect relocation) so demo can swing on 2026-10-19.
- `equipment.dumpster_arrive` 2026-10-12
- `general.site_setup` 2026-10-13
- `prep.heat_pump_relocate` + `prep.electrical_disconnect_relocate` 2026-10-14

> 👷 **Day 1 on-site (2026-10-12):** dumpster in, staging laid out, and the entire long-lead PO stack goes to the supplier the same day.

### Demolition & Protection
**2026-10-19 → 2026-10-21**
Three days total. Sawcut walkway + railroad ties in parallel; interior demo exposes the load-bearing wall for the LVL; haul-out closes the phase.
- `demo.sawcut_walkway` + `demo.site_obstructions` 2026-10-19
- `demo.interior_bearing_wall` 2026-10-20
- `demo.haul_out` 2026-10-21

### Structural & Shell
**2026-10-22 → 2026-12-08**
The long phase. Mini-ex arrives 2026-10-22, excavation 2026-10-23–26, monolithic pour 2026-11-02 after footing inspection, then a 2-day cure. Framing runs 2026-11-05 → 2026-11-25 (floor system → walls → roof). LVL install slots in 2026-10-27–28 in parallel with excavation. Windows + roofing button up the shell by 2026-12-02; siding/trim/gutters continuous 2026-12-03 → 2026-12-08.
- `inspect.footing` 2026-10-30
- `foundation.monolithic_pour` 2026-11-02
- `structural.install_lvl` 2026-10-27 → 2026-10-28
- `framing.floor_system` 2026-11-05 → 2026-11-12
- `framing.exterior_walls` 2026-11-13 → 2026-11-19
- `framing.roof` 2026-11-20 → 2026-11-25
- `windows.install` 2026-11-30 → 2026-12-01
- `roofing.shingles` 2026-12-02
- `milestone.dried_in` 2026-12-03
- `exterior.siding_trim_gutters` 2026-12-03 → 2026-12-08

> 👷 **Dried-in 2026-12-03** — this is the customer-visible milestone. Photograph roof + envelope, send weekly update the following Monday.

> ⚠ **Concealed roof tie-in (3/12 new into existing 6/12):** 3-day buffer built into `roof.concealed_buffer`. PM must document any hidden rafter conditions on framing day 1 for a fast change-order.

### Rough Trades
**2026-12-02 → 2026-12-07**
Underlayment + windows are the two gates; MEPs kick off same-day. Electrical starts 2026-12-02, tankless set + plumbing rough SS+1 behind it, mini-split rough SS+1 behind plumbing. WH vent extension slots in 2026-12-03 after shingles.
- `electrical.rough_in` 2026-12-02 → 2026-12-04
- `plumbing.tank_set` 2026-12-02, `plumbing.rough_in` 2026-12-03 → 2026-12-07
- `hvac.minisplit_rough` 2026-12-04
- `hvac.wh_vent_extend` 2026-12-03

### Rough Inspections
**2026-12-09 → 2026-12-11**
One inspector, one day, bundled E/P/M + framing. 2-day punch buffer after.
- `inspect.rough_bundled` 2026-12-09
- `buffer.post_rough_inspection` 2026-12-10 → 2026-12-11

> 👷 **Rough inspection day 2026-12-09** — anchor date for the PM. Confirm inspector 3 business days prior; walk the building with all three sub leads morning-of.

### Insulation & Drywall
**2026-12-14 → 2027-01-04**
Insulation, insulation inspection, dumpster swap, then an 8-day drywall hang/tape/sand across addition + retrofit bedroom + hall-bath patches. Paint phase 1 (prime + ceiling coat) closes the phase 2027-01-04. **Christmas holidays fall inside the drywall window** — the calendar accounts for it, but PM must confirm crew coverage.
- `insulation.air_seal` 2026-12-14
- `inspect.insulation` 2026-12-16
- `drywall.consolidated` 2026-12-18 → 2026-12-31
- `paint.phase_1` 2027-01-04

> ⚠ **Drywall spans Dec 24–26 holidays.** Cure/tape cycles keep working over the break, but confirm crew is back on-site 2026-12-28 to avoid slipping paint phase 1.

### Interior Finishes
**2027-01-05 → 2027-02-02**
Two interior trades at a time per rule. Tile substrate → flooring, cabinets, trim sequence; shower tile set → grout → glass template. This is where the critical path emerges.
- `tile.shower_substrate` 2027-01-05 → 2027-01-06
- `tile.shower_set` 2027-01-07 → 2027-01-12
- `flooring.install` 2027-01-07 → 2027-01-11
- `cabinets.install` 2027-01-12
- `trim.install` 2027-01-12 → 2027-01-15
- `tile.grout_seal` 2027-01-14
- `retrofit.hall_bath_window_infill` 2026-10-22 (has 64-d float, schedule opportunistically)
- `retrofit.hallway_switch_relocate` 2027-01-04
- `paint.phase_2` 2027-02-01 → 2027-02-02

> 👷 **Substantial completion 2027-02-03** — this is what the customer perceives as "done." Schedule client walk-through same morning.

### Finish Trades
**2027-01-12 → 2027-01-29**
Electrical finish first, then mini-split install (staggered per 2-trade cap), then plumbing finish waits on shower glass arrival.
- `electrical.finish` 2027-01-12 → 2027-01-14
- `hvac.minisplit_install` 2027-01-15
- `plumbing.finish` 2027-01-28 → 2027-01-29

### Closeout
**2027-02-03 → 2027-02-12**
PM walkthrough same day as substantial completion, 2 days of trade returns, clean, final inspection, owner walkthrough.
- `closeout.pm_walkthrough` 2027-02-03
- `closeout.punch_work` 2027-02-04 → 2027-02-05
- `closeout.final_clean` 2027-02-08
- `inspect.final_bundled` 2027-02-10
- `closeout.wills_walkthrough` 2027-02-12

## Long-lead procurement

> 📦 **Windows** — order 2026-10-12, arrive 2026-11-03 — consumer: `windows.install` 2026-11-30

> 📦 **Exterior door** — order 2026-10-12, arrive 2026-11-03 — consumer: `windows.install` 2026-11-30

> 📦 **LVL beam (3-ply 14")** — order 2026-10-12, arrive 2026-10-27 — consumer: `structural.install_lvl` 2026-10-27

> 📦 **100A subpanel** — order 2026-10-12 (after amperage check), arrive 2026-10-23 — consumer: `electrical.rough_in` 2026-12-02

> 📦 **Mini-split unit** — order 2026-10-12, arrive 2026-10-27 — consumer: `hvac.minisplit_install` 2027-01-15

> 📦 **Tankless water heater** — order 2026-10-12, arrive 2026-10-27 — consumer: `plumbing.tank_set` 2026-12-02

> 📦 **Master bath tile** — order 2026-10-12, arrive 2026-11-03 — consumer: `tile.shower_substrate` 2027-01-05

> 📦 **Flooring (LVP)** — order 2026-10-12, arrive 2026-10-23 — consumer: `flooring.install` 2027-01-07

> 📦 **Paint** — order 2026-10-12 (no separate wait) — consumer: `paint.phase_1` 2027-01-04

> 📦 **Vanity & bath fixtures** — order 2026-10-12, arrive 2026-10-27 — consumer: `cabinets.install` 2027-01-12

> 📦 **Shower glass** — template 2027-01-15 (right after grout), arrive 2027-01-28 — consumer: `plumbing.finish` 2027-01-28. **THIS IS THE CRITICAL-PATH ORDER. NO SLACK.**

> 📦 **TDEC septic permit** (regulatory lead) — filed 2026-09-08, expected clear 2026-10-09 — consumer: `excavation.dig` 2026-10-23

## Inspections

- **`inspect.footing`** — 2026-10-30. Gates `foundation.monolithic_pour`. Pre-check: forms squared and level, gravel base compacted, vapor barrier lapped, rebar chairs set to spec, TDEC permit doc on-site.
- **`inspect.rough_bundled`** — 2026-12-09. Gates `insulation.air_seal`. Pre-check: electrical + plumbing + HVAC + framing all complete with 1-day lag; walk the building morning-of with all three sub leads; sign-off tags visible.
- **`inspect.insulation`** — 2026-12-16. Gates `drywall.consolidated`. Pre-check: batts fully seated, no compressed cavities, air-sealing verified at penetrations, baffles at soffit vents.
- **`inspect.final_bundled`** — 2027-02-10. Gates CO / handoff. Pre-check: all finish trades demobilized, final clean complete, GFCI/AFCI verified, water tested at every fixture, mini-split cooling + heating cycle verified.

> ⚠ **All four inspections are single-day, single-inspector.** Book each 3 business days ahead. A missed inspection window is a lost week.

## Risk register

> ⚠ **TDEC septic dominates pre-con.** File 2026-09-08. Only 10 days of float on the CPM. If TDEC punts, excavation slides one-for-one and the on-site start moves.

> ⚠ **Shower glass is the critical-path item.** `tile.grout_seal` MUST land 2027-01-14; if it slips, handoff slips. Templater confirmed and on standby.

> ⚠ **Amperage / subpanel change-order risk.** If `prep.amperage_check` finds insufficient main service, service upgrade CO must be signed BEFORE 2026-10-12 mobilization. Do not start demo without a written answer.

> ⚠ **Concealed roof tie-in (3/12 new into existing 6/12).** 3-day buffer in `roof.concealed_buffer`. PM must photograph and document existing rafter conditions on framing.roof day 1 for immediate CO if needed.

> ⚠ **Winter weather exposure Nov–Feb.** Framing, roofing, siding all land in TCR's mid-Dec through mid-Feb outdoor-risk window. No weather buffer is in the CPM — add 20% pad mentally and communicate to customer up front.

> ⚠ **Christmas holidays inside drywall (2026-12-24 to 2026-12-26).** Confirm crew is back 2026-12-28. Any delay ripples straight into paint phase 1 and every downstream finish.

> ⚠ **Elevator shaft location ambiguous.** 4x4 shaft assumed inside addition footprint. PM confirm location + basement-to-2nd-floor extent BEFORE `framing.exterior_walls` starts 2026-11-13.

> ⚠ **2-trade interior cap during finishes.** Electrical, plumbing, mini-split, tile, cabinets, trim all compete for interior space Jan 4–29. Mini-split is already staggered after electrical finish. Don't let a sub push to double up beyond two trades.

> ⚠ **Trusses vs stick-frame TBD in scope.** Defaulted to stick-frame; if design changes to trusses, add 28–42 day procurement task immediately (would rebuild the whole schedule).

> ⚠ **Hall bath / hallway switch are retrofit (Signal A).** Owner may perceive credits on `hall_bath_bedroom_closeout` (-$1,714). Confirm scope + $ with customer before work begins.

## PM daily runsheet

### Day 1 on-site — 2026-10-12 (Monday)
> 👷 **Site setup day.**

> 📦 **Deliveries landing today:** dumpster on-site AM.

> 📦 **POs going out today:** windows, exterior door, LVL, subpanel, mini-split, tankless, tile, flooring, vanity/fixtures, paint. All orders confirmed with supplier by EOD.

- Confirm signed contract + 25% deposit in hand
- Verify customer selections locked (should be closed 2026-09-21)
- Confirm TDEC permit status
- Confirm amperage-check result and subpanel CO status
- Photos: pre-condition of walkway, existing heat pump, disconnect location, hall bath, existing bedroom
- Send weekly update to customer

### Rough inspection day — 2026-12-09 (Wednesday)
> 👷 **Bundled rough inspection — anchor date.**

- Inspector confirmed 3 business days prior
- Electrical, plumbing, HVAC sub leads all on-site morning-of
- Framer walking with inspector
- All rough-in photos taken BEFORE inspection (insurance for behind-drywall)
- Punch items logged same day
- 2-day buffer 2026-12-10–11 is for corrections, not new work

### Substantial completion — 2027-02-03 (Wednesday)
> 👷 **Substantial completion + PM walkthrough day.**

- Walk the addition with customer, produce written punch list same day
- Confirm final-inspection booking for 2027-02-10
- Schedule cleaning crew for 2027-02-08
- Confirm 4th payment draw against completion
- Photos of every finished space before-and-after for warranty file
- Owner (Will) confirmed for 2027-02-12 final walkthrough with customer

### Handoff — 2027-02-12 (Friday)
> 👷 **Owner walkthrough + handoff.**

- Final inspection passed 2027-02-10
- CO in hand
- Warranty file (photos + spec sheets + maintenance notes) delivered to customer
- Final payment collected
- Job archived; 1-year drywall crack return budgeted per TCR standard