---
generation_kind: pm_interview
session_at: 2026-07-01T18:09:01.881Z
based_on: _projects/308-evergreen-street_APPPROJ-01KWFCFSFZDJ01ZGRTNF78GYHC/jobs/308-evergreen-street-addition_JOB-01KWFCGKXVEGGGJZV1JB762C1C/intelligence/questions.md
round_at_save: 1
last_verified_at: 2026-07-01T18:09:01.881Z
---

# PM Interview · Round 1 · 2026-07-01

## q.scope_vs_csv_total_reconciliation
**Question:** The scope quotes a Total Investment of $173,850 but the CSV grand total is $100,778.92 — a gap of $73,071 (~42%). How should we treat this?
**Answer:** Scope figure includes markup / overhead / contingency / sub margins not in CSV — CSV is direct cost only

## q.tankless_water_heater_option
**Question:** Is the optional tankless water heater ($6,500 allowance) IN or OUT of this contract? CSV row 21 title says "Mini Split, Tankless WH & Relocations" but the $6,503 section total can't cover both plus the relocations.
**Answer:** OUT — existing tank WH stays, extend vent only per scope L37

## q.closet_cabinet_system_option
**Question:** Is the optional Closet & Cabinet System ($7,000 allowance) IN or OUT of this contract?
**Answer:** OUT — customer handling separately

## q.hall_bath_acrylic_shower_early_item
**Question:** Is the hall-bath acrylic shower swap ($1,000 allowance) a customer-requested EARLY item — done Day 1 before main demo so the family has a working shower during construction?
**Answer:** Yes — early item, swap Day 1 before demo (customer needs working shower)

## q.window_count_discrepancy
**Question:** Scope says "(4) windows including (3) 36"×60" and (1) transom." Plans schedule shows only **2 new windows** (a 3'×3' D.H. and a 3'×1' transom) plus **2 existing windows relocated**. Which is authoritative?
**Answer:** Plans are correct — 2 new (transom + 3'×3' DH) + 2 relocated existing

## q.siding_material
**Question:** Scope says "**vinyl siding** to match existing as closely as possible." Elevations label the new siding as "**NEW LAP SIDING**." What is the actual siding material?
**Answer:** Vinyl lap (per scope)

## q.roof_framing_truss_or_stick
**Question:** Scope says "truss or rafter framed — determined during design phase." Given 590 sqft new footprint, multi-valley tie-in to existing 6/12, and existing chimney to work around, we default to **stick-frame** (per belief `stick_frame_default_for_small_additions`) with no truss procurement. Confirm?
**Answer:** Stick-frame (default) — no `procurement.trusses`

## q.septic_grinder_direction
**Question:** Scope defers septic relocation / new septic tank / grinder pump to change order but calls out TDEC septic coordination + feasibility. Which direction do we plan against for the base schedule?
**Answer:** Grinder pump likely — connect to sewer line (change order pending)
