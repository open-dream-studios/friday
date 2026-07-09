---
generation_kind: intelligence_rebuild_v2
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWDVJA38HVW0W2JZ62XGQ7R8/jobs/308-evergreen-street-addition_JOB-01KWDVKJ8422ZNMTB2WJ7WYV9W/inputs/files/308_Evergreen_Addition.xlsx - Summary (1).csv.txt
---
# Extracted — breakdown.csv

**Source note:** The CSV template title reads "Two-Story Addition + Bedroom Remodel – Cost Breakdown (Incl. Tankless WH Option)" — the source scope reference in the CSV is `Simons_Addition_Scope_v2.txt`. The CSV also names the project "Simons Addition – 30'×10' Two-Story + Bedroom Remodel", implying the customer surname is Simons and the site address is 308 Evergreen Street. This is a bookkeeping mismatch with the scope filename ("308 Evergreens Scope") — flagged for confirmation.

## Project totals (CSV rows 1-5)

- Labor Cost: $45,167.59
- Material Cost: $52,171.33
- Equipment Cost: $3,440.00
- **Grand Total: $100,778.92**
- Overall footprint: **789 sqft**
- Ceiling height: 8'
- Total labor hours: **1,287.00**

Note: CSV Grand Total ($100,778.92) is materially lower than scope's "Total Investment: $173,850" — the scope's $173,850 is the customer-facing quote number; the CSV is TCR's internal cost breakdown. Delta = $73,071 (margin + overhead + optional packages if included).

## Trade totals — by section

| Section                                            | Labor    | Material   | Equip.  | Section total | Labor hrs |
|----------------------------------------------------|---------:|-----------:|--------:|--------------:|----------:|
| General Conditions, Permitting & Pre-Construction  | $2,316   | $2,130     | $0      | $4,446        | 56        |
| Selective Demolition & Site Work                   | $1,982   | $2,040     | $220    | $4,242        | 56        |
| Excavation, Foundation – Footings & Slab           | $2,699   | $2,416     | $1,950  | $7,065        | 78        |
| Structural Mods – LVL Beam & Shoring               | $2,118   | $2,422     | $0      | $4,540        | 60        |
| Framing – Floor System, Walls & Elevator Shaft     | $5,038   | $8,850     | $120    | $14,008       | 146       |
| Roof Framing, Sheathing & Roofing System           | $3,320   | $5,998     | $335    | $9,652        | 96        |
| Exterior Finishes – Siding, Trim & Gutters         | $2,475   | $2,697     | $560    | $5,731        | 72        |
| Windows, Exterior Door & Weatherproofing           | $1,494   | $2,172     | $0      | $3,666        | 44        |
| Electrical – 100A Subpanel, Rough-In & Finish      | $3,042   | $3,680     | $0      | $6,722        | 78        |
| Plumbing – Rough-In, Master Bath & W/D Relocation  | $1,357   | $2,160     | $0      | $3,517        | 40        |
| HVAC – Mini Split, Tankless WH & Relocations       | $1,363   | $5,140     | $0      | $6,503        | 36        |
| Insulation & Air Sealing                           | $1,494   | $1,591     | $0      | $3,084        | 44        |
| Drywall – New Addition & Existing Bedroom          | $5,428   | $3,647     | $255    | $9,331        | 159       |
| Interior Finish Carpentry, Painting & Flooring     | $5,540   | $7,291     | $0      | $12,832       | 162       |
| Master Bathroom – Custom Tile Shower & Finishes    | $3,018   | $4,137     | $0      | $7,155        | 88        |
| Existing Hall Bath Mod, Bedroom Remodel & Closeout | $2,485   | **-$4,199** | $0     | **-$1,714**   | 72        |

## Allowances embedded in scope

- LVT flooring: $3/sqft
- Windows: $300 each
- Interior doors: $250 each; pocket door systems: $400 each
- Recessed lights: $25 each (up to 18)
- Vanity (72"): $1,000
- Faucets: $150 each; vanity lights: $100 each; commode: $250; shower valve + trim: $250
- Wall tile: $3/sqft; floor mosaic tile: $6/sqft
- Waterproofing/setting materials: $500
- Mirrors: $150 each; mini-split: $2,500
- Exterior door: $500
- Guest (hall) bath acrylic pan + walls: $1,000
- **Optional — Closet & cabinet system: $7,000** (labor + materials)
- **Optional — Tankless WH: $6,500** (labor + materials)

## Silent omissions (in scope but not called out in CSV as separate lines)

- **Grinder pump / septic relocation** — scope excludes these as change orders; correctly absent from CSV.
- **Elevator system** — framing + 30A rough only; system NOT in CSV (correctly excluded per scope).
- **TDEC septic inspection fees** — $500 permit fee mentioned in TCR playbook is not itemized in CSV; likely folded into general conditions or absorbed as owner-paid.
- **Concealed roof tie-in change-order allowance** — no line item; scope handles via CO clause.
- **Amperage verification of existing main service** — scope assumes existing service can support the subpanel (scope.md L120); no CSV line and no verification-task line.

## Notes / anomalies

- **HVAC section labeled "Mini Split, Tankless WH & Relocations"** with $5,140 material vs. mini-split $2,500 + tankless allowance $6,500 = $9,000. HVAC section material is $5,140 total — CSV appears to include the mini-split ($2,500) + heat pump relocation materials + possibly a tank swap but NOT the full $6,500 optional tankless allowance. Read as: **tankless is likely IN the current breakdown but at a reduced pass-through cost, or the "Incl. Tankless WH Option" in the CSV title reflects the scope base assumption while the optional allowance is separately quoted.** Ambiguous — flag for PM.
- **"Existing Hall Bath Mod, Bedroom Remodel & Closeout" section total is NEGATIVE ($1,714)** with material at **-$4,199**. This is a credit or a "subtract from prior bid" line — consistent with scope's $1,000 hall-bath acrylic allowance netting against the existing bathroom's demoed value or against another bundled line. Rule 12 in dev_rules: with `section_total < 0` AND `labor_hours ≤ 24`, emit 1-2 closeout tasks; **here labor_hours = 72**, so this is NOT a small credit — the section is materially staffed (~72 hrs) despite the negative material total. Interpret as: retrofit labor is real (hall bath + bedroom remodel + closeout activities), material is offset by allowance drawdown from primary scope. Do NOT skip decomposition.
- **Drywall labor hours = 159** with the section titled "New Addition & Existing Bedroom" — retrofit drywall consolidates into main drywall block per Rule 4E and addition_rules. The 159 hrs already includes both.
- **Framing labor hours = 146**, includes floor system, walls, AND elevator shaft framing — elevator shaft is inside the addition footprint (see plans).
- **Plumbing labor = only 40 hrs** — light for a job with master bath (2 lavs + toilet + custom shower) + W/D relocation + vent stacks through roof. Per Rule 4H / Will's nominal, `plumbing.rough_in` defaults to 4 working days × 2 crew = 64 hrs; 40 hrs at 2 crew = 2.5 working days. Interpret as the labor number understates real duration — apply Will's nominal floor of 4 working days × 2 crew per editor rules.
- **HVAC labor = 36 hrs** — with mini-split + tankless (if included) + heat pump relocation + existing HVAC component relocations. Mini-split install is 1d × 1 person = 8 hrs; heat pump relocation 1d × 2 = 16 hrs; balance for tank set / vent extension + finish HVAC. Plausible.
- **Roof section labor = 96 hrs** at 3-crew standard is ~4 working days across framing + sheathing + underlayment + shingles + gutters. Reasonable for a ~300 sqft roof addition with tie-in complexity.
- **Interior Finish Carpentry, Painting & Flooring section = 162 hrs** — combines LVT install, baseboard, casing, paint. Includes primary bedroom remodel finishes.
