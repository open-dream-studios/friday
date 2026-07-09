---
generation_kind: intelligence_rebuild_v2
stage: synthesis
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWHW43S2QEWKEA40SMH16A80/jobs/308-evergreen-street-addition_JOB-01KWHW5QAKN18903FHSX0XPVBS/manifest.json
---

# Confirmed facts — PM interview provenance

- Septic work is inspection-only — keep existing septic system with TDEC inspection per job-type rule `tdec_septic_permit_offset` (30-working-day offset for permit.tdec_septic); no excavation, relocation, or grinder pump work in scope. *(round 1, q.septic_direction: Keep existing septic — TDEC inspection only, no excavation work)*
- Roof framing is stick-framed rafters — no truss procurement; lumber arrives day-of with framing crew per belief `stick_frame_default_for_small_additions`. *(round 1, q.roof_framing_method: Stick-framed rafters — lumber arrives day-of with framing crew)*
- Tankless water heater optional package NOT elected — existing water heater stays in place; only vent extends through new roof per scope; no `procurement.tank` or `plumbing.tank_set` tasks per dev_rules 4H. *(round 1, q.tankless_option_elected: No — existing water heater stays, only vent extends through new roof)*
- Closet & Cabinet System optional package NOT elected — walk-in closet remains empty room with no millwork; no cabinet procurement or install tasks. *(round 1, q.closet_system_elected: No — no closet system, empty walk-in closet)*
- Customer requested early item: hall bath acrylic shower swap to provide working shower during construction — triggers dev_rules 4V two-bucket pattern; early shower swap lives in `site_prep / customer_early_items` component on Day 1, SEPARATE from hall bath retrofit window-infill/repaint work in interior_finishes. *(round 1, q.customer_early_items: Yes — hall bath acrylic shower swap (early, for working shower during construction))*
- Hall bath acrylic shower reuses existing valve and trim per scope — no valve/trim procurement needed; plumbing rough for hall bath is zero-task (retrofit component only touches demo, shower pan/walls install, and finish paint). *(round 1, q.hall_bath_valve_reuse_confirmed: Yes — reuse existing valve and trim as scoped)*
- Exterior door is stock unit with 7-day lead per editor_rules — $500 allowance; no custom-order extended lead. *(round 1, q.exterior_door_type: Stock unit — 7-day lead)*
- Interior door count resolved: 4 doors total = 2 pre-hung + 2 pocket doors; procurement quantity confirmed; pocket doors frame BEFORE drywall per dev_rules framing/drywall sequencing. *(round 1, q.fourth_interior_door_type: Second pre-hung interior door (2 pre-hung + 2 pocket))*