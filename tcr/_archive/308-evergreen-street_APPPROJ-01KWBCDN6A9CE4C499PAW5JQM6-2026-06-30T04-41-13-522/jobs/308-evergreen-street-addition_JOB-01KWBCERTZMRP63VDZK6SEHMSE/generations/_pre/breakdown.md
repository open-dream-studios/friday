---
generation_kind: intel_gather_v1
artifact: breakdown_pre
derived_from:
  - path: _projects/308-evergreen-street_APPPROJ-01KWBCDN6A9CE4C499PAW5JQM6/jobs/308-evergreen-street-addition_JOB-01KWBCERTZMRP63VDZK6SEHMSE/inputs/files/308_Evergreen_Addition.xlsx - Summary (1).csv.txt
    sha256: c936d98fafac090e05c29bef7398fa04614394c69cf5793fb284d2147ae64d6f
  - path: _projects/308-evergreen-street_APPPROJ-01KWBCDN6A9CE4C499PAW5JQM6/jobs/308-evergreen-street-addition_JOB-01KWBCERTZMRP63VDZK6SEHMSE/inputs/scope.md
    sha256: cd479bfac8ead63c5439c8d4f8e8fa5c0af3af616a7f95321b42774ecebd81a6
last_verified_at: 2026-06-30T04:30:00Z
---

## Project totals

- Labor: $45,167.59
- Material: $52,171.33
- Equipment: $3,440.00
- **Grand Total: $100,778.92**
- Total labor hours: 1,287
- CSV title: "Two-Story Addition + Bedroom Remodel – Cost Breakdown (Incl. Tankless WH Option)" — this is the WITH-tankless variant

## Section totals (labor / material / equipment / total / labor hrs)

- General Conditions, Permitting & Pre-Construction: $2,316 / $2,130 / $0 / $4,446 / 56 hrs
- Selective Demolition & Site Work: $1,982 / $2,040 / $220 / $4,242 / 56 hrs
- Excavation, Foundation – Footings & Slab: $2,698 / $2,416 / $1,950 / $7,065 / 78 hrs
- Structural Modifications – LVL Beam & Shoring: $2,117 / $2,422 / $0 / $4,540 / 60 hrs
- Framing – Floor System, Walls & Elevator Shaft: $5,037 / $8,850 / $120 / $14,008 / 146 hrs
- Roof Framing, Sheathing & Roofing System: $3,319 / $5,997 / $335 / $9,652 / 96 hrs
- Exterior Finishes – Siding, Trim & Gutters: $2,474 / $2,696 / $560 / $5,731 / 72 hrs
- Windows, Exterior Door & Weatherproofing: $1,493 / $2,172 / $0 / $3,666 / 44 hrs
- Electrical – 100A Subpanel, Rough-In & Finish: $3,042 / $3,680 / $0 / $6,722 / 78 hrs
- Plumbing – Rough-In, Master Bath & W/D Relocation: $1,356 / $2,160 / $0 / $3,517 / 40 hrs
- HVAC – Mini Split, Tankless WH & Relocations: $1,363 / $5,140 / $0 / $6,503 / 36 hrs
- Insulation & Air Sealing: $1,493 / $1,590 / $0 / $3,084 / 44 hrs
- Drywall – New Addition & Existing Bedroom: $5,428 / $3,647 / $255 / $9,331 / 159 hrs
- Interior Finish Carpentry, Painting & Flooring: $5,540 / $7,291 / $0 / $12,832 / 162 hrs
- Master Bathroom – Custom Tile Shower & Finishes: $3,017 / $4,136 / $0 / $7,155 / 88 hrs
- Existing Hall Bath Mod, Bedroom Remodel & Closeout: $2,484 / **-$4,199** / $0 / **-$1,714** / 72 hrs

## Allowances (from scope.md L161-178, L182, L185)

- LVT Flooring: $3.00/sqft
- Windows: $300 each
- Interior Doors: $250 each
- Pocket Door Systems: $400 each
- Recessed Lights: $25 each, up to 18 fixtures
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
- Guest Bath Shower system (pan + walls): $1,000
- Optional: Custom closet/cabinet system $7,000
- Optional: Tankless WH (remove existing + install + venting) $6,500

## Silent omissions (in scope, NO matching CSV line)

- **Basement storage finish** — no dedicated section line; likely bundled into Framing + Drywall + Interior Finish lines. Confirm.
- **Hall bath modification** — bundled with bedroom remodel + closeout into ONE line with NEGATIVE material cost (`-$4,199`). Highly unusual; see Notes.
- **Future elevator shaft framing** — bundled into "Framing – Floor System, Walls & Elevator Shaft" but no separate line item; only the 30A circuit shows up implicitly in Electrical.
- **TDEC septic inspection / grinder pump** — explicitly excluded as change-order placeholders (scope L25-29), so the omission is intentional. Stage B should flag for PM confirmation.
- **Saw-cut concrete walkway** — line item in Demolition section but no dedicated saw/equipment line.
- **Heat pump relocation** + **electrical disconnect relocation** — bundled into Demolition section.
- **Existing gas WH vent extension through new roof** — bundled into either roofing or plumbing line, not called out.
- **Optional closet system + tankless WH packages** — listed as scope options; tankless appears bundled into HVAC line per CSV title, but no separate package line. Closet system not in any line.

## Notes

- **Grand Total $100,779 vs. scope L179 "Total Investment $173,850" — $73K gap.** Critical discrepancy. The Summary CSV may be a partial/raw cost build-up; scope total likely includes margin + overhead + allowances + change-order placeholders not in CSV.
- **Hall Bath Mod + Bedroom Remodel + Closeout line has NEGATIVE material cost (-$4,199), netting total -$1,714 with 72 labor hours.** This is a credit/allowance subtraction line, not actual work; per dev_rules §12, decompose into 1-2 close-out tasks rather than full expansion.
- **HVAC line title says "Mini Split, Tankless WH & Relocations" — tankless WH appears bundled in $6,503** but scope frames tankless as OPTIONAL ($6,500 allowance, scope L183-185). The CSV variant is the WITH-tankless build; if the customer DECLINES the option, the HVAC line drops by roughly the $6,500 allowance and tankless tasks disappear from the schedule.
- **Plumbing labor only 40 hrs / $1,356 labor** — for a job with master bath rough (2 lav + 1 toilet + 1 custom shower), W/D relocation, vent stack extensions, this is conspicuously low. Will's nominal for any job with master bath + W/D = 4 working days × 2 crew = 64 hrs labor. CSV underestimates.
- **HVAC labor only 36 hrs** — typical mini-split rough (0.5d/1p) + install (1d/1p) = ~12 hrs. The bulk here is probably the tankless WH portion + HVAC relocations. Confirm sizing.
- **Drywall 159 hrs / 9-11 working days × 3 crew consolidated** — matches editor_rules drywall consolidation expectation for a multi-zone job (addition + bedroom remodel + basement storage + hall bath patch).
- **Framing 146 hrs / 6 working days × 3 crew** — matches editor_rules worked example for a 2-story addition.
