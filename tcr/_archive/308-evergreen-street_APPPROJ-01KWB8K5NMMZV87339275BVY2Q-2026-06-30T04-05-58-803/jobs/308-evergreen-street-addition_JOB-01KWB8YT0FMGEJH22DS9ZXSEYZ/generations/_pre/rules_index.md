---
generation_kind: intel_gather_v1
artifact: rules_index
last_verified_at: 2026-06-30T03:26:48Z
---

## Company rules

- **_company/rules/dev_rules.md § 4A (Permits = 1d work task)** — this job has a permit; must NOT be modeled as a 14-day calendar `lead_time`. Emit `general.permitting` as 1d work, offset 15.
- **_company/rules/dev_rules.md § 4B (Monolithic foundation default)** — scope explicitly excludes CMU / foundation walls and calls for 12"×12" footings + 4" slab. Monolithic pour pattern applies. ONE pour task, ONE footing inspection.
- **_company/rules/dev_rules.md § 4C (Rough inspections bundled)** — addition has rough electrical + plumbing + mini-split + framing. All four roll into ONE `inspect.rough_bundled` task.
- **_company/rules/dev_rules.md § 4D (2-4d punch-list buffer after rough inspections)** — apply default 2d buffer between `inspect.rough_bundled` and `insulation.air_seal`.
- **_company/rules/dev_rules.md § 4E (Paint is always two phases)** — full-finish addition; emit `paint.phase_1` AND `paint.phase_2`. Phase 1 = primer + ceiling finish AM/PM same day.
- **_company/rules/dev_rules.md § 4F (Paint phase 2 gates substantial completion)** — predecessors must include trim, flooring, vanity, tile grout, plumbing finish, electrical finish, mini-split install.
- **_company/rules/dev_rules.md § 4G (HVAC type drives MEP order)** — scope explicitly says "mini-split" → MEP order plumbing → electrical → mini-split. Mini-split rough = 0.5d / 1 person.
- **_company/rules/dev_rules.md § 4H (Tank set FIRST — scope condition)** — **DOES NOT APPLY in base scope**: scope says "extend existing gas water heater vent through new roof" (vent change only). DO NOT emit `procurement.tank` or `plumbing.tank_set` for the base job. **Conditionally applies if** the Tankless WH Optional Package ($6,500) is accepted by customer — Stage B should ask PM.
- **_company/rules/dev_rules.md § 4I (MEPs depend on underlayment + windows, NOT dried-in)** — gate `electrical.rough_in`, `plumbing.rough_in`, `hvac.minisplit_rough` on `roofing.underlayment` + `windows.install`.
- **_company/rules/dev_rules.md § 4J (Windows install IMMEDIATELY after roof framed)** — `windows.install` FS after `framing.roof` + `checkpoint.windows_arrived`, runs parallel with `roofing.underlayment`.
- **_company/rules/dev_rules.md § 4K (Heat pump relocation BEFORE demo)** — scope explicitly relocates existing heat pump + electrical disconnect. Emit `prep.heat_pump_relocate` and `prep.electrical_disconnect_relocate` in `site_prep / prep_work_before_demo`, NOT in demo phase.
- **_company/rules/dev_rules.md § 4L (Interior finish dependency chain)** — apply strict deps: flooring → paint_1, trim → flooring, paint_2 → trim, electrical.finish → paint_1, plumbing.finish → cabinets+flooring+tile.
- **_company/rules/dev_rules.md § 4M (Final inspections bundled)** — one `inspect.final_bundled` covers final electrical/plumbing/HVAC + final building.
- **_company/rules/dev_rules.md § 4N (2-trades-max interior — HVAC stagger)** — apply default stagger: `hvac.minisplit_install` FS after `electrical.finish`. Emit warning.
- **_company/rules/dev_rules.md § 4O (Equipment day-before-phase + 2-week checkpoint)** — emit dumpster, demo machines (concrete saw, skid steer, mini-ex), scaffolding day-before-phase tasks + `checkpoint.equipment_confirmed_*` at offset 10.
- **_company/rules/dev_rules.md § 4P (Selections-finalized checkpoint mandatory)** — emit `checkpoint.selections_finalized` at offset 15.
- **_company/rules/dev_rules.md § 4Q (Trusses procurement CONDITIONAL)** — scope says "truss or rafter framed, determined during design phase" + roof span < 24 ft + footprint < 800 sqft → **default to stick-frame, NO `procurement.trusses` task.** Emit warning per Rule 25.
- **_company/rules/dev_rules.md § 4R (Procurement 3-task pattern)** — every procurement (windows, doors, subpanel, mini-split, LVT, paint, vanity, tile, fixtures, LVL) decomposes into order/wait/checkpoint trio. Short-lead items (≤7 day supplier) may collapse to single 1d order task.
- **_company/rules/dev_rules.md § 4S (Free-floating PC tasks need `pre_construction_offset_working_days`)** — apply to permit, selections checkpoint, amperage check, equipment checkpoints.
- **_company/rules/dev_rules.md § 4T (Lead-up windows)** — set `lead_up_working_days` per task per default table (selections=5, permit=2, equipment checkpoints=2, vendor-confirm orders=2, etc).
- **_company/rules/dev_rules.md § 4U (No-op checkpoints forbidden)** — every `checkpoint.*` must gate a downstream consumer.
- **_company/rules/dev_rules.md § 4V (Customer early items + retrofit two-bucket pattern)** — scope hall bath has BOTH an acrylic shower swap (customer-requested early item candidate per addition_rules 308 example) AND retrofit work (window infill, drywall patch, repaint). Two components: `early.acrylic_shower_swap` in `customer_early_items` Day 1, separate `hall_bath_mod` Component for retrofit work in interior_finishes.
- **_company/rules/dev_rules.md § 9 (Retrofit detection — three signals)** — apply to every breakdown section. Strong retrofit signals already visible: hall bath section, "existing" keywords throughout demo + electrical sections.
- **_company/rules/dev_rules.md § 11 mandatory warnings** — most likely to fire: #25 (ambiguous truss/rafter), #4 (some sections > 100h with few tasks), and possibly #8 (negative section_total on hall bath/closeout combo line, $-1,714, with 72h — flags as scope ambiguity).
- **_company/rules/editor_rules.md (whole document)** — full TCR scheduling baseline: phase spine, productivity table, lead-time table, paint two-phase, drywall consolidation, etc. Applies in full.
- **_company/rules/pep_rules.md (whole document)** — applies at PEP-generation stage downstream of intel.

## Company beliefs

- **_company/beliefs/_examples/stick_frame_default_for_small_additions.md** — confidence 0.92. Directly applicable: addition < 800 sqft AND scope is ambiguous ("truss OR rafter") AND roof span < 24 ft → default stick-frame, no `procurement.trusses`. No PM Interview override yet.

## Job-type rules

- **job_types/addition/rules/addition_rules.md § Septic (TDEC)** — CONDITIONAL: scope explicitly mentions TDEC coordination + septic feasibility + grinder pump. Master bath adds fixtures that count against TDEC capacity. **APPLIES IF home is on septic** — PM Interview must confirm septic vs city sewer. If septic: emit `permit.tdec_septic`, `kind: lead_time`, `lead_time_days: 42`, `pre_construction_offset_working_days: 30`, gates `excavation.dig`.
- **job_types/addition/rules/addition_rules.md § Structural long-lead — Trusses (CONDITIONAL)** — same conclusion as Rule 4Q: default stick-frame.
- **job_types/addition/rules/addition_rules.md § Structural long-lead — LVL beams** — applies: scope has (1) 3-ply 14" LVL spanning 15'-6". Default `lead_time_days: 14`; ask PM if pressure-treated/custom (then 21).
- **job_types/addition/rules/addition_rules.md § Windows order tied to install date** — applies. Confirm stock vs custom; allowance $300/each suggests stock; use `lead_time_days: 21`.
- **job_types/addition/rules/addition_rules.md § Windows install immediately after roof framed** — applies (same as Rule 4J).
- **job_types/addition/rules/addition_rules.md § MEPs gated on underlayment + windows** — applies (same as Rule 4I).
- **job_types/addition/rules/addition_rules.md § Heat pump relocation BEFORE demo** — applies; scope explicitly calls out heat pump + electrical disconnect relocation.
- **job_types/addition/rules/addition_rules.md § Retrofit detection HARD heuristic** — applies. Three signals visible: (A) hall bath / bedroom 3 outside named objective areas, (B) "existing" keyword throughout, (C) elevator shaft 4'×4' — location resolves inside addition per plans (NEW, not retrofit); window relocations + door reframes resolve as retrofit per plans.
- **job_types/addition/rules/addition_rules.md § Customer early items** — APPLIES with high confidence: hall bath acrylic shower swap matches the 308 canonical example word-for-word in the rules doc. Stage B must confirm at PM Interview and emit `early.acrylic_shower_swap` in `customer_early_items` Component.
- **job_types/addition/rules/addition_rules.md § Concealed roof tie-in** — APPLIES: new 3/12 gable into existing 6/12 + chimney near tie-in. Emit `roof.concealed_buffer` (`lead_time_days: 3`, `SS lag 1` after `framing.roof`) + warning.
- **job_types/addition/rules/addition_rules.md § Existing electrical service amperage check** — APPLIES: scope has 100A subpanel. Scope assumes existing service supports it but provides no verification. Emit `prep.amperage_check` (0.5d, general, pre_construction) + warning if missing.
- **job_types/addition/rules/addition_rules.md § LVL temporary shoring independent retrofit** — APPLIES: 3-ply 14" LVL opens existing load-bearing wall. PM Interview must confirm whether new floor/roof load bears on the LVL. Default: independent retrofit, do NOT gate `framing.floor_system` on LVL.
- **job_types/addition/rules/addition_rules.md § Material ordering — interior finishes wait** — applies: tile, cabinets/vanity, LVT, paint orders are install-date-driven, not start-of-project.
- **job_types/addition/rules/addition_rules.md § Procurement chains live in `procurement_long_leads` Phase (NOT pre_construction)** — applies for all order/wait/checkpoint trios. Pre-construction holds only permit/walkthrough/selections/amperage/equipment-confirmed.
- **job_types/addition/rules/addition_rules.md § Drywall cracking 1-year warranty** — applies: emit `assumptions[]` entry.
- **job_types/addition/rules/addition_rules.md § Will's walkthrough — final closeout** — applies: emit `closeout.wills_walkthrough` (0.5d, general, FS lag 1 after `inspect.final_bundled`).
- **job_types/addition/rules/tdec_septic_permit_offset.md** — applies CONDITIONALLY (same as TDEC septic rule above) — if home on septic, offset 30 is mandatory.

## Rules explicitly NOT applying (skipped)

- Tank-set sequence (Rule 4H base scope) — existing WH stays, vent extension only.
- Ducted HVAC sequence (Rule 4G ducted branch) — scope explicitly mini-split.
- Trusses procurement (Rule 4Q + addition_rules trusses condition) — small addition, ambiguous scope, stick-frame default.
- CMU / foundation wall multi-pour pattern (Rule 4B exception branch) — scope excludes CMU and foundation walls explicitly.
