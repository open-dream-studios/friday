---
generation_kind: intel_gather_v1
artifact: rules_index
last_verified_at: 2026-06-30T04:30:00Z
---

## Company rules

- **_company/rules/dev_rules.md §4A (permits = 1-day work task)** — scope L11 says "Contractor to obtain required permits"; emit `general.permitting` as 1d work + `pre_construction_offset_working_days: 15`, NOT a 14-day lead_time.
- **dev_rules.md §4B (monolithic foundation default)** — scope L40-45 explicitly says perimeter footings + 4" slab + NO CMU / NO foundation wall system. Use single monolithic pour task.
- **dev_rules.md §4C (rough inspections bundled)** — all four roughs (electrical, plumbing, mini-split, framing) must co-schedule on ONE day.
- **dev_rules.md §4D (2-4 day punch-list buffer post-rough)** — standard buffer required after `inspect.rough_bundled`.
- **dev_rules.md §4E + §4F (paint always 2 phases; phase 2 = last work, gates substantial completion)** — scope L111 specifies prime + 2 coats finish; emit `paint.phase_1` + `paint.phase_2` w/ phase 2 gated on EVERY finish trade.
- **dev_rules.md §4G (HVAC type drives MEP order)** — scope L99 specifies "ductless mini-split system" → MEP rough order = plumbing → electrical → mini-split.
- **dev_rules.md §4H (tank set FIRST when WH in scope)** — scope L37 says "Extend existing gas water heater vent through new roof" (existing WH STAYS); per rule's scope condition, DO NOT emit `procurement.tank` or `plumbing.tank_set`. **EXCEPTION:** if the optional tankless package (scope L183-185) is taken, the rule re-applies and the 3-task tank chain becomes mandatory.
- **dev_rules.md §4I (MEPs gate on underlayment + windows for additions)** — emit all rough MEPs `FS after roofing.underlayment` AND `FS after windows.install`, NOT after a dried-in milestone.
- **dev_rules.md §4J (windows install immediately after roof framed)** — emit `windows.install` `FS after framing.roof` + `checkpoint.windows_arrived`, parallel with underlayment.
- **dev_rules.md §4K (heat pump relocation BEFORE demo)** — scope L36 explicitly says "Relocate existing heat pump and electrical disconnect". Emit `prep.heat_pump_relocate` + `prep.electrical_disconnect_relocate` in `site_prep / prep_work_before_demo`, ≥3 working days before demo.
- **dev_rules.md §4L (interior finish dependencies)** — strict chain: flooring after paint.phase_1 + shower pan; trim after flooring; cabinets after flooring + paint.phase_1; electrical finish after paint.phase_1; plumbing finish after cabinets + flooring + tile.
- **dev_rules.md §4M (final inspections bundled)** — ONE inspector, ONE day for all finals + final building.
- **dev_rules.md §4N (2-trades-max interior + HVAC stagger)** — finish cluster (electrical + plumbing + mini-split install) will trip 3-trade overlap; default stagger = mini-split AFTER electrical finish.
- **dev_rules.md §4O (equipment day-before-phase + 2-week-out checkpoint)** — dumpster, demo equipment, scaffolding all need same-day-before tasks + checkpoint 2 weeks prior.
- **dev_rules.md §4P (selections-finalized checkpoint)** — mandatory `checkpoint.selections_finalized` w/ `pre_construction_offset_working_days: 15`. Gates tile/paint/LVT/vanity procurement.
- **dev_rules.md §4Q (trusses procurement CONDITIONAL)** — scope L57 says "truss OR rafter framed — determined during design phase"; addition footprint is 590 sqft (under 800), roof span is ~10' (under 24'). Per rule + stick_frame_default belief, DO NOT emit `procurement.trusses`. Stick-frame default applies.
- **dev_rules.md §4R (procurement 3-task pattern)** — windows, exterior door, LVL beam, electrical panel, mini-split unit, custom tile, vanity all need order / wait / checkpoint chains.
- **dev_rules.md §4S (pre_construction_offset_working_days on free-floating PC tasks)** — permits, selections checkpoint, equipment checkpoints, amperage check all need the offset field.
- **dev_rules.md §4T (lead_up_working_days on prep-heavy tasks)** — apply default table to permits (2), selections (5), order tasks (0-2), equipment checkpoints (2), phase-start bars (2), inspections (1).
- **dev_rules.md §4U (no-op checkpoints forbidden)** — every `checkpoint.*` must have a downstream consumer.
- **dev_rules.md §4V (customer early items SEPARATE from retrofit)** — hall bath has BOTH a customer-requested early item (acrylic shower swap, scope L145-147) AND retrofit work (window infill + drywall + repaint, scope L141-149). Emit TWO components: (1) `customer_early_items / early.acrylic_shower_swap` in `site_prep` Day 1; (2) `hall_bath_mod / retrofit.*` parallel with main scope. STAGE B MUST CONFIRM the acrylic swap is in fact "before main demo" per customer ask — the scope text doesn't explicitly say so.
- **dev_rules.md §6 (duration heuristic — mini-split overrides + plumbing floor)** — mini-split rough 0.5d/1p, install 1d/1p; subpanel 1d/1p; insulation install 1d; shingles 1d (small addition); plumbing rough 4d × 2 floor (master bath + W/D).
- **dev_rules.md §9 (retrofit detection — 3 signals)** — Bedroom 2/Bedroom 3, hall bath, primary bedroom remodel (~12'5" x 16') sit OUTSIDE the addition objective (which names ONLY primary bedroom/master bath/walk-in closet). All trip Signal A. Hall bath also trips Signal B ("existing"). Treat as separate components per dev_rules §9 step 3.
- **dev_rules.md warnings §11** — apply mandatory warning checks 1-31 to the eventual TaskGraph.

- **_company/rules/_examples/plumbing_rough_min_duration.md** — APPLIES: scope includes master bath (2 lav + 1 toilet + 1 custom shower) AND W/D relocation AND extended vent stacks. Plumbing rough-in MUST be ≥4 working days × 2 crew. CSV's 40 labor hours (5 days × 1 person or 2.5 days × 2 crew) is UNDER this floor and must be overridden upward.

- **_company/rules/editor_rules.md (full playbook)** — applies as default productivity / lead times / phase spine / interior 2-trade cap / procurement pattern / WH tank-set rule / drywall consolidation. Specific call-outs:
  - **Drywall consolidation (multi-zone)** — 4 zones to consolidate into ONE hang/finish block: new addition + bedroom remodel + basement storage + hall bath patch. Editor rules say 9-11d × 3 crew; CSV's 159 hrs aligns at ~7d × 3 crew — Stage B should reconcile.
  - **Material on site 1 week before install** — applies to LVT, vanity, fixtures, mini-split unit, paint, tile.
  - **Mechanical equipment ordered at dried-in** — mini-split unit + (optional) tankless WH.
  - **Customer early items two-bucket pattern** — see §4V above; editor rules give the worked example.
  - **Plumbing rough-in 4d × 2 floor for master bath + W/D + vent extensions** — same as the company rule above.
  - **Same-crew exterior pattern** — siding + trim + fascia + gutters as one contiguous block.
  - **Insulation material on site day of MEP inspection** — emit `equipment.insulation_material_arrival` same day as `inspect.rough_bundled`.

- **_company/rules/pep_rules.md** — applies for downstream PEP generation (Stage B / later); per-day checklist, lead-up day blocks, delivery callouts, trade-stack callouts, tomorrow previews all required.

## Company beliefs

- **_company/beliefs/_examples/stick_frame_default_for_small_additions.md** — APPLIES (confidence 0.92): addition footprint 590 sqft (under 800), roof span ~10' (under 24'). Use stick-frame default, no `procurement.trusses` task. Lumber arrives JIT w/ framing crew. Reinforces dev_rules §4Q.

## Job-type rules

- No `job_types/addition/rules/` directory present in context. Job-type layer is empty; relying entirely on company rules + beliefs.

## Rules deliberately NOT applied (and why)

- **Tank-set sequence (editor_rules + dev_rules §4H)** — scope keeps existing gas WH and only extends vent; plumbing rough-in proceeds without tank predecessor. ONLY re-applies if optional tankless package (scope L183-185) is taken.
- **Stem-wall / multi-pour foundation split (dev_rules §4B)** — scope explicitly excludes CMU + foundation walls (scope L45); monolithic default holds.
- **Trusses procurement (dev_rules §4Q)** — small addition + short span + ambiguous "truss OR rafter" scope text; stick-frame default per belief.
- **Ducted HVAC sequencing (dev_rules §4G)** — scope L99 explicitly says mini-split; ducted MEP order does NOT apply.
- **Septic / grinder pump tasks** — scope L25-29 explicitly excludes via change-order placeholders; do not emit unless PM confirms inclusion at interview.
