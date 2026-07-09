---
generation_kind: intelligence_rebuild_v2
stage: extract_breakdown
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWEEYTBJZXYA3GZMYAM45QX4/jobs/308-evergreen-street-addition_JOB-01KWEEZXTM9DFGBQGSDK40SE57/inputs/files/308_Evergreen_Addition.xlsx - Summary (1).csv.txt
  - _projects/308-evergreen-street_APPPROJ-01KWEEYTBJZXYA3GZMYAM45QX4/jobs/308-evergreen-street-addition_JOB-01KWEEZXTM9DFGBQGSDK40SE57/inputs/scope.md
---

# Breakdown extraction — 308 Evergreen Addition

**Source CSV:** `308_Evergreen_Addition.xlsx - Summary (1).csv`
**Project:** Simons Addition — 30′×10′ Two-Story + Bedroom Remodel
**Footprint:** 789 SF (295 + 295 first-floor addition + basement addition; 590 total addition area on the plan)
**Ceiling height:** 8′
**Template anchor:** Basement_Remodel_Breakdown_Locked_Template_v1.xlsx

## Project totals (rows 2–5)

| Bucket          | Amount        |
|-----------------|---------------|
| Labor Cost      | $45,167.59    |
| Material Cost   | $52,171.33    |
| Equipment Cost  | $3,440.00     |
| **Grand Total** | **$100,778.92** |
| Total Labor Hrs | 1,287.00      |

Note the CSV Grand Total ($100,778.92) does NOT match the scope's stated "Total Investment: $173,850." The scope figure is the customer-facing contract price (with markup, overhead, profit, and allowances); the CSV is a raw cost breakdown. Flag downstream — schedule should trust the CSV's labor-hour distribution, not the scope's investment figure, for duration math.

## Trade totals

Section-by-section from the summary tab (rows 11–27). All costs are raw section costs; labor hours are the primary driver for duration heuristics.

| Row | Section (verbatim)                                              | Labor $     | Material $   | Equip $   | Section Total | Labor Hrs |
|-----|-----------------------------------------------------------------|-------------|--------------|-----------|---------------|-----------|
| 11  | General Conditions, Permitting & Pre-Construction               | $2,316.08   | $2,130.00    | $0.00     | $4,446.08     | 56.00     |
| 12  | Selective Demolition & Site Work                                | $1,982.00   | $2,040.00    | $220.00   | $4,242.00     | 56.00     |
| 13  | Excavation, Foundation – Footings & Slab                        | $2,698.60   | $2,416.18    | $1,950.00 | $7,064.78     | 78.00     |
| 14  | Structural Modifications – LVL Beam & Shoring                   | $2,117.80   | $2,422.00    | $0.00     | $4,539.80     | 60.00     |
| 15  | Framing – Floor System, Walls & Elevator Shaft                  | $5,037.50   | $8,850.05    | $120.00   | $14,007.55    | 146.00    |
| 16  | Roof Framing, Sheathing & Roofing System                        | $3,319.80   | $5,997.50    | $335.00   | $9,652.30     | 96.00     |
| 17  | Exterior Finishes – Siding, Trim & Gutters                      | $2,474.70   | $2,696.61    | $560.00   | $5,731.31     | 72.00     |
| 18  | Windows, Exterior Door & Weatherproofing                        | $1,493.80   | $2,172.00    | $0.00     | $3,665.80     | 44.00     |
| 19  | Electrical – 100A Subpanel, Rough-In & Finish                   | $3,042.00   | $3,680.13    | $0.00     | $6,722.13     | 78.00     |
| 20  | Plumbing – Rough-In, Master Bath & W/D Relocation               | $1,356.80   | $2,160.00    | $0.00     | $3,516.80     | 40.00     |
| 21  | HVAC – Mini Split, Tankless WH & Relocations                    | $1,363.36   | $5,140.00    | $0.00     | $6,503.36     | 36.00     |
| 22  | Insulation & Air Sealing                                        | $1,493.80   | $1,590.64    | $0.00     | $3,084.44     | 44.00     |
| 23  | Drywall – New Addition & Existing Bedroom                       | $5,428.35   | $3,647.35    | $255.00   | $9,330.70     | 159.00    |
| 24  | Interior Finish Carpentry, Painting & Flooring                  | $5,540.30   | $7,291.28    | $0.00     | $12,831.58    | 162.00    |
| 25  | Master Bathroom – Custom Tile Shower & Finishes                 | $3,017.90   | $4,136.60    | $0.00     | $7,154.50     | 88.00     |
| 26  | Existing Hall Bath Mod, Bedroom Remodel & Closeout              | $2,484.80   | **−$4,199.00** | $0.00   | **−$1,714.20**| 72.00     |

## Allowances

Allowances live in the scope narrative, not the CSV summary. The CSV rolls allowances into their respective section material costs. Pulled from `scope.md` (Material Allowance Schedule + Optional Packages):

- LVT flooring: $3.00/sqft
- Windows: $300 each × 4 windows = $1,200
- Interior doors: $250 each × ~2 pre-hung = $500
- Pocket door systems: $400 each × 2 = $800
- Recessed lights: $25 each, up to 18 fixtures = up to $450
- Vanity (72″): $1,000
- Faucets: $150 each × 2 = $300
- Vanity lights: $100 each × 2 = $200
- Commode: $250
- Shower valve & trim (dual diverter): $250
- Tile (walls): $3.00/sqft
- Tile (floor mosaic): $6.00/sqft
- Waterproofing / setting materials: $500
- Mirrors: $150 each × 2 = $300
- Mini-split: $2,500
- Exterior door: $500
- Guest bath shower system (pan + walls): **$1,000 allowance**
- **Optional — Closet & cabinet system:** $7,000 (labor + materials)
- **Optional — Tankless water heater:** $6,500 (labor + materials, incl. venting)

## Silent omissions (scope items with NO matching CSV row)

Cross-referenced scope.md sections against the 16 CSV rows above. Items called out in the written scope that have no dedicated line item — either bundled invisibly into a larger section, or genuinely missing:

1. **TDEC septic inspection / septic feasibility work** — scope Pre-Construction & Design Phase explicitly calls out "Coordinate and complete septic inspection with TDEC" and evaluating "grinder pump system to connect to available sewer line." No CSV row for TDEC coordination, septic work, or grinder pump. Scope disclaims cost ("addressed via change order") but the *coordination* labor is still real and lands somewhere — likely absorbed into row 11 (general conditions). **Confirm with PM at interview whether septic/grinder is IN scope or out.**

2. **Water heater — tankless vs. existing** — scope offers a $6,500 tankless allowance as an *optional* package AND separately says "Extend existing gas water heater vent through new roof system" (row 12 / demo & site work). Row 21 is titled "HVAC – Mini Split, Tankless WH & Relocations" — the "Tankless WH" nomenclature suggests the tankless is baked into the base bid, but scope treats it as optional. **Ambiguous — confirm with PM.** This drives Rule 4H (tank set FIRST). If existing WH stays (vent-through-roof only), no `procurement.tank` / `plumbing.tank_set` tasks. If tankless is in, they're mandatory.

3. **Elevator shaft framing + 30A circuit** — scope calls out framing (1) 4′×4′ future elevator shaft AND rough-in for a dedicated 120V 30A circuit. Framing is folded into row 15 ("Framing – Floor System, Walls & Elevator Shaft"). The 30A elevator circuit is presumably folded into row 19 (electrical). No standalone line items, but the labor hours in row 15 (146 hrs) and row 19 (78 hrs) are likely sized to absorb this — verify at interview.

4. **Closet & cabinet system (optional package)** — no CSV row. Scope prices this at $7,000 optional allowance. If PM confirms it's IN, needs a `cabinets.install` / closet-buildout task; if OUT, no impact.

5. **Interior doors (4 total: 1 pre-hung + 2 pocket + 1 unclear)** — no dedicated door line item. Presumably bundled into row 24 (interior finish carpentry) but the pocket door SYSTEMS have a materials cost ($400 each) and specific framing needs (pockets go in during framing, not finish). Verify that framing labor in row 15 accommodates pocket-door rough-in.

6. **Roof tie-in / concealed conditions** — scope explicitly warns "concealed conditions … encountered during demolition will be addressed via change order." No buffer / contingency row in CSV. The addition's 3/12 roof ties into existing 6/12 — this is a known high-risk seam. Schedule needs a discovery buffer, but the CSV allocates no dollars for it.

7. **Cleanup & closeout as a discrete line item** — scope has a "Cleanup & Closeout" section (debris removal, final cleaning, coordinate inspections). Row 26 bundles closeout with hall bath mod + bedroom remodel (which is why row 26 is negative — see Notes). No standalone closeout row. Debris removal shows up on row 12 equipment ($220) and row 13 equipment ($1,950 — likely mini-ex + dump runs).

8. **Painting of the primary bedroom remodel** — scope Primary Bedroom Remodel section calls out "Prime and paint entire room" AND "Install new LVT flooring" AND "full trim package." These are almost certainly folded into row 24 (interior finish carpentry, painting & flooring — 162 labor hours is large enough to cover it) but not called out separately, so a schedule needs to make sure the retrofit bedroom's paint/flooring/trim are consolidated with the addition's rather than modeled as a separate crew visit.

9. **Hall bath acrylic shower swap — customer early item candidate** — scope explicitly calls out removing tub/shower combo and installing acrylic shower system with $1,000 allowance for pan/walls. This is the classic Rule 4V customer-requested early item pattern (customer wants a working shower during construction). No CSV row explicitly separates it from the rest of the hall bath mod work (row 26 bundles it all). **PM interview MUST confirm** whether this is a Day-1 early item or truly part of end-of-job closeout.

## Notes (anomalies, negative rows, credits)

- **Row 26 is NEGATIVE** — `Existing Hall Bath Mod, Bedroom Remodel & Closeout` totals **−$1,714.20** with material cost of **−$4,199.00**. Labor is positive ($2,484.80 / 72 hrs) but material is a **credit of $4,199**. Per dev_rules.md §12 and Rule 11 warning #8: negative section_total with labor_hours > 40 = probable scope ambiguity, surface for human resolution. Working theory: the negative material is a "subtract from prior bid" or a template-anchor artifact where the retrofit work's materials were double-counted elsewhere and this row net-zeros them. **PM must clarify at interview** — could indicate the row is a credit against another section (e.g., drywall material for the hall bath patch was already counted in row 23). Do NOT expand row 26 into a full task tree — decompose per dev_rules.md §12 (one or two closeout tasks: hall bath acrylic swap-out + bedroom repaint touch-up + final walkthrough).

- **Row 21 HVAC – includes "Tankless WH"** in its title alongside mini-split and relocations. Material cost of $5,140 is roughly consistent with $2,500 mini-split + $2,500-ish tankless allowance + relocation misc. This suggests the tankless IS in the base bid despite scope labeling it "optional package." Confirm.

- **Row 15 Framing labor is large (146 hrs, ~6d @ crew 3)** — accommodates addition framing (2×4 basement walls, floor system, exterior + interior walls, roof gable, sheathing, LVL install/shoring, elevator shaft). Per editor_rules "Framing, labor_hours=146, crew=3 → 6d → split," which matches this row exactly. Good data.

- **Row 23 Drywall labor is 159 hrs, ~9d @ crew 3** — covers addition + existing bedroom + basement storage per the row title. Consolidate per editor_rules "drywall consolidation" guidance. Editor rules explicitly cite `labor_hours=159, crew=3 → 9–11 working days consolidated`, which matches.

- **Row 20 Plumbing – 40 hrs, ~2.5d @ crew 2** — LOW for a job with master bath (dual lav, toilet, custom shower with dual diverter) + W/D relocation + vent-through-roof. Rule 4H / editor rules "Plumbing rough-in" default is **4 days × 2 crew for any job with master bath / 2+ bath fixtures / W/D relocation** (Will's transcript nominal). CSV's 40 hrs implies ~2.5d which VIOLATES the 4d floor. Duration must be overridden to 4d per Rule 4H — flag as `labor_hours vs. Will's nominal` anomaly.

- **Row 18 Windows/Doors – 44 hrs** — 4 windows (3× 36″×60″ DH + 1 transom) + 1 exterior door. At 2 people that's ~2.75 days, which lines up with editor rules "~3 windows/day install."

- **Row 24 Interior Finish Carpentry, Painting & Flooring – 162 hrs** — largest single row. Bundles LVT flooring, baseboard (5-1/4″ MDF), 2-1/4″ casing, primer + 2 coats paint, and interior door install. This is the two-phase paint work per Rule 4E — decompose into paint.phase_1 (1d), paint.phase_2 (1d), flooring.install (2–4d), trim.install (2–3d), interior_doors.install.

- **Row 13 Excavation/Foundation Equipment = $1,950** — highest equipment cost in CSV. Aligns with scope's backhoe usage rate ($1,100/wk) + dump trailer runs ($450 each). Suggests ~1.5–2 weeks of machine time on site.

- **Total labor hours = 1,287** — at nominal ~40 hrs/person-week and typical 2-person average, ballpark 16 person-weeks of on-site labor. On-site duration will be driven by dependency chains, not raw labor hours; expect ~55–70 working days on-site based on comparable addition patterns.

- **No procurement / lead-time line items in CSV** — all procurement is invisible to the summary tab (materials rolled up). Schedule must derive procurement tasks from scope: windows (14–21 d), LVL (7–14 d for 3-ply 14″), mini-split (7–14 d), tankless WH if in (7–14 d), electrical panel (7–14 d), tile custom (14–21 d). Trusses conditional per belief `stick_frame_default_for_small_additions` — the addition is 30′×10′ = 300 SF footprint, well under the 800 SF / 24-ft-span thresholds AND scope explicitly says "truss or rafter framed — determined during design phase," so stick-frame default applies. No `procurement.trusses`.
