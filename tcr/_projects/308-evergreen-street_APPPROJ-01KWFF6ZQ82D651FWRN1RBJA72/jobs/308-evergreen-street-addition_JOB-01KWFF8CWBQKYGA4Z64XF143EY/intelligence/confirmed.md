---
generation_kind: intelligence_rebuild_v2
stage: synthesis
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWFF6ZQ82D651FWRN1RBJA72/jobs/308-evergreen-street-addition_JOB-01KWFF8CWBQKYGA4Z64XF143EY/interview/round-1.md
---

# PM-Confirmed Facts — 308 Evergreen Addition

PM-confirmed facts with round provenance. Each item is authoritative — the PM has explicitly answered.

## Scope reconciliation

- Scope-vs-CSV $73,071 gap (42.1%) is explained by markup/margin: scope's $173,850 already includes materials cost+15% / subs cost+30% + margin, whereas CSV shows raw costs only. *(round 1, q.scope_vs_csv_total_reconciliation: Scope includes markup; CSV shows raw costs)*

## Sewer / septic

- Existing septic stays; TDEC inspection only (confirms capacity). No grinder pump, no septic relocation. `permit.tdec_septic` is the inspection-only path — no downstream install-gating on septic. *(round 1, q.sewer_septic_direction: Existing septic stays; TDEC inspection only)*

## Fenestration

- Windows: order 2 NEW (1× 3'-0"×3'-0" D.H. + 1× 3'-0"×1'-0" transom) per drawings + relocate 2 existing windows. Add a relocate-labor line. Scope's "(4) new windows × $300" material allowance overstates by half. *(round 1, q.window_count_and_relocation: Drawings authoritative — 2 new + 2 relocated)*

## Exterior cladding

- All exterior cladding is vinyl lap siding — NO brick veneer. The plans' "NEW BRICK TO MATCH EXISTING" callouts reflect an outdated design; scope is current. *(round 1, q.brick_veneer_scope: No brick — design updated to all vinyl lap siding)*

## Customer early item — hall bath

- Hall bath acrylic shower swap (remove tub/combo, install acrylic pan+walls, reuse existing valve/trim) is a CUSTOMER-REQUESTED EARLY ITEM. Emit `early.acrylic_shower_swap` in `site_prep / customer_early_items` on Day 1 BEFORE main demo. *(round 1, q.hall_bath_acrylic_shower_timing: Customer early item — Day 1 before demo)*
- Hall bath retrofit remainder (window infill + drywall patch + repaint) stays in a separate `hall_bath_mod` component running in parallel with main interior finishes. *(round 1, q.hall_bath_acrylic_shower_timing: implicit — Rule 4V two-bucket pattern)*

## Water heater

- Tankless WH Optional Package is NOT elected. Existing gas water heater stays. Only the vent extension through the new roof is in scope. Rule 4H (tank_set FIRST) does NOT apply — no `procurement.tank` or `plumbing.tank_set` tasks. *(round 1, q.tankless_water_heater_election: Not elected — keep existing gas WH; vent extension only)*

## Interior doors

- Interior door mix: 3 pre-hung panel doors + 1 pocket door (at hall bath entry per plans p.3). Total 4 interior doors matches scope. *(round 1, q.interior_doors_pocket_vs_panel: 3 pre-hung panel + 1 pocket at hall bath)*

## Plumbing labor floor

- Plumbing rough repriced to Will's nominal: 4 working days × 2 crew = 64 person-hours. Overrides the CSV's 40-hr figure, satisfying company hard rule `plumbing_rough_min_duration`. *(round 1, q.plumbing_rough_labor_floor: Reprice to 64 hrs — 4d × 2 crew)*
