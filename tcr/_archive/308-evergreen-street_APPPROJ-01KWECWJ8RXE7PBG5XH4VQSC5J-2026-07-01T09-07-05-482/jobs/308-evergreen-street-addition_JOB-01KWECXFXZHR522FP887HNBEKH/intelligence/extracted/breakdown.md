---
generation_kind: intelligence_rebuild_v2
stage: extract_breakdown
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWECWJ8RXE7PBG5XH4VQSC5J/jobs/308-evergreen-street-addition_JOB-01KWECXFXZHR522FP887HNBEKH/inputs/files/308_Evergreen_Addition.xlsx - Summary (1).csv.txt
  - _projects/308-evergreen-street_APPPROJ-01KWECWJ8RXE7PBG5XH4VQSC5J/jobs/308-evergreen-street-addition_JOB-01KWECXFXZHR522FP887HNBEKH/inputs/scope.md
---

# Breakdown extraction — 308 Evergreen (Simons Addition, 30'×10' Two-Story + Bedroom Remodel)

**Source CSV:** `308_Evergreen_Addition.xlsx - Summary (1).csv`
**Project totals (rows 2–5):** Labor $45,167.59 · Material $52,171.33 · Equipment $3,440.00 · **Grand Total $100,778.92** · Labor Hours 1,287.00
**Footprint:** 789 sqft overall (row 6). Ceiling height 8' (row 7).

> Note: CSV Grand Total is **$100,778.92** but scope PDF quotes a "Total Investment" of **$173,850**. These do not match — see Notes.

---

## Trade totals

Section rows from the CSV (rows 11–26). Columns: Labor / Material / Equipment / Section Total / Labor Hours.

| # | Section (verbatim) | Labor | Material | Equip | Section Total | Hours | CSV row |
|---|---|---:|---:|---:|---:|---:|:---:|
| 1 | General Conditions, Permitting & Pre-Construction | $2,316.08 | $2,130.00 | $0.00 | $4,446.08 | 56.0 | row 11 |
| 2 | Selective Demolition & Site Work | $1,982.00 | $2,040.00 | $220.00 | $4,242.00 | 56.0 | row 12 |
| 3 | Excavation, Foundation – Footings & Slab | $2,698.60 | $2,416.18 | $1,950.00 | $7,064.78 | 78.0 | row 13 |
| 4 | Structural Modifications – LVL Beam & Shoring | $2,117.80 | $2,422.00 | $0.00 | $4,539.80 | 60.0 | row 14 |
| 5 | Framing – Floor System, Walls & Elevator Shaft | $5,037.50 | $8,850.05 | $120.00 | $14,007.55 | 146.0 | row 15 |
| 6 | Roof Framing, Sheathing & Roofing System | $3,319.80 | $5,997.50 | $335.00 | $9,652.30 | 96.0 | row 16 |
| 7 | Exterior Finishes – Siding, Trim & Gutters | $2,474.70 | $2,696.61 | $560.00 | $5,731.31 | 72.0 | row 17 |
| 8 | Windows, Exterior Door & Weatherproofing | $1,493.80 | $2,172.00 | $0.00 | $3,665.80 | 44.0 | row 18 |
| 9 | Electrical – 100A Subpanel, Rough-In & Finish | $3,042.00 | $3,680.13 | $0.00 | $6,722.13 | 78.0 | row 19 |
| 10 | Plumbing – Rough-In, Master Bath & W/D Relocation | $1,356.80 | $2,160.00 | $0.00 | $3,516.80 | 40.0 | row 20 |
| 11 | HVAC – Mini Split, Tankless WH & Relocations | $1,363.36 | $5,140.00 | $0.00 | $6,503.36 | 36.0 | row 21 |
| 12 | Insulation & Air Sealing | $1,493.80 | $1,590.64 | $0.00 | $3,084.44 | 44.0 | row 22 |
| 13 | Drywall – New Addition & Existing Bedroom | $5,428.35 | $3,647.35 | $255.00 | $9,330.70 | 159.0 | row 23 |
| 14 | Interior Finish Carpentry, Painting & Flooring | $5,540.30 | $7,291.28 | $0.00 | $12,831.58 | 162.0 | row 24 |
| 15 | Master Bathroom – Custom Tile Shower & Finishes | $3,017.90 | $4,136.60 | $0.00 | $7,154.50 | 88.0 | row 25 |
| 16 | Existing Hall Bath Mod, Bedroom Remodel & Closeout | $2,484.80 | **-$4,199.00** | $0.00 | **-$1,714.20** | 72.0 | row 26 |
| | **TOTALS** (row 27) | **$45,167.59** | **$52,171.33** | **$3,440.00** | **$100,778.92** | **1,287.0** | row 27 |

### Trade grouping (rough)

Rolling the labor cost by implied trade family:

- **General / PM / permits:** row 11 ($2,316 labor, 56 hrs)
- **Demo:** row 12 ($1,982 labor, 56 hrs) — includes heat pump + electrical disconnect relocate, WH vent extension
- **Excavation / concrete:** row 13 ($2,699 labor, 78 hrs) — has $1,950 equipment (backhoe/mini-ex week + saw)
- **Structural (LVL):** row 14 ($2,118 labor, 60 hrs)
- **Framing:** rows 15 + 16 combined = $8,357 labor, 242 hrs (framing + roof structure)
- **Roofing / exterior envelope:** rows 16 + 17 + 18 = $7,288 labor / 212 hrs (roofing, siding/trim/gutters, windows/doors)
- **Electrical:** row 19 ($3,042 labor, 78 hrs) — subpanel + rough + finish bundled
- **Plumbing:** row 20 ($1,357 labor, 40 hrs) — rough + master bath + W/D relocate bundled
- **HVAC:** row 21 ($1,363 labor, 36 hrs) — mini-split + tankless WH + relocations
- **Insulation:** row 22 ($1,494 labor, 44 hrs)
- **Drywall:** row 23 ($5,428 labor, 159 hrs) — consolidated addition + existing bedroom
- **Interior finish (paint / trim / LVT):** row 24 ($5,540 labor, 162 hrs)
- **Tile (master bath):** row 25 ($3,018 labor, 88 hrs)
- **Retrofit / closeout:** row 26 ($2,485 labor, 72 hrs, negative material $-4,199)

---

## Allowances

The CSV summary sheet does **not** carry a separate allowance schedule — allowances are embedded inside the section material costs. The scope PDF lists an explicit **Material Allowance Schedule** which the breakdown material costs presumably fund:

- LVT flooring: $3.00 / sqft (scope: "Interior Finishes – General")
- Windows: $300 each (scope: "Exterior Finishes"; 4 windows implied → ~$1,200 in row 18 material)
- Interior doors: $250 each × 4 = $1,000 (scope: "Interior Doors")
- Pocket door systems: $400 each × 2 (scope: "Interior Doors")
- Recessed lights: $25 each, up to 18 fixtures = up to $450 (scope: "Electrical")
- Vanity (72"): $1,000 (scope: "Master Bathroom")
- Faucets: $150 each × 2 (scope: "Master Bathroom")
- Vanity lights: $100 each × 2 (scope: "Master Bathroom")
- Commode: $250 (scope: "Master Bathroom")
- Shower valve & trim: $250 (scope: "Master Bathroom")
- Tile (walls): $3.00 / sqft (scope: "Master Bathroom")
- Tile (floor mosaic): $6.00 / sqft (scope: "Master Bathroom")
- Waterproofing / setting materials: $500 (scope: "Master Bathroom")
- Mirrors: $150 each × 2 (scope: "Master Bathroom")
- Mini split: $2,500 (scope: "HVAC") — visible inside row 21 material $5,140
- Exterior door: $500 (scope: "Exterior Finishes")
- Guest bath shower pan + walls (acrylic): $1,000 (scope: "Existing Hall Bathroom Modification")

### Optional (add-on) packages, per scope

- **Closet & cabinet system:** $7,000 allowance (labor + materials). **Not visible as a CSV section.** Priced separately.
- **Tankless water heater:** $6,500 allowance (labor + materials). Row 21 header says "HVAC – Mini Split, **Tankless WH** & Relocations" — the CSV title implies the Tankless WH option **is included** in row 21's totals (row 21 material $5,140 ≈ $2,500 mini-split + ~$2,640 tankless-related material). Confirm at PM interview.

---

## Silent omissions (scope items with NO matching CSV row)

Items called out in `inputs/scope.md` that lack a dedicated CSV section or line — likely rolled into an existing section, but flag for PM confirmation:

1. **Septic / TDEC coordination.** Scope Pre-Construction section says "coordinate and complete septic inspection with TDEC" and "evaluate installation of grinder pump system" — scope explicitly excludes their cost via change-order. No CSV row for septic inspection labor or a TDEC permit lead-time. **Confirm:** is any TDEC permitting labor buried in row 11 (General Conditions), or genuinely $0?
2. **Grinder pump system.** Scope explicitly names this as a change-order candidate → no line in CSV. Expected omission; flag as a **procurement / plumbing rough decision point** the PM must resolve before plumbing rough-in starts.
3. **Optional Closet & Cabinet System ($7,000 allowance).** Scope calls it out explicitly; CSV has no cabinets/closet section. Row 15 ("Framing – Floor System, Walls & Elevator Shaft") does not include finish cabinets. If accepted, needs to be added.
4. **Optional Tankless WH package ($6,500 allowance).** The CSV row-21 header mentions "Tankless WH" but grand total is only $100,778.92 vs scope's $173,850 quote. Ambiguity: is tankless "in" (matching header) or "out" (matching total)? See Notes.
5. **Elevator shaft — dedicated 30A circuit run.** Scope: "rough-in electrical for 30 amp circuit run from sub panel." Row 19 (Electrical) 78 hrs likely absorbs this, but no line-item confirmation.
6. **Elevator shaft framing (4'×4').** Row 15 title *does* say "…Walls & Elevator Shaft" — captured. No omission.
7. **Waste vent stacks through roof.** Scope: "Extend vent stacks through roof as required." Assumed inside row 20 (Plumbing $1,357 labor / 40 hrs) — no separate line.
8. **W/D relocation (water, drain, roof vent).** Row 20 title says "…& W/D Relocation" — captured. No omission.
9. **Gas WH vent extension through new roof.** Scope demo: "Extend existing gas water heater vent through new roof system per code." No dedicated line — likely inside row 12 (Demo) or row 16 (Roof). **Flag:** since the CSV row 21 includes a tankless WH option, this legacy-vent-extension line may be redundant if the tank is being removed. Interview should clarify.
10. **Interior doors (4 total: 1 pre-hung, 2 pocket, per scope).** Only 3 accounted for verbally ("(1) pre-hung interior doors and (2) pocket door systems"). Scope says "(4) interior doors total" — one door has no configuration assigned. Doors expected inside row 24 (Interior Finish Carpentry) — no dedicated line.
11. **Foundation waterproofing / French drains.** Scope explicitly excludes — no omission; expected.
12. **Rock excavation / unsuitable soils.** Scope explicitly excludes — no omission; expected.
13. **Concrete walkway saw-cut & removal.** Row 12 (Demo) 56 hrs likely covers. No dedicated line.
14. **Railroad-tie removal + site obstructions.** Row 12 (Demo) likely covers. No dedicated line.
15. **Master bath niche and bench.** Scope calls both out; row 25 (Master Bath tile shower $3,018 labor / 88 hrs) presumably covers.
16. **Master bath exhaust fan/light combo.** Row 19 (Electrical) presumably covers wiring; row 25 or row 24 covers install. No separate line.
17. **Basement storage: framing + drywall + paint + lighting fixture.** Row 15 (framing), row 23 (drywall — title explicitly says "New Addition & Existing Bedroom," not basement storage), row 24 (paint), row 19 (electrical) likely absorb. **Watch row 23:** its title does not name basement storage — confirm it's included.
18. **Primary bedroom remodel (~12'5" × 16').** Row 24 (Interior Finish Carpentry, Painting & Flooring) likely covers paint/LVT/trim; row 23 (Drywall — "…& Existing Bedroom") covers drywall. Framing modifications likely in row 15.
19. **Hall bath window infill + insulation + drywall + acrylic shower + PVC trim + repaint.** All rolled into row 26 (Existing Hall Bath Mod, Bedroom Remodel & Closeout) — but that row also names "Bedroom Remodel & Closeout." Row 26 material is **negative $-4,199**, so it's functioning as a credit / offset section, not a positive work bucket. See Notes.
20. **Final cleaning & inspection coordination.** Scope closeout; row 26 title says "Closeout" so likely bundled. No separate cleanup line.
21. **Dumpster / dump-run debris removal.** Scope demo: "multiple dump runs." Row 12 equipment $220 is small (one dump-trailer run at scope's $450/removal is not even represented). **Flag:** dump-run costs may be under-represented in equipment column.

---

## Notes (anomalies, negative rows, credits, contradictions)

1. **Row 26 has a negative material cost of −$4,199 and a negative section total of −$1,714.20** (labor $2,485, hours 72). This is a credit line — the retrofit hall bath modification net-nets material against another section, or it represents an allowance offset. The CSV title bundles three concerns into one row ("Existing Hall Bath Mod, **Bedroom Remodel & Closeout**"), which obscures how the credit maps. Rule 4V flags this pattern: hall bath acrylic shower swap is a **customer early item**, hall bath window infill + insulation + drywall + repaint is a **retrofit** — they belong in separate components. Row 26 conflates them.
   - Labor hours (72) is above the 24-hr threshold in Dev Rule §12 for a "closeout-only" expansion, so this is **not** a pure close-out row — it contains real work that must be decomposed.

2. **Grand Total mismatch: CSV $100,778.92 vs scope "Total Investment $173,850."** The CSV is roughly 58% of the quoted scope total. Candidates for the gap:
   - Markup / margin (materials +15%, subs +30% per scope Rates section) — not applied inside CSV section totals.
   - Optional packages: closet $7,000 + tankless $6,500 = $13,500 add-on (still doesn't close a ~$73k gap alone).
   - Change-order-eligible items (septic, grinder pump, rock excavation) are excluded.
   - Backhoe usage ($1,100/wk) may be under-counted in row 13's $1,950 equipment.
   - **Flag hard for PM interview.** Do NOT infer the total is complete.

3. **Row 21 header contradiction: "HVAC – Mini Split, Tankless WH & Relocations."** Header suggests tankless is included in base; scope lists tankless as an **optional package with $6,500 allowance**. Material column ($5,140) is *close* to $2,500 mini-split + ~$2,640 tankless-related, which supports "included." But then scope's total_investment $173,850 doesn't add up. Ambiguity → **PM interview must resolve WH scope**:
   - If tankless IS in: existing gas WH is being removed → scope's "extend existing gas WH vent through new roof" is stale.
   - If tankless is OUT (base bid only): row 21 material is inconsistent with mini-split alone at $2,500.

4. **Roof shingles single-day + underlayment.** Row 16 96 hrs / crew 3 = ~4 days per productivity table — consistent with a small-addition roof + tie-in. Nothing anomalous.

5. **Framing hours (row 15) = 146 hrs @ crew 3 = ~6.1 days.** Editor rules example matches almost exactly; decomposition template applies cleanly.

6. **Drywall hours (row 23) = 159 hrs @ crew 3 = ~6.6 days**, but editor rules say a consolidated addition + retrofit block is 9–11 days. The row 23 title says "New Addition & Existing Bedroom" — it may be **under-counted** because basement storage drywall isn't named in the title. Or Will's 9–11d nominal includes cure/sand slack that the raw labor-hour math misses. **Flag.**

7. **No dedicated procurement / lead-time line items in the CSV.** Windows, LVL, mini-split, tankless, cabinets, tile, custom-shower glass — none appear as procurement rows. Procurement structure will be inferred entirely from the scope narrative and Rule 4R (3-task pattern).

8. **No dedicated inspection line items in the CSV.** Footing, rough MEP bundled, insulation, final bundled — all zero in the breakdown. Expected; inspection labor is inspector-side, not TCR-side. Emitted from rules, not from CSV.

9. **No dedicated equipment-delivery lines in the CSV.** Dumpster, mini-ex, saw, scaffolding — Rule 4O will emit these; CSV row 12 has $220 in equipment column (likely one dump-trailer run) and row 13 has $1,950 (mini-ex week + saw). Under-represented for a 3–4 month job.

10. **Row 15 mentions elevator shaft framing; no elevator install or door.** Scope confirms "Elevator system not included." Row 19 covers the 30A rough-in circuit implicitly. Not an omission — an explicit exclusion.

11. **Row 12 (Demo) $220 equipment is anomalously low** given scope calls for "multiple dump runs" at $450 each per the Rates section. Either dump-run costs live under row 11 (general conditions) or they're rolled into a hidden markup layer. **Flag for PM.**

12. **Small hours on row 20 (Plumbing) = 40 hrs @ crew 2 = 2.5 days** — this DIRECTLY conflicts with Rule 4H / editor rules / plumbing_rough_min_duration.md (Will's nominal: 4d × 2 for any job with master bath + W/D relocation = 64 hrs). The CSV is under-budgeted for plumbing labor by ~24 hrs. **Hard rule violation risk; schedule must use 4d × 2, not the CSV number.**
