---
generation_kind: intelligence_rebuild_v2
stage: extract_breakdown
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWFF6ZQ82D651FWRN1RBJA72/jobs/308-evergreen-street-addition_JOB-01KWFF8CWBQKYGA4Z64XF143EY/inputs/files/308_Evergreen_Addition.xlsx - Summary (1).csv.txt
  - _projects/308-evergreen-street_APPPROJ-01KWFF6ZQ82D651FWRN1RBJA72/jobs/308-evergreen-street-addition_JOB-01KWFF8CWBQKYGA4Z64XF143EY/inputs/scope.md
---

# Breakdown extraction — 308 Evergreen Addition

**Source CSV:** `308_Evergreen_Addition.xlsx - Summary (1).csv`
**Project:** Simons Addition – 30'x10' Two-Story + Bedroom Remodel
**Footprint:** 789 SF · 8' ceilings
**Template anchor:** Basement_Remodel_Breakdown_Locked_Template_v1.xlsx

## Trade totals

| # | Section | Labor $ | Material $ | Equip $ | Section Total | Labor hrs |
|---|---|---:|---:|---:|---:|---:|
| 1 | General Conditions, Permitting & Pre-Construction | 2,316.08 | 2,130.00 | 0.00 | **4,446.08** | 56.0 |
| 2 | Selective Demolition & Site Work | 1,982.00 | 2,040.00 | 220.00 | **4,242.00** | 56.0 |
| 3 | Excavation, Foundation – Footings & Slab | 2,698.60 | 2,416.18 | 1,950.00 | **7,064.78** | 78.0 |
| 4 | Structural Modifications – LVL Beam & Shoring | 2,117.80 | 2,422.00 | 0.00 | **4,539.80** | 60.0 |
| 5 | Framing – Floor System, Walls & Elevator Shaft | 5,037.50 | 8,850.05 | 120.00 | **14,007.55** | 146.0 |
| 6 | Roof Framing, Sheathing & Roofing System | 3,319.80 | 5,997.50 | 335.00 | **9,652.30** | 96.0 |
| 7 | Exterior Finishes – Siding, Trim & Gutters | 2,474.70 | 2,696.61 | 560.00 | **5,731.31** | 72.0 |
| 8 | Windows, Exterior Door & Weatherproofing | 1,493.80 | 2,172.00 | 0.00 | **3,665.80** | 44.0 |
| 9 | Electrical – 100A Subpanel, Rough-In & Finish | 3,042.00 | 3,680.13 | 0.00 | **6,722.13** | 78.0 |
| 10 | Plumbing – Rough-In, Master Bath & W/D Relocation | 1,356.80 | 2,160.00 | 0.00 | **3,516.80** | 40.0 |
| 11 | HVAC – Mini Split, Tankless WH & Relocations | 1,363.36 | 5,140.00 | 0.00 | **6,503.36** | 36.0 |
| 12 | Insulation & Air Sealing | 1,493.80 | 1,590.64 | 0.00 | **3,084.44** | 44.0 |
| 13 | Drywall – New Addition & Existing Bedroom | 5,428.35 | 3,647.35 | 255.00 | **9,330.70** | 159.0 |
| 14 | Interior Finish Carpentry, Painting & Flooring | 5,540.30 | 7,291.28 | 0.00 | **12,831.58** | 162.0 |
| 15 | Master Bathroom – Custom Tile Shower & Finishes | 3,017.90 | 4,136.60 | 0.00 | **7,154.50** | 88.0 |
| 16 | Existing Hall Bath Mod, Bedroom Remodel & Closeout | 2,484.80 | **-4,199.00** | 0.00 | **-1,714.20** | 72.0 |
| | **CSV TOTALS** | **45,167.59** | **52,171.33** | **3,440.00** | **100,778.92** | **1,287.0** |

## Allowances

Pulled from `inputs/scope.md` (Material Allowance Schedule + Optional Packages). The CSV rolls these into section material subtotals but does not itemize them — surface individually so procurement + PM can track.

**Material allowances (in base scope, folded into section rows):**
- LVT flooring — **$3.00/sqft**
- Windows — **$300 each** × 4 (3× 36"×60" DH + 1× transom) = $1,200
- Interior doors — **$250 each** (× 1 pre-hung, per interior doors line)
- Pocket door systems — **$400 each** × 2 = $800
- Recessed lights — **$25 each**, up to 18 fixtures (scope says ~12 planned) = ~$300–$450
- Vanity (72") — **$1,000**
- Faucets — **$150 each** × 2 = $300
- Vanity lights — **$100 each** × 2 = $200
- Commode — **$250**
- Shower valve & trim — **$250**
- Tile — walls **$3/sqft**, floor mosaic **$6/sqft**
- Waterproofing/setting materials — **$500**
- Mirrors — **$150 each** × 2 = $300
- Mini split — **$2,500**
- Exterior door — **$500**
- Guest bath acrylic shower (pan + walls) — **$1,000**

**Optional packages (NOT in CSV totals — separate line items if elected):**
- Closet & cabinet system — **$7,000** (labor + materials)
- Tankless water heater — **$6,500** (labor + materials, utility upgrades excluded)

**Rate/soft-cost notes from scope:**
- General labor: **$70/hr**; team-lead +$15; electrical/HVAC +$30; plumbing +$40
- Materials/consumables/permits at **cost + 15%**
- Subs at **cost + 30%**
- Debris: **$450 per dump-trailer removal**
- Backhoe: **$1,100/wk**
- Deposit: **$20,000**; weekly invoicing

## Silent omissions (scope items with NO clearly-matching CSV row)

Cross-referenced against `inputs/scope.md`. Items the scope mentions but which do not appear as a discrete CSV line — priced-inside-a-bucket at best, dropped at worst.

1. **TDEC septic inspection & feasibility for relocation / grinder pump** — scope says "Coordinate and complete septic inspection with TDEC" and "Evaluate installation of grinder pump system." Scope explicitly excludes actual septic relocation / grinder install as change-order territory, but the inspection + evaluation work itself is not visible in the CSV. Likely folded into (row 10: "General Conditions… $4,446") but no confirmation.
2. **Gas water heater vent extension through new roof** — scope: "Extend existing gas water heater vent through new roof system per code." Not evident in the HVAC row (which reads as "Mini Split, Tankless WH & Relocations" — implies NEW tankless, but scope base case retains existing gas WH). Ambiguous which row carries this.
3. **Elevator shaft framing + 30A rough-in circuit** — scope: "Frame (1) future elevator shaft approximately 4' x 4'" and "Install (1) dedicated 120V, 30A circuit for future elevator." Framing likely inside row 14 ("Framing… Elevator Shaft — $14,007"), but the dedicated 30A circuit is not called out separately in the electrical row (row 13).
4. **Temporary shoring for LVL install** — scope: "including temporary shoring." Likely inside row 13 (Structural Modifications — $4,539) but not itemized.
5. **Temporary dry-in measures** — scope: "Temporary dry-in measures will be installed." Not itemized; presumably inside row 15 (Roof Framing… $9,652).
6. **Sheathing + WRB** — scope calls out sheathing under Exterior Finishes; CSV puts "Siding, Trim & Gutters" as row 16 ($5,731) — WRB and sheathing not itemized (may be split between row 15 roofing and row 16 siding).
7. **Interior doors — 4 total (1 pre-hung + 2 pocket doors + ?)** — scope specifies (4) interior doors but only lists slots for 3 (1 pre-hung + 2 pocket + one unaccounted). No dedicated doors line in CSV; folded into row 23 (Interior Finish Carpentry — $12,831).
8. **Dryer vent relocation through roof** — scope: "Install washer and dryer relocation including… roof venting." Referenced in row 19 (Plumbing) label but not confirmed as itemized.
9. **Chimney tie-in / detail** — plans PDF shows a "CHIMNEY" annotation on the roof plan. Neither scope nor CSV addresses chimney work explicitly. Possible field surprise.
10. **Baseboard + casing specific SKUs** — scope: 5-1/4" MDF/finger-joint base + 2-1/4" casing. Not itemized but presumably in row 23 material subtotal.
11. **Insulation inspection material staging** — no line item; TCR editor rules require insulation material delivered same day as rough-bundled inspection. Not a scope omission per se; call-out for the PM.
12. **Final cleaning + final inspections coordination** — scope: "Perform final cleaning. Coordinate inspections." Ostensibly inside row 25 (Existing Hall Bath Mod, Bedroom Remodel & Closeout) — the "Closeout" tail — but that row is a NEGATIVE $-1,714 which makes the encoding suspicious (see Notes).

## Notes (anomalies, negative rows, credits, arithmetic)

### 🔴 Scope-vs-CSV total gap — 42.1% (Rule `scope_vs_csv_total_reconciliation` TRIGGERS)

- **Scope "Total Investment": $173,850** (from `scope.md`)
- **CSV Grand Total: $100,778.92** (row 26)
- **Delta: $73,071.08 (42.1% under scope)**

The gap dwarfs the 5% rule threshold. Two arithmetic-visible optional packages account for only $13,500 of the delta:
- Closet & cabinet system: $7,000
- Tankless WH: $6,500
- **Remaining unexplained gap: ~$59,571**

Even if BOTH optional packages are elected, the CSV still comes in ~$59.5k below the scope's stated total. Candidate explanations (PM must confirm):
- Scope's "Total Investment" includes markup/margin not yet applied in the CSV summary (CSV shows raw labor + material + equipment only; scope says materials are cost+15% and subs cost+30%).
- CSV omits substantial line items.
- Scope figure is stale relative to a repriced CSV.

**→ This MUST generate an interview question per company rule `scope_vs_csv_total_reconciliation`** and pin `interview_status: needs_more`.

### 🔴 Row 25 — "Existing Hall Bath Mod, Bedroom Remodel & Closeout" is NEGATIVE

- Section total: **−$1,714.20** (labor +$2,484.80, material **−$4,199.00**, equipment $0, 72 labor hrs)
- Negative material figure suggests either (a) a credit / trade-back from a bundled fixture allowance, (b) an offset against the primary bath materials, or (c) a data-entry error.
- Under company `dev_rules.md §12`: "Negative `labor_cost` or negative `section_total` is usually a credit… If `section_total < 0` and `labor_hours ≤ 24`, emit just one or two close-out tasks." **But labor_hours here is 72, not ≤24** — meaning this row bundles real work (hall bath acrylic swap, bedroom remodel, closeout) that CANNOT be collapsed to a couple of punch tasks.
- Also carries `dev_rules.md §11 warning #8`: "section_total is negative and labor_hours > 40. Probable scope ambiguity — surface for human resolution."
- **Recommended interview question:** what does the −$4,199 material credit represent, and does the 72 labor hrs cover BOTH (a) customer-early hall bath acrylic shower swap AND (b) primary bedroom remodel (drywall, paint, LVT, trim) AND (c) closeout?

### 🟡 Row 11 — HVAC row label mentions "Tankless WH" but scope treats tankless as OPTIONAL

CSV row 11 is labeled "HVAC – Mini Split, Tankless WH & Relocations" ($6,503.36 total, $5,140 material). Scope treats the tankless WH as an **Optional Package** at $6,500. The CSV appears to include tankless WH cost inside the base bid — but the scope's Optional Package pricing ($6,500) is separate from — and inconsistent with — this row's $5,140 material figure.

- If CSV row 11 INCLUDES tankless WH → then Optional Package is redundant.
- If CSV row 11 EXCLUDES tankless WH and scope-base retains the existing gas WH (vent extension only) → the $5,140 material figure is only the mini-split ($2,500 allowance) + HVAC relocations, and the row label is misleading.

Ambiguous. Interview question warranted.

### 🟡 Room-count / plumbing productivity check

Row 19 (Plumbing) shows **40 labor hours** for full rough-in + master bath (2 lav, 1 toilet, 1 custom shower) + W/D relocation + vent stacks. At crew=2 that's 2.5 working days. Company rule `plumbing_rough_min_duration.md` (severity: **hard**) mandates **≥ 4 working days × 2 crew (= 64 person-hrs)** for any job containing a master bath / 2+ bath fixtures / W/D relocation. **40 hrs is below the floor.** The CSV is under-scoped for plumbing labor per company rule. Flag for PM.

### 🟡 Recessed light count mismatch

- Scope §Electrical: "approximately (12) recessed lights"
- Scope §Material Allowance: "Recessed Lights: $25 each, up to 18 fixtures"
- 12 vs "up to 18" — is CSV row 13 material ($3,680.13) priced at 12 fixtures or 18?

### 🟡 Truss vs stick-frame ambiguity (roof)

Scope: "Construct new gable roof system (**truss or rafter framed, determined during design phase**)." CSV row 15 (Roof Framing) does not distinguish. Per company belief `stick_frame_default_for_small_additions.md` (confidence 0.92), a 30'×10' addition (300 sqft roof) with a 3/12 pitch defaults to stick-frame; no `procurement.trusses` task should be emitted absent PM confirmation. Company rule `dev_rules.md §4Q` also mandates: only emit trusses if scope explicitly says so — this scope's language is ambiguity, not confirmation. **Default = stick-frame.**

### 🟡 Grinder pump / septic — explicit change-order carve-out

Scope explicitly says grinder pump / septic relocation "not included and will be addressed via change order." CSV correctly omits it. No action required, but PM should confirm current disposition at interview (in / out / TBD).

### 🟢 Arithmetic check

Row-sum sanity check: sum of Section Totals rows 10–25 = **$100,778.92** ✓ matches Grand Total ($100,778.92). Labor-hour sum = 1,287 ✓ matches TOTALS row. CSV is internally consistent.

### 🟢 Equipment total

Row 20-column equipment total = $3,440. Ties to dumpster removals ($450 × ~4–5 pulls per scope) + backhoe ($1,100/wk × ~2 weeks) + concrete equipment (row 12 shows $1,950 equipment on excavation/foundation — matches a mini-ex week). Plausible.
