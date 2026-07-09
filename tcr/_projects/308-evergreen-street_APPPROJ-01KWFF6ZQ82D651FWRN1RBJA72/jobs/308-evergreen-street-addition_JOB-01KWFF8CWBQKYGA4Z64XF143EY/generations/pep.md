---
generation_kind: pep_v2
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWFF6ZQ82D651FWRN1RBJA72/jobs/308-evergreen-street-addition_JOB-01KWFF8CWBQKYGA4Z64XF143EY/manifest.json
  - _projects/308-evergreen-street_APPPROJ-01KWFF6ZQ82D651FWRN1RBJA72/jobs/308-evergreen-street-addition_JOB-01KWFF8CWBQKYGA4Z64XF143EY/generations/task_graph.json
  - _projects/308-evergreen-street_APPPROJ-01KWFF6ZQ82D651FWRN1RBJA72/jobs/308-evergreen-street-addition_JOB-01KWFF8CWBQKYGA4Z64XF143EY/generations/schedule.json
  - _projects/308-evergreen-street_APPPROJ-01KWFF6ZQ82D651FWRN1RBJA72/jobs/308-evergreen-street-addition_JOB-01KWFF8CWBQKYGA4Z64XF143EY/generations/daily_schedule.md
  - _projects/308-evergreen-street_APPPROJ-01KWFF6ZQ82D651FWRN1RBJA72/jobs/308-evergreen-street-addition_JOB-01KWFF8CWBQKYGA4Z64XF143EY/generations/risks.md
  - _projects/308-evergreen-street_APPPROJ-01KWFF6ZQ82D651FWRN1RBJA72/jobs/308-evergreen-street-addition_JOB-01KWFF8CWBQKYGA4Z64XF143EY/intelligence/facts.md
  - _projects/308-evergreen-street_APPPROJ-01KWFF6ZQ82D651FWRN1RBJA72/jobs/308-evergreen-street-addition_JOB-01KWFF8CWBQKYGA4Z64XF143EY/intelligence/confirmed.md
  - _projects/308-evergreen-street_APPPROJ-01KWFF6ZQ82D651FWRN1RBJA72/jobs/308-evergreen-street-addition_JOB-01KWFF8CWBQKYGA4Z64XF143EY/intelligence/applicable_rules.json
version: 1
supersedes: null
status: draft
customer_price_usd: 173850.00
direct_cost_usd: 100778.92
margin_pct: 42.03
on_site_start_target: "2026-07-01"
on_site_completion_target: "2026-10-05"
duration_working_days: 68
duration_calendar_weeks: 14
pm_signed_by: null
pm_signed_at: null
customer_signed_by: null
customer_signed_at: null
milestones:
  - id: checkpoint.selections_finalized
    name: Selections finalized (finishes, tile, LVT, vanity, fixtures)
    target_day: -15
    gate_kind: checkpoint
    blocks: [procurement.windows.order, procurement.tile.order, procurement.doors.order]
    notes: "Pre-con Day 1 (2026-06-10); 5-working-day lead-up window 2026-06-03 → 2026-06-09."
  - id: checkpoint.equipment_confirmed
    name: Equipment / spec sheets confirmed (mini-split, subpanel, exterior door, vanity)
    target_day: -10
    gate_kind: checkpoint
    blocks: [procurement.mini_split.order, procurement.subpanel.order, procurement.doors.order]
    notes: "Pre-con Day 8 (2026-06-17); 5-working-day lead-up window 2026-06-10 → 2026-06-16."
  - id: procurement.lvl.arrived
    name: LVL beam on site
    target_day: 10
    gate_kind: procurement
    blocks: [structural.lvl_install]
    notes: "Arrives 2026-07-20. Order placed on Day 5 (2026-07-07); 10 cal-d supplier lead."
  - id: procurement.doors.arrived
    name: Doors on site (pocket-door frame gates framing)
    target_day: 12
    gate_kind: procurement
    blocks: [framing.walls, trim.install]
    notes: "Arrives 2026-07-24. Pocket-door frame required during framing.walls (Day 18)."
  - id: procurement.windows.arrived
    name: Windows on site
    target_day: 21
    gate_kind: procurement
    blocks: [windows.install]
    notes: "Arrives 2026-08-07. Order placed Day 14 (2026-07-20); 18 cal-d supplier lead — zero float."
  - id: milestone.dried_in
    name: Dried-in (roof + windows + WRB complete)
    target_day: 24
    gate_kind: milestone
    blocks: []
    notes: "Informational marker on 2026-08-11. MEPs are gated on roofing.underlayment (Day 21), not this milestone."
  - id: procurement.subpanel.arrived
    name: 100A subpanel on site
    target_day: 26
    gate_kind: procurement
    blocks: [electrical.rough]
    notes: "Arrives 2026-08-13. Amperage check must clear before subpanel order (Day 17, 2026-07-31)."
  - id: procurement.tile.arrived
    name: Master bath tile + waterproofing on site
    target_day: 41
    gate_kind: procurement
    blocks: [master_bath.tile_shower]
    notes: "Arrives 2026-09-08. Zero float on critical path."
  - id: procurement.mini_split.arrived
    name: Mini-split on site
    target_day: 51
    gate_kind: procurement
    blocks: [hvac.mini_split_install]
    notes: "Arrives 2026-09-23. Ordered Day 43 (2026-09-10)."
  - id: milestone.substantial_completion
    name: Substantial completion
    target_day: 68
    gate_kind: milestone
    blocks: []
    notes: "2026-10-05. Balance due per scope terms; customer walkthrough Fri 2026-10-02 with Will."
critical_path:
  - prep.relocate_heat_pump
  - site.demo
  - foundation.excavate
  - foundation.footings_slab_pour
  - structural.lvl_install
  - framing.floor_system
  - framing.walls
  - framing.roof
  - roofing.sheathing
  - roofing.underlayment
  - windows.install
  - plumbing.rough
  - electrical.rough
  - hvac.mini_split_rough
  - inspect.rough_bundled
  - punch.rough_buffer
  - insulation.install
  - inspect.insulation
  - drywall.hang_finish
  - paint.phase_1
  - master_bath.tile_shower
  - flooring.lvt
  - trim.install
  - electrical.finish
  - hvac.mini_split_install
  - paint.phase_2
  - inspect.final
  - punch.closeout
  - milestone.substantial_completion
open_commitments:
  - description: "Execute amperage check by 2026-06-24 (10 wd pre-con) — if existing service <200A, service upgrade change order before checkpoint.equipment_confirmed."
    owner: pm
    due: "2026-06-24"
  - description: "Reconcile Row 25 negative section total (−$1,714, 72 labor hrs) — material credit before baseline budget close."
    owner: pm
    due: "2026-06-30"
  - description: "TDEC septic inspection outcome — confirm capacity sufficient for added bedroom + bath; reverts to grinder-pump CO if insufficient."
    owner: pm
    due: "2026-06-15"
  - description: "Line-item scope $173,850 vs CSV cost+markup arithmetic — identify margin dollar figure explicitly."
    owner: pm
    due: "2026-06-30"
contingencies:
  - trigger: "Framing.tie_in_discovery exceeds 2 crew-days (chimney flashing + cricket + 3/12↔6/12 slope transition worse than plans imply)"
    response: "Invoke pre-written change order template; add chimney flashing + cricket to procurement (7–14 cal-d lead) if not already ordered."
    cost_impact_usd: 6000
    schedule_impact_days: 5
  - trigger: "Amperage check finds existing service <200A capacity for new 100A subpanel + mini-split + 30A elevator circuit"
    response: "Utility coordination + POCO drop; PM change order BEFORE 2026-06-17 equipment checkpoint."
    cost_impact_usd: 5000
    schedule_impact_days: 15
  - trigger: "Silent omissions in CSV (chimney, WH vent extension, elevator 30A circuit, W/D roof venting) draw against burden markup instead of change order"
    response: "PM to reconcile line-by-line before baseline_v2 sign-off; convert each silent line to CSV row OR documented change-order trigger."
    cost_impact_usd: 15000
    schedule_impact_days: 0
  - trigger: "Basement walk-out vs below-grade ambiguity surfaces during excavation (grade slopes toward addition, or customer expected waterproofed below-grade)"
    response: "Photo + written customer acknowledgement before 2026-07-01 on-site start; drainage change order before slab pour (2026-07-13) if grading shifts."
    cost_impact_usd: 4000
    schedule_impact_days: 4
  - trigger: "Plumbing rough burn exceeds 56 hrs (87.5% of 64-hr floor) or roof-penetration cluster hits existing-condition surprises (rot, framing conflict, code clearance)"
    response: "Weekly plumbing burn tracking; coordinate all roof penetration flashings with roofer on 2026-08-06 underlayment day."
    cost_impact_usd: 3500
    schedule_impact_days: 2
last_verified_at: "2026-07-01T19:00:39.512Z"
---

## Project summary

You're building a 30'×10' two-story addition at 308 Evergreen — 590 sqft total across a basement-level storage room and a 1st-floor primary bedroom + master bath + walk-in-closet expansion, plus a hall-bath retrofit and a framed 4'×4' shaft for a future 101 Mobility elevator. Pre-construction opens Wed **2026-06-10** (3 weeks ahead of on-site) and on-site work runs Wed **2026-07-01** through substantial completion on Mon **2026-10-05** — **68 working days** across ~14 calendar weeks, minus Independence Day observance (Sat 2026-07-04) and Labor Day (Mon 2026-09-07). Customer price is locked at **$173,850** (materials cost+15% / subs cost+30% + margin); raw cost basis is **$100,778.92** per the CSV, targeting ~42% gross margin before contingency draws. The three real schedule risks are (1) the multi-valley 3/12↔6/12 roof tie-in with the existing chimney inside the new envelope — no chimney cricket in the CSV; (2) the amperage check outcome, which gates the 100A subpanel order and could trigger a 5–15 wd utility-coordination service upgrade; (3) an 18-cal-d window supplier chain with zero float — an order slip on Day 14 lands directly on the critical path. Framing is stick-built (no truss procurement) per company default for a 295-sqft/level, ~10 ft-span addition, and cladding is 100% vinyl lap siding — the "NEW BRICK TO MATCH EXISTING" note on the design set is out of date per PM confirmation.

---

## Day-by-day

### Wed Jun 3 — PC Day -5

*Selections clock starts — push customer for tile, LVT, vanity, paint, fixture answers all week.*

- **Preparing: Selections finalized** — kick off customer follow-up on outstanding tile, LVT, vanity, paint, fixture SKUs. Due Wed Jun 10 (5 working days out).


### Thu Jun 4 — PC Day -4

- **Preparing: Selections finalized** — send selection summary email; confirm master-bath tile sample receipt. Due Wed Jun 10 (4 working days out).


### Fri Jun 5 — PC Day -3

- **Preparing: Selections finalized** — review homeowner responses; circle back on unanswered items. Due Wed Jun 10 (3 working days out).


### Mon Jun 8 — PC Day -2

- **Preparing: Selections finalized** — press for final answers; flag any vendor delays. Due Wed Jun 10 (2 working days out).
- **Preparing: Building permit** — assemble permit package (drawings, scope, fees) for Washington Co. TN office. Due Wed Jun 10 (2 working days out).
- **Preparing: TDEC septic inspection** — call TDEC inspector, pull septic as-built if available. Due Wed Jun 10 (2 working days out).
- **Preparing: Amperage check** — confirm existing service panel location + access with electrician. Due Wed Jun 10 (2 working days out).


### Tue Jun 9 — PC Day -1

- **Preparing: Selections finalized** — lock final selections today; checkpoint hits tomorrow. Due Wed Jun 10 (1 working day out).
- **Preparing: Building permit** — final scope/fee check; ready to walk in tomorrow. Due Wed Jun 10 (1 working day out).
- **Preparing: TDEC septic inspection** — confirm inspector arrival window; capacity-only, no install. Due Wed Jun 10 (1 working day out).
- **Preparing: Amperage check** — verify meter access + panel schedule with electrician for tomorrow. Due Wed Jun 10 (1 working day out).

> ⚠ **Watch:** Amperage check outcome is the single biggest pre-con gate. If existing service is <200A, service upgrade (~$2.5–5K, 5–15 wd utility coordination) fires and the 2026-06-17 equipment checkpoint slips. Escalation deadline is Wed 2026-06-24 (T-10wd) — if amperage isn't verified by then, pause the subpanel order.


### Wed Jun 10 — PC Day 1 (Pre-Con Kickoff)

*Pre-con anchor day — three checkpoints and permits go in the same morning.*

- **Selections finalized** (checkpoint) — hits today. Downstream: tile / LVT / doors / vanity orders unblock.
- **Building permit application + issuance** (pm · 1d) — walk-in at Washington Co. TN permit office.
- **TDEC septic inspection** (pm · 1d) — inspection-only per q.sewer_septic_direction; confirms existing septic capacity for added bedroom + bath.
- **Amperage check** (electrical · 0.5d) — verify existing service can support new 100A subpanel + mini-split + 30A elevator circuit.
- **Preparing: Equipment / spec sheets confirmed** — kick off supplier spec-sheet pulls for mini-split, subpanel, exterior door, vanity. Due Wed Jun 17 (5 working days out).

> ⚠ **Watch:** TDEC finding capacity insufficient reverses the "existing septic stays" decision and opens grinder-pump / relocation CO territory (scope carves this to change order). Also — if amperage check fails today, pause `procurement.subpanel.order` immediately.


### Thu Jun 11 — PC Day 2

- **Preparing: Equipment / spec sheets confirmed** — request cut sheets from mini-split supplier + subpanel + exterior door vendor. Due Wed Jun 17 (4 working days out).


### Fri Jun 12 — PC Day 3

- **Preparing: Equipment / spec sheets confirmed** — review received spec sheets; flag any dimension conflicts. Due Wed Jun 17 (3 working days out).


### Mon Jun 15 — PC Day 4

- **Preparing: Equipment / spec sheets confirmed** — press vendors on any late spec sheets; verify vanity cut dimensions. Due Wed Jun 17 (2 working days out).


### Tue Jun 16 — PC Day 5

- **Preparing: Equipment / spec sheets confirmed** — lock all spec sheets today; checkpoint hits tomorrow. Due Wed Jun 17 (1 working day out).


### Wed Jun 17 — PC Day 6 (Equipment Checkpoint)

*Equipment locked — mini-split / subpanel / exterior-door / vanity spec sheets signed off.*

- **Equipment confirmed** (checkpoint) — hits today. Downstream: mini-split order + subpanel order + doors order unblock.

> ⚠ **Watch:** Six long-lead procurement chains ride on this checkpoint (windows, LVL, mini-split, subpanel, tile, doors). Any slip today cascades — windows in particular have zero float on the 18-cal-d supplier chain.

*Weeks Jun 18 → Jun 30 are slack absorption — orders release when their upstream gates hit (see procurement anchors on Days 5, 9, 14, 23, 38, 51). No new PM prep tasks land in this window.*

---

### Wed Jul 1 — Day 1 (On-Site Kickoff)

*Two-bucket kickoff — customer-early hall bath swap runs alongside heat-pump relocation to open the 3-wd demo lag.*

- **Hall bath acrylic shower swap** (plumbing · 1d) — customer-requested early item per q.hall_bath_acrylic_shower_timing; remove tub/shower combo, install acrylic pan + walls, REUSE existing valve/trim. Customer keeps a working shower for the rest of the job.
- **Relocate existing heat pump + electrical disconnect** (hvac · 1d) — dev_rules §4K requires this ≥3 wd before demo. Opens the demo lag window.

> 👷 **On site today:** Plumbing (hall-bath acrylic swap) + HVAC (heat-pump relocate). Two trades — at cap.

> ⚠ **Watch:** No demo today. Days 2–4 are the mandatory 3-wd lag before `site.demo` can start. Use them for dumpster staging.


### Thu Jul 2 — Day 2

*Site idle — heat-pump lag continues.*

- No active work. PM should stage the demo dumpster + backhoe rental for Tuesday.


### Mon Jul 6 — Day 4

*Site idle — final lag day; demo mobilizes tomorrow.*

- Confirm 3-crew demo team, dumpster on site, backhoe delivered.

*Tomorrow:* Demo crew arrives 7:00 AM; sawcut walkway + railroad-tie removal begins.


### Tue Jul 7 — Day 5 ★

*Demo starts — critical-path Day 1. LVL order goes in.*

- **Selective demo** (demo · 3 crew, 2d) — sawcut concrete walkway, remove railroad ties, clear site.
- **LVL order placed** (pm · procurement) — 3-ply 14" @ ~15'-6" span; 7–14 cal-d supplier wait begins.

> 📦 **Delivery today:** Dumpster + backhoe on site (verify by 7:00 AM).


### Wed Jul 8 — Day 6 ★

- **Selective demo** (demo · day 2 of 2) — finish site clearing.

*Tomorrow:* Excavator on site 7:00 AM for footing dig.


### Thu Jul 9 — Day 7 ★

*Excavation opens — 2-day dig window.*

- **Foundation excavate** (excavation · 2 crew, 2d) — dig for 12"×12" perimeter footings + slab base.


### Fri Jul 10 — Day 8 ★

- **Foundation excavate** (excavation · day 2 of 2) — finish grading; ready for gravel/vapor barrier/rebar Monday.
- **Preparing: Foundation inspection** — schedule TN foundation inspector for Monday's pre-pour walk. Due Mon Jul 13 (1 working day out).

*Tomorrow:* Concrete crew arrives Monday for pre-pour prep + monolithic pour.


### Mon Jul 13 — Day 9 ★

*Critical pour day — inspector on site pre-pour.*

- **Foundation footings + slab pour** (concrete · 3 crew, day 1 of 2) — monolithic 12"×12" perimeter footings + 4" slab; gravel base, vapor barrier, rebar.
- **Foundation inspection** (inspector · 0.5d, SS with pour) — pre-pour footing walk.
- **Doors order placed** (pm · procurement) — 3× pre-hung panel + 1× pocket door frame + 1 exterior door; 10 cal-d wait.

> ⚠ **Watch:** PM required on site for pre-pour inspection. Get the sign-off before concrete truck backs in.

> 👷 **On site today:** Concrete (pour) + Inspector (foundation). Verify inspector cleared before concrete arrives.


### Tue Jul 14 — Day 10 ★

- **Foundation footings + slab pour** (concrete · day 2 of 2) — finish pour; screed + trowel.

*Days 11–13 (Wed–Fri) are the 3-wd slab-cure lag. LVL is still in supplier lead-time — no on-site work.*


### Mon Jul 20 — Day 14 ★

*Structural core starts — LVL install opens the existing bearing wall.*

- **LVL install + temporary shoring** (framing · 3 crew, day 1 of 2) — 3-ply 14" beam spanning ~15'-6"; open existing bearing wall between old house + new primary bedroom.
- **Windows order placed** (pm · procurement) — 2 new units (3'×3' D.H. + 3'×1' transom); 18 cal-d wait begins — **zero float**.

> 📦 **Delivery today:** LVL beam (3-ply 14"). Verify count + straightness before framing crew unloads. Stage adjacent to bearing-wall opening.

> ⚠ **Watch:** Windows are the tightest procurement chain on the job. Any vendor slip lands directly on Day 28 windows.install and pushes MEP rough right.


### Tue Jul 21 — Day 15 ★

- **LVL install + temporary shoring** (framing · day 2 of 2).


### Wed Jul 22 — Day 16 ★

*Floor system framing — 2-day block.*

- **Frame floor system + subfloor** (framing · 3 crew, day 1 of 2) — glued + fastened subfloor over LVL + joists.


### Thu Jul 23 — Day 17 ★

- **Frame floor system + subfloor** (framing · day 2 of 2).


### Fri Jul 24 — Day 18 ★

*Wall framing opens — pocket-door frame on hard gate; doors arrive today.*

- **Frame exterior + interior walls both levels** (framing · 3 crew, day 1 of 5) — includes elevator shaft framing + pocket-door frame rough-in.

> 📦 **Delivery today:** Doors (3× pre-hung panel + 1× pocket-door frame + 1 exterior door). Count + inspect glass on exterior door; hard-gate the pocket-door frame — framing needs it today.


### Mon Jul 27 — Day 19 ★

- **Frame walls** (framing · day 2 of 5).


### Tue Jul 28 — Day 20 ★

*Wall framing continues + retrofit tie-in discovery starts (SS+2 overlap).*

- **Frame walls** (framing · day 3 of 5).
- **Retrofit tie-in discovery + framing** (framing · 3 crew, day 1 of 2) — chimney envelope, 3/12↔6/12 slope transition, window/door relocation framing. Per rule `retrofit_tie_in_discovery` (job_types/addition, rank 200).

> ⚠ **Watch:** Chimney flashing + cricket is NOT itemized in scope or CSV (Silent Omission #9). If field conditions are worse than plans imply, framing.tie_in_discovery exceeds 2 crew-days — invoke the pre-written "roof tie-in field conditions" change-order template.


### Wed Jul 29 — Day 21 ★

- **Frame walls** (framing · day 4 of 5).
- **Retrofit tie-in discovery + framing** (framing · day 2 of 2).


### Thu Jul 30 — Day 22 ★

- **Frame walls** (framing · day 5 of 5).


### Fri Jul 31 — Day 23 ★

*Roof framing opens — stick-built (no truss). Subpanel order releases.*

- **Frame new gable roof** (framing · 3 crew, day 1 of 3) — stick-frame 3/12 gable tying to existing 6/12 per belief `stick_frame_default_for_small_additions`.
- **Subpanel order placed** (pm · procurement) — 100A subpanel; amperage-check pre-req satisfied (pre-con Day 1). 10 cal-d wait.


### Mon Aug 3 — Day 24 ★

- **Frame roof** (framing · day 2 of 3).


### Tue Aug 4 — Day 25 ★

- **Frame roof** (framing · day 3 of 3).

*Tomorrow:* Sheathing + WRB — the last framing-crew day before roofing takes over.


### Wed Aug 5 — Day 26 ★

- **Roof sheathing + wall WRB** (framing · 3 crew, 1d).

*Tomorrow:* Roofing crew mobilizes; underlayment is the dry-in gate.


### Thu Aug 6 — Day 27 ★

*Dry-in gate — unlocks windows, MEPs, and siding.*

- **Roofing underlayment + drip edge + temporary dry-in** (roofing · 2 crew, 1d) — synthetic underlayment per dev_rules §4I/§4J and rule `siding_starts_at_underlayment`.

> ⚠ **Watch:** Weather-sensitive. Rain-day risk mid-August TN. Roofing + siding share the same 2-person crew (belief `roof_and_siding_same_crew`) — serialize.

*Tomorrow:* Windows arrive + install starts; roofing crew moves to shingles.


### Fri Aug 7 — Day 28 ★

*Windows land + install opens; shingles start on the same roofing crew.*

- **Install 2 new windows + relocate 2 existing + set exterior door** (windows_doors · 2 crew, day 1 of 2) — +1d absorbed for window relocation labor per q.window_count_and_relocation.
- **Roofing shingles** (roofing · 2 crew, day 1 of 2) — architectural shingles, valleys, chimney cricket, ridge vent.

> 📦 **Delivery today:** Windows (2 units: 3'×3' D.H. + 3'×1' transom). Verify count + inspect glass for damage; sign off with driver.

> 👷 **On site today:** Windows/doors + Roofing. Two exterior trades — coordinate the ladder access.


### Mon Aug 10 — Day 29 ★

- **Windows install** (windows_doors · day 2 of 2) — finish new + relocated openings.
- **Roofing shingles** (roofing · day 2 of 2) — chimney cricket + ridge vent.

> 👷 **On site today:** Windows/doors + Roofing. Both wrap today.


### Tue Aug 11 — Day 30 ★

*Dried-in milestone. Exterior siding starts + MEP rough kicks off.*

#### Milestone — Dried-in

- **Milestone: Dried-in** (pm, informational) — roof + windows + WRB complete.
- **Siding install** (siding · 2 crew, day 1 of 3) — vinyl lap, ALL exterior; NO brick veneer per q.brick_veneer_scope.
- **Plumbing rough-in** (plumbing · 2 crew, day 1 of 4) — supply/waste/vent, master bath, W/D relocation, gas WH vent extension through new roof.

> 👷 **On site today:** Siding + Plumbing. Two trades — at cap.

> ⚠ **Watch:** Plumbing repriced to 64-hr floor per company rule `plumbing_rough_min_duration` (up from CSV's 40 hrs). Track burn against 64 hrs; escalate at 56 hrs (~87.5%).


### Wed Aug 12 — Day 31 ★

- **Siding install** (siding · day 2 of 3).
- **Exterior trim + gutters** (siding · SS+1 overlap) — fascia, vinyl soffit, seamless gutters.
- **Plumbing rough-in** (plumbing · day 2 of 4).

> 👷 **On site today:** Siding (2 tasks — same crew) + Plumbing. At cap.


### Thu Aug 13 — Day 32 ★

*Electrical rough joins the stack — SS+2 stagger per §4N.*

- **Siding install** (siding · day 3 of 3).
- **Plumbing rough-in** (plumbing · day 3 of 4).
- **Electrical rough** (electrical · 2 crew, day 1 of 3) — subpanel install, receptacles, lighting, 30A elevator circuit.

> 📦 **Delivery today:** 100A subpanel. Verify meter + panel schedule with electrician before install.

> 👷 **On site today:** Siding + Plumbing + Electrical. Three trades — one is exterior (siding), so ≤2 interior at cap ✓.


### Fri Aug 14 — Day 33 ★

- **Plumbing rough-in** (plumbing · day 4 of 4) — final day at the 64-hr floor.
- **Electrical rough** (electrical · day 2 of 3).

> 👷 **On site today:** Plumbing + Electrical. Two interior trades — at cap.


### Mon Aug 17 — Day 34 ★

- **Electrical rough** (electrical · day 3 of 3).
- **Preparing: Bundled rough inspection** — schedule TN inspector for Tuesday; framing + plumbing + electrical + HVAC all bundled per dev_rules §4C. Due Tue Aug 18 (1 working day out).


### Tue Aug 18 — Day 35 ★

*Mini-split rough (LAST in MEP sequence) + bundled inspection Day 1.*

- **Mini-split rough** (hvac · 1 crew, 0.5d) — line-set + condensate; LAST in MEP order per §4G.
- **Bundled rough inspection** (inspector · 1d, day 1 of 1) — framing + plumbing + electrical + HVAC.

> ⚠ **Watch:** PM required on site for rough inspection. One inspector, one day, all trades — any red-tag consumes the 2-day punch buffer.


### Wed Aug 19 — Day 36 ★

- **Rough inspection wrap-up** (paperwork; sign-off).
- **Post-rough punch buffer** (general · day 1 of 2) — address any red-tags before insulation.


### Thu Aug 20 — Day 37 ★

- **Post-rough punch buffer** (general · day 2 of 2).


### Fri Aug 21 — Day 38 ★

*Insulation opens. Tile order releases.*

- **Insulation install** (insulation · 2 crew, day 1 of 2) — R13 walls, R30 attic, R30 floor + air seal.
- **Tile order placed** (pm · procurement) — master bath tile (wall + mosaic floor) + waterproofing; 14 cal-d wait.


### Mon Aug 24 — Day 39 ★

- **Insulation install** (insulation · day 2 of 2).
- **Preparing: Insulation inspection** — schedule TN insulation inspector for Tuesday; drywall crew calendared per belief `drywall_soft_schedule`. Due Tue Aug 25 (1 working day out).


### Tue Aug 25 — Day 40 ★

- **Insulation inspection** (inspector · 0.5d).

> ⚠ **Watch:** PM required on site. Drywall crew commit fires TODAY per soft-schedule belief — call the drywall sub within 1 wd of inspection clearing.


### Wed Aug 26 — Day 41 ★

*Drywall opens — longest single critical block on the job.*

- **Drywall hang + finish** (drywall · 3 crew, day 1 of 6) — hang + 3-coat compound + sand to L3 (addition + primary bedroom + hall bath).


### Thu Aug 27 — Day 42 ★

- **Drywall hang + finish** (drywall · day 2 of 6).


### Fri Aug 28 — Day 43 ★

- **Drywall hang + finish** (drywall · day 3 of 6).


### Mon Aug 31 — Day 44 ★

- **Drywall hang + finish** (drywall · day 4 of 6).


### Tue Sep 1 — Day 45 ★

- **Drywall hang + finish** (drywall · day 5 of 6).


### Wed Sep 2 — Day 46 ★

- **Drywall hang + finish** (drywall · day 6 of 6).

*Tomorrow:* Paint phase 1 (primer + ceilings) opens.


### Thu Sep 3 — Day 47 ★

*Paint phase 1 opens — primer + ceilings per dev_rules §4E.*

- **Paint phase 1** (paint · 2 crew, day 1 of 2) — primer + ceilings.


### Fri Sep 4 — Day 48 ★

- **Paint phase 1** (paint · day 2 of 2).

*Mon 2026-09-07 — Labor Day; no work.*


### Tue Sep 8 — Day 49 ★

*Master bath tile shower opens (critical path). Hall bath retrofit finish also opens (off-critical).*

- **Master bath tile shower** (tile · 2 crew, day 1 of 4) — waterproof + wall tile + mosaic floor + niche + bench.
- **Hall bath finish** (general · 2 crew, day 1 of 2) — remove window/infill, insulate, drywall patch, PVC trim, repaint (acrylic swap already done Day 1).

> 📦 **Delivery today:** Master bath tile + waterproofing. Verify quantities against tile schedule; stage indoors.

> 👷 **On site today:** Tile + General (hall bath). Two trades — at cap.


### Wed Sep 9 — Day 50 ★

- **Master bath tile shower** (tile · day 2 of 4).
- **Hall bath finish** (general · day 2 of 2).

> 👷 **On site today:** Tile + General.


### Thu Sep 10 — Day 51 ★

*Mini-split order releases with 7–14 cal-d wait.*

- **Master bath tile shower** (tile · day 3 of 4).
- **Mini-split order placed** (pm · procurement).


### Fri Sep 11 — Day 52 ★

- **Master bath tile shower** (tile · day 4 of 4).

*Tomorrow:* LVT flooring opens Monday.


### Mon Sep 14 — Day 53 ★

*LVT flooring — precedes trim per §4L.*

- **LVT flooring throughout** (flooring · 2 crew, day 1 of 2) — $3/sqft; entire addition + primary bedroom + hall bath.


### Tue Sep 15 — Day 54 ★

- **LVT flooring throughout** (flooring · day 2 of 2).


### Wed Sep 16 — Day 55 ★

*Trim carpentry opens — 3-day block; doors get hung.*

- **Trim install** (trim_carpentry · 2 crew, day 1 of 3) — 5-1/4" base + 2-1/4" casing + hang 3 pre-hung panel doors + 1 pocket door.


### Thu Sep 17 — Day 56 ★

- **Trim install** (trim_carpentry · day 2 of 3).


### Fri Sep 18 — Day 57 ★

- **Trim install** (trim_carpentry · day 3 of 3).


### Mon Sep 21 — Day 58 ★

*Electrical + plumbing finish opens (float 1d on plumbing).*

- **Electrical finish** (electrical · 2 crew, day 1 of 2) — devices, ~12 recessed (18-cap allowance), vanity lights, fan/light, GFCI/AFCI.
- **Plumbing finish** (plumbing · 2 crew, day 1 of 2) — 72" double vanity, 2 faucets, commode, shower valve trim.

> 👷 **On site today:** Electrical + Plumbing. Two interior trades — at cap.


### Tue Sep 22 — Day 59 ★

- **Electrical finish** (electrical · day 2 of 2).
- **Plumbing finish** (plumbing · day 2 of 2).

> 👷 **On site today:** Electrical + Plumbing (finish tail).

*Tomorrow:* Mini-split install (single-day HVAC task) — mini-split arrives.


### Wed Sep 23 — Day 60 ★

*Mini-split install — 1d, 1 person per §4G.*

- **Mini-split install** (hvac · 1 crew, 1d) — head + condenser set + commissioning.

> 📦 **Delivery today:** Mini-split unit. Verify serial + accessories against spec sheet locked at PC Day 6.

*Tomorrow:* Paint phase 2 opens — every finish trade must be complete first.


### Thu Sep 24 — Day 61 ★

*Paint phase 2 — every finish trade complete, per dev_rules §4E/§4F.*

- **Paint phase 2** (paint · 2 crew, day 1 of 3) — finish coats (2) + trim touch-up.


### Fri Sep 25 — Day 62 ★

- **Paint phase 2** (paint · day 2 of 3).


### Mon Sep 28 — Day 63 ★

- **Paint phase 2** (paint · day 3 of 3).
- **Preparing: Final inspection** — schedule TN final inspector for Tuesday; building + electrical + plumbing + HVAC all bundled. Due Tue Sep 29 (1 working day out).


### Tue Sep 29 — Day 64 ★

*Final inspection — one inspector, one day, all trades.*

- **Final inspection** (inspector · 1d) — building + electrical + plumbing + HVAC.

> ⚠ **Watch:** PM required on site. Any red-tag consumes the 3-day closeout punch buffer that follows.


### Wed Sep 30 — Day 65 ★

*Closeout punch opens.*

- **Punch list + closeout** (general · 2 crew, day 1 of 3) — punch list from inspection.


### Thu Oct 1 — Day 66 ★

- **Punch list + closeout** (general · day 2 of 3) — final cleaning.


### Fri Oct 2 — Day 67 ★

*Customer walkthrough with Will.*

- **Punch list + closeout** (general · day 3 of 3) — customer walkthrough with Will (addition playbook).

> ⚠ **Watch:** This is the customer-facing closeout moment. Have the PEP + punch-list sign-off ready. Balance-due invoice teed up for Monday.

*Tomorrow:* Substantial completion Monday; balance due.


### Mon Oct 5 — Day 68 ★

*Job closes. Balance due per scope terms.*

#### Milestone — Substantial completion

- **Milestone: Substantial completion** (pm) — final marker.

---

## Key assumptions

- **Customer price is fully-loaded.** $173,850 includes materials cost+15% / subs cost+30% + margin; CSV $100,778.92 is raw cost basis only. Both figures are correct for their purposes. *(round 1, q.scope_vs_csv_total_reconciliation; rule `_company/rules/scope_vs_csv_total_reconciliation.md`, rank 100.)*
- **Framing is stick-built. No truss procurement.** Small addition (295 sqft/level, ~10 ft span) defaults to stick-frame per belief `job_types/addition/beliefs/stick_frame_default_for_small_additions.md` (rank 200). Scope's "truss OR rafter" ambiguity resolved to stick per company default + dev_rules §4Q. If wrong, add 14–28 cal-d truss procurement ahead of `framing.roof` (Days 23–25 slip right).
- **Existing septic stays; TDEC inspection is capacity-only.** No new septic tank, leach field, or grinder pump. *(round 1, q.sewer_septic_direction.)* If TDEC finds capacity insufficient, the `tdec_septic_permit_offset` rule fires (30-wd pre-con offset + 42-cal-d permit wait) and the pre-con runway blows out to ≥8 weeks.
- **Existing gas water heater remains.** Tankless Optional Package NOT elected. Scope only includes extending existing gas WH vent through the new roof — no `plumbing.tank_set` task. *(round 1, q.tankless_water_heater_election.)* CSV row 11's label "HVAC – Mini Split, Tankless WH & Relocations" is misleading; $5,140 material is mini-split + HVAC relocations only.
- **Cladding is 100% vinyl lap siding. No brick veneer.** Plans' "NEW BRICK TO MATCH EXISTING" notes are out of date. *(round 1, q.brick_veneer_scope.)* Same 2-person crew handles roof + siding per belief `roof_and_siding_same_crew` (rank 100) — serialized in wall-clock.
- **Windows: 2 new + 2 relocated existing.** Procurement order is for 2 new units (3'×3' D.H. + 3'×1' transom); labor line includes window relocation. *(round 1, q.window_count_and_relocation.)* Scope's "(4) windows" was counting relocated existing as new.
- **Interior doors: 3 pre-hung panel + 1 pocket.** Pocket door at hall-bath entry per plans p.3; pocket-door frame rough-in happens during framing.walls (Day 18). *(round 1, q.interior_doors_pocket_vs_panel.)*
- **Hall-bath acrylic shower swap runs Day 1 as customer-early.** Two-bucket the hall bath: acrylic swap Day 1 (customer needs working shower), remainder of retrofit runs mid-job Days 49–50. *(round 1, q.hall_bath_acrylic_shower_timing; dev_rules §4V.)*
- **Plumbing rough labor at 64-hr floor.** Repriced from CSV's 40 hrs to 4 wd × 2 crew = 64 hrs per company rule `plumbing_rough_min_duration`. Adds ~24 labor-hrs to plumbing budget. *(round 1, q.plumbing_rough_labor_floor; rule `_company/rules/dev_rules.md` §4G.)*
- **Existing electrical service assumed to support new 100A subpanel.** `prep.amperage_check` on PC Day 1 (2026-06-10) gates the subpanel order per rule `_company/rules/service_amperage_check.md` (rank 100). If existing service <200A, service upgrade CO fires and the equipment checkpoint (2026-06-17) slips.
- **Foundation is monolithic slab-on-grade.** 12"×12" perimeter footings + 4" slab poured together per dev_rules §4B. No CMU or full-height foundation wall. Combined with 8ft basement-wall height + brick-veneer removal, the "basement" is effectively a walk-out / at-grade framed lower level, not a waterproofed below-grade space.
- **Rough inspections bundled. One inspector, one day, all trades.** Framing + plumbing + electrical + HVAC on Day 35 per dev_rules §4C, followed by 2-wd punch buffer per §4D.
- **Selections + equipment are separate checkpoints.** `checkpoint.selections_finalized` at PC Day 1 (-15 wd) and `checkpoint.equipment_confirmed` at PC Day 6 (-10 wd) per dev_rules §4P. Selections lead-up 5 wd; equipment lead-up 5 wd — overlapping windows PM works Jun 3 → Jun 16.
- **Drywall crew is soft-scheduled.** Committed only after `inspect.insulation` calendared per belief `drywall_soft_schedule` (rank 100). If insulation inspection (2026-08-25) slips, drywall booking window compresses — PM should call the drywall sub within 1 wd of inspection clearing.
- **Chimney flashing / cricket NOT itemized in CSV.** Surfaces via rule `job_types/addition/rules/retrofit_tie_in_discovery.md` (rank 200) — 2-day `framing.tie_in_discovery` buffer already in the graph (Days 20–21, SS+2 with framing.walls). If field conditions worse than plans imply, this buffer overruns and the pre-written CO template fires. See contingencies[0] in frontmatter — ~$2.5–6K, 2–5 wd.
