---
generation_kind: intelligence_interview_v2
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWBXP28R0M3VYB6NXFZMY9V0/jobs/308-evergreen-street-addition_JOB-01KWBXQF226SWCB8W7F05C39G9/interview/round-1.md
  - _projects/308-evergreen-street_APPPROJ-01KWBXP28R0M3VYB6NXFZMY9V0/jobs/308-evergreen-street-addition_JOB-01KWBXQF226SWCB8W7F05C39G9/interview/round-2.md
---

# Confirmed — PM-confirmed facts with round provenance

## Round 1 — 2026-06-30

- New gable roof is **stick-framed**. 590 sqft addition / ~10 ft gable span is well under the 24-ft truss threshold per addition_rules. No `procurement.trusses` task is emitted; framing lumber delivered just-in-time with the framing crew. *(round 1, q.roof_framing: Stick-framed)*

- **Hall bath acrylic shower swap IS a customer-requested early item** — the homeowner wants a working shower throughout construction. Emit `early.acrylic_shower_swap` in a `customer_early_items` Component under `site_prep`, scheduled Day 1, off the critical path. The retrofit hall bath repaint / drywall patch / window infill still lives in a separate `hall_bath_mod` Component in `interior_finishes` — two buckets, same room, as dev_rules 4V prescribes. *(round 1, q.customer_early_items: Yes — hall bath acrylic shower swap before main demo)*

- Scope L131 "Primary Bedroom Remodel ~12'5"×16'" refers to the **EXISTING primary bedroom in the original house**, being repurposed now that the new master suite lives in the addition. Two distinct bedroom buckets must be planned: (a) the addition's new primary bedroom (new construction inside addition phase), and (b) the existing primary bedroom retrofit Component (framing mods, drywall, LVT, trim, paint) running parallel under interior_finishes. *(round 1, q.retrofit_primary_bedroom_scope: Existing original-house primary bedroom retrofit)*

- **308 Evergreen is on SEPTIC** and TCR handles the TDEC septic permit because adding a bedroom + master bath triggers a soil/field review. Plan a 6-week pre-construction window for TDEC; this **anchors the realistic on-site start date**. Emit `permit.tdec_septic` `kind: lead_time, lead_time_days: 42, pre_construction_offset_working_days: 30` (rule: job_type:tdec_septic_permit_offset, rank 200). Septic relocation/leach field/grinder install remain explicit change-order exclusions. *(round 1, q.septic_or_sewer: Septic — TCR handles TDEC)*

- **Tankless WH IS in the contracted scope** (customer signed off on the $6,500 option). Emit `procurement.tank` ~10 cal-d standard lead (collapse to 1d order task) + `plumbing.tank_set` 0.5d that gates `plumbing.rough_in` per dev_rules 4H. Gas line + vent extension to the new roof stays in. *(round 1, q.tankless_vs_existing_wh_contract: Tankless in scope, ~10d lead)*

- **The new addition's floor system DOES bear load on the LVL beam location.** `framing.floor_system` MUST FS-after `structural.install_lvl` — the LVL retrofit sub-chain is NOT independent for this job. Standard 3-ply 14" LVL, ~7-14 cal-d lead (no custom / pressure-treated). *(round 1, q.lvl_load_bearing: Yes — new floor bears on LVL)*

- **Window procurement count = 2 stock vinyl windows** per the drawing schedule, which the PM has marked authoritative over scope text: 1 transom (3'×1') + 1 DH (3'×3'). ~14 cal-d supplier lead, collapse to short `procurement.windows` chain. Scope's "(4) new windows" line gets a ~$1,200 scope reduction. Install labor for relocated existing windows (plans show 3+ callouts) still applies but carries no procurement task. *(round 1, q.windows_stock_custom_and_count: 2 stock vinyl per drawing schedule)*

- **Addition exterior is NEW BRICK on basement-level walls + vinyl lap siding on second floor** (drawings authoritative; scope's vinyl-only line is stale). Requires a masonry sub + `procurement.brick` (~2 wk lead). Revise the siding line to vinyl lap (not fiber cement). Flagged as a **LIKELY materials change-order** — see round 2 follow-ups on sub availability + CO certainty. *(round 1, q.brick_or_vinyl_addition: Brick lower + vinyl lap upper)*

## Round 2 — 2026-06-30

- **TDEC septic application NOT YET SUBMITTED. Target submission date: 2026-07-07.** PM is collecting field/soil data this week. With TDEC's 6-week typical turnaround plus a 1-week buffer, the realistic on-site start anchors to **2026-08-24**. The `permit.tdec_septic` lead-time countdown starts 2026-07-07, not earlier — baseline_v2 and daily_schedule_v2 must use this date as the anchor; pep_v2 phases its lead-up bullets against it. *(round 2, q.tdec_application_status: Not yet submitted; target 2026-07-07; realistic start 2026-08-24)*

- **Masonry sub is Bristol Brick & Masonry** (TCR's usual for brick veneer; 3-4 week advance notice typical — they confirm availability on notice). **Brick supplier: General Shale, distributed through Builders FirstSource** — "brick to match existing" is a known SKU through that channel and should be stock-orderable. Brick chain is concrete and de-risked: `procurement.brick` ~2 wk lead + `exterior.brick_veneer` install with Bristol crew; **no `prep.masonry_sub_select` task needed**. Advance notice to Bristol must go out ≥ 3-4 weeks before the brick install date (after the framing schedule is locked). *(round 2, q.masonry_sub_status: Bristol Brick & Masonry; General Shale via Builders FirstSource)*

- **Brick + lap exterior is CONFIRMED, not a contingency.** The drawings are the design package the homeowner signed off on, so brick is part of the visually-agreed scope — the missing cost line is a paper-only CO to reconcile dollars, not a "will the customer accept" decision. Plan as confirmed brick lower + vinyl lap upper. **No vinyl-only fallback variant** needs to be carried in risks_v2 or baseline_v2. The CO appears as a routine billing reconciliation, not a schedule risk. *(round 2, q.brick_co_certainty: Sure thing — brick part of signed design package; CO is paperwork only)*
