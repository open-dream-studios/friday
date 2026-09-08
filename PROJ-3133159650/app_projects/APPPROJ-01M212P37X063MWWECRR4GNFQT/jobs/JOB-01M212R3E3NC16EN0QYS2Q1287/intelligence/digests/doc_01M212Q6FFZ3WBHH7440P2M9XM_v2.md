---
document_id: doc_01M212Q6FFZ3WBHH7440P2M9XM
version: 2
name: 308_Evergreen_Addition_Breakdown.csv
role: breakdown
content_sha: c936d98fafac090e05c29bef7398fa04614394c69cf5793fb284d2147ae64d6f
brief_sha: 838666d1aa30
analyzed_at: 2026-09-08T18:05:37.853Z
analysis_ms: 130262
pipeline_version: 1
page_count: 1
---

## Digest

308_Evergreen_Addition_Breakdown.csv is a single-page, single-table INTERNAL COST BREAKDOWN spreadsheet (no author/date/revision), titled "Two-Story Addition + Bedroom Remodel – Cost Breakdown (Incl. Tankless WH Option)" for "Simons Addition – 30'x10' Two-Story + Bedroom Remodel." It cites Source Scope "Simons_Addition_Scope_v2.txt" (a name/version not matching the reviewed anchor "308 Evergreens Scope" document) and Template Anchor "Basement_Remodel_Breakdown_Locked_Template_v1.xlsx" — i.e., a locked template originally built for a basement-remodel job type is being reused for this two-story-addition project, which is a risk factor for missing or mismatched line items. Header fields: Overall Footprint SF = 789 (does not cleanly reconcile with the scope's stated ~30'x10'=300 sqft addition footprint); Ceiling Height = 8 (ft, unit implied).

Totals: Labor Cost $45,167.59; Material Cost $52,171.33; Equipment Cost $3,440.00; Grand Total $100,778.92; Total Labor Hours 1,287.00. These roll up arithmetically consistently from the 16 section rows (verified by summation). This Grand Total is dramatically lower than the anchor scope's stated "Total Investment $173,850" (~$73k / 42% gap), unreconciled — could reflect a cost-basis figure vs a marked-up customer price, but no markup logic is stated in this document.

16 cost sections (Labor/Material/Equipment/Total/Hours): (1) General Conditions, Permitting & Pre-Construction — $4,446.08 / 56 hrs; (2) Selective Demolition & Site Work — $4,242.00 / 56 hrs; (3) Excavation, Foundation – Footings & Slab — $7,064.78 / 78 hrs; (4) Structural Modifications – LVL Beam & Shoring — $4,539.80 / 60 hrs; (5) Framing – Floor System, Walls & Elevator Shaft — $14,007.55 / 146 hrs; (6) Roof Framing, Sheathing & Roofing System — $9,652.30 / 96 hrs; (7) Exterior Finishes – Siding, Trim & Gutters — $5,731.31 / 72 hrs; (8) Windows, Exterior Door & Weatherproofing — $3,665.80 / 44 hrs; (9) Electrical – 100A Subpanel, Rough-In & Finish — $6,722.13 / 78 hrs; (10) Plumbing – Rough-In, Master Bath & W/D Relocation — $3,516.80 / 40 hrs; (11) HVAC – Mini Split, Tankless WH & Relocations — $6,503.36 / 36 hrs (bundles the scope's OPTIONAL $6,500 tankless-WH package into base HVAC cost, contrary to the scope treating it as a separately priced add-on); (12) Insulation & Air Sealing — $3,084.44 / 44 hrs; (13) Drywall – New Addition & Existing Bedroom — $9,330.70 / 159 hrs; (14) Interior Finish Carpentry, Painting & Flooring — $12,831.58 / 162 hrs; (15) Master Bathroom – Custom Tile Shower & Finishes — $7,154.50 / 88 hrs; (16) Existing Hall Bath Mod, Bedroom Remodel & Closeout — NEGATIVE total -$1,714.20 (Labor $2,484.80, Material -$4,199.00, Equipment $0, 72 hrs) — an unexplained negative material cost anomaly that drags this section's total below zero.

No line items exist for: the scope's optional $7,000 closet/cabinet organization system, countertops, carpet/floating floor, shower glass enclosure, concrete/patio/landscaping, roof trusses (distinct from rafters), stair construction (despite the addition spanning basement to second floor), or discrete permit sub-types (TDEC septic, electrical-service, mechanical) — all consistent with their absence/deferral in the anchor scope, EXCEPT the closet organization system and stairs, which are plausible gaps. No material brands/SKUs/specs, no site-access constraints, no owner/contractor responsibility assignments, and no calendar dates/milestones appear anywhere — the only schedule-adjacent data is per-section labor-hour totals (1,287 hrs total).

## Brief findings

- [doc_identity] found: 'Two-Story Addition + Bedroom Remodel – Cost Breakdown (Incl. Tankless WH Option)' / Project: 'Simons Addition – 30'x10' Two-Story + Bedroom Remodel' / Source Scope: 'Simons_Addition_Scope_v2.txt' / Template Anchor: 'Basement_Remodel_Breakdown_Locked_Template_v1.xlsx'. No author, date, or revision number given anywhere. (pp 1)
- [scope_inclusions] found: 16 costed sections: General Conditions/Permitting/Pre-Construction; Selective Demolition & Site Work; Excavation/Foundation Footings & Slab; Structural Modifications LVL Beam & Shoring; Framing Floor System/Walls & Elevator Shaft; Roof Framing/Sheathing/Roofing; Exterior Finishes Siding/Trim/Gutters; Windows/Exterior Door/Weatherproofing; Electrical 100A Subpanel Rough-In & Finish; Plumbing Rough-In/Master Bath/W-D Relocation; HVAC Mini Split/Tankless WH/Relocations; Insulation & Air Sealing; Drywall New Addition & Existing Bedroom; Interior Finish Carpentry/Painting/Flooring; Master Bathroom Custom Tile Shower & Finishes; Existing Hall Bath Mod/Bedroom Remodel & Closeout. (pp 1)
- [scope_exclusions] found: No explicit exclusions list, but the title 'Cost Breakdown (Incl. Tankless WH Option)' and the line 'HVAC – Mini Split, Tankless WH & Relocations' $6,503.36 show the optional tankless water heater package is folded into base cost here rather than kept as a separate optional line — the document gives no separate/deferred pricing the way the anchor scope does. (pp 1)
- [dimensions_areas] contradicts_known: Breakdown states 'Overall Footprint SF, 789' and 'Ceiling Height, 8'. The anchor scope describes the addition as a '~30'x10' footprint' (=300 sqft), so a stated 789 sqft footprint does not reconcile with the scope's own footprint dimension (789 would only approach 3 stacked 300-sqft levels, ~900 sqft, and even that doesn't match exactly). (pp 1)
- [structural] found: 'Excavation, Foundation – Footings & Slab' $7,064.78; 'Structural Modifications – LVL Beam & Shoring' $4,539.80; 'Framing – Floor System, Walls & Elevator Shaft' $14,007.55; 'Roof Framing, Sheathing & Roofing System' $9,652.30 — consistent with the scope's footings/slab, 3-ply 14" LVL beam with shoring, elevator shaft framing, and new gable roof tie-in. (pp 1)
- [existing_conditions] found: 'Selective Demolition & Site Work' $4,242.00 and 'Existing Hall Bath Mod, Bedroom Remodel & Closeout' -$1,714.20 (Material Cost -$4,199.00) — the latter is a negative section total, an anomaly not explained in the document. (pp 1)
- [materials_finishes] not_found: Only cost-category labels are given (e.g., 'Master Bathroom – Custom Tile Shower & Finishes', 'Interior Finish Carpentry, Painting & Flooring'); no brands, SKUs, species, grades, or colors are specified anywhere in the document. (pp 1)
- [site_access] not_found: not addressed in this document (pp 1)
- [permits_inspections] found: 'General Conditions, Permitting & Pre-Construction' $2,316.08 labor / $2,130.00 material / $4,446.08 total, 56 labor hours — cost is bucketed but no permit types, code citations, or inspection line items are itemized. (pp 1)
- [schedule_dates] found: Per-section 'Labor Hours' column totals 1,287.00 hours (e.g., 56, 56, 78, 60, 146, 96, 72, 44, 78, 40, 36, 44, 159, 162, 88, 72) — this is the only duration-related data; no calendar start/completion dates, deadlines, or milestones appear anywhere. (pp 1)
- [money] contradicts_known: Breakdown 'Grand Total' is '$100,778.92' (Labor $45,167.59 + Material $52,171.33 + Equipment $3,440.00). The anchor scope states 'Total Investment $173,850' — the two documents' bottom-line totals differ by roughly $73,071 (breakdown total is ~58% of the scope's stated price), which is unreconciled in either document (could reflect cost-vs-price/markup, but that relationship is not stated). (pp 1)
- [responsibilities] not_found: not addressed in this document (pp 1)
- [revisions_conflicts] found: Internal conflicts within this document: (1) 'Existing Hall Bath Mod, Bedroom Remodel & Closeout' has Material Cost '-$4199.00' producing a negative Section Total '-$1714.20', unexplained; (2) 'Source Scope' is listed as 'Simons_Addition_Scope_v2.txt', a filename/version not matching the anchor '308 Evergreens Scope' document reviewed elsewhere, leaving it unclear whether this breakdown was priced against the same scope revision; (3) 'Overall Footprint SF' of 789 does not cleanly reconcile with the scope's stated 30'x10' footprint. (pp 1)
- [phase_procurement] found: Cost sections give FOR evidence for: proc_foundation_package ('Excavation, Foundation – Footings & Slab' $7,064.78), proc_windows_doors ('Windows, Exterior Door & Weatherproofing' $3,665.80), proc_lvl ('Structural Modifications – LVL Beam & Shoring' $4,539.80), proc_framing_package ('Framing – Floor System, Walls & Elevator Shaft' $14,007.55), proc_subpanel ('Electrical – 100A Subpanel, Rough-In & Finish' $6,722.13), proc_hvac_equipment (mini-split/tankless in 'HVAC – Mini Split, Tankless WH & Relocations' $6,503.36 — note this bundles the tankless WH, normally an option, into base HVAC), proc_electrical_package (same electrical line), proc_water_heater (same HVAC line explicitly names 'Tankless WH'), proc_plumbing_package ('Plumbing – Rough-In, Master Bath & W/D Relocation' $3,516.80), proc_tile ('Master Bathroom – Custom Tile Shower & Finishes' $7,154.50), proc_hard_flooring (flooring bundled in 'Interior Finish Carpentry, Painting & Flooring' $12,831.58), proc_insulation ('Insulation & Air Sealing' $3,084.44), proc_drywall ('Drywall – New Addition & Existing Bedroom' $9,330.70), proc_paint (bundled in same carpentry/painting/flooring line), proc_doors_trim (same line), proc_plumbing_fixtures (Master Bath line + Plumbing line), proc_light_fixtures (Electrical line). AGAINST/absent: proc_trusses (no distinct truss line — 'Roof Framing' line doesn't specify truss vs rafter, consistent with scope's undetermined framing method), proc_cabinets, proc_countertops, proc_carpet, proc_shower_glass, proc_concrete_patio (none of these appear as line items anywhere). (pp 1)
- [phase_permits] found: 'General Conditions, Permitting & Pre-Construction' $4,446.08 covers permit_building generically. No line item or cost for permit_tdec_septic, permit_electrical_service, permit_plumbing, or permit_mechanical individually — consistent with scope's septic being deferred/excluded and subpanel (not service upgrade) not needing separate electrical-service permit. (pp 1)
- [phase_retrofit] found: 'Existing Hall Bath Mod, Bedroom Remodel & Closeout' -$1,714.20 (72 labor hours) bundles retrofit_demo, retrofit_rough_meps, and closeout into one line with an anomalous negative total — no separate utility_relocations or retrofit_drywall/retrofit_finishes line items are broken out. (pp 1)
- [phase_demolition] found: 'Selective Demolition & Site Work' $1,982.00 labor / $2,040.00 material / $220.00 equipment / $4,242.00 total, 56 hours. (pp 1)
- [phase_site_foundation] found: 'Excavation, Foundation – Footings & Slab' $2,698.60 labor / $2,416.18 material / $1,950.00 equipment / $7,064.78 total, 78 hours. (pp 1)
- [phase_framing_shell] found: 'Framing – Floor System, Walls & Elevator Shaft' $14,007.55 (146 hrs) and 'Windows, Exterior Door & Weatherproofing' $3,665.80 (44 hrs). No deck_build line appears, consistent with no deck in scope. (pp 1)
- [phase_exterior_finishes] found: 'Roof Framing, Sheathing & Roofing System' $9,652.30 (96 hrs) and 'Exterior Finishes – Siding, Trim & Gutters' $5,731.31 (72 hrs). No distinct appliance_vent_extension line item for the existing water heater vent extension. (pp 1)
- [phase_rough_trades] found: 'Electrical – 100A Subpanel, Rough-In & Finish' $6,722.13 (78 hrs); 'Plumbing – Rough-In, Master Bath & W/D Relocation' $3,516.80 (40 hrs); 'HVAC – Mini Split, Tankless WH & Relocations' $6,503.36 (36 hrs). (pp 1)
- [phase_rough_inspections] not_found: not addressed in this document (pp 1)
- [phase_insulation_drywall] found: 'Insulation & Air Sealing' $3,084.44 (44 hrs) and 'Drywall – New Addition & Existing Bedroom' $9,330.70 (159 hrs). No separately labeled 'paint_phase_1' or 'insulation_inspection' line — paint appears combined with later interior finish carpentry line instead. (pp 1)
- [phase_interior_finishes] found: 'Interior Finish Carpentry, Painting & Flooring' $12,831.58 (162 hrs) and 'Master Bathroom – Custom Tile Shower & Finishes' $7,154.50 (88 hrs). No cabinets_counters, carpet_floating, or stair_build line items appear anywhere, despite the addition spanning basement-to-second-floor. (pp 1)
- [phase_concrete_landscaping] not_found: not addressed in this document — no concrete_flatwork or landscaping line items appear, consistent with the scope's silence on patio/landscaping. (pp 1)
- [phase_closeout] found: Closeout is bundled into 'Existing Hall Bath Mod, Bedroom Remodel & Closeout' -$1,714.20 rather than broken out as its own line; no separate customer_walkthrough or final_inspections cost appears. (pp 1)
- [procurement_signals] not_found: The document allocates dollar costs and labor hours per category but gives no lead-time, spec/size, selection status, or supplier information for any item (foundation, windows, LVL, trusses, subpanel, HVAC equipment, water heater, tile, flooring, cabinets, countertops, paint, doors/trim, fixtures, or concrete). (pp 1)

## Cross-page notes

- Single-page document; 'cross-page' notes below are cross-document observations against the anchor scope and company canon.
- MAJOR MONEY GAP: breakdown Grand Total $100,778.92 vs anchor scope 'Total Investment $173,850' — a ~$73,071 (42%) discrepancy that neither document explains (possible cost-vs-price/markup relationship, but unstated).
- SOURCE MISMATCH: this breakdown's 'Source Scope' field says 'Simons_Addition_Scope_v2.txt' while the reviewed anchor document is titled '308 Evergreens Scope' with no version marker — cannot confirm both describe the identical, current scope revision.
- TEMPLATE MISMATCH RISK: 'Template Anchor' is 'Basement_Remodel_Breakdown_Locked_Template_v1.xlsx' reused for a two-story addition job — raises risk that category structure omits addition-specific items (e.g., no explicit line for TDEC septic evaluation, elevator-shaft rough electrical circuit, or stairs).
- DIMENSION MISMATCH: 'Overall Footprint SF' = 789 does not cleanly match the scope's stated ~30'x10' (300 sqft) addition footprint, even accounting for basement + 2 stories (~900 sqft expected, not 789).
- INTERNAL ANOMALY: 'Existing Hall Bath Mod, Bedroom Remodel & Closeout' section has a negative Material Cost (-$4,199.00) producing a negative Section Total (-$1,714.20) — undocumented and unexplained; likely a template artifact or data-entry error rather than an intentional credit.
- OPTIONAL-VS-BASE CONFLICT: the scope prices the tankless water heater as a separate $6,500 OPTIONAL package ('utility upgrades not included'), but this breakdown's title explicitly says '(Incl. Tankless WH Option)' and folds tankless-WH cost into the base 'HVAC – Mini Split, Tankless WH & Relocations' line — meaning this particular breakdown assumes the option was accepted, without stating so plainly.
- PROMISED-BUT-ABSENT CONTENT: the scope's $7,000 optional closet/cabinet organization package and any stair-construction cost (needed given the basement-to-second-floor span) are not represented anywhere in this cost breakdown.

## Extracted content

[p1 | table] Two-Story Addition + Bedroom Remodel – Cost Breakdown (Incl. Tankless WH Option),,,,,,,,,Project Totals,
,,,,,,,,,Labor Cost,"$45,167.59"
Project,Simons Addition – 30'x10' Two-Story + Bedroom Remodel,,,,,,,,Material Cost,"$52,171.33"
Source Scope,Simons_Addition_Scope_v2.txt,,,,,,,,Equipment Cost,"$3,440.00"
Template Anchor,Basement_Remodel_Breakdown_Locked_Template_v1.xlsx,,,,,,,,Grand Total,"$100,778.92"
Overall Footprint SF,789,,,,,,,,,
Ceiling Height,8,,,,,,,,,
Note,"Use this workbook as a locked template. Populate detail rows only; preserve formulas, tabs, and section order.",,,,,,,,,
,,,,,,,,,,
Section,Labor Cost,Material Cost,Equipment Cost,Section Total,Labor Hours,,,,,
"General Conditions, Permitting & Pre-Construction",$2316.08,$2130.00,$0.00,$4446.08,56.00,,,,,
Selective Demolition & Site Work,$1982.00,$2040.00,$220.00,$4242.00,56.00,,,,,
"Excavation, Foundation – Footings & Slab",$2698.60,$2416.18,$1950.00,$7064.78,78.00,,,,,
Structural Modifications – LVL Beam & Shoring,$2117.80,$2422.00,$0.00,$4539.80,60.00,,,,,
"Framing – Floor System, Walls & Elevator Shaft",$5037.50,$8850.05,$120.00,$14007.55,146.00,,,,,
"Roof Framing, Sheathing & Roofing System",$3319.80,$5997.50,$335.00,$9652.30,96.00,,,,,
"Exterior Finishes – Siding, Trim & Gutters",$2474.70,$2696.61,$560.00,$5731.31,72.00,,,,,
"Windows, Exterior Door & Weatherproofing",$1493.80,$2172.00,$0.00,$3665.80,44.00,,,,,
"Electrical – 100A Subpanel, Rough-In & Finish",$3042.00,$3680.13,$0.00,$6722.13,78.00,,,,,
"Plumbing – Rough-In, Master Bath & W/D Relocation",$1356.80,$2160.00,$0.00,$3516.80,40.00,,,,,
"HVAC – Mini Split, Tankless WH & Relocations",$1363.36,$5140.00,$0.00,$6503.36,36.00,,,,,
Insulation & Air Sealing,$1493.80,$1590.64,$0.00,$3084.44,44.00,,,,,
Drywall – New Addition & Existing Bedroom,$5428.35,$3647.35,$255.00,$9330.70,159.00,,,,,
"Interior Finish Carpentry, Painting & Flooring",$5540.30,$7291.28,$0.00,$12831.58,162.00,,,,,
Master Bathroom – Custom Tile Shower & Finishes,$3017.90,$4136.60,$0.00,$7154.50,88.00,,,,,
"Existing Hall Bath Mod, Bedroom Remodel & Closeout",$2484.80,-$4199.00,$0.00,-$1714.20,72.00,,,,,
TOTALS,"$45,167.59","$52,171.33","$3,440.00","$100,778.92","1,287.00",,,,,
