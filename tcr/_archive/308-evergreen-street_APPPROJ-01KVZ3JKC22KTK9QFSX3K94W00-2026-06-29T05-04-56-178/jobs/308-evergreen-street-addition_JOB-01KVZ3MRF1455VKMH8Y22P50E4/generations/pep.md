---
generation_kind: pep_v1
depends_on:
  - _company/rules/pep_rules.md
  - _company/rules/editor_rules.md
  - _company/rules/dev_rules.md
  - _company/knowledge/308_evergreen_wills_audit_transcript.md
  - _company/knowledge/_examples/wills_voice.md
  - _schemas/pep.schema.md
  - job_types/addition/rules/addition_rules.md
  - job_types/addition/rules/tdec_septic_permit_offset.md
  - job_types/addition/beliefs/stick_frame_default_for_small_additions.md
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/manifest.json
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/inputs/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/inputs/files/308_scope.pdf.txt
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/inputs/files/308_Evergreen_Addition.xlsx - Summary (1).csv.txt
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/beliefs/initial.md
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/generations/baseline.md
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/generations/risks.md
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/generations/task_graph.md
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/generations/task_graph.json
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/generations/schedule.json
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/generations/daily_schedule.md
last_verified_at: "2026-06-27T00:31:18.445Z"

version: 1
supersedes: null
status: draft

customer_price_usd: 173850
direct_cost_usd: 100778.92
margin_pct: 42.0

on_site_start_target: "2026-06-25"
on_site_completion_target: "2026-10-08"
duration_working_days: 75
duration_calendar_weeks: 16

pm_signed_by: null
pm_signed_at: null
customer_signed_by: null
customer_signed_at: null

milestones:
  - id: tdec_kickoff
    name: TDEC septic clock starts (call + $500 fee)
    target_day: -30
    gate_kind: permit
    blocks: [excavation.dig]
    notes: "6-cal-wk anchor. PM places call within 1 working day of contract signing. On-site Day 1 floats until this fires."
  - id: selections_finalized
    name: Customer selections locked
    target_day: -15
    gate_kind: customer_decision
    blocks: [order.tile, order.minisplit, order.vanity, order.vanity_fixtures, order.interior_doors, order.exterior_door, order.paint, order.lvt]
    notes: "Vanity model, faucets, mirrors, vanity lights, mini-split aesthetic, interior + pocket door styles, exterior door (still TBD per Round 2)."
  - id: permit_in_hand
    name: Building permit pulled (same-day walk-in)
    target_day: -15
    gate_kind: permit
    blocks: [demo.selective_demo]
    notes: "1-day walk-in per Will's audit. ~90% same-day approval."
  - id: amperage_verified
    name: Existing service amperage verified for 100A subpanel
    target_day: -15
    gate_kind: other
    blocks: [electrical.subpanel_install]
    notes: "CO trigger if insufficient. Per Round 1: assumed adequate but not verified."
  - id: equipment_confirmed_demo
    name: Demo equipment reserved (dumpster, saw, mini-ex, scaffolding)
    target_day: -10
    gate_kind: other
    blocks: [equipment.dumpster_arrive, equipment.demo_machines_arrive]
    notes: "2-wk reservation horizon."
  - id: tdec_clears
    name: TDEC septic permit in hand
    target_day: -1
    gate_kind: permit
    blocks: [excavation.dig]
    notes: "End of the 6-cal-wk window. Excavation cannot start until cleared."
  - id: onsite_start
    name: On-site Day 1 — site live
    target_day: 0
    gate_kind: trade_start
    blocks: [demo.protection]
    notes: "Site setup + Day-1 procurement orders + customer early item + prep-work-before-demo all fire."
  - id: lvl_arrived
    name: LVL beam delivered
    target_day: 10
    gate_kind: delivery
    blocks: [structural.install_lvl]
    notes: "Standard 3-ply 14\", 14 cal-d supplier lead."
  - id: subpanel_arrived
    name: 100A subpanel delivered
    target_day: 10
    gate_kind: delivery
    blocks: [electrical.subpanel_install]
    notes: "14 cal-d supplier lead."
  - id: tile_arrived
    name: Master bath tile delivered (special order)
    target_day: 10
    gate_kind: delivery
    blocks: [tile.shower_substrate]
    notes: "Per Round 4: special-order wall + mosaic combo, 14 cal-d. Float 41.5d to substrate; not bottleneck unless selections slipped."
  - id: footing_inspection
    name: Footing & slab-prep inspection (covers both, monolithic)
    target_day: 13
    gate_kind: inspection
    blocks: [foundation.monolithic_pour]
    notes: "Single inspection per Rule 4B. PM on site with camera + spray paint."
  - id: windows_arrived
    name: Windows + exterior door delivered
    target_day: 15
    gate_kind: delivery
    blocks: [windows.install]
    notes: "21 cal-d stock supplier lead."
  - id: roof_concealed_open
    name: Existing ceiling at roof tie-in opened (CO risk window)
    target_day: 24
    gate_kind: trade_start
    blocks: [roof.concealed_buffer]
    notes: "PM opens AM Day 1 of framing.roof to maximize 3-cal-d discovery buffer. Top CO risk on this job."
  - id: dried_in
    name: Structure dried-in (underlayment + windows complete)
    target_day: 29
    gate_kind: trade_start
    blocks: [siding.install, order.minisplit]
    notes: "Gates exterior siding + mini-split order trigger. Per Rule 4I, does NOT gate MEPs."
  - id: rough_inspection_bundled
    name: Rough bundled inspection (plumbing + electrical + HVAC + framing)
    target_day: 34
    gate_kind: inspection
    blocks: [buffer.post_rough_inspection]
    notes: "ONE inspector, ONE day per Rule 4C. PM on site full visit — photos, spray-paint, verbal pass/fail."
  - id: insulation_inspection
    name: Insulation inspection
    target_day: 39
    gate_kind: inspection
    blocks: [drywall.consolidated]
    notes: "Procedural; almost always passes. PM calls drywall crew when this is scheduled — gives 3-day-out target."
  - id: minisplit_arrived
    name: Mini-split unit delivered
    target_day: 39
    gate_kind: delivery
    blocks: [hvac.minisplit_install]
    notes: "Ordered Day 30 at dried-in per editor rules, 14 cal-d lead."
  - id: paint_phase_1
    name: Paint phase 1 (primer + ceiling finish coat, 1 day)
    target_day: 51
    gate_kind: trade_start
    blocks: [tile.shower_substrate, flooring.install, electrical.finish, retrofit.hall_bath_repaint]
    notes: "Per Rule 4E: AM primer walls+ceilings, PM ceiling finish coat. Walls left in primer for downstream trades."
  - id: substantial_completion
    name: Substantial completion (paint phase 2 ends)
    target_day: 68
    gate_kind: other
    blocks: [closeout.client_walkthrough]
    notes: "Per Rule 4F: fires when paint.phase_2 ends. Home is functionally usable."
  - id: final_inspection_bundled
    name: Final bundled inspection (electrical + plumbing + HVAC + building)
    target_day: 73
    gate_kind: inspection
    blocks: [milestone.co_handoff]
    notes: "ONE inspector, ONE day per Rule 4M. PM on site."
  - id: co_handoff
    name: Certificate of Occupancy + customer handoff
    target_day: 73
    gate_kind: other
    blocks: [closeout.wills_walkthrough]
    notes: "Fires same day as final inspection passes."
  - id: wills_walkthrough
    name: Will's personal final walkthrough with customer
    target_day: 74
    gate_kind: customer_decision
    blocks: []
    notes: "Per addition_rules: actual end of project from TCR's standpoint."

critical_path:
  - general.site_setup
  - prep.heat_pump_relocate
  - demo.protection
  - demo.selective_demo
  - demo.haul_out
  - excavation.dig
  - foundation.form_and_prep
  - inspect.footing
  - foundation.monolithic_pour
  - foundation.cure
  - framing.basement_walls
  - framing.floor_system
  - framing.exterior_walls
  - framing.roof
  - framing.sheathing
  - windows.install
  - roofing.underlayment
  - plumbing.rough_in
  - hvac.minisplit_rough
  - inspect.rough_bundled
  - buffer.post_rough_inspection
  - insulation.air_seal
  - insulation.install
  - inspect.insulation
  - drywall.consolidated
  - paint.phase_1
  - tile.shower_substrate
  - tile.shower_install
  - tile.grout_seal
  - shower.glass_template
  - wait.shower_glass
  - shower.glass_install
  - paint.phase_2
  - milestone.substantial_completion
  - closeout.client_walkthrough
  - closeout.punch_list_returns
  - closeout.final_clean
  - inspect.final_bundled
  - closeout.wills_walkthrough

open_commitments:
  - description: "TDEC septic call + $500 fee placed within 1 working day of signed agreement/deposit"
    owner: pm
    due: null
  - description: "Vanity model, faucets, mirrors, vanity lights, mini-split aesthetic, interior + pocket door styles, exterior door — lock with homeowner before checkpoint.selections_finalized"
    owner: customer
    due: "2026-06-04"
  - description: "Existing main service amperage verified for new 100A subpanel — schedule electrician for amperage check"
    owner: pm
    due: "2026-06-04"
  - description: "Demo equipment reserved (dumpster, concrete saw, mini-ex, skid steer, scaffolding)"
    owner: pm
    due: "2026-06-11"
  - description: "Customer notified that no verbal calendar start date is committed until contract signs — realistic start = signing + 6 cal-wk + 1 wk buffer"
    owner: pm
    due: null
  - description: "Shower glass supplier templating slot booked for Thu Sep 17 AM (immediately after grout cures)"
    owner: pm
    due: "2026-09-09"

contingencies:
  - trigger: "TDEC clock drags past 6 cal-wk (no soil scientist visit by T+10 cal-d, no report by T+21 cal-d, OR review queue holds permit past T+42 cal-d)"
    response: "Notify homeowner weekly of slip; on-site Day 1 moves 1:1 with TDEC clearance date. No on-site work begins until permit is in hand."
    cost_impact_usd: 0
    schedule_impact_days: 14
  - trigger: "TDEC soil scientist flags existing septic inadequate for new fixture count"
    response: "PM drafts CO (relocation / new tank+leach / grinder pump) within 48h of report. Homeowner approval BEFORE excavation Day 10 to avoid rebaselining."
    cost_impact_usd: 25000
    schedule_impact_days: 30
  - trigger: "Concealed roof tie-in reveals undersized rafters or rot when existing ceiling opens Day 25 (Wed Jul 29)"
    response: "3-cal-d buffer reserved (roof.concealed_buffer). PM photo-documents, generates CO same day if outside buffer scope. Major structural rebuild = ~5-10 wd slip."
    cost_impact_usd: 5000
    schedule_impact_days: 5
  - trigger: "Existing main service amperage insufficient for 100A subpanel (discovered Thu Jun 4 amperage check)"
    response: "Service upgrade CO; coordinate POCO scheduling 1-2 wk lead. If caught pre-contract, rebaseline. If post-contract, +5-10 wd to electrical.subpanel_install."
    cost_impact_usd: 3500
    schedule_impact_days: 10
  - trigger: "Selections still TBD on Day -1 (Wed Jun 3) lead-up to checkpoint.selections_finalized"
    response: "PM exercises pre-authorized backup-pick authority (from contract) within supplier catalog allowance. Document in events.jsonl."
    cost_impact_usd: 0
    schedule_impact_days: 5
  - trigger: "Shower glass template slot slips past Thu Sep 17 (Day 60)"
    response: "Substantial completion (Day 69 Wed Sep 30) slips 1:1 with template slip. 10-cal-d fab is the binding window — escalate to glass supplier same day."
    cost_impact_usd: 0
    schedule_impact_days: 3
  - trigger: "Homeowner reopens tankless WH option mid-job"
    response: "PM evaluates BEFORE plumbing rough Day 30 (Wed Aug 5). If approved later, insert tank-set sequence BEFORE rough; +0.5-1d if late."
    cost_impact_usd: 6500
    schedule_impact_days: 1
  - trigger: "Drywall hairline cracking at addition tie-ins (year-1 warranty)"
    response: "TCR returns to patch + touch-up paint. Standard addition practice; ~1d crew labor budgeted as warranty cost."
    cost_impact_usd: 0
    schedule_impact_days: 0
---

## Project summary

You're building a 30'×10' two-story addition for 308 Evergreen Street — basement storage below and a primary suite (bedroom + master bath + walk-in closet) above — plus retrofit work on the existing primary bedroom, hall bath, and basement storage. Pre-construction runs ~6 cal-weeks anchored on the TDEC septic permit (42 cal-d), targeting on-site Day 1 = **Thu Jun 25, 2026** and Will's final walkthrough = **Thu Oct 8, 2026** (75 working days on-site, ~16 cal-weeks). Customer total is **$173,850** against $100,779 direct cost (42% gross margin). The three live risks are (1) the TDEC clock — it floats until contract signs and PM places the call same-day; (2) the concealed roof tie-in into the existing 6/12 roof — biggest CO source on the job, absorbed by a 3-cal-d buffer that the PM has to *open the ceiling early on Day 25 to actually use*; and (3) the shower glass 10-cal-d fab chain — template MUST fire same-day as tile grout cure (Day 60) or substantial completion slips 1:1. The hall bath acrylic shower swap is a Rule 4V customer early item — it lands Day 2, BEFORE main demo, so the homeowner has a working shower during construction.

---

## Day-by-day

### Mon May 11 — PC Day -32

- **Preparing: TDEC septic kickoff** — confirm signed agreement + deposit are in hand; ready paperwork for the $500 fee and the soil-scientist site address. Due Wed May 13 (2 working days out).


### Tue May 12 — PC Day -31

- **Preparing: TDEC septic kickoff** — finalize TDEC contact + site-visit logistics; clear PM calendar for Wednesday's call. Due Wed May 13 (1 working day out).


### Wed May 13 — PC Day -30

*TDEC clock starts today — this is the anchor for the entire on-site Day 1 date.*

- **TDEC septic call + $500 fee** (`permit.tdec_septic` opens 42 cal-d window) — place call same day as signed agreement; record kickoff date in events.jsonl so the countdown is tracked. Soil scientist site visit follows in 1–2 weeks.

> ⚠ **Watch:** Per Will's voice: "TDEC can take a long time, it can go pretty quick — you can't really predict." 6 cal-wk is the safety budget, not a guarantee. If no soil scientist visit is scheduled by Wed May 27 (T+10 cal-d), escalate. On-site Day 1 floats 1:1 with TDEC clearance.


### Thu May 28 — PC Day -18

- **Preparing: Selections finalized** — kick off customer follow-up on vanity model, faucets, mirrors, vanity lights, mini-split aesthetic, interior + pocket door styles, exterior door. Tile/LVT/paint base palette already locked per Round 2. Due Thu Jun 4 (5 working days out).


### Fri May 29 — PC Day -17

- **Preparing: Selections finalized** — send written selection summary; confirm vendor catalogs received; flag tile sample receipt. Due Thu Jun 4 (4 working days out).


### Mon Jun 1 — PC Day -16

- **Preparing: Selections finalized** — review homeowner responses over the weekend; circle back on unanswered items by phone. Due Thu Jun 4 (3 working days out).


### Tue Jun 2 — PC Day -15

- **Preparing: Selections finalized** — press for final answers; flag any vendor delays on long-lead items. Due Thu Jun 4 (2 working days out).
- **Preparing: Pull building permit** — assemble permit package (drawings, scope, fees). Due Thu Jun 4 (2 working days out).


### Wed Jun 3 — PC Day -14

- **Preparing: Selections finalized** — lock final selections today; checkpoint hits tomorrow. If anything still TBD, exercise backup-pick authority and document. Due Thu Jun 4 (1 working day out).
- **Preparing: Pull building permit** — final scope/fee check; ready to walk in tomorrow. Due Thu Jun 4 (1 working day out).
- **Preparing: Amperage check** — confirm electrician scheduled for tomorrow's service-panel verification. Due Thu Jun 4 (1 working day out).


### Thu Jun 4 — PC Day -15 (anchor day)

*Selections lock, permit walk-in, pre-con walkthrough, amperage check — the pre-con anchor day.*

#### Milestone — Selections finalized

- **`checkpoint.selections_finalized`** fires today. All finish selections must be locked or PM-fallback-documented.
- **`general.permitting`** (general · 1d) — same-day walk-in. Per Will's audit, ~90% same-day approval.
- **`prep.amperage_check`** (electrical · 0.5d) — verify existing main supports new 100A subpanel. CO trigger if insufficient.
- **`general.pre_construction_walkthrough`** (general · 0.5d) — verify tie-in points + existing dimensions with homeowner. Photo-document the existing roof tie-in zone from below (baseline for the concealed-buffer CO conversation later).

> ⚠ **Watch:** Amperage-check failure is the only true CO trigger today. If main service can't accept the subpanel, PM presents service-upgrade CO within 48h. Pre-contract, this rebaselines the schedule; post-contract, it adds 5–10 wd to electrical rough.


### Tue Jun 9 — PC Day -12

- **Preparing: Equipment confirmed for demo** — call dumpster + concrete saw + mini-ex + skid steer + scaffolding vendors; confirm reservations. Due Thu Jun 11 (2 working days out).


### Wed Jun 10 — PC Day -11

- **Preparing: Equipment confirmed for demo** — final confirmations; lock delivery slot for Fri Jun 26. Due Thu Jun 11 (1 working day out).


### Thu Jun 11 — PC Day -10

#### Milestone — Equipment confirmed for demo

- **`checkpoint.equipment_confirmed_demo`** fires today. All five pieces (dumpster, concrete saw, mini-ex, skid steer, scaffolding) reserved for Fri Jun 26 delivery.


### Tue Jun 23 — PC Day -2

- **Preparing: Place windows order** — verify spec with supplier (3× 36"×60" DH + 1 transom), confirm pricing. Due Thu Jun 25 (2 working days out).
- **Preparing: Place LVL order** — verify standard 3-ply 14" availability with lumber supplier. Due Thu Jun 25 (2 working days out).
- **Preparing: Place subpanel order** — verify 100A subpanel SKU + breaker complement with electrical supplier. Due Thu Jun 25 (2 working days out).
- **Preparing: Place tile order** — confirm 30 sqft wall + mosaic floor combo + 14-cal-d lead time with tile supplier. Due Thu Jun 25 (2 working days out).
- **Preparing: Place vanity order** — confirm homeowner-selected 72" vanity model SKU. Due Thu Jun 25 (2 working days out).
- **Preparing: Place vanity-fixtures order** — bundle 2× faucets + 2× mirrors + 2× vanity lights + toilet. Due Thu Jun 25 (2 working days out).
- **Preparing: Place interior-doors order** — 1 pre-hung + 2 pocket door systems, styles per selections. Due Thu Jun 25 (2 working days out).
- **Preparing: Place exterior-door order** — confirm style from selections, $500 allowance. Due Thu Jun 25 (2 working days out).
- **Preparing: Site setup** — confirm signage, porta-john, staging zone with homeowner; verify driveway access for tomorrow's deliveries. Due Thu Jun 25 (2 working days out).


### Wed Jun 24 — PC Day -1

*TDEC permit clears today — the gate opens.*

- **`permit.tdec_septic`** ends today (42-cal-d window closes). Excavation gate is now clear for Day 10 (Wed Jul 8).
- **Preparing: Place windows order** — final supplier-pricing confirmation; press purchase tomorrow. Due Thu Jun 25 (1 working day out).
- **Preparing: Place LVL order** — confirm LVL availability + ship date; press purchase tomorrow. Due Thu Jun 25 (1 working day out).
- **Preparing: Place subpanel order** — confirm subpanel availability; press purchase tomorrow. Due Thu Jun 25 (1 working day out).
- **Preparing: Place tile order** — confirm 14-cal-d delivery commitment from supplier; press purchase tomorrow. Due Thu Jun 25 (1 working day out).
- **Preparing: Place vanity, vanity-fixtures, interior-doors, exterior-door orders** — confirm stock + 7-cal-d availability across the bundle; press purchase tomorrow. Due Thu Jun 25 (1 working day out).
- **Preparing: Site setup** — verify materials staged; confirm crew arrival window with foreman. Due Thu Jun 25 (1 working day out).

> ⚠ **Watch:** If TDEC has NOT cleared today, do NOT proceed to on-site Day 1. Hold the schedule. Notify homeowner same day.

*Tomorrow:* On-site Day 1 — crew arrives 7:00 AM, site goes live.

---

### Thu Jun 25 — Day 1 (On-Site Start)

*Site goes live; Day-1 procurement orders fire.*

- **`general.site_setup`** (general · 1d) [CP] — signage, porta-john, staging.
- **`order.windows`** — PM places windows + transom order today.
- **`order.lvl`** — PM places LVL beam order today.
- **`order.subpanel`** — PM places 100A subpanel order today.
- **`order.tile`** — PM places special-order tile combo today (14-cal-d to `checkpoint.tile_arrived`).
- **`order.exterior_door`**, **`order.vanity`**, **`order.vanity_fixtures`**, **`order.interior_doors`**, **`order.paint`**, **`order.lvt`** — PM fires all 6 collapsed finish orders today.

> 👷 **On site today:** General (site setup). Single trade — easy day for the foreman.

*Tomorrow:* HVAC + electrical + plumbing all on site for prep work + customer early item. Three trades — full coordination day.


### Fri Jun 26 — Day 2

*Prep-work-before-demo + customer early item — three trades on a 2-wd buffer before main demo.*

- **`prep.heat_pump_relocate`** (hvac · 1d) [CP] — relocate existing heat pump out of addition footprint.
- **`prep.electrical_disconnect_relocate`** (electrical · 0.5d) — relocate disconnect.
- **`early.acrylic_shower_swap`** (plumbing · 1d) — hall bath shower swap so homeowner has a working shower during construction. Rule 4V bucket #1.
- **`equipment.dumpster_arrive`** (general · 0.5d) — dumpster lands.
- **`equipment.demo_machines_arrive`** (general · 0.5d) — concrete saw, mini-ex, skid steer, scaffolding land.

> 👷 **On site today:** HVAC (heat pump), Electrical (disconnect), Plumbing (acrylic shower), General (equipment). Four trades — heavy coordination. Stagger arrival times so they're not tripping over each other.

> 📦 **Delivery today:** Dumpster (verify location with homeowner), concrete saw, mini-ex, skid steer, scaffolding. PM signs off on each delivery.

> ⚠ **Watch:** The acrylic shower swap is the customer's "working shower during construction" — verify it's functional before crew leaves. Do NOT tile or seal anything that gets disturbed by the Day 9 window infill or Day 53 repaint.


### Mon Jun 29 — Day 3

*Buffer day between prep work and demo (Rule 4K minimum 3 wd).*

- **Preparing: Floor protection & dust walls** — confirm demo crew (3-person) arrival Wed AM; verify dust-wall materials staged. Due Wed Jul 1 (2 working days out).


### Tue Jun 30 — Day 4

- **Preparing: Floor protection & dust walls** — final walk-through to identify all surfaces needing protection; pre-stage zip walls. Due Wed Jul 1 (1 working day out).


### Wed Jul 1 — Day 5

- **`demo.protection`** (demo · 1d, crew 3) [CP] — floor protection + dust walls. Site fully sealed before selective demo tomorrow.

*Tomorrow:* Selective demo crew + LVL bearing-wall expose crew (independent retrofit). Two demo crews working separate zones.


### Thu Jul 2 — Day 6

- **`demo.selective_demo`** Day 1/3 (demo · crew 3) [CP] — saw-cut walkway, addition demo, hall bath window removal.
- **`demo.expose_bearing_wall`** (demo · 1d, crew 2) — independent LVL retrofit, opens existing 2nd-story load-bearing wall.

> 👷 **On site today:** Demo (addition + walkway), Demo (LVL wall expose). Two demo crews — separate zones.


### Fri Jul 3 — Day 7

- **`demo.selective_demo`** Day 2/3 [CP].
- **`structural.temp_shoring`** (framing · 0.5d) — install temp shoring under exposed bearing wall.

> 👷 **On site today:** Demo, Framing. Two trades.

*(Sat Jul 4 — Independence Day observed Saturday; no schedule impact, weekend anyway.)*


### Mon Jul 6 — Day 8

- **`demo.selective_demo`** Day 3/3 [CP] — wraps remaining selective demo + railroad-tie removal.
- **Preparing: Excavate footing & slab area** — confirm mini-ex operator schedule; verify TDEC permit cleared (Wed Jun 24). Due Wed Jul 8 (2 working days out).


### Tue Jul 7 — Day 9

- **`demo.haul_out`** (demo · 1d, crew 2) [CP] — debris removal, dump runs.
- **`retrofit.hall_bath_window_infill_framing`** (framing · 0.5d) — frame the hall bath window opening (Rule 4V bucket #2, runs in parallel; rolled into drywall consolidation later).
- **Preparing: Excavate footing & slab area** — verify mini-ex on site, excavation flagged + utility-locate confirmed. Due Wed Jul 8 (1 working day out).

> 👷 **On site today:** Demo (haul-out), Framing (hall bath retrofit). Two trades.


### Wed Jul 8 — Day 10

*Excavation starts; three procurement checkpoints fire today.*

#### Milestone — LVL + subpanel + tile arrived

- **`excavation.dig`** Day 1/2 (excavation · crew 2 + mini-ex) [CP] — dig footings + slab area.
- **`framing.elevator_shaft`** (framing · 1d) — independent retrofit, framing only (no elevator system). Per Will's audit, elevator shaft is outside addition footprint.

> 📦 **Delivery today:** LVL beam (3-ply 14", verify dimensions before signing). Subpanel (100A, verify breakers + lugs). Tile (master bath wall + mosaic floor — count pieces, check for damage, stage in dry zone).

> 👷 **On site today:** Excavation (footings), Framing (elevator shaft). Plus three deliveries to receive — the PM owns the receiving desk today.


### Thu Jul 9 — Day 11

- **`excavation.dig`** Day 2/2 [CP].
- **`structural.install_lvl`** Day 1/1 (framing · crew 3) — gated on LVL arrival + temp shoring; FS lag 0 with checkpoint.lvl_arrived.

> 👷 **On site today:** Excavation, Framing (LVL install). Two trades.


### Fri Jul 10 — Day 12

- **`foundation.form_and_prep`** Day 1/1.5 (concrete · crew 4) [CP] — form footings + gravel base + vapor barrier + rebar in ONE continuous task (Rule 4B monolithic).
- **`structural.remove_temp_shoring`** (framing · 0.5d) — closes the LVL retrofit sub-chain (covered by bundled framing inspection later).

> 👷 **On site today:** Concrete (foundation form), Framing (LVL closeout). Two trades.


### Mon Jul 13 — Day 13

- **`foundation.form_and_prep`** Day 2/1.5 (last 0.5d) [CP].
- **Preparing: Footing inspection** — call inspector to schedule tomorrow's slot; verify drawings + permit are on site. Due Tue Jul 14 (1 working day out).


### Tue Jul 14 — Day 14

#### Milestone — Footing inspection

- **`inspect.footing`** (inspector · 0.5d) [CP] — single inspection covers BOTH footing and slab prep (monolithic per Rule 4B). **PM physically on site** — camera, spray paint, get verbal pass/fail same day.

> ⚠ **Watch:** Inspectors write shitty reports and don't answer phones. PM on site is the only way to know what failed and why. Spray-paint anything flagged before crew leaves.


### Wed Jul 15 — Day 15

- **`foundation.monolithic_pour`** (concrete · 1d, crew 4) [CP] — footings + 4" slab same day, single pour.


### Thu Jul 16 — Day 16

*Foundation cure begins (2 cal-d); windows arrive.*

#### Milestone — Windows arrived

- **`foundation.cure`** Day 1/2 (cal-d lead_time) [CP] — no on-site work.
- **Preparing: Frame basement walls** — confirm framing crew (3-person) arrival Mon AM; verify lumber drop. Due Mon Jul 20 (2 working days out).

> 📦 **Delivery today:** Windows (3× 36"×60" DH + 1 transom) + 1 exterior door. Verify count, glass condition, sign off with driver. Stage in garage.


### Fri Jul 17 — Day 17

- **`foundation.cure`** Day 2/2 (cal-d lead_time) [CP] — slab cured, ready for framing Monday.
- **Preparing: Frame basement walls** — verify lumber on site, layout chalked. Due Mon Jul 20 (1 working day out).


### Mon Jul 20 — Day 18

- **`framing.basement_walls`** Day 1/2 (framing · crew 3) [CP].


### Tue Jul 21 — Day 19

- **`framing.basement_walls`** Day 2/2 [CP].


### Wed Jul 22 — Day 20

- **`framing.floor_system`** Day 1/2 (framing · crew 3) [CP] — depends only on basement walls (LVL retrofit independent per Will's audit).


### Thu Jul 23 — Day 21

- **`framing.floor_system`** Day 2/2 [CP].


### Fri Jul 24 — Day 22

- **`framing.exterior_walls`** Day 1/3 (framing · crew 3) [CP].


### Mon Jul 27 — Day 23

- **`framing.exterior_walls`** Day 2/3 [CP].
- **`framing.interior_walls`** Day 1/2 (framing · crew 3, SS lag 1 with exterior) — interior partitions for primary bedroom, master bath, WIC.


### Tue Jul 28 — Day 24

- **`framing.exterior_walls`** Day 3/3 [CP].
- **`framing.interior_walls`** Day 2/2.

*Tomorrow:* Roof framing starts — concealed tie-in CO risk window opens.


### Wed Jul 29 — Day 25 (concealed roof tie-in window opens)

- **`framing.roof`** Day 1/3 (framing · crew 3) [CP] — stick-frame 3/12 gable, tie into existing 6/12 per Round 2.

> ⚠ **Watch:** Open the existing ceiling at the tie-in **TODAY, AM**, before the framing crew commits. This is the single biggest CO source on the job. Photo-document existing rafter conditions immediately. The 3-cal-d `roof.concealed_buffer` starts tomorrow (SS lag 1) — early discovery = full buffer to absorb a CO without slipping interior trades.


### Thu Jul 30 — Day 26

- **`framing.roof`** Day 2/3 [CP].
- **`roof.concealed_buffer`** opens (3 cal-d lead_time, SS lag 1 after framing.roof start).


### Fri Jul 31 — Day 27

- **`framing.roof`** Day 3/3 [CP] — roof framed. Concealed buffer continues over weekend.

*Tomorrow:* Sheathing + windows install — windows go in IMMEDIATELY after roof framed per Rule 4J, parallel with underlayment.


### Mon Aug 3 — Day 28

- **`framing.sheathing`** (framing · 1d) [CP].
- **`windows.install`** Day 1/2 (windows_doors · crew 2) [CP] — install immediately after roof framed per Rule 4J, parallel with underlayment. Concealed buffer closes today (Day 3 of 3 cal-d).
- **Preparing: Place mini-split order** — verify homeowner-locked aesthetic + supplier stock, ~14 cal-d lead. Due Wed Aug 5 (2 working days out).
- **Preparing: Plumbing rough-in** — confirm plumber (2-crew) arrival Wed AM; verify vent-stack penetration locations with framing crew. Due Wed Aug 5 (2 working days out).

> 👷 **On site today:** Framing (sheathing), Windows/doors (install). Two trades.


### Tue Aug 4 — Day 29

- **`roofing.underlayment`** (roofing · 1d, crew 3) [CP].
- **`windows.install`** Day 2/2 [CP].
- **Preparing: Place mini-split order** — press purchase tomorrow. Due Wed Aug 5 (1 working day out).
- **Preparing: Plumbing rough-in** — verify supply + waste materials staged. Due Wed Aug 5 (1 working day out).

> 👷 **On site today:** Roofing (underlayment), Windows/doors (install). Two trades.


### Wed Aug 5 — Day 30 (dried-in)

#### Milestone — Dried-in

- **`roofing.shingles`** (roofing · 1d, crew 3) — up to 6,000 sqft/day per Will; 300 sqft addition = 1 day easy.
- **`milestone.dried_in`** fires (after underlayment + windows). Gates exterior siding + `order.minisplit`.
- **`plumbing.rough_in`** Day 1/4 (plumbing · crew 2) [CP] — Will's nominal 4d floor for master bath + W/D relocation + vent stacks.
- **`electrical.subpanel_install`** (electrical · 1d, crew 1) — gated on subpanel arrived + amperage check (cleared Jun 4).
- **`siding.install`** Day 1/3 (siding · crew 3) — exterior crew, doesn't count vs. 2-trade interior cap.
- **`order.minisplit`** — PM places mini-split order today (timed at dried-in per editor rules).

> 👷 **On site today:** Roofing (shingles), Plumbing (rough), Electrical (subpanel), Siding (install). Four crews active — exterior crews (roofing + siding) free to overlap; PM coordinates interior crew arrival times.


### Thu Aug 6 — Day 31

- **`plumbing.rough_in`** Day 2/4 [CP].
- **`electrical.rough_in`** Day 1/1.5 (electrical · crew 2, SS lag 1 with plumbing).
- **`siding.install`** Day 2/3.

> 👷 **On site today:** Plumbing (rough), Electrical (rough), Siding. Three trades — plumbing + electrical interior at 2-trade cap, siding exterior.


### Fri Aug 7 — Day 32

- **`plumbing.rough_in`** Day 3/4 [CP].
- **`electrical.rough_in`** Day 2/1.5 — finishes today.
- **`siding.install`** Day 3/3 — siding wraps.

> 👷 **On site today:** Plumbing, Electrical, Siding. Three trades.


### Mon Aug 10 — Day 33

- **`plumbing.rough_in`** Day 4/4 [CP].
- **`siding.trim_fascia_soffit_gutters`** Day 1/2 (siding · crew 3) — same-crew continuation.

> 👷 **On site today:** Plumbing (rough wraps), Siding (trim). Two trades.


### Tue Aug 11 — Day 34

- **`hvac.minisplit_rough`** (hvac · 0.5d, crew 1) [CP] — mini-split line set only, last MEP per Rule 4G.
- **`siding.trim_fascia_soffit_gutters`** Day 2/2.
- **Preparing: Bundled rough inspection** — call inspector to lock tomorrow's slot; confirm all four rough trades complete + ready for walk. Due Wed Aug 12 (1 working day out).

> 👷 **On site today:** HVAC (line set), Siding (trim). Two trades.

*Tomorrow:* Bundled rough inspection day — single inspector covers plumbing + electrical + HVAC + framing in one visit.


### Wed Aug 12 — Day 35

#### Milestone — Bundled rough inspection

- **`inspect.rough_bundled`** (inspector · 0.5d) [CP] — ONE inspector, ONE day, covers plumbing + electrical + HVAC line set + framing per Rule 4C. **PM physically on site full visit** — camera, spray-paint flagged items, get verbal pass/fail same day.
- **`equipment.insulation_material_arrival`** (general · 0.5d) — insulation material lands SAME DAY as inspection so it's staged for post-inspection install (TCR-specific rule).

> 📦 **Delivery today:** Insulation material (R13 walls + R30 attic + R30 floor). Stage in garage; don't unwrap.

> ⚠ **Watch:** Expect at least one trade to be flagged. The 2-wd punch-list buffer (Thu–Fri) is for re-inspection. If plumbing flags something serious, hold insulation crew over the weekend.


### Thu Aug 13 — Day 36

- **`buffer.post_rough_inspection`** Day 1/2 (lead_time) [CP] — punch-list loop; trades return for fixes.
- **Preparing: Insulation air-seal** — confirm insulation crew (2-person) arrival Mon AM; verify air-seal materials. Due Mon Aug 17 (2 working days out).


### Fri Aug 14 — Day 37

- **`buffer.post_rough_inspection`** Day 2/2 [CP] — re-inspection if needed.
- **Preparing: Insulation air-seal** — verify all rough-inspection punch items cleared; if not, hold Mon start. Due Mon Aug 17 (1 working day out).


### Mon Aug 17 — Day 38

- **`insulation.air_seal`** (insulation · 0.5d, crew 2) [CP] — air-seal all penetrations.
- **`insulation.install`** Day 1/1 (insulation · crew 2) [CP] — R13 walls + R30 attic + R30 floor.
- **`retrofit.hall_bath_insulation`** (insulation · 0.5d) — retrofit insulation runs alongside main crew (Rule 4V bucket #2 same trade).

> 👷 **On site today:** Insulation (main + retrofit, same trade). Single trade in two zones.


### Tue Aug 18 — Day 39

- **`insulation.install`** finishes [CP] (Day 2 covers wrap of Day 1's scheduled span).
- **Preparing: Insulation inspection** — call inspector for tomorrow's slot. Due Wed Aug 19 (1 working day out).
- **Preparing: Drywall consolidated** — call drywall crew (3-person) NOW (per editor rule: call when insulation inspection is scheduled, not after it passes — 3-day-out target). Confirm Thu AM arrival. Due Thu Aug 20 (2 working days out).


### Wed Aug 19 — Day 40

#### Milestone — Insulation inspection + mini-split arrived

- **`inspect.insulation`** (inspector · 0.5d) [CP] — procedural, almost always passes. PM on site.
- **`checkpoint.minisplit_arrived`** fires today — mini-split delivered.
- **Preparing: Drywall consolidated** — verify drywall + tape + mud + sander all staged; confirm crew arrival. Due Thu Aug 20 (1 working day out).

> 📦 **Delivery today:** Mini-split unit (verify model matches homeowner selection). Stage in garage.


### Thu Aug 20 — Day 41

- **`drywall.consolidated`** Day 1/11 (drywall · crew 3) [CP] — single block: addition + existing primary bedroom + hall bath patch + basement storage. Hang → tape → sand → prime, internal cure baked in.


### Fri Aug 21 — Day 42

- **`drywall.consolidated`** Day 2/11 [CP].


### Mon Aug 24 — Day 43

- **`drywall.consolidated`** Day 3/11 [CP].


### Tue Aug 25 — Day 44

- **`drywall.consolidated`** Day 4/11 [CP].


### Wed Aug 26 — Day 45

- **`drywall.consolidated`** Day 5/11 [CP].


### Thu Aug 27 — Day 46

- **`drywall.consolidated`** Day 6/11 [CP].


### Fri Aug 28 — Day 47

- **`drywall.consolidated`** Day 7/11 [CP].


### Mon Aug 31 — Day 48

- **`drywall.consolidated`** Day 8/11 [CP].


### Tue Sep 1 — Day 49

- **`drywall.consolidated`** Day 9/11 [CP].


### Wed Sep 2 — Day 50

- **`drywall.consolidated`** Day 10/11 [CP].


### Thu Sep 3 — Day 51

- **`drywall.consolidated`** Day 11/11 [CP] — drywall block wraps.
- **Preparing: Master bath tile substrate** — verify tile delivery (`checkpoint.tile_arrived` fired Jul 9) staged dry; confirm tile crew (2-person) arrival Tue AM (Labor Day Monday). Due Tue Sep 8 (2 working days out, skip Labor Day).


### Fri Sep 4 — Day 52

- **`paint.phase_1`** (paint · 1d, crew 2) [CP] — AM: primer walls + ceilings. PM: ceiling finish coat (same day per Will's standard sequence). Walls left in primer for downstream trades.
- **Preparing: Master bath tile substrate** — verify shower-pan waterproofing membrane + foam-board substrate staged. Due Tue Sep 8 (1 working day out, skip Labor Day).

*(Mon Sep 7 — Labor Day, off.)*


### Tue Sep 8 — Day 53 (interior finishes begin)

- **`tile.shower_substrate`** (tile · 1d, crew 2) [CP] — pan + waterproofing prep.
- **`electrical.finish`** Day 1/2.5 (electrical · crew 2) — devices, recessed cans, dimmers, vent fan.
- **`retrofit.hall_bath_repaint`** (paint · 0.5d) — Rule 4V bucket #2 closeout.

> 👷 **On site today:** Tile (master bath), Electrical (finish), Paint (hall bath touch-up). Three trades — paint is brief touch-up in different zone; effective interior cap is 2 (tile + electrical).


### Wed Sep 9 — Day 54

- **`tile.shower_install`** Day 1/5 [CP] — wall tile + mosaic floor + niche + bench.
- **`electrical.finish`** Day 2/2.5.
- **`flooring.install`** Day 1/3 (flooring · crew 2) — LVT throughout addition + bedroom + storage.

> 👷 **On site today:** Tile (master bath), Electrical (finish), Flooring (LVT). Three trades — schedule electrical to finish AM so two-trade cap (tile + flooring) holds PM.

> ⚠ **Watch:** Book the shower glass supplier's templating slot TODAY for Thu Sep 17 AM. The 10-cal-d fab window is the binding constraint; template slot must be locked a week out.


### Thu Sep 10 — Day 55

- **`tile.shower_install`** Day 2/5 [CP].
- **`electrical.finish`** Day 3/2.5 — wraps today.
- **`flooring.install`** Day 2/3.
- **`hvac.minisplit_install`** Day 1/1 (hvac · crew 1) — staggered AFTER electrical.finish per Rule 4N HVAC stagger to preserve interior cap.

> 👷 **On site today:** Tile, Electrical (wraps AM), Flooring, HVAC (mini-split). Four trades briefly — Rule 4N stagger keeps it manageable: electrical wraps morning, HVAC takes electrical's slot afternoon. Effective trade count = 2 interior at any moment.


### Fri Sep 11 — Day 56

- **`tile.shower_install`** Day 3/5 [CP].
- **`flooring.install`** Day 3/3 — LVT wraps.
- **`hvac.minisplit_install`** Day 2/2 — wraps today (1d / 1 person per editor rules; spans Thu–Fri due to install-day scheduling).

> 👷 **On site today:** Tile, Flooring, HVAC. Three trades — flooring wraps morning, manageable.


### Mon Sep 14 — Day 57

- **`tile.shower_install`** Day 4/5 [CP].
- **`vanity.install`** (cabinets · 0.5d, crew 2) — 72" double vanity.
- **`trim.install`** Day 1/3 (trim_carpentry · crew 2) — base, casing, 4 interior doors (1 pre-hung + 2 pocket + 1 closet).

> 👷 **On site today:** Tile, Cabinets (vanity), Trim. Three trades — vanity 0.5d wraps AM, then tile + trim at cap.


### Tue Sep 15 — Day 58

- **`tile.shower_install`** Day 5/5 [CP].
- **`trim.install`** Day 2/3.

> 👷 **On site today:** Tile (last day), Trim. Two trades — at cap.


### Wed Sep 16 — Day 59

- **`tile.grout_seal`** Day 1/1.5 [CP].
- **`trim.install`** Day 3/3 — wraps.

> 👷 **On site today:** Tile (grout), Trim (wraps). Two trades.


### Thu Sep 17 — Day 60 (shower glass template — critical)

- **`tile.grout_seal`** finishes (AM) [CP].
- **`shower.glass_template`** (glazing · 0.5d) [CP] — glass supplier templates AFTER grout sets. **Same-day-as-grout** is non-negotiable.
- **`plumbing.finish`** Day 1 (plumbing · crew 2) — faucets, toilet, dual-valve shower trim, W/D hookup.

> 👷 **On site today:** Tile (grout AM), Glazing (template), Plumbing (finish). Three trades — tile wraps AM, glazing is brief PM, plumbing the active interior trade.

> ⚠ **Watch:** This is the most fragile day in the schedule. If glass templating slips even 2–3 days, substantial completion (Day 69 Wed Sep 30) slips 1:1. Confirm template slot was held; PM on site when glass supplier arrives.


### Fri Sep 18 — Day 61

- **`wait.shower_glass`** opens (10 cal-d fab) [CP] — no on-site glass work until Wed Sep 30.
- **`plumbing.finish`** Day 2 (continues, finishes Mon Sep 21 per schedule scheduled_end).


### Mon Sep 21 — Day 62

- **`plumbing.finish`** wraps (scheduled_end 2026-09-21) — fixtures complete.

*Days 63–68 (Tue Sep 22 → Tue Sep 29): the master bath is idle awaiting glass fab. No other interior finish work fills the gap — every finish trade is already done. Crew off site; PM stays in monitoring mode.*


### Tue Sep 29 — Day 68

- **Preparing: Shower glass install + Paint phase 2** — confirm glass supplier installation slot for Wed AM; confirm paint crew (2-person) arrival Wed AM. Verify nothing got scuffed in the empty week.


### Wed Sep 30 — Day 69 (substantial completion eve)

- **`shower.glass_install`** (glazing · 0.5d) [CP] — frameless 3/8" door + return panel.
- **`paint.phase_2`** Day 1/1 (paint · crew 2) [CP] — final wall cut-in + roll. LAST work task on site per Rule 4F.

> 👷 **On site today:** Glazing (install AM), Paint (phase 2). Two trades — glazing wraps morning.

*Tomorrow:* Substantial completion + client walkthrough.


### Thu Oct 1 — Day 70

#### Milestone — Substantial completion

- **`paint.phase_2`** finishes [CP].
- **`milestone.substantial_completion`** fires (FS-after paint.phase_2 only per Rule 4F).
- **`closeout.client_walkthrough`** (general · 0.5d) — PM walks homeowner through using Will's punch-list SOP; **point out at least 2 items the customer didn't see (builds trust)**; customer SIGNS the punch list to lock it.

> ⚠ **Watch:** The signed punch list IS the closing scope. Anything not on it after Thursday becomes a warranty issue or a CO, not a closeout fix. Be thorough.

---

### Fri Oct 2 — Day 71

- **`closeout.punch_list_returns`** Day 1/2 [CP] — trades return for flagged items.


### Mon Oct 5 — Day 72

- **`closeout.punch_list_returns`** Day 2/2 [CP].


### Tue Oct 6 — Day 73

- **`closeout.final_clean`** (cleanup · 1d, crew 2) [CP] — whole-house final clean.
- **Preparing: Final bundled inspection** — call inspector to confirm tomorrow's slot; verify all finals (electrical + plumbing + HVAC + building) are ready. Due Wed Oct 7 (1 working day out).


### Wed Oct 7 — Day 74

#### Milestone — Final inspection + CO

- **`inspect.final_bundled`** (inspector · 0.5d) [CP] — ONE inspector covers all four finals (electrical + plumbing + HVAC + building) per Rule 4M. PM on site.
- **`milestone.co_handoff`** fires (FS-after final inspection). Certificate of Occupancy in hand.

*Tomorrow:* Will's personal walkthrough — actual end of project from TCR's standpoint.


### Thu Oct 8 — Day 75 (project end)

- **`closeout.wills_walkthrough`** (general · 0.5d) [CP] — Will's personal final touchpoint with the customer. **Project ends.**

---

## Key assumptions

- **TDEC clock starts at contract signing.** On-site Day 1 (Thu Jun 25) is anchored on TDEC kickoff Wed May 13 — if signing slips, Day 1 moves 1:1. No verbal calendar date was committed to homeowner per Round 2.
- **Stick-framed roof, no truss procurement.** 300 sqft footprint / ~10' max wall / 3/12 pitch all inside the sub-800 sqft / sub-24' default per `stick_frame_default_for_small_additions`. Lumber arrives day-of with the framing crew. If design pivots to engineered trusses, add 28–42 cal-d truss procurement and re-anchor.
- **Monolithic foundation pour** per Rule 4B (95% of TCR jobs). Single footing inspection covers both footing + slab. If scope pivots to stem walls / CMU (rare), add ~3 wd for separate pour + cure + inspection.
- **Existing gas water heater stays** per Round 1 (tankless WH optional NOT accepted). Vent extension through new roof only — no `procurement.tank`, no `plumbing.tank_set`. If homeowner reopens mid-job, insert tank-set BEFORE plumbing rough Day 30.
- **Closet & cabinet optional NOT accepted** per Round 3. Master WIC finishes = paint + LVT + trim only (covered by base interior).
- **Plumbing rough = 4d × 2-crew floor** (Will's nominal, transcript line 1942) — master bath + W/D relocation + vent stacks all qualify. Not compressible.
- **Drywall consolidated to 11 wd** — multi-zone (addition + existing primary bedroom + hall bath patch + basement storage) per editor multi-zone guidance.
- **Mini-split sequence: 0.5d rough / 1d install / 1 person** per Will's audit (lines 476, 494).
- **HVAC stagger per Rule 4N** — `hvac.minisplit_install` serialized AFTER `electrical.finish` to preserve 2-trade interior cap when the finish cluster converges Days 53–56.
- **Special-order tile, 14-cal-d chain** per Round 4. `order.tile` Day 1 → `wait.tile` → `checkpoint.tile_arrived` Day 10. Float 41.5 wd — not bottleneck unless selections slip past PC Day -15.
- **Shower glass enclosure: frameless 3/8" tempered, 10-cal-d fab** per Round 4. Template MUST fire same-day as grout cures (Day 60) — substantial completion slips 1:1 if delayed.
- **No weather days budgeted.** Roofing (Days 28–30), siding (Days 30–34), exterior trim (Days 33–34) are weather-sensitive. v0.1 of the scheduler does not model weather; if heavy rain falls on those dates, add days at face value.
- **Drywall hairline cracking warranty return** in year 1 at addition tie-ins (standard TCR practice per `addition_rules`). Internal cost; not in main schedule.
- **2-trade interior cap is a HARD constraint per Rule 4N.** Schedule shows 3+ trades on Days 53–55 — manage via time-of-day stagger (e.g. electrical AM, HVAC PM Day 55).
- **Customer early item Rule 4V two-bucket pattern:** `early.acrylic_shower_swap` is Day 2 (site_prep), the hall bath retrofit window infill + drywall patch + repaint is separate (`hall_bath_mod` Component, Days 9/41/53). Same physical room, two timing buckets.
- **Critical path covers 41% of tasks (39/94)** — schedule reflow warning. Graph may be over-parallelized; real construction has more serial dependency than people expect. If interior-finish trades trip over each other Days 53–57, expect 1–2 wd absorbed from float.
