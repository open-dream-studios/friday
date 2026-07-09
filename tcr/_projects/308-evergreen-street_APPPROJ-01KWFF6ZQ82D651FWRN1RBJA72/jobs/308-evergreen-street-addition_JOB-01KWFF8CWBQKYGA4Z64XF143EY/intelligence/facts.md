---
generation_kind: intelligence_rebuild_v2
stage: synthesis
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWFF6ZQ82D651FWRN1RBJA72/jobs/308-evergreen-street-addition_JOB-01KWFF8CWBQKYGA4Z64XF143EY/manifest.json
  - _projects/308-evergreen-street_APPPROJ-01KWFF6ZQ82D651FWRN1RBJA72/jobs/308-evergreen-street-addition_JOB-01KWFF8CWBQKYGA4Z64XF143EY/intelligence/extracted/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KWFF6ZQ82D651FWRN1RBJA72/jobs/308-evergreen-street-addition_JOB-01KWFF8CWBQKYGA4Z64XF143EY/intelligence/extracted/breakdown.md
  - _projects/308-evergreen-street_APPPROJ-01KWFF6ZQ82D651FWRN1RBJA72/jobs/308-evergreen-street-addition_JOB-01KWFF8CWBQKYGA4Z64XF143EY/intelligence/extracted/plans.md
  - _projects/308-evergreen-street_APPPROJ-01KWFF6ZQ82D651FWRN1RBJA72/jobs/308-evergreen-street-addition_JOB-01KWFF8CWBQKYGA4Z64XF143EY/intelligence/applicable_rules.json
---

# Facts — 308 Evergreen Addition

Synthesized from stage-A extractions. Each fact is one sentence with source citation.

## Customer & Job

- Job label is "308 Evergreen Street — addition" and job_type is `addition`. *(manifest.json L4, L11)*
- Job ID `JOB-01KWFF8CWBQKYGA4Z64XF143EY` under project `APPPROJ-01KWFF6ZQ82D651FWRN1RBJA72`. *(manifest.json L2, L5)*
- Scope document titled "308 Evergreens Scope" from Simons Addition drawing set by Greyscale Design LLC (Rebecca Lineberry, NCIDQ), dated 01/22/2026. *(extracted/scope.md L11; extracted/plans.md L5-6)*
- Scope Total Investment quoted at $173,850; CSV grand total is $100,778.92 — a 42.1% gap. *(extracted/scope.md L16; extracted/breakdown.md — CSV totals row)*
- Deposit is $20,000 upon signed agreement; weekly invoicing thereafter with balance at completion. *(extracted/scope.md L18-20)*
- Rates: $70/hr general; +$15 team-lead; +$30 electrical/HVAC; +$40 plumbing; materials cost+15%; subs cost+30%. *(extracted/scope.md — Rates section)*

## Scope

- Two-story addition approximately 30' × 10' (295 sqft basement + 295 sqft first floor = 590 sqft total). *(extracted/scope.md L21-23; extracted/plans.md L14-15)*
- Second-floor expansion covers primary bedroom, master bathroom, and walk-in closet. *(extracted/scope.md L21-23)*
- Basement-level 295 sqft is finished storage (framed, drywalled, painted, lighting fixture, unfinished concrete floor). *(extracted/scope.md L27; extracted/scope.md — Basement Storage Finish)*
- Primary Bedroom Remodel area ~12'5" × 16' (drywall Level 3, prime + paint, new LVT, full trim package). *(extracted/scope.md L25-26)*
- Master Bathroom includes custom tile shower (scope: ~7'×4' — plans show different dimensions, see Discrepancies), 72" double vanity, dual-valve diverter, 2 lav + toilet + fan/light combo. *(extracted/scope.md — Master Bathroom section)*
- Existing hall bathroom modification: remove window (window infill), remove tub/shower combo, install acrylic shower (reuse existing valve/trim), PVC trim, patch/repaint. *(extracted/scope.md — Existing Hall Bathroom Modification)*
- Future elevator shaft 4'×4' framed (elevator not included) + rough-in 30A/120V circuit from subpanel. *(extracted/scope.md L27, L59-60; extracted/plans.md — floor plan)*
- Optional Package: Closet & Cabinet System — $7,000 allowance (labor + materials). *(extracted/scope.md — Optional Packages)*
- Optional Package: Tankless Water Heater — $6,500 allowance; utility upgrades excluded. *(extracted/scope.md — Optional Packages)*
- IRC 2018 + NEC compliance required; contractor verifies all existing conditions/dimensions before construction. *(extracted/scope.md — General Conditions; extracted/plans.md — boilerplate note)*

## Site

- Existing structure has a chimney within the roof tie-in zone (plans p.5) — scope does NOT mention chimney flashing or cricket detail. *(extracted/plans.md — Things plans show scope doesn't mention)*
- Plans require field verification of existing plumbing, venting, septic tank, HVAC locations before construction (hard note on p.4). *(extracted/plans.md — Retrofit indicators)*
- Plans require field verification of existing roof slopes (6/12 assumed) and soffit depth before construction (hard note on p.5). *(extracted/plans.md — Retrofit indicators)*
- Standard soil conditions assumed; rock excavation/unsuitable soils excluded (change order). *(extracted/scope.md — General Conditions)*
- Standard site access assumed for equipment, staging, and construction operations. *(extracted/scope.md — General Conditions)*
- Two existing windows are being RELOCATED (not just added new); one existing door also relocated. *(extracted/plans.md — Retrofit indicators)*
- Existing primary bedroom wall is opened at the LVL location (15'-6" span) — the LVL sits at the interior seam between existing bedroom and new addition, NOT an exterior wall. *(extracted/plans.md — Retrofit indicators)*

## Trades — labor & scope

- **Foundation:** continuous 12"×12" perimeter footings; 4" gravel base; vapor barrier; rebar/mesh; 4" slab with smooth finish; no CMU or foundation walls. *(extracted/scope.md — Foundation & Slab)*
- **Framing:** 2x4 @ 16" O.C. throughout; 3-ply 14" LVL spanning ~15'-6" with temporary shoring; new gable roof at 3/12 tying into existing 6/12; footprint 300 sqft roof area. *(extracted/scope.md — Framing; L57-58)*
- **Roof framing method** is unresolved by scope ("truss OR rafter framed, determined during design phase") — company belief `stick_frame_default_for_small_additions` (confidence 0.92) applies: default stick-frame, NO `procurement.trusses`. *(extracted/scope.md L57; applicable_rules.json — stick_frame_default_for_small_additions)*
- **Roofing:** architectural asphalt shingles + synthetic underlayment + drip edge + flashing + ridge vent + fascia board/metal + vinyl soffit + seamless gutters. *(extracted/scope.md — Roof System)*
- **Exterior:** sheathing + WRB + vinyl siding to match existing; plans show elevations that CONTRADICT scope (see Discrepancies). *(extracted/scope.md — Exterior Finishes; extracted/plans.md — Discrepancies)*
- **Electrical:** new 100A subpanel; full rough + trim; ~12 recessed lights (allowance up to 18); 2 vanity lights; bath fan/light combo; standard outlets + GFCI/AFCI; dedicated 30A/120V elevator circuit; scope ASSUMES existing service supports subpanel. *(extracted/scope.md — Electrical)*
- **Plumbing:** full rough (supply/waste/vent); quarter-turn shutoffs; master bath (2 lav + toilet + custom shower dual valve diverter); W/D relocation with roof-vented dryer; vent stacks extended through new roof; existing sewer/septic capacity assumed. *(extracted/scope.md — Plumbing)*
- **HVAC:** 1 ductless mini-split ($2,500 allowance); relocate existing HVAC components; extend existing gas WH vent through new roof. *(extracted/scope.md — HVAC; extracted/scope.md — Selective Demolition)*
- **Insulation:** R13 exterior walls; R30 attic/roof; R30 floor system between basement and living space; seal penetrations. *(extracted/scope.md — Insulation)*
- **Drywall:** Level 3 finish (3 coats compound + sand); primer + 2 finish coats — applies to addition, primary bedroom remodel, basement storage, hall bath. *(extracted/scope.md — Interior Finishes; Drywall row)*
- **Interior finishes:** LVT throughout ($3/sqft allowance); 5-1/4" base + 2-1/4" casing; trim/caulk/fill/sand/paint; 4 total interior doors (mix of pre-hung + pocket — resolved in round 1). *(extracted/scope.md — Interior Finishes; Interior Doors)*
- **Master bath tile:** custom tile shower with waterproofing, tile walls + mosaic floor, niche + bench, dual valve diverter, exhaust fan/light vented exterior. *(extracted/scope.md — Master Bathroom)*
- **CSV labor totals: 1,287 labor hrs, $45,167.59 labor, $52,171.33 material, $3,440 equipment, $100,778.92 grand total.** *(extracted/breakdown.md — trade totals)*
- **Row 25 (Hall Bath Mod + Bedroom Remodel + Closeout) has NEGATIVE $-4,199 material and $-1,714.20 section total** on 72 labor hrs — anomaly flagged. *(extracted/breakdown.md — anomalies)*
- **CSV plumbing row (40 labor hrs) is BELOW company hard-floor** of 4d × 2 crew = 64 hrs per `plumbing_rough_min_duration` — resolved in round 1 (reprice to 64 hrs). *(extracted/breakdown.md — Room-count/plumbing productivity check; applicable_rules.json)*

## Sequencing / Applicable Rules

- Company rule `scope_vs_csv_total_reconciliation` was TRIGGERED by the 42.1% gap; resolved in round 1 (scope figure includes markup + margin). *(applicable_rules.json; interview round 1)*
- Company rule `service_amperage_check` REQUIRES a `prep.amperage_check` task before `procurement.panel.order` and `electrical.rough` — this job adds ≥4 circuits, subpanel, and mini-split, so it applies. *(applicable_rules.json; extracted/scope.md — Electrical)*
- Company belief `drywall_soft_schedule` (confidence 0.85): drywall crew is `soft_start: true` — pencil from nominal but do not commit until first insulation inspection is calendared. *(applicable_rules.json)*
- Company belief `roof_and_siding_same_crew` (confidence 0.90): default single 2-3 person crew serializes roofing then siding on TCR jobs. *(applicable_rules.json)*
- Job-type rule `retrofit_tie_in_discovery` REQUIRES a `framing.tie_in_discovery` task SS with tie-in framing — this job has explicit tie-in (LVL at existing wall, roof tie 3/12→6/12, two window relocations, chimney in roof-tie zone). *(applicable_rules.json; extracted/plans.md)*
- Job-type rule `siding_starts_at_underlayment` allows siding to soft-overlap with underlayment + windows; combined with `roof_and_siding_same_crew` belief, expect serial in practice. *(applicable_rules.json)*
- Job-type rule `tdec_septic_permit_offset` anchors `permit.tdec_septic` at `pre_construction_offset_working_days: 30` (6 weeks) — TDEC inspection is in scope even though relocation is a change order (resolved in round 1: existing septic stays, inspection only). *(applicable_rules.json; interview round 1)*
- Company rule 4V (customer early items separate component): applies — hall bath acrylic shower swap resolved as `early.acrylic_shower_swap` in `site_prep / customer_early_items` (round 1). *(applicable_rules.json; interview round 1)*

## Procurement (long-lead items)

- **Windows:** 2 new units per plans (1× 3'×3' DH + 1× 3'×1' transom) + relocate 2 existing (round 1 resolution) — stock windows at 14-21 calendar days supplier lead. *(extracted/plans.md — window schedule; interview round 1)*
- **Doors:** 3 pre-hung panel + 1 pocket + 1 exterior metal (round 1 resolution). *(interview round 1; extracted/plans.md — door schedule)*
- **LVL beam** (3-ply 14", ~15'-6" span): standard LVL lead 7-14 calendar days per editor rules. *(extracted/scope.md — Framing; editor_rules.md lead-time table)*
- **Electrical panel** (100A subpanel): 7-14 calendar days supplier lead. *(extracted/scope.md — Electrical; editor_rules.md)*
- **Mini-split unit:** 7-14 calendar days; $2,500 allowance. *(extracted/scope.md — HVAC; editor_rules.md)*
- **Tile (custom master bath):** 14-21 calendar days for custom tile ($3/sqft walls, $6/sqft mosaic floor). *(extracted/scope.md — Material Allowances; editor_rules.md)*
- **Acrylic shower system** for hall bath (round 1: customer early item — needs on site Day 1). *(interview round 1)*
- **NO trusses procurement task** per stick-frame default belief. *(applicable_rules.json — stick_frame_default_for_small_additions)*
- **NO water heater procurement / tank_set** — round 1 confirmed existing gas WH stays (vent extension only). Rule 4H (tank set FIRST) does NOT apply. *(interview round 1)*

## Retrofit / tie-in flags

- **Hall bath work is TWO components per Rule 4V:** bucket 1 = `early.acrylic_shower_swap` (Day 1, before demo); bucket 2 = `hall_bath_mod` retrofit (window infill, drywall patch, repaint — runs in parallel with main scope). *(applicable_rules.json — Rule 4V; interview round 1)*
- **Existing primary bedroom remodel is retrofit-in-parallel** with new addition (drywall, paint, LVT, trim). *(extracted/scope.md — Primary Bedroom Remodel; retrofit heuristic §9 signals A + C)*
- **Roof tie-in from new 3/12 gable to existing 6/12** with existing chimney in path — concealed-condition discovery risk. *(extracted/plans.md; extracted/scope.md — Roof System)*
- **Basement addition layout in plans is ambiguous** — labels "garage / lounge / living / kitchen-dining" may be EXISTING context rather than new 295-sqft build; needs PM confirmation. *(extracted/plans.md — Things plans show scope doesn't mention)*

## Discrepancies (plans vs scope)

- Master shower dimensions: scope says ~7'×4', plans show ~5'7½"×10' — affects tile quantities. *(extracted/plans.md — Discrepancies)*
- Window count/size: resolved round 1 (drawings authoritative — 2 new + 2 relocated). *(interview round 1)*
- Exterior cladding: plans show brick base + lap siding; resolved round 1 (design updated, plans out of date — all vinyl lap siding). *(interview round 1)*
- Interior door mix: resolved round 1 (3 pre-hung panel + 1 pocket at hall bath entry). *(interview round 1)*
- Chimney flashing/cricket at roof tie-in NOT in scope — potential change-order item. *(extracted/plans.md — Discrepancies; Things plans show scope doesn't mention)*

## Change-order / carve-out items (explicitly excluded)

- Septic relocation / grinder pump install — round 1 confirmed existing septic stays, inspection only. *(extracted/scope.md — Pre-Construction; interview round 1)*
- Rock excavation, unsuitable soils, additional structural requirements. *(extracted/scope.md — General Conditions)*
- Concealed-condition discoveries (wiring, plumbing, structural irregularities) during demo. *(extracted/scope.md — General Conditions)*
- French drains, foundation waterproofing, drainage improvements. *(extracted/scope.md — Water Management)*
- Utility upgrades for tankless WH option (moot — not elected). *(extracted/scope.md — Optional Packages)*
- Elevator system itself (framing + 30A circuit only). *(extracted/scope.md — Elevator Shaft)*
