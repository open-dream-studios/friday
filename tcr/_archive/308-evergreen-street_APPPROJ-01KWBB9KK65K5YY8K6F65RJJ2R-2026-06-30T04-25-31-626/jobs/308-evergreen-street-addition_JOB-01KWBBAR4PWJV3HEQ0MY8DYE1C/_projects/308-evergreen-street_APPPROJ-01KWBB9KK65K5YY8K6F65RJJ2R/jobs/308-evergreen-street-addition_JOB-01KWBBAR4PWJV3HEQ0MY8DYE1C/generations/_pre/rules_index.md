---
generation_kind: intel_gather_v1
artifact: rules_index
last_verified_at: 2026-06-30T04:08:07Z
---

## Company rules

- **_company/rules/dev_rules.md:§3 Hard rules** — TaskGraph format contract (unique ids, acyclic, FS default, inspection / procurement / milestone shapes) — applies to every emitted graph for this job.
- **_company/rules/dev_rules.md:4A permits 1-day work task** — scope.md L11 requires permit per local jurisdiction; emit as 1d general work scheduled 15 wd before on-site, NOT 14-day lead_time.
- **_company/rules/dev_rules.md:4B monolithic foundation default** — scope.md L40-45 specifies 12"×12" footings + 4" slab on gravel + NO CMU / NO foundation walls → monolithic pour is the right shape (footing + slab same day, one footing inspection).
- **_company/rules/dev_rules.md:4C bundled rough inspections** — bundle rough electrical + plumbing + mini-split rough + framing into ONE inspector visit (mini-split job; HVAC rough is line-set only).
- **_company/rules/dev_rules.md:4D 2-4d punch-list buffer after rough inspections** — required as standard; insert `buffer.post_rough_inspection` 2 wd before insulation air-seal.
- **_company/rules/dev_rules.md:4E paint two phases (mandatory)** — drywall is in scope (L108) → must emit `paint.phase_1` + `paint.phase_2`. Phase 1 covers primer walls/ceilings AM + ceiling finish PM same day per Will's standard.
- **_company/rules/dev_rules.md:4F paint phase 2 = last work task + substantial completion** — gate phase 2 on EVERY finish trade (trim, flooring, vanity, tile grout, plumbing finish, electrical finish, mini-split install).
- **_company/rules/dev_rules.md:4G HVAC type drives MEP order** — scope.md L99 explicitly says "ductless mini-split" → MEP order is plumbing → electrical → mini-split rough (line set 0.5d/1 person).
- **_company/rules/dev_rules.md:4H tank set FIRST — EXCEPTION FIRES HERE** — scope.md L37 only EXTENDS existing gas WH vent through new roof; existing WH stays. Base scope → DO NOT emit `procurement.tank` or `plumbing.tank_set`. Plumbing rough proceeds without tank predecessor. (If Optional Tankless WH package opts in → rule activates.)
- **_company/rules/dev_rules.md:4I MEPs depend on underlayment + windows (NOT dried-in milestone)** — addition job → gate all rough MEPs on `roofing.underlayment` + `windows.install`.
- **_company/rules/dev_rules.md:4J windows install immediately after roof framed** — `windows.install` FS after `framing.roof` + `procurement.windows`; parallel with `roofing.underlayment`.
- **_company/rules/dev_rules.md:4K heat pump relocation BEFORE demo** — scope.md L36 "Relocate existing heat pump and electrical disconnect" → emit in `site_prep / prep_work_before_demo`, NOT demo phase; ≥3 wd before demo.
- **_company/rules/dev_rules.md:4L interior finish dependencies (strict)** — flooring/trim/cabinets/paint-2 chain is non-negotiable.
- **_company/rules/dev_rules.md:4M final inspections bundled** — emit `inspect.final_bundled` (0.5d, one inspector covering electrical + plumbing + HVAC + building).
- **_company/rules/dev_rules.md:4N 2-trades-max interior + HVAC stagger** — finish cluster will have electrical finish + plumbing finish + mini-split install all gated off paint phase 1 / flooring / cabinets cluster → apply default HVAC-after-electrical stagger.
- **_company/rules/dev_rules.md:4O equipment day-before-phase + 2-week checkpoint** — dumpster (demo), backhoe / mini-ex (excavation, breakdown line $1,950), scaffolding (roof / siding, breakdown line $560) — each gets day-before delivery + 2-wk equipment-confirmed checkpoint.
- **_company/rules/dev_rules.md:4P selections-finalized checkpoint (mandatory)** — emit `checkpoint.selections_finalized` 3 wks before on-site (offset 15) — many open selections: tile, vanity finish, paint, LVT, faucets, mirrors, recessed-light style.
- **_company/rules/dev_rules.md:4Q trusses procurement CONDITIONAL — SKIP** — scope.md L57 says "truss OR rafter framed, determined during design phase"; footprint <800 sqft (590 sqft addition); span small (10' deep addition); no explicit truss callout → stick-frame default, NO `procurement.trusses` task.
- **_company/rules/dev_rules.md:4R procurement 3-task pattern (order/wait/arrived)** — windows (4 incl. transom), exterior door, LVL beam (3-ply 14"), 100A subpanel, mini-split unit — each decomposes to order + wait + checkpoint.
- **_company/rules/dev_rules.md:4S pre-construction offsets** — permit, selections checkpoint, amperage check (assumed-but-unverified service capacity per scope.md L86), equipment-confirmed checkpoints all need explicit `pre_construction_offset_working_days`.
- **_company/rules/dev_rules.md:4T lead-up windows** — apply default table to selections (5), permit (2), order tasks (2 if vendor confirm), phase-start bars (2), inspections (1).
- **_company/rules/dev_rules.md:4U no-op checkpoints forbidden** — every `checkpoint.*` must have a downstream consumer; do not emit `checkpoint.tdec_septic_complete` or similar tail-only milestones.
- **_company/rules/dev_rules.md:4V customer early items + retrofit = SEPARATE components** — scope.md L141-149 hall bath: acrylic shower swap (likely customer early item, day 1 before demo, in `customer_early_items` component) vs. window infill + drywall patch + repaint (retrofit, in `hall_bath_mod` component, parallel with main scope). **Confirm acrylic-shower-swap timing intent with PM** — if "before main demo so homeowner has working shower" is the customer's ask, two-bucket required.
- **_company/rules/editor_rules.md:§Permits** — corroborates 4A.
- **_company/rules/editor_rules.md:§Material ordering** — 1 week on site before install; equipment dried-in for mechanical.
- **_company/rules/editor_rules.md:§Equipment day-before rule** — dumpster, mini-ex, scaffolding land day before consuming phase.
- **_company/rules/editor_rules.md:§Default crew sizes** — apply table for plumbing (default 4d × 2 floor for master bath / W/D / vent extension — relevant given low CSV labor hours), electrical (subpanel 1d/1 person), insulation (1d typical addition), drywall (consolidated 9-11d).
- **_company/rules/editor_rules.md:§Lead-time items** — windows stock 14-21d, exterior door 21-28d, LVL standard 7d (14d safety), mini-split 7-14d, electrical panel 7-14d, paint 1-2d, LVT 7d, vanity/fixtures 7d.
- **_company/rules/editor_rules.md:§Bundled rough inspection + punch buffer** — corroborates 4C/4D.
- **_company/rules/editor_rules.md:§Material delivery tied to inspection date** — insulation material on site same day as `inspect.rough_bundled`.
- **_company/rules/editor_rules.md:§Crew concurrency hard interior limit** — 2-trades max; HVAC-after-electrical stagger.
- **_company/rules/editor_rules.md:§Same-crew exterior pattern** — siding + trim + fascia/soffit + gutters as one contiguous same-crew block (breakdown bundles them: $5,731 exterior section).
- **_company/rules/editor_rules.md:§Customer early items — TWO-BUCKET pattern** — explicit precedent for hall bath acrylic shower swap scenario.
- **_company/rules/editor_rules.md:§Paint two phases** — corroborates 4E/4F.
- **_company/rules/editor_rules.md:§Foundation monolithic default** — corroborates 4B.
- **_company/rules/editor_rules.md:§HVAC sequencing — ducted vs mini-split** — mini-split for this job.
- **_company/rules/editor_rules.md:§Plumbing — tank set FIRST when WH in scope** — exception fires here (vent extension only).
- **_company/rules/editor_rules.md:§Plumbing rough-in duration** — default 4d × 2 crew floor for master bath + W/D + vent through roof; CSV's 40 lh is low → expect duration override.
- **_company/rules/editor_rules.md:§Drywall consolidation** — addition + bedroom remodel + basement storage + hall bath patch → consolidate into one hang/finish block (breakdown already bundles addition + bedroom drywall, 159 lh).
- **_company/rules/editor_rules.md:§Interior finish dependencies** — rewrites of flooring/trim/cabinets/paint chain.
- **_company/rules/editor_rules.md:§Closeout punch list workflow** — walkthrough → returns → final clean → bundled final inspection → CO handoff.
- **_company/rules/pep_rules.md** — applies to any downstream PEP-author generation for this job (whitespace discipline, lead-up day blocks, delivery/trade-stack callouts).

## Company beliefs

- **_company/beliefs/_examples/stick_frame_default_for_small_additions.md** — APPLIES. Footprint 590 sqft (well under 800), roof depth ~10' (well under 24'), scope explicitly says "truss OR rafter — determined during design phase" → stick-frame default fires. No `procurement.trusses` task.

## Job-type rules

- _No `job_types/addition/` rules folder present in trunk; only `_company/` rules apply at job-type layer for now._

## Job-specific rules

- _None — `rules/.gitkeep` only._
