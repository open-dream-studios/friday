---
generation_kind: intelligence_interview_v2
stage: synthesis
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWFCFSFZDJ01ZGRTNF78GYHC/jobs/308-evergreen-street-addition_JOB-01KWFCGKXVEGGGJZV1JB762C1C/manifest.json
  - _projects/308-evergreen-street_APPPROJ-01KWFCFSFZDJ01ZGRTNF78GYHC/jobs/308-evergreen-street-addition_JOB-01KWFCGKXVEGGGJZV1JB762C1C/intelligence/extracted/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KWFCFSFZDJ01ZGRTNF78GYHC/jobs/308-evergreen-street-addition_JOB-01KWFCGKXVEGGGJZV1JB762C1C/intelligence/extracted/breakdown.md
  - _projects/308-evergreen-street_APPPROJ-01KWFCFSFZDJ01ZGRTNF78GYHC/jobs/308-evergreen-street-addition_JOB-01KWFCGKXVEGGGJZV1JB762C1C/intelligence/extracted/plans.md
  - _projects/308-evergreen-street_APPPROJ-01KWFCFSFZDJ01ZGRTNF78GYHC/jobs/308-evergreen-street-addition_JOB-01KWFCGKXVEGGGJZV1JB762C1C/intelligence/applicable_rules.json
  - _projects/308-evergreen-street_APPPROJ-01KWFCFSFZDJ01ZGRTNF78GYHC/jobs/308-evergreen-street-addition_JOB-01KWFCGKXVEGGGJZV1JB762C1C/interview/round-1.md
---

# Facts — 308 Evergreen Street Addition

## Customer & Job

- Customer / site: 308 Evergreen Street; job type is `addition` (manifest.json `customer`, `job_type`).
- Job label: "308 Evergreen Street — addition" (manifest.json `summary`).
- Objective: construct a two-story addition ~30' × 10' with basement-level storage and second-floor expansion of primary bedroom, master bath, and walk-in closet (extracted/scope.md "Customer & Job").
- Design set: Simons Addition, prepared by Rebecca Lineberry NCIDQ / Greyscale Design LLC, dated 2026-01-22, 5 sheets (extracted/plans.md header).
- Contract Total Investment quoted at $173,850 (extracted/scope.md L179).
- CSV grand total: $100,778.92 (labor $45,167.59 + material $52,171.33 + equip $3,440) with 1,287 labor hours across 16 sections (extracted/breakdown.md "Source file / Project totals").
- **Scope-total vs CSV-total gap = $73,071 (~42%) is RECONCILED**: PM confirmed scope figure includes markup, overhead, contingency, and sub margins not in CSV; CSV is direct cost only (round 1, q.scope_vs_csv_total_reconciliation).
- Deposit / billing: $20,000 signed-agreement deposit; weekly invoicing thereafter (extracted/scope.md L198–L203).
- Rates: $70/hr general; +$15 teamlead / +$30 electrical & HVAC / +$40 plumbing; materials cost +15%; subs cost +30%; debris $450/removal; backhoe $1,100/wk (extracted/scope.md L188–L197).
- **Both optional packages OUT**: Closet & cabinet system ($7,000) customer handling separately; tankless water heater ($6,500) OUT, existing tank WH stays (round 1, q.closet_cabinet_system_option + q.tankless_water_heater_option).

## Scope

- Footprint per plans: 295 sqft 1st-floor addition + 295 sqft basement = **590 sqft new construction**; CSV "Overall Footprint SF" of 789 includes ~200 sqft existing bedroom being remodeled (extracted/plans.md "Structural decisions").
- Wall heights 8'-0" both levels with a 1'-0" floor-system band; roof 3/12 tying into existing 6/12 (extracted/plans.md "Structural decisions").
- LVL beam: 3-ply 14" spanning ~15'-6" to open existing load-bearing wall with temporary shoring (extracted/scope.md "Framing"; extracted/plans.md "Structural decisions").
- Elevator shaft: framed only, 4' × 4', carries through both levels; 30A rough-in electrical from subpanel; elevator itself not included (extracted/scope.md L154–L155; extracted/plans.md "Structural decisions").
- Master bath: custom tile shower ~7' × 4' with niche + bench, dual-valve diverter, 72" double vanity, 2 faucets/mirrors/lights, commode, exhaust fan/light (extracted/scope.md "Master Bathroom").
- Primary bedroom remodel ~12'5" × 16' (drywall / prime+paint / LVT / full trim) — retrofit (extracted/scope.md L130–L135).
- Basement storage finish: framed & drywalled walls, Level 3 finish + paint, 1 light; concrete floor unfinished (extracted/scope.md L136–L140).
- **Existing hall bath modification SPLIT into two buckets per rule 4V**: (1) acrylic shower swap ($1,000 allowance) is a customer-requested EARLY item — site_prep/customer_early_items/early.acrylic_shower_swap Day 1 before main demo so family has working shower; (2) window infill (framing + insulation + drywall + patch/repaint) + PVC trim lives separately in hall_bath_mod retrofit component (round 1, q.hall_bath_acrylic_shower_early_item; extracted/scope.md L141–L149).
- **Windows: 2 new + 2 relocated** — plans are authoritative: 1 transom 3'×1' + 1 D.H. 3'×3' new; 2 existing windows relocated (round 1, q.window_count_discrepancy; extracted/plans.md "Structural decisions"). Scope's "(4) windows including (3) 36"×60" and (1) transom" was inaccurate.
- Doors (plans schedule): 5 total — 2×32", 1×30", 1×28", 1×36" exterior metal (extracted/plans.md "Structural decisions").
- Electrical: new 100A subpanel, full rough + trim, ~12 recessed lights, 2 vanity lights, 1 bath vent-fan/light, hallway switch relocation with drywall patch, dimmers at bed/bath, GFCI/AFCI per code, dedicated 120V/30A elevator circuit (extracted/scope.md "Electrical").
- Plumbing: full rough (supply/waste/vent), quarter-turn stops, master-bath fixtures, W/D relocation with roof venting, vent stacks extended through roof (extracted/scope.md "Plumbing").
- **NO tankless water heater** — existing tank WH stays; extend existing gas water-heater vent through new roof only (round 1, q.tankless_water_heater_option; extracted/scope.md "HVAC"; L36–L37). NO `procurement.tank` / `plumbing.tank_set` tasks.
- HVAC: one ductless mini-split ($2,500 budget), relocate existing heat pump + electrical disconnect (extracted/scope.md "HVAC"; L36–L37).
- Insulation: R13 exterior walls, R30 attic/roof, R30 floor between basement and living space, all penetrations air-sealed (extracted/scope.md "Insulation & Air Sealing").
- Interior finishes: Level 3 drywall, primer + 2 finish coats paint, LVT ($3/sqft budget), 5-1/4" baseboard, 2-1/4" casing (extracted/scope.md "Interior Finishes – General").
- Interior doors: 4 total — 1 pre-hung + 2 pocket-door systems; final locations TBD in design (extracted/scope.md L118–L120).
- **NO closet & cabinet system** — customer handling separately (round 1, q.closet_cabinet_system_option). NO `cabinets.install` or procurement chain.
- Cleanup / closeout: debris + material removal, final clean, coordinate inspections (extracted/scope.md L156–L159).

## Site

- Site access assumed standard for equipment, staging, and construction operations (extracted/scope.md L22).
- Soil assumed standard; rock excavation / unsuitable soils excluded (extracted/scope.md L16–L18).
- Existing conditions to verify before construction: dimensions/elevations/tie-in points (scope); plumbing/venting/septic/HVAC locations (plans p.4 note); roof slopes and soffit depth (plans p.5 note) (extracted/plans.md "General plan notes").
- Existing chimney shown on roof plan — new roof envelope integrates around it (extracted/plans.md "Retrofit indicators").
- Site prep demo: saw-cut concrete walkway, remove railroad ties + site obstructions, multiple dump runs (extracted/scope.md L33–L38).
- Heat pump + electrical disconnect relocation happens as a site-prep item BEFORE demo per company rule 4K (extracted/scope.md L36; extracted/breakdown.md "Silent omissions" #8–#9).
- **Acrylic shower swap (hall bath) is a customer-requested EARLY item** — lives in site_prep/customer_early_items, Day 1 before main demo (round 1, q.hall_bath_acrylic_shower_early_item).
- Existing bedroom wall (load-bearing) is demoed / opened via LVL at the tie-in; two existing windows and one existing door relocated (extracted/plans.md "Retrofit indicators").
- Covered deck and front porch abut the addition footprint; flashing/tie-in at those junctions not called out (extracted/plans.md "Things plans show scope doesn't mention").
- **Septic direction: new septic tank + leach field likely (change order pending)**. TDEC septic permit with pre_construction_offset_working_days=30 required per job_types/addition/rules/tdec_septic_permit_offset.md. Plumbing tie-in for new septic tank + leach field should be stubbed as a placeholder; full relocation scope addressed via change order (round 1, q.septic_grinder_direction; extracted/scope.md L25–L28; extracted/plans.md discrepancy #7).

## Trades

- Sixteen CSV sections roughly one-per-trade; 1,287 total labor hours; largest sections by hours: Interior Finish Carpentry/Paint/Flooring (162), Drywall (159), Framing (146), Roof (96), Master Bath (88); smallest: HVAC (36) and Plumbing (40) (extracted/breakdown.md "Trade totals").
- Row 21 HVAC section title says "Mini Split, Tankless WH & Relocations" but tankless is OUT per PM (round 1, q.tankless_water_heater_option) — section covers mini-split + relocations only.
- Row 16 (Hall Bath Mod + Bedroom Remodel + Closeout) has **negative material −$4,199 → section total −$1,714** with 72 labor hrs; treated as a credit / template artifact bundling three retrofit blocks. Hall bath acrylic shower swap now lives separately in site_prep/customer_early_items per PM (round 1, q.hall_bath_acrylic_shower_early_item). Remaining row 16 scope: hall bath window infill + drywall patch + repaint (hall_bath_mod retrofit) + primary bedroom remodel + closeout (extracted/breakdown.md "Notes" — Row 16).
- Plumbing 40 labor hrs is thin for master bath + W/D relocation + vent-stack extension; company `plumbing_rough_min_duration` rule pins rough at ≥4d × 2 crew regardless of CSV hours (editor_rules "Plumbing rough-in duration"; extracted/breakdown.md row 10).
- Mini-split job → MEP rough order is plumbing → electrical → mini-split rough (line set only, 0.5d × 1); mini-split install 1d × 1 (editor_rules "HVAC sequencing"; dev_rules 4G, 4J).
- Amperage check task required in pre-construction — adding subpanel + mini-split + 30A elevator circuit clearly triggers `_company/rules/service_amperage_check.md` (extracted/breakdown.md "Silent omissions" #10).
- Roof + siding default to same 2–3 person crew per `_company/beliefs/roof_and_siding_same_crew.md` — schedule serializes wall-clock unless PM sets two_crew=true.

## Sequencing

- 3-week-out pre-construction anchors: `general.permitting` (offset 15), `checkpoint.selections_finalized` (offset 15), `prep.amperage_check` (offset 10), **`permit.tdec_septic` (offset 30)** per dev_rules 4A / 4P / 4S, company rules, and job_types/addition/rules/tdec_septic_permit_offset.md (round 1, q.septic_grinder_direction).
- Foundation is monolithic by default (footings + slab same day, one footing inspection, 2 calendar-day cure) per dev_rules 4B; scope L40–L44 is consistent (12"×12" perimeter footing + 4" slab, no CMU / stem walls).
- Windows install `FS after framing.roof` in parallel with `roofing.underlayment` — NOT after `milestone.dried_in` per dev_rules 4J / editor_rules.
- Rough MEPs (electrical, plumbing, mini-split line set) `FS after roofing.underlayment AND windows.install` — NOT after `milestone.dried_in` per dev_rules 4I.
- Bundled rough inspection covers rough electrical + rough plumbing + rough HVAC + framing on one day, one inspector; followed by 2-day punch-list buffer before insulation air-seal per dev_rules 4C / 4D.
- Paint two-phase mandatory: `paint.phase_1` after `drywall.consolidated`; `paint.phase_2` after all finish trades (trim, flooring, tile grout, plumbing finish, electrical finish, mini-split install) — gates `milestone.substantial_completion` per dev_rules 4E / 4F.
- 2-trades-max interior cap; default 3-trade stagger serializes HVAC install AFTER electrical.finish per dev_rules 4N.
- Drywall consolidated (9–11d) for addition + primary bedroom retrofit + basement storage + hall bath patch — single hang/tape/sand cycle per editor_rules "Drywall consolidation"; treated as soft_start slidable per `drywall_soft_schedule` belief.
- Retrofit tie-in discovery: framing.tie_in_discovery must SS with tie-in framing per `job_types/addition/rules/retrofit_tie_in_discovery.md` (roof tie-in + existing bedroom wall opening + LVL are the risk zones per extracted/plans.md discrepancy #4).
- **Siding: vinyl lap** (round 1, q.siding_material). Siding may start once underlayment + windows are on per `siding_starts_at_underlayment` — but wall-clock serializes with roofing due to same-crew belief.
- **Acrylic shower swap early item** — lives in site_prep/customer_early_items per rule 4V; Day 1 before main demo (round 1, q.hall_bath_acrylic_shower_early_item).

## Procurement

- Long-lead / procurement items to model via 3-task pattern (order / wait / arrived) per dev_rules 4R:
  - **Trusses (28–42 cal-d)** — PM confirmed trusses, overriding stick_frame_default_for_small_additions belief (round 1, q.roof_framing_truss_or_stick). Must order early; critical path item.
  - **Windows (stock 14–21 cal-d)** — 2 new (1 transom 3'×1' + 1 D.H. 3'×3') per PM (round 1, q.window_count_discrepancy). 2 existing windows relocated (no procurement, labor only).
  - Exterior door (custom 21–28 cal-d) — 36" × 1-3/4" metal per plans schedule D.
  - LVL beam (standard 7–14 cal-d) — 3-ply 14" × 15'-6".
  - Electrical panel / 100A subpanel (7–14 cal-d).
  - Mini-split unit (7–14 cal-d) — $2,500 allowance.
  - Custom tile (14–21 cal-d) — master bath walls + mosaic floor.
  - **NO tankless WH procurement** — existing tank WH stays (round 1, q.tankless_water_heater_option).
  - **NO closet & cabinet system procurement** — customer handling separately (round 1, q.closet_cabinet_system_option).
- **TDEC septic permit** must be modeled as `permit.tdec_septic` with `pre_construction_offset_working_days: 30` per `job_types/addition/rules/tdec_septic_permit_offset.md` (round 1, q.septic_grinder_direction; extracted/scope.md L25–L28; extracted/plans.md discrepancy #7).
- Selections lock (`checkpoint.selections_finalized`) at PC offset 15 gates finish-material procurement (LVT, paint, fixtures, vanity, tile) per dev_rules 4P.
- Materials on site 1 week before install; mechanical equipment (mini-split) ordered near dried-in per editor_rules "Material ordering".
- ≤7-day items (paint, stock LVT, stock fixtures) may collapse to single-day `order.<item>` 1 week before install per dev_rules 4R exception.
- **Acrylic shower swap early item** — $1,000 allowance; procurement for acrylic shower pan + walls happens at project start, install Day 1 in site_prep/customer_early_items (round 1, q.hall_bath_acrylic_shower_early_item; dev_rules 4V).