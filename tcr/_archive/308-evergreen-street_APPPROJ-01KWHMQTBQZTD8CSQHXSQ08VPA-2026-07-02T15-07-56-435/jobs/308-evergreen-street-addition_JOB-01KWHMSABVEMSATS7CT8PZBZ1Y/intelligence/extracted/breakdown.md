---
generation_kind: intelligence_rebuild_v2
stage: extract_breakdown
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWHMQTBQZTD8CSQHXSQ08VPA/jobs/308-evergreen-street-addition_JOB-01KWHMSABVEMSATS7CT8PZBZ1Y/inputs/files/308_Evergreen_Addition.xlsx - Summary (1).csv.txt
  - _projects/308-evergreen-street_APPPROJ-01KWHMQTBQZTD8CSQHXSQ08VPA/jobs/308-evergreen-street-addition_JOB-01KWHMSABVEMSATS7CT8PZBZ1Y/inputs/scope.md
---

# Breakdown extraction — 308 Evergreen Addition

Source CSV: `308_Evergreen_Addition.xlsx - Summary (1).csv.txt`
Project: Simons Addition — 30'x10' Two-Story + Bedroom Remodel
Overall footprint: 789 SF · Ceiling height: 8'

**CSV Grand Total: $100,778.92** (Labor $45,167.59 · Material $52,171.33 · Equipment $3,440.00 · Labor Hours 1,287.00)

**Scope "Total Investment": $173,850** — gap of **~$73,071 (≈ 42%)** vs the CSV grand total. This triggers rule `scope_vs_csv_total_reconciliation` (≥5% gap → interview question required). See Notes.

---

## Trade totals

| # | Section (verbatim from CSV) | Labor $ | Material $ | Equipment $ | Section Total $ | Labor Hrs | Source |
|---|---|---:|---:|---:|---:|---:|---|
| 1 | General Conditions, Permitting & Pre-Construction | 2,316.08 | 2,130.00 | 0.00 | **4,446.08** | 56.00 | row 11 |
| 2 | Selective Demolition & Site Work | 1,982.00 | 2,040.00 | 220.00 | **4,242.00** | 56.00 | row 12 |
| 3 | Excavation, Foundation – Footings & Slab | 2,698.60 | 2,416.18 | 1,950.00 | **7,064.78** | 78.00 | row 13 |
| 4 | Structural Modifications – LVL Beam & Shoring | 2,117.80 | 2,422.00 | 0.00 | **4,539.80** | 60.00 | row 14 |
| 5 | Framing – Floor System, Walls & Elevator Shaft | 5,037.50 | 8,850.05 | 120.00 | **14,007.55** | 146.00 | row 15 |
| 6 | Roof Framing, Sheathing & Roofing System | 3,319.80 | 5,997.50 | 335.00 | **9,652.30** | 96.00 | row 16 |
| 7 | Exterior Finishes – Siding, Trim & Gutters | 2,474.70 | 2,696.61 | 560.00 | **5,731.31** | 72.00 | row 17 |
| 8 | Windows, Exterior Door & Weatherproofing | 1,493.80 | 2,172.00 | 0.00 | **3,665.80** | 44.00 | row 18 |
| 9 | Electrical – 100A Subpanel, Rough-In & Finish | 3,042.00 | 3,680.13 | 0.00 | **6,722.13** | 78.00 | row 19 |
| 10 | Plumbing – Rough-In, Master Bath & W/D Relocation | 1,356.80 | 2,160.00 | 0.00 | **3,516.80** | 40.00 | row 20 |
| 11 | HVAC – Mini Split, Tankless WH & Relocations | 1,363.36 | 5,140.00 | 0.00 | **6,503.36** | 36.00 | row 21 |
| 12 | Insulation & Air Sealing | 1,493.80 | 1,590.64 | 0.00 | **3,084.44** | 44.00 | row 22 |
| 13 | Drywall – New Addition & Existing Bedroom | 5,428.35 | 3,647.35 | 255.00 | **9,330.70** | 159.00 | row 23 |
| 14 | Interior Finish Carpentry, Painting & Flooring | 5,540.30 | 7,291.28 | 0.00 | **12,831.58** | 162.00 | row 24 |
| 15 | Master Bathroom – Custom Tile Shower & Finishes | 3,017.90 | 4,136.60 | 0.00 | **7,154.50** | 88.00 | row 25 |
| 16 | Existing Hall Bath Mod, Bedroom Remodel & Closeout | 2,484.80 | **-4,199.00** | 0.00 | **-1,714.20** | 72.00 | row 26 |
|   | **TOTALS** | **45,167.59** | **52,171.33** | **3,440.00** | **100,778.92** | **1,287.00** | row 27 |

### Trades by section-total ranking (descending)
1. Framing – Floor / Walls / Elevator shaft — $14,007.55 (146 hrs) — largest bucket
2. Interior Finish Carpentry, Painting & Flooring — $12,831.58 (162 hrs) — highest labor-hour section
3. Roof Framing / Sheathing / Roofing — $9,652.30 (96 hrs)
4. Drywall (Addition + Bedroom) — $9,330.70 (159 hrs) — 2nd-highest labor-hours
5. Master Bath tile shower — $7,154.50 (88 hrs)
6. Excavation & Foundation — $7,064.78 (78 hrs) — includes $1,950 equipment (backhoe/mini-ex)
7. Electrical (100A subpanel + rough + finish) — $6,722.13 (78 hrs)
8. HVAC (mini-split + tankless WH + relocations) — $6,503.36 (36 hrs) — high material ($5,140), low labor
9. Exterior Finishes – Siding / Trim / Gutters — $5,731.31 (72 hrs)
10. Structural Mods (LVL & shoring) — $4,539.80 (60 hrs)
11. General Conditions & Permitting — $4,446.08 (56 hrs)
12. Selective Demo & Site Work — $4,242.00 (56 hrs)
13. Windows, Exterior Door & Weatherproofing — $3,665.80 (44 hrs)
14. Plumbing – Rough / Master Bath / W/D Relocation — $3,516.80 (40 hrs) — see anomaly in Notes
15. Insulation & Air Sealing — $3,084.44 (44 hrs)
16. Existing Hall Bath Mod / Bedroom Remodel / Closeout — **-$1,714.20** (72 hrs) — credit row, see Notes

---

## Allowances

The CSV summary does NOT itemize allowances — they live in the scope (`inputs/scope.md`), presumably rolled into the section totals above. From scope for cross-reference:

**Material Allowance Schedule (from scope):**
- LVT Flooring: $3.00/sqft
- Windows: $300 each
- Interior Doors: $250 each
- Pocket Door Systems: $400 each
- Recessed Lights: $25 each (up to 18 fixtures)
- Vanity (72"): $1,000
- Faucets: $150 each
- Vanity Lights: $100 each
- Commode: $250
- Shower Valve & Trim: $250
- Tile (Walls): $3.00/sqft
- Tile (Floor Mosaic): $6.00/sqft
- Waterproofing/Setting Materials: $500
- Mirrors: $150 each
- Mini Split: $2,500
- Exterior Door: $500
- Guest Bath Shower system pan and walls: **$1,000** (hall bath acrylic swap allowance)

**Optional packages (NOT in CSV totals — separate line items in scope):**
- Closet & Cabinet System: $7,000 (labor + material)
- Tankless Water Heater: $6,500 (labor + material) — *but* CSV row 21 already includes "Tankless WH" in the section name and title says "Incl. Tankless WH Option," so this may be double-flagged. Interview question warranted.

---

## Silent omissions (scope items with NO clean matching CSV row)

Cross-referenced against `inputs/scope.md`. Items scoped but not clearly line-itemed:

1. **TDEC septic inspection / septic feasibility / grinder pump evaluation** — scope explicitly lists this in the "Pre-Construction & Design Phase" section and says costs of relocation / grinder are "not included and will be addressed via change order." No CSV row for it, but scope says the *evaluation* is in scope. Not visible in row 11 (General Conditions) breakdown. **Silent omission for pre-construction work.**

2. **Elevator shaft framing & 30A elevator circuit rough-in** — scope calls for framing a 4'x4' future elevator shaft AND a dedicated 120V/30A circuit run from subpanel. Row 15 name mentions "Elevator Shaft" (so framing is likely rolled in), but electrical row 19 makes no mention of the 30A elevator circuit. Likely rolled into rough-in total; verify.

3. **Interior doors (4 total: 1 pre-hung + 2 pocket door systems + implied balance)** — scope calls for 4 doors including 2 pocket doors. No dedicated CSV row; likely embedded in row 24 (Interior Finish Carpentry). Allowance is $250/$400 per unit per scope. Silent within row 24 lump sum.

4. **Waterproofing / shower niche / bench for master bath** — scope calls out shower niche, bench, waterproofing system. Rolled into row 25 lump; not itemized.

5. **Extended gas water heater vent through new roof** — scope explicitly requires extending EXISTING gas WH vent through new roof. This is a plumbing/roofing action but no dedicated line. Likely rolled into row 16 (roofing) or row 20 (plumbing). **Note: this signals existing WH stays — see rule 4H — despite CSV row 21 mentioning tankless WH; potential scope-CSV conflict.**

6. **Relocated existing heat pump & electrical disconnect (pre-demo)** — scope calls for these before demo. Likely embedded in row 12 (Selective Demo & Site Work) at $220 equipment + labor; not itemized separately.

7. **Relocation of (1) existing hallway switch including drywall patch + prime + paint** — small scope item. Absorbed into row 19 (electrical) or row 23 (drywall) lump.

8. **Hall bath acrylic shower swap allowance ($1,000)** — scope lists this as an existing hall bath modification. Row 26 has a NEGATIVE material total (-$4,199) — the acrylic swap credit is embedded in the row-26 net. Not a silent omission but obscured; see Notes.

9. **French drains / foundation waterproofing / drainage** — scope EXPLICITLY excludes these. Correctly absent from CSV. Not an omission, just noting the alignment.

10. **101 Mobility coordination for elevator company** — scope says will coordinate if homeowner requests. Not in CSV, and likely not billable — informational only.

11. **Concrete floor finish in basement storage** — scope says "concrete floor remains unfinished." Correctly no CSV line for basement floor finish. Not an omission.

12. **Weekly invoicing / $20,000 deposit / debris removal rate ($450/removal) / backhoe rate ($1,100/wk)** — these are billing terms + rate cards, not scope work. Correctly not in CSV; noted for completeness.

---

## Notes (anomalies, negative rows, credits)

### 1. Scope-total vs CSV-total mismatch — MANDATORY interview question
**Scope "Total Investment": $173,850.** **CSV Grand Total: $100,778.92.** **Delta: $73,071.08 (≈42%).** This vastly exceeds the 5% threshold in `_company/rules/scope_vs_csv_total_reconciliation.md`. Per that rule, `intelligence/questions.md` MUST emit `q.scope_vs_csv_total_reconciliation` and `manifest.json` MUST set `interview_status: needs_more`. Downstream stages cannot silently proceed.

Possible explanations to surface for PM:
- Scope total includes overhead / margin / contingency / soft costs not itemized in the section CSV
- Scope total includes both optional packages (Closet $7,000 + Tankless WH $6,500 = $13,500) plus a much larger markup
- CSV is missing sections
- Scope figure is a customer-facing "sticker" price; CSV is internal cost
- Arithmetic error somewhere

### 2. Row 26 has a NEGATIVE material cost (-$4,199.00) → NEGATIVE section total (-$1,714.20)
`(row 26: "Existing Hall Bath Mod, Bedroom Remodel & Closeout — Labor $2,484.80 / Material -$4,199.00 / Section Total -$1,714.20 / 72.00 hrs")`

Per `_company/rules/dev_rules.md` §12: negative `section_total` with `labor_hours ≤ 24` is a credit; with `labor_hours > 24` (this row: 72 hrs) is "probable scope ambiguity — surface for human resolution." This row combines THREE distinct activity types (hall bath modification, primary bedroom remodel, project closeout) with 72 labor hours, which is legitimate work, but the -$4,199 material figure suggests either:
- A returned-material / credit line (e.g. tub/shower combo removed with reusable value credited back)
- A "subtract from prior bid" reconciliation
- A material-cost offset from the demo credit for the tub/shower combo removal

Emit a warning; needs PM confirmation. This also collides with the customer's "acrylic shower swap ($1,000 allowance)" scoped in this section — a POSITIVE $1,000 line item sitting inside a section with -$4,199 material net.

### 3. Row 21 HVAC labor is unusually low relative to material
`(row 21: "HVAC – Mini Split, Tankless WH & Relocations — Labor $1,363.36 / Material $5,140.00 / 36.00 hrs")`

36 labor hours for mini-split rough (0.5d × 1) + mini-split install (1d × 1) + tankless WH set + existing heat pump / vent relocation feels tight if tankless WH IS included, but reasonable if only mini-split is in scope. Row title says "Tankless WH" but scope treats tankless as an OPTIONAL PACKAGE ($6,500 allowance) — potential double-count risk. **Interview: is tankless WH IN the base scope (rolled into row 21) or only in the optional add-on?**

### 4. Row 20 Plumbing total ($3,516.80 / 40 hrs) is low for a master-bath + W/D relocation job
`(row 20: "Plumbing – Rough-In, Master Bath & W/D Relocation — Labor $1,356.80 / Material $2,160.00 / 40 hrs")`

Per `_company/rules/editor_rules.md`, plumbing rough for master bath + W/D relocation is default 4 working days × 2 crew = 64 hours labor alone, before finishes. 40 total hours (which must cover rough + finish + tank set if applicable + W/D drain/vent) is thin. Rule `plumbing_rough_min_duration` sets a 4d×2 hard floor. Flag for PM: labor may be under-budgeted, or fixture materials are being sub'd out with labor absorbed elsewhere.

### 5. No line item for LVL beam procurement / long-lead items
`(row 14: "Structural Modifications – LVL Beam & Shoring — $4,539.80 / 60 hrs")` combines LVL + shoring as one lump. Per editor rules, the LVL is a 7-21 calendar day lead-time item requiring the 3-task procurement pattern. The CSV summary doesn't (and needn't) itemize procurement; this is a task-graph concern, not a CSV concern. Noting for stage-B/C awareness.

### 6. Row 16 title conflict with existing WH vent
`(row 16: "Roof Framing, Sheathing & Roofing System — $9,652.30 / 96 hrs")` — scope explicitly requires "Extend existing gas water heater vent through new roof system per code requirements." This aligns with the SCOPE'S signal that the existing (gas) WH remains — which conflicts with the CSV title on row 21 mentioning "Tankless WH." The tankless option is a scope ADD-ON, not baseline. This is important for Rule 4H (tank-set sequencing) in task-graph stage: baseline = existing WH stays, no `plumbing.tank_set` needed.

### 7. Row 6 Roofing lump ($9,652.30) includes multiple deliverables
Row 16 combines roof framing + sheathing + shingles + underlayment + fascia/soffit/gutters + tie-in to existing 6/12 roof. This is a healthy total for 300+ sqft addition roof, but the tie-in (3/12 addition into existing 6/12) is a KNOWN discovery risk not visible in the number.

### 8. Row 11 General Conditions ($4,446.08 / 56 hrs) is where permit + selections + walkthrough live
Not an anomaly, but noting for stage-B: permits ($4,446 for 56 hrs of GC work) covers permit walk-in + PM coordination + selections work. Per Rule 4A, permit itself is a 1-day work task, so the 56 hours span the pre-con management window, not just the permit itself.

### 9. Arithmetic sanity check (CSV totals row)
Labor: 45,167.59 · Material: 52,171.33 · Equipment: 3,440.00 · Sum: **100,778.92** ✓ matches Grand Total row.
Labor hours sum: 56+56+78+60+146+96+72+44+78+40+36+44+159+162+88+72 = **1,287** ✓ matches TOTALS row 27.

The internal arithmetic is consistent. The mismatch is scope-total vs CSV-total, not intra-CSV.
