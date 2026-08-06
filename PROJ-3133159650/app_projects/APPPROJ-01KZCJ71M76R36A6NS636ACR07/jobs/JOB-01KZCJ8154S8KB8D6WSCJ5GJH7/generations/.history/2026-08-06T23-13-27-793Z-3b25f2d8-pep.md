# Project Execution Plan — 308 Evergreen Two-Story Addition

## Snapshot
- **Customer / site:** 308 Evergreen (customer name not on record — confirm before Day 1).
- **Scope:** Two-story ~30'×10' addition (789 SF per breakdown) — basement storage, primary bedroom expansion, master bath, walk-in closet. Ties into existing stair; existing hall bath modified. IRC 2018 / NEC.
- **On-site start:** 2026-10-12 · **Pre-construction start:** 2026-09-21 · **Substantial completion:** 2027-02-05 · **Job complete (CO):** 2027-02-12.
- **Cost basis:** $100,778.92 (Labor $45,167.59 / Material $52,171.33 / Equip $3,440.00), 1,287 labor hours. Valuation field null — no contracted price recorded.
- **System notes:** mini-split HVAC (no ducted rough-in), new tankless WH, 3-ply 14" LVL over a 15'-6" opening with temporary shoring, future elevator shaft framed + 120V/30A circuit only.

## Critical path
The schedule runs 62 of 66 tasks on the critical path — near-zero float end to end. Treat every dated hand-off below as a hard gate.

- `permit_tdec_septic` — 2026-09-21 → 2026-10-30 (30 cal days, starts in pre-construction).
- `utility_relocations` 2026-10-12→10-13 → `retrofit_demo` 10-14 → `retrofit_rough_meps` 10-15→10-19 → `retrofit_drywall` 10-20→10-21 → `retrofit_finishes` 10-22→10-26 → `retrofit.end` 10-27.
- `site_and_structure_demo` 2026-10-27→10-28 → `site_prep` 10-29→10-30 → `excavation` 11-02→11-03 → `foundation` 11-04→11-09.
- `framing` 2026-11-17→12-02 → `exterior_windows_doors` 12-03→12-04 → `roofing` 12-07→12-08.
- `rough_plumbing` 12-09→12-11 → `rough_hvac` 12-11 → `rough_electrical` 12-11→12-16 → `bundled_rough_inspections` 12-17→12-18.
- `insulation` 12-30 → `insulation_inspection` 12-31 → `drywall` 2027-01-04→01-08 → `paint_phase_1` 01-11→01-12.
- `shower_work` 01-13→01-19 → `hard_flooring` 01-20→01-22 → `cabinets_counters` 01-25→01-26 → `mep_fixture_install` 01-27→01-28 → `finish_carpentry` 01-29→02-02 → `paint_phase_2` 02-03→02-04 → `substantial_completion` 02-05.
- `customer_walkthrough` 02-09 → `final_inspections` 02-10 → `job_complete` 02-12.

> ⚠ The `permit_tdec_septic` 30-day gate (2026-09-21 → 2026-10-30) directly binds `excavation` (11-02); a late TDEC issuance slides foundation, framing, and every downstream trade day-for-day.

## Phases

### Procurement
Pre-construction (starts 2026-09-21). PM places every long-lead order against its use date, not project start. Cabinets and countertops are the tail items and land inside the January finish window with no slack.

- `proc_foundation_package` order-by 2026-10-16 for `foundation` (11-04).
- `proc_lvl` + `proc_framing_package` order-by 2026-11-03 for `framing` (11-17).
- `proc_windows_doors` order-by 2026-11-09 for `exterior_windows_doors` (12-03).
- `proc_cabinets` / `proc_countertops` order-by 2026-12-22 / 12-29 for `cabinets_counters` (01-25).

> 📦 **Cabinets/counters are the pacing items:** order-by 2026-12-22 — holiday shipping swings hard in Nov/Dec; confirm the vendor ship date in writing before Thanksgiving.

### Permits
Building, plumbing, and mechanical permits pull alongside the septic evaluation. TDEC is the long pole and must already be in motion at the 09-21 pre-construction start. Building permit (10-13→10-26) releases main demo; plumbing/mechanical release the December rough MEPs.

- `permit_building` 2026-10-13→10-26 → gates `site_and_structure_demo`.
- `permit_tdec_septic` 2026-09-21→10-30 → gates `excavation`.
- `permit_plumbing` 2026-11-23→12-08 → gates `rough_plumbing`; `permit_mechanical` 2026-11-25→12-10 → gates `rough_hvac`.

> ⚠ Septic costs are excluded from the base contract pending the TDEC evaluation (relocate vs. new tank/leach field vs. grinder-to-sewer) — write the change order before any septic scope is confirmed.

### Retrofit (pre-addition work)
2026-10-12 → 2026-10-27. PM works the existing house first: relocate the heat pump, disconnect, and lines, then demo and rebuild the affected interior (incl. existing hall bath mod) so the shell demo can follow cleanly. This whole block is on the critical path — no idle days.

- `utility_relocations` 10-12→10-13 (heat pump, disconnect, lines).
- `retrofit_demo` 10-14 → `retrofit_rough_meps` 10-15→10-19 → `retrofit_drywall` 10-20→10-21 → `retrofit_finishes` 10-22→10-26 → `retrofit.end` 10-27.

> 👷 Site setup / crew mobilization lands 2026-10-12 — utility relocations are the first on-site anchor; confirm the customer has an alternate for any disrupted service that day.

### Demolition
2026-10-27 → 2026-10-28. Structure + site demo at the addition footprint, released only once both `retrofit.end` and `permit_building` are in hand. Dumpster stages the day before.

- `site_and_structure_demo` 10-27→10-28 → hands off to `site_prep`.

> 👷 Dumpster on site 2026-10-26 (day before demo) — never demo without the next phase's materials staged.

### Site Prep & Foundation
2026-10-29 → 2026-11-10. Site protection/staging/access, then excavation (gated by TDEC), then a single monolithic foundation pour with footing inspection folded in. A 5-day cure lag sits between `site_foundation.end` (11-10) and framing start.

- `site_prep` 10-29→10-30 → `excavation` 11-02→11-03 → `foundation` 11-04→11-09 → `site_foundation.end` 11-10.

> ⚠ Foundation pour lands 2026-11-04→11-09 heading into cold weather — hold the 20% weather buffer and do not pour on a hard-freeze forecast.

### Framing & Shell
2026-11-17 → 2026-12-04. Floor/walls/roof structure/sheathing in one 10-day block, then exterior windows and the new door. The 3-ply LVL over the 15'-6" opening drops here — temporary shoring stays until the beam is set and loaded.

- `framing_shell.start` 11-17 → `framing` 11-17→12-02 → `exterior_windows_doors` 12-03→12-04.

> 👷 Framing raise week is 2026-11-17 — pre-framing attic/roof documentation of existing rafters at the 3/12-into-6/12 tie-in must be shot before the roof is opened.

### Exterior Finishes
2026-12-07 → 2026-12-14. Roof dry-in first (gates rough plumbing), then siding + fascia/soffit/gutters run as one continuous same-crew block. Existing appliance vents extend through the new roof alongside roofing. Siding carries 41 days of float — it can flex around interior work if weather turns.

- `roofing` 12-07→12-08 → `appliance_vent_extension` 12-07 (SS).
- `siding` 12-07→12-11 · `fascia_soffit_gutters` 12-07→12-08 → `exterior_finishes.end` 12-14.

> 👷 Roof dry-in complete 2026-12-08 — this is the gate that lets rough plumbing start inside; verify shingle tie-in blend to existing before crews move indoors.

### Rough Trades (MEPs)
2026-12-09 → 2026-12-16. Plumbing (tankless set first, then rough), mini-split line-set, and electrical (100A subpanel) run tightly overlapped via -1 day lags. Requires plumbing + mechanical permits issued and equipment on site.

- `rough_plumbing` 12-09→12-11 → `rough_hvac` 12-11 → `rough_electrical` 12-11→12-16 → `rough_trades.end` 12-17.

> ⚠ Rough electrical must include the future-elevator 120V/30A circuit and shaft provisions — miss it here and it's buried behind drywall.

### Rough Inspections
2026-12-17 → 2026-12-21. Bundled MEP-then-framing inspection with one inspector, 1-day scheduling lead. A 5-day lag follows before insulation starts.

- `bundled_rough_inspections` 12-17→12-18 → `rough_inspections.end` 12-21.

> ⚠ This bundled inspection gates all of insulation/drywall — schedule the inspector before 12-17 and have MEP + framing sign-off packets ready in one visit.

### Insulation & Drywall
2026-12-30 → 2027-01-13. Insulation + air seal, a separate insulation inspection, then the hang/tape/sand drywall cycle, then paint phase 1 (prime + ceilings) before finish work.

- `insulation` 12-30 → `insulation_inspection` 12-31 → `drywall` 01-04→01-08 → `paint_phase_1` 01-11→01-12 → `insulation_drywall.end` 01-13.

> 👷 Drywall hang starts 2027-01-04 — second dumpster/swap lands 01-02 and photograph all wall cavities before board goes up (warranty file).

### Interior Finishes
2027-01-13 → 2027-02-05. Master-bath shower waterproofing + tile, hard flooring, cabinets/counters/vanities, MEP fixture install (mini-split head, tankless trim, plumbing + light fixtures), finish carpentry, then paint phase 2 = substantial completion. Keep to two interior trades at a time.

- `shower_work` 01-13→01-19 → `hard_flooring` 01-20→01-22 → `cabinets_counters` 01-25→01-26 → `mep_fixture_install` 01-27→01-28 → `finish_carpentry` 01-29→02-02 → `paint_phase_2` 02-03→02-04 → `substantial_completion` 02-05.

> 👷 Trim start 2027-01-29 leading into paint phase 2 (02-03→02-04); substantial completion — the customer's "done" milestone — is 2027-02-05. Kerdi/Wedi behind the shower, no exceptions.

### Closeout
2027-02-09 → 2027-02-12. PM walkthrough + punch list, bundled final building/E/P/M inspection, then owner walkthrough and CO.

- `customer_walkthrough` 02-09 → `final_inspections` 02-10 → `job_complete` 02-12.

> 👷 Substantial-completion walk with customer 2027-02-09 — log punch items same day; final inspection 02-10 gates the CO.

## Long-lead procurement
Order-by = task scheduled start; arrive = scheduled end; each gates its consumer via FS+3.

- `proc_foundation_package` — 14d · order-by 2026-10-16 · arrive 2026-10-29 · → `foundation` (11-04).
- `proc_lvl` — 10d · order-by 2026-11-03 · arrive 2026-11-11 · → `framing` (11-17).
- `proc_framing_package` — 10d · order-by 2026-11-03 · arrive 2026-11-11 · → `framing` (11-17).
- `proc_windows_doors` — 18d · order-by 2026-11-09 · arrive 2026-11-25 · → `exterior_windows_doors` (12-03).
- `proc_water_heater` — 12d · order-by 2026-11-19 · arrive 2026-12-03 · → `rough_plumbing` (12-09).
- `proc_hvac_equipment` — 10d · order-by 2026-11-25 · arrive 2026-12-07 · → `rough_hvac` (12-11).
- `proc_subpanel` — 5d · order-by 2026-12-02 · arrive 2026-12-07 · → `rough_electrical` (12-11).
- `proc_electrical_package` — 5d · order-by 2026-12-02 · arrive 2026-12-07 · → `rough_electrical` (12-11).
- `proc_plumbing_package` — 3d · order-by 2026-12-02 · arrive 2026-12-03 · → `rough_plumbing` (12-09).
- `proc_drywall` — 5d · order-by 2026-12-21 · arrive 2026-12-28 · → `drywall` (01-04).
- `proc_insulation` — 2d · order-by 2026-12-22 · arrive 2026-12-22 · → `insulation` (12-30).
- `proc_cabinets` — 25d · order-by 2026-12-22 · arrive 2027-01-19 · → `cabinets_counters` (01-25).
- `proc_countertops` — 21d · order-by 2026-12-29 · arrive 2027-01-19 · → `cabinets_counters` (01-25).
- `proc_tile` — 10d · order-by 2026-12-29 · arrive 2027-01-07 · → `shower_work` (01-13).
- `proc_hard_flooring` — 14d · order-by 2026-12-31 · arrive 2027-01-14 · → `hard_flooring` (01-20).
- `proc_paint` — 2d · order-by 2027-01-05 · arrive 2027-01-05 · → `paint_phase_1` (01-11).
- `proc_plumbing_fixtures` — 7d · order-by 2027-01-15 · arrive 2027-01-21 · → `mep_fixture_install` (01-27).
- `proc_light_fixtures` — 7d · order-by 2027-01-15 · arrive 2027-01-21 · → `mep_fixture_install` (01-27).
- `proc_doors_trim` — 7d · order-by 2027-01-19 · arrive 2027-01-25 · → `finish_carpentry` (01-29).

> 📦 **Cabinets arrive 2027-01-19 / order-by 2026-12-22** — confirm site-ready and field-verify measurements before install day 01-25; holiday-window vendor slippage is the top delivery risk on this job.

## Inspections
- `bundled_rough_inspections` — 2026-12-17→12-18. Gates insulation/drywall (via `rough_inspections.end`). Prep: MEP rough complete and pressure-tested, framing exposed with LVL/shoring documented, 1-day scheduling lead placed.
- `insulation_inspection` — 2026-12-31. Gates `drywall`. Prep: batts + air sealing complete and photographed; do not board any wall until pass is logged.
- `final_inspections` — 2027-02-10 (building + E/P/M bundled). Gates `job_complete`/CO. Prep: punch list from 02-09 walkthrough addressed, all trades' finish work signed off, tankless and mini-split commissioned.

> ⚠ Three inspection gates carry 1-day scheduling leads and zero float — book each inspector a full day ahead or the whole downstream chain slides.

## Risk register

> ⚠ **TDEC septic (30-day lead, on critical path):** confirm the evaluation is submitted at the 2026-09-21 pre-construction start; septic scope + cost is a live change order that must be signed before any modification.

> ⚠ **Under-parallelized schedule (62/66 tasks critical, 94%):** there is almost no float — treat every hand-off date as hard and escalate any one-day slip same day, since it moves the 2027-02-12 CO.

> ⚠ **Cold-weather foundation + framing (2026-11-04 pour, framing into December):** hold the 20% weather buffer; reschedule pours off hard-freeze days rather than pouring cold.

> ⚠ **LVL beam / temporary shoring over 15'-6" opening:** keep shoring in place until the 3-ply 14" LVL is fully set and loaded; verify engineer's detail before removing supports during `framing`.

> ⚠ **Cabinet/countertop lead in the holiday window:** `proc_cabinets` order-by 2026-12-22 collides with Nov/Dec shipping swings — get a written ship commitment early and pre-stage a fallback vendor.

> ⚠ **Landscaping / site restoration excluded (per assumption):** seed/straw restoration is out of scope — confirm with customer in writing so the disturbed yard isn't a closeout surprise.

> ⚠ **Roofing duration clamped (3→2 days) at the 3/12-into-6/12 tie-in:** the 2-day roof window is tight for a pitch-transition blend — verify crew size and weather before `roofing` (12-07) since it gates all rough MEPs.

## PM daily runsheet

**Day 1 — 2026-10-12**
- Confirm signed contract + deposit and verify customer name/contact on file before mobilizing.
- Verify TDEC septic evaluation already submitted (should be running since 09-21).
- Kick off `utility_relocations` — heat pump, disconnect, lines; confirm customer service alternates.

> 👷 On-site crew mobilizes 2026-10-12 — first anchor is utility relocations, not addition demo.

**Day of first major inspection — 2026-12-17 (`bundled_rough_inspections`)**
- Inspector confirmed the day prior (1-day lead).
- Rough plumbing pressure-tested, mini-split line-set and 100A subpanel rough complete, elevator circuit roughed.
- Framing exposed; LVL + shoring documentation ready; photos of all cavities filed.

> 📦 No delivery lands this day — next material drop is drywall (arrives 2026-12-28) for the 01-04 hang.

**Substantial completion — 2027-02-05 → walkthrough 2027-02-09**
- Paint phase 2 complete; tankless + mini-split commissioned; fixtures trimmed.
- Walk the job with customer 02-09, log punch list same day.
- Book bundled final inspection for 02-10; target `job_complete` / CO 2027-02-12.

> 👷 Substantial-completion walk 2027-02-09 is the customer's "done" moment — closeout inspection and CO follow, but functionally complete here.