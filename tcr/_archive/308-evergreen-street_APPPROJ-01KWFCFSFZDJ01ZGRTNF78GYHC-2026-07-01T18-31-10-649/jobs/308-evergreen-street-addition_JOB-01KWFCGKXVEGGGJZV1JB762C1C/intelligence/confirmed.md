---
generation_kind: intelligence_interview_v2
stage: synthesis
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWFCFSFZDJ01ZGRTNF78GYHC/jobs/308-evergreen-street-addition_JOB-01KWFCGKXVEGGGJZV1JB762C1C/manifest.json
  - _projects/308-evergreen-street_APPPROJ-01KWFCFSFZDJ01ZGRTNF78GYHC/jobs/308-evergreen-street-addition_JOB-01KWFCGKXVEGGGJZV1JB762C1C/interview/round-1.md
---

# PM-Confirmed Facts — 308 Evergreen Street Addition

- Scope Total Investment $173,850 vs CSV grand total $100,778.92 (~$73k gap) is reconciled: scope figure includes markup, overhead, contingency, and sub margins; CSV is direct cost only. *(round 1, q.scope_vs_csv_total_reconciliation: scope includes markup/overhead/contingency/sub margins not in CSV)*

- Optional tankless water heater ($6,500 allowance) is OUT of contract; existing tank WH stays, extend vent through new roof only per scope L37. *(round 1, q.tankless_water_heater_option: OUT — existing tank WH stays, extend vent only)*

- Optional Closet & Cabinet System ($7,000 allowance) is OUT of contract; customer handling separately. *(round 1, q.closet_cabinet_system_option: OUT — customer handling separately)*

- Hall-bath acrylic shower swap ($1,000 allowance) is a customer-requested EARLY item; install Day 1 before main demo so family has working shower during construction. Rule 4V two-bucket pattern applies: early.acrylic_shower_swap lives in site_prep/customer_early_items; hall-bath window infill + drywall patch + repaint live separately in hall_bath_mod retrofit component. *(round 1, q.hall_bath_acrylic_shower_early_item: Yes — early item, swap Day 1 before demo)*

- Window count: plans are authoritative — 2 new windows (1 transom 3'×1' + 1 D.H. 3'×3') plus 2 existing windows relocated. Scope's "(4) windows including (3) 36"×60" and (1) transom" was inaccurate. *(round 1, q.window_count_discrepancy: Plans are correct — 2 new + 2 relocated existing)*

- Siding material: vinyl lap per scope. Elevations' "NEW LAP SIDING" label is consistent; material is vinyl lap siding to match existing. *(round 1, q.siding_material: Vinyl lap per scope)*

- Roof framing: trusses — emit procurement.trusses with 28–42 calendar-day lead time. Overrides belief stick_frame_default_for_small_additions. *(round 1, q.roof_framing_truss_or_stick: Trusses — emit procurement.trusses with 28–42 cal-d lead)*

- Septic direction: new septic tank + leach field likely (change order pending). Base schedule must include permit.tdec_septic with pre_construction_offset_working_days=30 per job_types/addition/rules/tdec_septic_permit_offset.md. Plumbing tie-in for new septic tank + leach field should be stubbed as a placeholder; full relocation scope addressed via change order. *(round 1, q.septic_grinder_direction: New septic tank + leach field likely — full relocation change order pending)*