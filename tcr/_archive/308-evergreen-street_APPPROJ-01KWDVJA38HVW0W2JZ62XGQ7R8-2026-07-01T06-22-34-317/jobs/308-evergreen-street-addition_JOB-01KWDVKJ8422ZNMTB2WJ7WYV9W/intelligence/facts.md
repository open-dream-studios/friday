---
generation_kind: intelligence_rebuild_v2
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWDVJA38HVW0W2JZ62XGQ7R8/jobs/308-evergreen-street-addition_JOB-01KWDVKJ8422ZNMTB2WJ7WYV9W/manifest.json
  - _projects/308-evergreen-street_APPPROJ-01KWDVJA38HVW0W2JZ62XGQ7R8/jobs/308-evergreen-street-addition_JOB-01KWDVKJ8422ZNMTB2WJ7WYV9W/inputs/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KWDVJA38HVW0W2JZ62XGQ7R8/jobs/308-evergreen-street-addition_JOB-01KWDVKJ8422ZNMTB2WJ7WYV9W/inputs/files/308_Evergreen_Addition.xlsx - Summary (1).csv.txt
  - _projects/308-evergreen-street_APPPROJ-01KWDVJA38HVW0W2JZ62XGQ7R8/jobs/308-evergreen-street-addition_JOB-01KWDVKJ8422ZNMTB2WJ7WYV9W/inputs/files/3725 SIMONS 012226.pdf.txt
  - _projects/308-evergreen-street_APPPROJ-01KWDVJA38HVW0W2JZ62XGQ7R8/jobs/308-evergreen-street-addition_JOB-01KWDVKJ8422ZNMTB2WJ7WYV9W/intelligence/extracted/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KWDVJA38HVW0W2JZ62XGQ7R8/jobs/308-evergreen-street-addition_JOB-01KWDVKJ8422ZNMTB2WJ7WYV9W/intelligence/extracted/breakdown.md
  - _projects/308-evergreen-street_APPPROJ-01KWDVJA38HVW0W2JZ62XGQ7R8/jobs/308-evergreen-street-addition_JOB-01KWDVKJ8422ZNMTB2WJ7WYV9W/intelligence/extracted/plans.md
  - _projects/308-evergreen-street_APPPROJ-01KWDVJA38HVW0W2JZ62XGQ7R8/jobs/308-evergreen-street-addition_JOB-01KWDVKJ8422ZNMTB2WJ7WYV9W/intelligence/applicable_rules.json
  - _company/rules/dev_rules.md
  - _company/rules/editor_rules.md
  - _company/rules/pep_rules.md
  - job_types/addition/rules/addition_rules.md
  - job_types/addition/rules/tdec_septic_permit_offset.md
---
# Facts — what we know

## Customer & job

- Job type: **addition** (manifest.json).
- Customer / site: **308 Evergreen Street** (manifest.json) — customer surname likely Simons per CSV project label and drawing set title.
- Project ID: `APPPROJ-01KWDVJA38HVW0W2JZ62XGQ7R8`; Job ID: `JOB-01KWDVKJ8422ZNMTB2WJ7WYV9W` (manifest.json).
- Status: `in_progress`; started 2026-07-01 (manifest.json).
- No scheduled on-site start date recorded on the job yet.

## Scope

- **Two-story addition, ~30' × 10' footprint** — basement storage below + second-floor expansion of primary bedroom + master bath + walk-in closet above (scope.md L3-6).
- CSV pegs footprint at **789 sqft**; plans state **590 sqft** total addition area (295 first floor + 295 basement). Discrepancy flagged — CSV likely counts the second-floor remodel envelope; **needs PM confirmation** (extracted/plans.md discrepancy #1).
- **Grand total (internal): $100,779**; customer-facing quote: $173,850 (extracted/breakdown.md, scope.md).
- **1,287 total labor hours** across 16 breakdown sections (extracted/breakdown.md).
- Comply with **IRC 2018 + NEC** (scope.md L11).

## Site & existing conditions

- **Home is on septic** per scope's TDEC references (scope.md L33-40). **Not confirmed** — scope also mentions "grinder pump system to connect to available sewer line" as an alternative, so the property may have city-sewer availability. **CRITICAL PM question** (see questions.md q.septic_or_sewer).
- **Existing heat pump + electrical disconnect are in the way of the addition** and must be relocated before demo (scope.md L44) — this is Rule 4K territory; goes in `site_prep.prep_work_before_demo`, NOT in demo phase (rule: company:_company/rules/dev_rules.md Rule 4K, rank 100).
- **Existing gas water heater vent must be extended through the new roof** — indicates the existing WH stays in place. This is a vent-extension scope only (scope.md L45).
- **Chimney adjacent to roof tie-in** (plans sheet 5). Adds change-order risk to `roof.concealed_buffer`.
- Standard soil conditions assumed; rock excavation / unsuitable soils = change order (scope.md L18-20).
- Concealed conditions inside existing walls (wiring, plumbing, structural) = change order (scope.md L21-24).
- (2) existing windows will be **relocated** — retrofit framing not called out separately in scope but shown on plans (extracted/plans.md retrofit indicators).

## Trades

### Structural
- **(1) 3-ply 14" LVL beam spanning ~15'-6"**, replaces existing load-bearing wall, temporary shoring required (scope.md L61-64). Standard LVL default lead time 14 calendar days safety; pressure-treated or custom = 21 days (rule: job_type:job_types/addition/rules/addition_rules.md, rank 200 — "Structural long-lead items").
- **LVL is an independent retrofit sub-chain** (per addition_rules): does NOT gate new floor framing UNLESS new floor/roof load actually bears on the LVL location. **PM Interview needed** to confirm load-bearing dependency.

### Foundation
- **Monolithic default applies** — Rule 4B: continuous 12" × 12" footings + 4" gravel + vapor + rebar + 4" slab, one pour, one footing inspection covers both (rule: company:_company/rules/dev_rules.md Rule 4B, rank 100). Scope explicitly excludes CMU / stem walls (scope.md L54).

### Framing
- Floor system, walls, and elevator shaft framing rolled into one CSV section (Framing: 146 labor hours). Elevator shaft is **inside the addition footprint** per plans — not a retrofit signal (extracted/plans.md).
- **Roof: gable, 3/12 pitch tying into existing 6/12** (scope.md L69-71). Truss vs. rafter framing "determined during design phase" — this is Rule 4Q ambiguity language; **default = stick-frame** for a 30'-span footprint (rule: job_type:job_types/addition/rules/addition_rules.md — trusses conditional, rank 200). **PM Interview should confirm.**

### Roofing
- Architectural asphalt shingles matching existing, synthetic underlayment, drip edge, flashing, ridge vent, fascia, vinyl soffit, seamless gutters (scope.md L73-80). One roofing crew handles siding + trim + fascia + gutters as a same-crew block per editor rules (rule: company:_company/rules/editor_rules.md — same-crew exterior pattern, rank 100).
- **Concealed roof tie-in change-order buffer required** (rule: job_type:job_types/addition/rules/addition_rules.md, rank 200): 2-3 day discovery buffer inside `framing.roof`, SS lag 1.

### Electrical
- **(1) new 100A subpanel** (scope.md L106). **Amperage check on existing main service required** per addition_rules — scope explicitly assumes existing service can support the subpanel but has NOT verified. Emit `prep.amperage_check` in `pre_construction` with `pre_construction_offset_working_days: 15` (rule: job_type:job_types/addition/rules/addition_rules.md — existing electrical service, rank 200; company:_company/rules/editor_rules.md — pre_construction_offset, rank 100).
- **Subpanel install = 1 day, 1 person** (rule: company:_company/rules/editor_rules.md — productivity table, rank 100).
- ~12 recessed lights, 3 master closet outlets, storage outlets, dimmer switches, GFCI/AFCI per code, (1) dedicated 120V/30A elevator circuit (scope.md L108-119).
- (1) existing hallway switch relocated with drywall patch, prime, paint (scope.md L114) — retrofit; roll patch into `drywall.consolidated`.

### Plumbing
- Full rough-in: supply, waste, vent (scope.md L124).
- **Master bath fixtures**: (2) lavs + (1) toilet + (1) custom dual-valve-diverter shower (scope.md L126-130).
- **W/D relocation** including water, drain, roof vent (scope.md L131).
- **Vent stacks extended through new roof** (scope.md L132).
- Rule 4H applies to tank set order — **but only if scope adds/replaces a water heater**. Current base scope keeps existing WH (vent extension only), so `plumbing.tank_set` is NOT needed unless the Tankless WH optional package is exercised. **PM Interview needed** to confirm inclusion of optional tankless.
- **Rule 4H / plumbing.rough_in default = 4 working days × 2 crew** for master bath + W/D relocation + vent stacks — CSV's 40 labor hours understates real duration (rule: company:_company/rules/editor_rules.md — Will's nominal, rank 100). Set duration_days = 4, crew_size = 2 regardless of the 40-hr CSV number.

### HVAC
- **(1) ductless mini-split system**, $2,500 budget (scope.md L136-137) — **mini-split rough = 0.5d × 1 person; install = 1d × 1 person** (Rule 4G + editor productivity, rank 100).
- **MEP rough order for mini-split jobs**: plumbing → electrical → mini-split rough (Rule 4G).
- **Existing HVAC components relocated as required** (scope.md L138) — goes into `site_prep.prep_work_before_demo` component (Rule 4K).

### Insulation
- R13 exterior walls, R30 attic/roof, R30 floor between basement and living space (scope.md L142-146).

### Interior finishes (base)
- LVT throughout, $3/sqft budget (scope.md L154).
- 5-1/4" MDF or finger-jointed pine baseboard; 2-1/4" casing profile (scope.md L155-156).
- Level 3 drywall finish everywhere (scope.md L152).
- Primer + 2 finish coats (scope.md L153) — Rule 4E: paint is ALWAYS two phases (rank 100). `paint.phase_1` = primer + ceiling finish AM+PM; `paint.phase_2` = final wall coat AFTER all finish trades.
- (4) interior doors: (1) pre-hung + (2) pocket + 1 unspecified (scope.md L158-161).

### Master bathroom
- Custom tile shower ~7' × 4', tile walls + mosaic floor, niche, bench, dual-valve diverter, 72" double vanity, (2) faucets/mirrors/lights, commode, exhaust fan/light vented exterior (scope.md L163-172).
- **Tile → apply Rule 6 productivity bump**: tile always takes longer than labor accounting says; split into substrate + install + grout_seal.

### Retrofit items
- **Existing hall bath modification** — remove existing window, frame opening, insulate, drywall patch, remove tub/shower, install acrylic shower using existing valve+trim, PVC trim, patch+repaint (scope.md L187-194).
  - Retrofit signals: **Signal A** (hall bath is NOT in addition objective) AND **Signal B** ("existing" keyword used repeatedly). Both trip; goes in its own retrofit Component (rule: company:_company/rules/dev_rules.md Rule 4V + job_type:addition_rules — retrofit heuristic, rank 200).
  - **The acrylic shower swap is a strong customer-requested-early-item candidate** — addition_rules literally names "308 example: hall bath acrylic shower swap, customer wanted a fresh shower before the job broke ground" (rule: job_type:job_types/addition/rules/addition_rules.md, rank 200 — customer_early_items). **PM Interview MUST confirm** — if confirmed, split into TWO buckets per Rule 4V: `early.acrylic_shower_swap` in `site_prep.customer_early_items` (Day 1) + `hall_bath_mod` in `interior_finishes` for window infill + drywall patch + repaint.
- **Primary bedroom remodel** (~12'5" × 16') — modify framing, drywall Level 3, prime+paint, new LVT, full trim (scope.md L174-179). Objective explicitly names "second-floor expansion of the primary bedroom" — bedroom is part of the addition envelope; work is addition-tie-in retrofit, not a standalone retrofit component. Consolidate drywall + paint into main blocks.
- **Basement storage finish** — frame + drywall + Level 3 + paint + light, concrete floor unfinished (scope.md L181-184). This is inside new addition footprint; treat as main-scope not retrofit.
- **Elevator shaft** — RESOLVED as new-addition-scope per plans (extracted/plans.md). Not a retrofit signal.

## Sequencing

- **Phase spine**: pre_construction → procurement_long_leads → site_prep → demo_and_protection → structural_and_shell → rough_trades → rough_inspections → insulation_and_drywall → interior_finishes → finish_trades → closeout (rule: company:_company/rules/editor_rules.md phase spine + job_type:addition_rules procurement-phase rule, rank 200).
- **MEPs gated on `roofing.underlayment` + `windows.install`** — NOT on `milestone.dried_in` (rule: job_type:addition_rules — MEPs gated on underlayment+windows, rank 200; also Rule 4I rank 100).
- **Windows install FS after `framing.roof`** — NOT after dried-in (Rule 4J + addition_rules).
- **Rough inspections BUNDLED**: rough electrical + rough plumbing + rough HVAC + framing all one day, one inspector, then 2-day punch-list buffer (Rule 4C + 4D).
- **Final inspections BUNDLED**: all 3 finals + final building on one day (Rule 4M).
- **Interior trade cap = 2 concurrent**; standard 3-trade overlap (electrical finish + plumbing finish + mini-split install) → **HVAC serializes after electrical finish** (Rule 4N default stagger).
- **Paint phase 2 gates on EVERY finish trade** — trim, flooring, cabinets/vanity, tile grout, plumbing finish, electrical finish, mini-split install (Rule 4F). Substantial completion FS-after paint.phase_2 only.
- **Selections-finalized checkpoint** MANDATORY, `pre_construction_offset_working_days: 15`, gates finish-material procurement (Rule 4P).
- **Will's final walkthrough** is the last task in the schedule, FS lag 1 after `inspect.final_bundled` (rule: job_type:addition_rules — Will's walkthrough, rank 200).

## Procurement

- All non-trivial procurement uses the **3-task order/wait/checkpoint pattern** in the `procurement_long_leads` phase (Rule 4R + addition_rules "CRITICAL: do NOT put procurement chains in pre_construction").
- **Windows**: (2) new (per plans schedule; possibly (4) per scope) — **stock 14-21d OR custom 28-42d**, unknown. **PM Interview needed.**
- **LVL beam (3-ply 14")**: standard = 14 calendar-day default safety; PT/custom = 21 days. **PM Interview needed.**
- **Electrical panel (100A subpanel)**: 14-21 days per editor rules lead table.
- **Mini-split unit**: 7-14 days; order tied to dried-in, not project start (rule: company:_company/rules/editor_rules.md — mechanical equipment exception, rank 100).
- **Tankless WH** (if optional package exercised): 7-14 days; would trigger `procurement.tank` + `plumbing.tank_set` FIRST per Rule 4H.
- **TDEC septic permit**: `kind: lead_time`, `lead_time_days: 42` (calendar, ~6 weeks), `pre_construction_offset_working_days: 30` — MANDATORY if home is on septic (rule: job_type:job_types/addition/rules/tdec_septic_permit_offset.md, rank 200). Gates `excavation.dig` via FS. **PM Interview needed** — confirm septic vs. city sewer.
- **General permit** (`general.permitting`): `kind: work`, 1d, `pre_construction_offset_working_days: 15` (Rule 4A).
- **Tile (custom, $3-6/sqft allowances)**: 14-21 days; order ~3 weeks before tile install (addition_rules).
- **LVT, paint, standard fixtures**: 7-day supplier or collapsed 1-day order task 1 week before install.

## Risks & open items (in priority order)

1. **TDEC septic gate** — if the home is on septic, TDEC is the 6-week critical-path anchor. Cannot proceed with excavation until permit issued. Property-verification question is CRITICAL.
2. **Roof framing method (trusses vs. stick)** — scope leaves this to design phase. Default stick-frame per rule; if PM overrides to trusses, add 4-6 week procurement chain.
3. **Customer early item (hall bath acrylic swap)** — literal example from addition_rules for THIS site. If confirmed, Rule 4V two-bucket split required.
4. **Concealed roof tie-in** — chimney adjacent; existing rafter conditions unknown until demo opens ceiling. 2-3 day discovery buffer required.
5. **Amperage verification** — subpanel scope assumes existing service capacity; no verification task in CSV. Emit `prep.amperage_check`.
6. **Tankless WH optional package** — CSV title claims "Incl. Tankless WH Option" but HVAC section material ($5,140) doesn't clearly include the $6,500 tankless allowance. If tankless IS in scope, Rule 4H applies (tank set FIRST).
7. **LVL load-bearing dependency** — if new floor/roof load bears on LVL location, framing gates on LVL install. If independent (common), LVL sub-chain runs parallel.
8. **Window count / dimension mismatch** — plans schedule (2 new) vs. scope (4 windows, some relocated). Order quantity uncertain.
