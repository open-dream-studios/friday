---
generation_kind: intelligence_interview_v2
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWBXP28R0M3VYB6NXFZMY9V0/jobs/308-evergreen-street-addition_JOB-01KWBXQF226SWCB8W7F05C39G9/manifest.json
  - _projects/308-evergreen-street_APPPROJ-01KWBXP28R0M3VYB6NXFZMY9V0/jobs/308-evergreen-street-addition_JOB-01KWBXQF226SWCB8W7F05C39G9/intelligence/extracted/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KWBXP28R0M3VYB6NXFZMY9V0/jobs/308-evergreen-street-addition_JOB-01KWBXQF226SWCB8W7F05C39G9/intelligence/extracted/breakdown.md
  - _projects/308-evergreen-street_APPPROJ-01KWBXP28R0M3VYB6NXFZMY9V0/jobs/308-evergreen-street-addition_JOB-01KWBXQF226SWCB8W7F05C39G9/intelligence/extracted/plans.md
  - _projects/308-evergreen-street_APPPROJ-01KWBXP28R0M3VYB6NXFZMY9V0/jobs/308-evergreen-street-addition_JOB-01KWBXQF226SWCB8W7F05C39G9/intelligence/applicable_rules.json
  - _projects/308-evergreen-street_APPPROJ-01KWBXP28R0M3VYB6NXFZMY9V0/jobs/308-evergreen-street-addition_JOB-01KWBXQF226SWCB8W7F05C39G9/interview/round-1.md
  - _projects/308-evergreen-street_APPPROJ-01KWBXP28R0M3VYB6NXFZMY9V0/jobs/308-evergreen-street-addition_JOB-01KWBXQF226SWCB8W7F05C39G9/interview/round-2.md
---

# Facts — what we know about 308 Evergreen Addition

This file is the synthesized "what we know" layer. Downstream generations (task_graph_v2, baseline_v2, pep_v2) read THIS instead of raw inputs + rules. Citations: `(scope L<n>)`, `(breakdown row)`, `(plans p<n>)`, `(rule: <layer>:<path>, rank <N>)`, `(round N, q.<id>)`.

## Customer & job

- Customer: 308 Evergreen Street (manifest.json `customer`), internally "Simons Addition" (scope L1, plans title block).
- Job type: **addition** (manifest.json `job_type`), priced contract value $100,778.92 base (breakdown row 5 Grand Total) within the customer-quoted $173,850 total investment (scope L82).
- Started 2026-06-30; no completion date (manifest.json).

## Scope — what's being built

- **Two-story addition, ~30' × 10' footprint, 590 sqft new addition area** (plans p3: 295 first-floor + 295 basement).
- **Objective areas** (addition_rules retrofit detection Step 1): basement-level **storage**, second-floor **primary bedroom**, **master bathroom**, **walk-in closet** (scope L3-6).
- Plus retrofit work to existing primary bedroom (~12'5"×16') and existing hall bath (scope L131, L145).
- Plus framing-only future elevator shaft 4'×4' inside the addition footprint (scope L49, plans p3) — electrical 30A circuit only; elevator system NOT in scope.
- CSV header footprint 789 sqft includes ~200 sqft existing primary bedroom retrofit area on top of the 590 sqft new addition (breakdown header note).

## Site

- Existing house: brick on basement level + lap siding upper per plans elevations. Addition matches: **NEW BRICK on basement-level + NEW vinyl lap siding on second floor** — drawings authoritative; scope's vinyl-only line (L62) is stale and being revised. Requires masonry sub + `procurement.brick` (~2 wk lead). Flagged as LIKELY materials change-order. *(round 1, q.brick_or_vinyl_addition)*
- Sewer/septic: **Home is on SEPTIC. TCR handles the TDEC septic permit** (adding bedroom + master bath triggers soil/field review). 6-week pre-construction window anchors the realistic on-site start date. Emit `permit.tdec_septic` `kind: lead_time, lead_time_days: 42, pre_construction_offset_working_days: 30` (rule: job_type:tdec_septic_permit_offset, rank 200). Septic relocation/replacement and grinder install remain explicit CHANGE-ORDER exclusions (scope L29-30). *(round 1, q.septic_or_sewer)*
- **TDEC application: NOT YET SUBMITTED. Target submit date 2026-07-07** (PM gathering field/soil data this week). 6-week typical TDEC turnaround + 1-week buffer → **realistic on-site start anchors to 2026-08-24**. baseline_v2, daily_schedule_v2 and pep_v2 MUST use 2026-08-24 as the addition's earliest physical-work start; the `permit.tdec_septic` lead-time clock starts 2026-07-07, not earlier. *(round 2, q.tdec_application_status)*
- Existing heat pump and electrical disconnect in the way of new footprint — both relocated (scope L21).
- **Existing gas water heater is being REPLACED with tankless** — customer signed off on the $6,500 tankless option. Gas line + vent extension to new roof stays in (scope L22). See Trades — Plumbing tank set for sequencing. *(round 1, q.tankless_vs_existing_wh_contract)*
- Existing main electrical service: scope assumes adequate to support new 100A subpanel (scope L83). Per addition_rules amperage-check rule, `prep.amperage_check` 0.5d in pre-construction is REQUIRED to verify before contract signing.

## Trades — what we expect

- **Foundation** (rule: company:editor_rules monolithic default): single monolithic pour — 12"×12" footings + 4" slab + gravel + vapor + rebar in ONE form/prep task; ONE footing inspection covers both; cure = `kind: lead_time` 2 cal-d (scope L33-38, dev_rules 4B).
- **Framing** (146 labor hrs, breakdown): basement walls 2×4, floor system, exterior + interior walls 2×4, future elevator shaft framing.
- **Roof** (96 labor hrs): new gable 3/12 tying into existing 6/12. **CONFIRMED stick-frame** — 590 sqft / ~10 ft span, well under the 24-ft truss threshold. No `procurement.trusses` task emitted; framing lumber delivered just-in-time with framing crew. *(round 1, q.roof_framing)*
- **Concealed roof tie-in** (rule: job_type:addition_rules concealed-roof-tie-in): multi-valley tie-in into existing 6/12 (plans p4 multiple V markings) → CHANGE-ORDER RISK. Emit `roof.concealed_buffer` 3 cal-d SS lag 1 after `framing.roof`. Plans note "VERIFY EXISTING ROOF SLOPES AND SOFFIT DEPTH BEFORE CONSTRUCTION" (plans p4).
- **Windows**: PM defers to drawing schedule (authoritative). **2 stock vinyl windows: 1 transom (3'×1') + 1 DH (3'×3')** with ~14 cal-d supplier lead. Scope's "(4) new windows" line gets a ~$1,200 scope reduction. Install labor for relocated existing windows (plans show 3+ callouts) still applies — no procurement task for those. Per addition_rules, windows install FS-after `framing.roof` (NOT after dried-in milestone), in parallel with `roofing.underlayment`. *(round 1, q.windows_stock_custom_and_count)*
- **Exterior siding** (72 labor hrs combined): vinyl lap on second floor + **NEW BRICK on basement-level walls** per plans (confirmed authoritative). Requires masonry sub + `procurement.brick` (~2 wk lead). Current 72-hr allocation insufficient — paper-only CO already accepted, brick + lap planned as CONFIRMED scope. *(round 1, q.brick_or_vinyl_addition; round 2, q.brick_co_certainty)*
- **Masonry sub: Bristol Brick & Masonry** (TCR's usual brick veneer crew; 3-4 week advance notice typical — they confirm availability on notice). **Brick supplier: General Shale** distributed through **Builders FirstSource** — "brick to match existing" is a known SKU through that channel, stock-orderable on the ~2 wk lead. No `prep.masonry_sub_select` task needed. The 3-4 wk Bristol notice MUST go out as soon as the framing schedule locks. *(round 2, q.masonry_sub_status)*
- **Electrical** (78 labor hrs): 100A subpanel (1d/1 person per editor_rules subpanel productivity), full rough-in 1-1.5d/2 crew, full finish 2-3d. (1) dedicated 120V 30A circuit for future elevator. Existing hall switch relocation = small retrofit drywall patch (scope L78).
- **Plumbing** (40 labor hrs in breakdown — INSUFFICIENT vs rule floor): scope has master bath (2 lav + 1 toilet + custom shower with dual diverter), W/D relocation, AND extend vent stacks through roof. Per dev_rules 4H + editor_rules L138-142, plumbing rough-in MUST be ≥ 4 working days × 2 crew = 64 labor hrs (rule: company:editor_rules plumbing-rough Will's nominal). **Schedule will expand 40-hr allocation to 64-hr floor with a warning**.
- **Plumbing — tank set sequence** (rule 4H): **Tankless WH CONFIRMED in contracted scope** (customer signed off on $6,500 option). Tank-set sequence applies: emit `procurement.tank` ~10 cal-d standard lead (collapse to 1d order task) + `plumbing.tank_set` 0.5d that gates `plumbing.rough_in`. Tankless arrives, set first, then plumbing rough-in stubs into it. *(round 1, q.tankless_vs_existing_wh_contract)*
- **HVAC** (36 labor hrs): mini-split ductless ($2,500 budget per scope L97). Per editor_rules mini-split sequence: rough = 0.5d/1 person line-set, install = 1d/1 person. **HVAC type = mini-split** → MEP order is plumbing → electrical → mini-split (rule: company:dev_rules 4G + editor_rules HVAC sequencing).
- **Insulation** (44 labor hrs): R13 exterior walls, R30 attic/roof, R30 floor between basement and living space. Standard ~1-day install per editor_rules productivity. `equipment.insulation_material_arrival` lands same day as `inspect.rough_bundled` (rule: company:editor_rules material-tied-to-inspection).
- **Drywall** (159 labor hrs — LARGEST section): consolidate addition + retrofit primary bedroom + retrofit hall bath + basement storage into ONE `drywall.consolidated` block per editor_rules drywall-consolidation. 9-11 working days for typical addition; this is on the higher end given 4 zones.
- **Interior finish carpentry, painting & flooring** (162 labor hrs): LVT throughout addition + existing primary bedroom retrofit; trim 5-1/4" base + 2-1/4" casing; primer + 2 finish coats. Paint TWO PHASES MANDATORY (rule: company:dev_rules 4E). The "primary bedroom remodel" share covers the **EXISTING primary bedroom in the original house** (being repurposed since the new master suite is in the addition) — separate retrofit Component from the addition's new primary bedroom. *(round 1, q.retrofit_primary_bedroom_scope)*
- **Tile shower master bath** (88 labor hrs): custom 7'×4' shower with mosaic floor + wall tile + niche + bench + dual-valve diverter (scope L121-128). Per editor_rules tile productivity, this is `tile.shower_substrate` 1d → `tile.shower_install` 4-5d → `tile.grout_seal` 1d sequence.
- **"Existing Hall Bath Mod, Bedroom Remodel & Closeout"** (72 labor hrs, NEGATIVE -$1,714.20 material — credit/overlap). Three streams compressed: hall bath retrofit (window infill, acrylic shower swap, drywall patch, paint), existing primary bedroom retrofit, closeout. Per dev_rules section 12, the 72 hrs are REAL work to be decomposed; the negative material is overlap-credit.

## Sequencing — known patterns

- **Phase spine** (rule: company:editor_rules): pre_construction → site_prep → demo_and_protection → structural_and_shell → rough_trades → rough_inspections → insulation_and_drywall → interior_finishes → finish_trades → closeout.
- **Pre-construction free-floating tasks** require `pre_construction_offset_working_days` (rule: company:dev_rules 4S): permit walk-in (15), selections finalized (15), amperage check (15), equipment-confirmed checkpoints (10).
- **TDEC septic** (rule: job_type:tdec_septic_permit_offset, rank 200): `permit.tdec_septic` `kind: lead_time, lead_time_days: 42, pre_construction_offset_working_days: 30` — **CONFIRMED ACTIVE** (home is on septic, TCR handles permit). **Submission target 2026-07-07; realistic on-site start 2026-08-24** — use as anchor date, not a generic offset. *(round 1, q.septic_or_sewer; round 2, q.tdec_application_status)*
- **Heat pump relocation BEFORE demo** (rule: company:dev_rules 4K): `prep.heat_pump_relocate` 1d hvac in site_prep, 3+ working days before main demo.
- **Customer early items** (rule: company:dev_rules 4V + addition_rules customer-early-items): **CONFIRMED** — emit `early.acrylic_shower_swap` in a `customer_early_items` Component under site_prep phase, Day 1 before main demo (homeowner keeps a working shower throughout construction). The retrofit hall bath repaint / drywall patch / window infill still goes in a separate `hall_bath_mod` Component in interior_finishes — TWO buckets, same room. *(round 1, q.customer_early_items)*
- **Monolithic foundation** (rule: company:dev_rules 4B): single pour, single inspection, no secondary slab inspection (scope L33-39 supports — no CMU, no foundation walls).
- **Bundled rough inspection** (rule: company:dev_rules 4C): rough electrical + rough plumbing + mini-split rough + framing all inspected ONE day by ONE inspector. Add `buffer.post_rough_inspection` `lead_time_days: 2` (working) after.
- **Windows install IMMEDIATELY after roof framed** (rule: job_type:addition_rules windows-install): NOT after dried-in milestone.
- **MEPs gated on roofing.underlayment + windows.install** (rule: job_type:addition_rules MEP-gating): NOT on dried-in milestone.
- **Paint two phases mandatory** (rule: company:dev_rules 4E): `paint.phase_1` 1d (primer walls+ceilings AM, ceiling finish PM same day) → gates flooring/electrical-finish/tile-substrate. `paint.phase_2` 1d → gates substantial completion, predecessors include EVERY finish trade.
- **Interior 2-trades-max** with HVAC-after-electrical stagger (rule: company:dev_rules 4N + editor_rules crew concurrency): default stagger `hvac.minisplit_install` `FS after electrical.finish`.
- **Substantial completion = paint.phase_2 end** (rule: company:dev_rules 4F): NO other predecessors on `milestone.substantial_completion`.
- **LVL retrofit chain — NEW FLOOR BEARS ON LVL** (rule: job_type:addition_rules LVL-temporary-shoring): scope L45-47 has 3-ply 14" LVL spanning ~15'-6". Sub-chain: `demo.expose_bearing_wall` → `structural.temp_shoring` → `structural.install_lvl` (FS after `procurement.lvl`) → `structural.remove_temp_shoring`. **NOT independent** — `framing.floor_system` MUST FS-after `structural.install_lvl` because the new floor system above bears on the LVL. Standard 3-ply, ~7-14 cal-d lead. *(round 1, q.lvl_load_bearing)*

## Procurement — order/wait/arrived chains (per dev_rules 4R)

- `procurement.windows` — **14 cal-d, stock vinyl, 2 units** (1 transom + 1 DH). Collapse to short order chain. *(round 1, q.windows_stock_custom_and_count)*
- `procurement.lvl` — **7-14 cal-d standard 3-ply** (no custom / pressure-treated). *(round 1, q.lvl_load_bearing)*
- `procurement.electrical_panel` (100A subpanel) — 7-14 cal-d per editor_rules table; collapse to 1-day order task if ≤7d.
- `procurement.tank` (tankless WH) — **~10 cal-d standard**, tankless CONFIRMED in scope. Collapse to 1-day order task. *(round 1, q.tankless_vs_existing_wh_contract)*
- `procurement.hvac_equipment` (mini-split unit) — 7-14 cal-d.
- `procurement.brick` (brick to match existing, basement-level walls) — **~14 cal-d (2 wk lead) via General Shale @ Builders FirstSource**. CO is paperwork only — not a gating decision. Pair with `exterior.brick_veneer` install task (Bristol Brick & Masonry crew, 3-4 wk advance notice required). *(round 1, q.brick_or_vinyl_addition; round 2, q.masonry_sub_status, q.brick_co_certainty)*
- `procurement.lvt` — 7 cal-d (stock), collapse to 1d order task.
- `procurement.tile_master_bath` — 7-21 cal-d depending on stock vs custom; PM confirms.
- `procurement.exterior_door` — 21-28 cal-d if custom; PM confirms.
- `procurement.vanity` — 7 cal-d stock (scope L190 $1,000 allowance suggests stock).

## Risk / change-order watch

- **Concealed roof tie-in into existing 6/12 with multi-valley intersection** (plans p4) — change-order risk; 3-day buffer modeled.
- **Plumbing rough-in 40hr allocation vs 64hr rule floor** — schedule expands to floor with warning.
- **Brick + masonry sub** — CONFIRMED, no contingency. Bristol Brick & Masonry (TCR's usual) + General Shale via Builders FirstSource. CO is paperwork-only billing reconciliation, not a "will customer accept" risk. No vinyl-only fallback variant in baseline_v2 or risks_v2. *(round 1, q.brick_or_vinyl_addition; round 2, q.masonry_sub_status, q.brick_co_certainty)*
- **TDEC septic submission timing** — application targets 2026-07-07; realistic start 2026-08-24. If submission slips past 2026-07-07, the entire on-site schedule slides by the same number of working days. Track submission as a pre-construction milestone. *(round 1, q.septic_or_sewer; round 2, q.tdec_application_status)*
- **Negative "Existing Hall Bath Mod, Bedroom Remodel & Closeout" section total** (-$1,714.20) — overlap credit, 72 labor hrs still real; decomposition driven by confirmed buckets (early.acrylic_shower_swap on Day 1 + hall_bath_mod retrofit Component + existing primary bedroom retrofit Component + closeout).
- **Septic relocation / grinder pump / service upgrade** all explicit CHANGE-ORDER exclusions per scope.

### Resolved in round 1

- ~~Roof framing trusses vs stick~~ → stick-frame confirmed.
- ~~Septic vs city sewer~~ → septic confirmed; TDEC in scope.
- ~~Tankless WH variant uncertainty~~ → tankless confirmed in scope.
- ~~LVL load-bearing dependency on new framing~~ → new floor bears on LVL; `framing.floor_system` gates on `structural.install_lvl`.
- ~~Window count + stock/custom~~ → 2 stock vinyl per drawing schedule, ~14d lead.
- ~~Existing primary bedroom remodel ambiguity~~ → existing original-house bedroom, separate retrofit Component.
- ~~Customer early items~~ → hall bath acrylic shower swap Day-1, off critical path.

### Resolved in round 2

- ~~TDEC application status~~ → not yet submitted; target 2026-07-07; realistic on-site start 2026-08-24.
- ~~Masonry sub status~~ → Bristol Brick & Masonry confirmed; General Shale via Builders FirstSource; 3-4 wk advance notice.
- ~~Brick CO certainty~~ → confirmed (drawings ARE the signed design package); paperwork-only reconciliation; no vinyl-only fallback.

## Manifest / generation hints

- Job type addition rules (rank 200) win over company defaults (rank 100) for window install gating, MEP gating, TDEC offset.
- No project-level or job-level rule overrides exist.
- Interview round 1 completed 2026-06-30 — 8/8 questions answered cleanly, 3 follow-ups opened.
- Interview round 2 completed 2026-06-30 — 3/3 follow-ups answered cleanly, no new questions opened. **Status: `complete`** — task_graph_v2 and downstream generations can proceed.
