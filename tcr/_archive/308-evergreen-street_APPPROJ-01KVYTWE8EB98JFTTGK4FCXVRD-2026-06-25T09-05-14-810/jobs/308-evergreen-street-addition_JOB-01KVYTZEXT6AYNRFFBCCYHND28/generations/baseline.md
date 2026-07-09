---
generation_kind: baseline_estimate_v1
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KVYTWE8EB98JFTTGK4FCXVRD/jobs/308-evergreen-street-addition_JOB-01KVYTZEXT6AYNRFFBCCYHND28/inputs/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KVYTWE8EB98JFTTGK4FCXVRD/jobs/308-evergreen-street-addition_JOB-01KVYTZEXT6AYNRFFBCCYHND28/inputs/files/scope.pdf.ref.json
  - _projects/308-evergreen-street_APPPROJ-01KVYTWE8EB98JFTTGK4FCXVRD/jobs/308-evergreen-street-addition_JOB-01KVYTZEXT6AYNRFFBCCYHND28/inputs/files/308_Evergreen_Addition.xlsx - Summary (1).csv.ref.json
  - _projects/308-evergreen-street_APPPROJ-01KVYTWE8EB98JFTTGK4FCXVRD/jobs/308-evergreen-street-addition_JOB-01KVYTZEXT6AYNRFFBCCYHND28/inputs/files/3725 SIMONS 012226.pdf.ref.json
  - _projects/308-evergreen-street_APPPROJ-01KVYTWE8EB98JFTTGK4FCXVRD/jobs/308-evergreen-street-addition_JOB-01KVYTZEXT6AYNRFFBCCYHND28/manifest.json
  - _company/rules/editor_rules.md
  - _company/rules/dev_rules.md
  - _company/knowledge/308_evergreen_wills_audit_transcript.md
  - _company/knowledge/_examples/wills_voice.md
  - _company/beliefs/_examples/stick_frame_default_for_small_additions.md
  - job_types/addition/rules/addition_rules.md
  - job_types/addition/rules/tdec_septic_permit_offset.md
  - job_types/addition/beliefs/stick_frame_default_for_small_additions.md
  - job_types/addition/reference_jobs/index.md
last_verified_at: "2026-06-25T07:37:12.110Z"
---

# Baseline estimate — 308 Evergreen Street two-story addition

- **Job:** JOB-01KVYTZEXT6AYNRFFBCCYHND28
- **AppProject:** APPPROJ-01KVYTWE8EB98JFTTGK4FCXVRD — 308 Evergreen Street
- **Job type:** addition (two-story, ~30'×10' footprint, 789 sqft total per breakdown header)
- **Customer total (scope.pdf, "Total Investment" line):** **$173,850** (base scope, exclusive of two optional packages)

## Input provenance — read this first

The trunk's hydration loop has uploaded the three input ref.json pointers (scope.pdf, the Excel-summary CSV, the architect's 3725 SIMONS PDF) but has not yet emitted the `.txt` extractions next to them. This baseline is grounded in the equivalent content sourced from the PM_AUDIT working copies of the same files (`PM_AUDIT/308_Scope.txt` and `PM_AUDIT/308_Evergreen_Addition.xlsx - Summary (1).csv`), which Will and Joey reviewed together — the discussion is captured in `_company/knowledge/308_evergreen_wills_audit_transcript.md`. When the trunk-side `.txt` files land, content-hashes should match these external copies; if they don't, this baseline is stale and must regenerate.

## Scope summary (from scope.pdf)

Two-story addition tying into an existing single-family home. Lower level is unfinished storage on a 4" slab over 12"×12" perimeter footings (monolithic pour). Upper level expands the primary bedroom, master bathroom, and walk-in closet. New construction: gable roof at 3/12 tying into existing 6/12, vinyl siding to match, (4) windows + (1) exterior door, 100A subpanel, mini-split HVAC, custom 7'×4' tile shower with niche/bench, 72" double vanity, LVT flooring.

**Long-lead and structural items called out by scope:**
- TDEC septic coordination explicitly named ("Coordinate and complete septic inspection with TDEC … determine feasibility of relocating septic system or installing new septic tank and leach field"). Costs of septic relocation / grinder pump are CO placeholders — NOT in base price.
- (1) 3-ply 14" LVL spanning ~15'-6" with temporary shoring (retrofit sub-chain; opens existing load-bearing wall).
- Future elevator shaft framed only (4'×4') with a dedicated 30A circuit; elevator system NOT included.
- "Truss or rafter framed, determined during design phase" — scope ambiguous; defaults to **stick-frame** per `_company/beliefs/_examples/stick_frame_default_for_small_additions.md` (sub-800-sqft addition with sub-24' span, 3/12 over 30'×10').

**Retrofit + customer-early-item scope captured by section 16:**
- Existing hall bathroom: remove window + insulate/drywall/finish; remove tub-shower combo and install acrylic shower (reuse existing valve). The acrylic shower swap is the **customer-requested early item** (transcript lines 659–665 — homeowner wanted a fresh shower BEFORE the job broke ground); the rest of the hall-bath retrofit is mid-job retrofit work. Two buckets, same room, per `_company/rules/editor_rules.md` "Customer early items — the TWO-BUCKET pattern" and `_company/rules/dev_rules.md` Rule 4V.
- Existing primary bedroom remodel (~12'5"×16'): demo/reframe as required, drywall, paint, new LVT, full trim. Drywall consolidates into the main `drywall.consolidated` block per addition_rules.md.
- Heat-pump + electrical-disconnect relocation BEFORE main demo (addition_rules.md "Heat pump / HVAC component relocation"; transcript lines 274–278 — minimum 3 working days before demo).
- Existing gas WH vent **extended through new roof** — existing tank stays. **No `procurement.tank` / `plumbing.tank_set` task** per dev_rules.md Rule 4H scope condition. Tankless WH is an **optional package** ($6,500 allowance), not in base.

## Direct cost subtotal (from 308_Evergreen_Addition CSV)

| Bucket | Amount | Source line |
|---|---:|---|
| Labor | $45,167.59 | CSV "Project Totals → Labor Cost" |
| Material | $52,171.33 | CSV "Project Totals → Material Cost" |
| Equipment | $3,440.00 | CSV "Project Totals → Equipment Cost" |
| **Direct subtotal (Grand Total)** | **$100,778.92** | CSV "Project Totals → Grand Total" |
| **Labor hours** | **1,287** | CSV "TOTALS" row |

### Per-section direct cost (CSV verbatim — labor / material / equipment / total / hours)

| # | Section | Labor | Material | Equip | Section total | Hours |
|---|---|---:|---:|---:|---:|---:|
| 1 | General Conditions, Permitting & Pre-Construction | $2,316.08 | $2,130.00 | $0.00 | $4,446.08 | 56 |
| 2 | Selective Demolition & Site Work | $1,982.00 | $2,040.00 | $220.00 | $4,242.00 | 56 |
| 3 | Excavation, Foundation – Footings & Slab | $2,698.60 | $2,416.18 | $1,950.00 | $7,064.78 | 78 |
| 4 | Structural Modifications – LVL Beam & Shoring | $2,117.80 | $2,422.00 | $0.00 | $4,539.80 | 60 |
| 5 | Framing – Floor System, Walls & Elevator Shaft | $5,037.50 | $8,850.05 | $120.00 | $14,007.55 | 146 |
| 6 | Roof Framing, Sheathing & Roofing System | $3,319.80 | $5,997.50 | $335.00 | $9,652.30 | 96 |
| 7 | Exterior Finishes – Siding, Trim & Gutters | $2,474.70 | $2,696.61 | $560.00 | $5,731.31 | 72 |
| 8 | Windows, Exterior Door & Weatherproofing | $1,493.80 | $2,172.00 | $0.00 | $3,665.80 | 44 |
| 9 | Electrical – 100A Subpanel, Rough-In & Finish | $3,042.00 | $3,680.13 | $0.00 | $6,722.13 | 78 |
| 10 | Plumbing – Rough-In, Master Bath & W/D Relocation | $1,356.80 | $2,160.00 | $0.00 | $3,516.80 | 40 |
| 11 | HVAC – Mini Split, Tankless WH & Relocations | $1,363.36 | $5,140.00 | $0.00 | $6,503.36 | 36 |
| 12 | Insulation & Air Sealing | $1,493.80 | $1,590.64 | $0.00 | $3,084.44 | 44 |
| 13 | Drywall – New Addition & Existing Bedroom | $5,428.35 | $3,647.35 | $255.00 | $9,330.70 | 159 |
| 14 | Interior Finish Carpentry, Painting & Flooring | $5,540.30 | $7,291.28 | $0.00 | $12,831.58 | 162 |
| 15 | Master Bathroom – Custom Tile Shower & Finishes | $3,017.90 | $4,136.60 | $0.00 | $7,154.50 | 88 |
| 16 | Existing Hall Bath Mod, Bedroom Remodel & Closeout | $2,484.80 | **−$4,199.00** | $0.00 | **−$1,714.20** | 72 |

**Section 16 anomaly.** Material line is negative ($-4,199). This is Will's manual "10% material reduction" applied as a credit on the closeout line — he flagged it during audit ("Wills modification, 10% reduction in material … I shouldn't have, I'll just roll with it anyway", transcript lines 42–46). Per dev_rules.md §12, negative section totals at low labor hours are usually credits or a "subtract from prior bid" line, not real work. Confirmed here. The labor portion of section 16 ($2,485 / 72 hrs) IS real work: customer-early-item acrylic shower swap (~1 day, ~16 hrs); hall bath window-infill retrofit drywall/finish; bedroom-remodel drywall/paint/trim; closeout walkthrough + punch list.

## Customer total — gap reconciliation

| | Amount |
|---|---:|
| Customer total (scope.pdf "Total Investment") | $173,850.00 |
| Direct cost subtotal | $100,778.92 |
| **Gross gap (markup spread)** | **$73,071.08** |

The scope's `Rates` block lets us trace the gap mechanically:

- **Labor at sell.** Base $70/hr × 1,287 hrs = $90,090. Trade differentials: plumbing 40 hrs × +$40 = $1,600; electrical 78 hrs × +$30 = $2,340; HVAC 36 hrs × +$30 = $1,080. Team-lead differential (+$15/hr) applied to an estimated ~30% of hours ≈ $5,790. **Labor sell ≈ $100,900.** Loaded direct labor at $45,168 / 1,287 hrs = **$35.10/hr fully-burdened wage cost** — a clean 2× revenue-to-cost ratio for labor, consistent with TCR's owner-operator structure.
- **Material at sell.** $52,171 × 1.15 (cost + 15% per scope) = **$59,997.** This assumes no items are billed at cost+30% sub markup; in practice some specialty material (mini-split, LVL) may move through subs and earn the higher markup.
- **Equipment at sell.** $3,440 direct; the scope's $450-per-dump and $1,100/wk backhoe rates suggest equipment is billed near cost. Call it **~$3,500–$5,000.**
- **Reconciled sell subtotal ≈ $164,400–$165,900.**
- **Remaining ~$8,000–$9,500** = PM overhead + contingency + warranty reserve + profit. Plausible given Will's 1-year warranty on drywall tie-in cracks (transcript lines 805–809) and his policy of treating customer-add work after-the-fact rather than pricing it tight.

This is a ~72% markup over direct cost, or ~42% gross margin. Within TCR's normal envelope for an owner-PM'd addition; nothing flags as mispriced.

**Not included in $173,850:**
- Optional Closet & Cabinet System: +$7,000 allowance
- Optional Tankless Water Heater: +$6,500 allowance (scope already extends existing tank's vent through new roof; tankless is an upgrade)
- TDEC septic relocation / new tank / leach field / grinder pump — explicit change-order placeholders, NOT in base
- Rock excavation, unsuitable soils, additional structural work uncovered during demo, concealed-condition surprises — all CO placeholders

## Pre-construction runway estimate

**Anchor: TDEC septic — 6 weeks before on-site start.**

Per `job_types/addition/rules/tdec_septic_permit_offset.md` (severity `hard`) and addition_rules.md "Septic — TDEC, the long-lead permit": `permit.tdec_septic` is `kind: lead_time`, `lead_time_days: 42` (calendar), `pre_construction_offset_working_days: 30`. Will's number from the audit (transcript lines 158–171): "six weeks, the most non-typical thing — can come in faster, can drag … plan for six and you'll be safe." Rule applies because scope explicitly names TDEC AND the addition adds a bathroom + W/D relocation (TDEC-counted fixtures).

| Pre-con anchor | Lead | Trigger |
|---|---:|---|
| TDEC septic permit | **6 weeks calendar** | Scope names septic + new bath; assumes home is on septic (verify in PM Interview). |
| Custom windows? | 4–6 weeks if custom; 2–3 weeks if stock | Verify with PM. Scope budgets $300/window, suggesting stock — call it ~3 weeks. |
| LVL beam (3-ply 14", ~15'-6" span) | 1–3 weeks | Standard LVL is ~1 week, but addition_rules.md defaults to `lead_time_days: 14` for safety. Pressure-treated would push to 3 weeks. Verify spec. |
| Mini-split unit | 1–2 weeks | Order at dried-in (mid-build), NOT pre-con. |
| Permit walk-in | 1 day, 3 weeks before on-site | Will: walks in / out same day ~90% of the time (transcript line 134). |
| Selections finalized | 1 day, 3 weeks before on-site | Latest acceptable per Will (transcript line 192). |
| Existing service amperage check | 0.5 day, 3 weeks before on-site | Required because subpanel is in scope (addition_rules.md "Existing electrical service"). |
| Equipment confirmed (dumpster, mini-ex, skid steer, concrete saw) | 0 (milestone), 2 weeks before on-site | addition_rules.md Rule 4O. |

**Pre-construction runway: 6 weeks**, gated by TDEC. Permits/selections/amperage/equipment confirmations all land inside that window.

## On-site duration estimate

Working-day counts (Mon–Fri, federal holidays excluded). Crew sizes and productivity from `_company/rules/editor_rules.md` "Default crew sizes and productivity" table unless overridden. Heuristic: `duration_days ≈ labor_hours / (crew × 8)`, then rounded and tuned per dev_rules.md §6.

| # | Phase / work block | Days | Reasoning |
|---|---|---:|---|
| 1 | Site setup, dumpster + equipment delivery, heat-pump relocate, electrical disconnect relocate, **acrylic shower swap (customer early item)** | 1–2 | Day 1 prep; acrylic swap runs concurrent (transcript lines 659–665, two-bucket pattern). |
| 2 | Demolition + utility prep (post-relocation) | 2–3 | 56 hrs / (3 demo × 8) ≈ 2.3d; round to 2–3. |
| 3 | Excavation | 1–2 | Mini-ex, 78 hrs across foundation section split into excavation + form/inspect/pour. |
| 4 | Foundation form + prep (footings + gravel + vapor + rebar, monolithic) | 1.5 | dev_rules.md Example A: ONE consolidated form/prep task. |
| 5 | Footing inspection (covers both footing and slab for monolithic) | 0.5 | Rule 4B. |
| 6 | **Monolithic pour** (footings + 4" slab same day) | 1 | Rule 4B; scope's 4" slab + 12"×12" footings is canonical monolithic. |
| 7 | Foundation cure | 2 cal-d | Rule 4B; lead_time, not duration. |
| 8 | Basement walls + floor system + subfloor + exterior + interior walls | 9–10 | 146 framing hrs / 3 crew. Per editor_rules.md template: basement walls 2d + floor 2d + ext walls 3d + int walls 2d + elev shaft 1d. |
| 9 | LVL retrofit (expose wall + temp shore + install + remove shoring) | 2 | Independent sub-chain per addition_rules.md "LVL temporary shoring — independent retrofit." Runs PARALLEL with main framing. |
| 10 | Roof framing (3/12 stick-frame into existing 6/12) + sheathing | 3–4 | 96 hrs section, but split across framing + roofing. Stick-frame default. |
| 11 | **Concealed roof tie-in discovery buffer** | 3 cal-d, SS lag 1 on framing.roof | addition_rules.md "Concealed roof tie-in — change order risk." Runs concurrent with framing.roof, not after. |
| 12 | Roof underlayment + drip edge + flashing | 1 | editor_rules.md productivity. |
| 13 | Shingles | 1 | Will: "up to 6,000 sqft in 1 day" (transcript line 420). |
| 14 | **Windows + exterior door install (gated on framing.roof + procurement, parallel with underlayment)** | 1.5–2 | 4 windows + 1 door = ~5 openings, 3/day = 1.5d. addition_rules.md "Windows install — IMMEDIATELY after roof framed." |
| 15 | Exterior siding + fascia/soffit + gutters (same-crew block) | 5–6 | Editor_rules.md "Same-crew exterior pattern." Runs PARALLEL with rough trades + interior dry-in. |
| 16 | Plumbing rough-in (master bath + W/D relocate + vent stack extension) | **4** × 2 crew | Will hard rule (transcript line 484, "four days for two guys, that's fine"). Existing WH stays — NO tank_set. Gated on roofing.underlayment + windows.install, NOT dried-in milestone (addition_rules.md "MEPs gated on underlayment + windows"). |
| 17 | Electrical rough-in + subpanel | 1.5 + 1 (1 person) | Subpanel = 1d × 1 person (transcript line 474). SS-overlapped with plumbing. |
| 18 | Mini-split rough (line set only) | 0.5 × 1 person | Will: "1 guy half a day" (transcript line 482). |
| 19 | **Bundled rough inspection** (electrical + plumbing + mini-split + framing — ONE inspector, ONE day) | 0.5 | dev_rules.md Rule 4C; transcript lines 506–513. |
| 20 | Post-rough punch-list buffer | 2 working days | dev_rules.md Rule 4D; transcript lines 530–532 ("two to four day, depending on the job"). Default 2. Insulation material delivered SAME day as inspection (editor_rules.md). |
| 21 | Insulation air seal + install | 1 | Typical addition = 1 day (editor_rules.md). |
| 22 | Insulation inspection | 0.5 | Procedural — Will: "you have to be a dumbass to fail" (transcript line 585). |
| 23 | **Drywall consolidated** (hang + tape + sand + prime, addition + bedroom + hall-bath patch all in one block) | 9–11 | 159 hrs / 3 crew. Editor_rules.md says 9–11 for typical addition; Will: "maybe 9 days, 11 is on the high end" (transcript line 627). Bedroom + hall-bath retrofit drywall rolled in per addition_rules.md "Retrofit drywall consolidates into main drywall block." Plan **10**. |
| 24 | Paint phase 1 (prime walls + ceilings AM, ceiling finish PM, optional roll on walls) | 1 | dev_rules.md Rule 4E; transcript line 629 — Will's standard 1-day sequence. |
| 25 | Tile shower substrate (waterproofing) | 1 | After paint phase 1 (Rule 4L). |
| 26 | Tile shower install (custom 7'×4', niche + bench, mosaic floor) | 4–5 | 88 hrs / 2 crew = 5.5d; bump for finish-heavy (dev_rules.md §6.3). The long pole of interior finishes. |
| 27 | LVT flooring (gated on paint.phase_1 + shower-pan-set) | 2–3 | ~250 sqft/day; addition footprint + bedroom remodel = ~600 sqft. |
| 28 | Tile grout + seal | 1 | |
| 29 | Cabinets / vanity install (72" double vanity) | 0.5–1 | Vanity ~0.5d (editor_rules.md). |
| 30 | Trim install (base, case, interior doors, hall bath PVC trim) | 2–3 | 162 hrs section split across paint + flooring + trim. |
| 31 | Electrical finish (recessed lights, devices, exhaust fan/light, dimmer switches) | 2–3 | Gated on paint phase 1, NOT paint phase 2 (Rule 4L). |
| 32 | Plumbing finish (vanity hookup, shower trim, valve, toilet) | 2 | After cabinets + flooring + tile (Rule 4L). |
| 33 | Mini-split install | 1 × 1 person | **Staggered AFTER electrical finish** per dev_rules.md Rule 4N (HVAC stagger rule) — keeps interior trades at 2-max. |
| 34 | Hall bath repaint + bedroom paint touchups | (rolled in) | Inside section 14 / 16. |
| 35 | **Paint phase 2** (LAST work task; predecessors include every finish trade) | 1 | dev_rules.md Rule 4F. Fires `milestone.substantial_completion`. |
| 36 | Bundled final inspection (electrical + plumbing + HVAC + building, ONE day) | 0.5 | dev_rules.md Rule 4M; transcript lines 820–823. |
| 37 | Client walkthrough + punch list signed (Will's SOP form) | 0.5 | Transcript lines 783–796. |
| 38 | Punch-list returns | 1–3 | Will: "anywhere between 1 and 3 days" (transcript line 829). |
| 39 | Paint touch-ups + final clean | 1 | |
| 40 | **Will's personal final walkthrough with customer** | 0.5 | addition_rules.md "Will's walkthrough — final closeout." |

**On-site working days, summed with parallelism:**

- Days 1–10: site prep → demo → excavation → foundation form/pour/cure → start framing.
- Days 11–20: framing (basement walls → floor → ext walls → int walls → elev shaft → roof framing + concealed buffer) → sheathing → underlayment + windows install → shingles. LVL retrofit and exterior siding running in parallel.
- Days 21–28: rough plumbing (4d) + rough electrical (1.5d, SS) + mini-split rough (0.5d) → bundled inspection → 2d punch buffer → insulation (1d) + insp (0.5d).
- Days 29–39: drywall consolidated 10d. Exterior siding finishes by ~day 30.
- Days 40–55: paint phase 1 → tile shower (5d) || LVT flooring (3d) || cabinets (1d) → tile grout → trim (3d) → plumbing finish (2d) || electrical finish (2.5d) → mini-split install (1d) → paint phase 2 (1d, gates substantial completion + final bundled inspection).
- Days 56–61: client walkthrough → punch list returns (1–3d) → paint touch-ups + final clean → Will's walkthrough.

**On-site total: 58–65 working days ≈ 12–13 calendar weeks.**

**Scope-signed to handoff: ~18–19 weeks** (6 weeks pre-con anchored on TDEC + 12–13 weeks on-site). If TDEC clears faster (3–4 weeks), trims to ~16 weeks; if the existing roof tie-in surprises hit a change-order loop, +1–2 weeks.

## Critical-path summary (the 5–8 tasks that drive total duration)

1. **TDEC septic permit (pre-con)** — 6 calendar weeks. The longest single item in the project. One day of slip in TDEC = one day of project slip until on-site can begin. Anchored at the START of pre-con via `pre_construction_offset_working_days: 30`.
2. **Framing block (basement walls → floor → ext walls → int walls → roof framing + sheathing)** — ~10 working days, all serial. Slip in roof framing propagates directly through underlayment/windows into the MEP rough start.
3. **Concealed roof tie-in (3 calendar-day discovery buffer, SS lag 1 on roof framing)** — the single biggest change-order risk per addition_rules.md. If existing rafters aren't sized for the new load, a CO loop adds 1–2 weeks. PM must open the ceiling early in `framing.roof` to use the full buffer.
4. **Plumbing rough-in — 4 working days × 2 crew (HARD floor)** — Will's nominal from transcript line 484. Master bath + W/D relocation + vent stack extension all hit this floor. Gates the bundled rough inspection.
5. **Bundled rough inspection + 2-day punch buffer** — dev_rules.md Rule 4C/4D. Failure on any single rough item pushes the whole bundle right by a full re-inspection cycle.
6. **Drywall consolidated — 10 working days** — the longest single block of any phase. Consolidates addition + bedroom retrofit + hall bath patches into one continuous hang/tape/sand cycle. No way to shorten without doubling crew.
7. **Custom tile shower — 4–5 working days** — interior-finish long pole. Tile always takes longer than labor accounting suggests; finish-heavy bump per dev_rules.md §6.3.
8. **Paint phase 2 → substantial completion** — gates on EVERY finish trade (trim, flooring, cabinets, tile grout, plumbing finish, electrical finish, mini-split install). The natural funnel point that fires `milestone.substantial_completion`.

## Open questions for PM Interview

1. **Is the home on septic?** Scope explicitly mentions TDEC coordination but the on-septic-vs-city-sewer status governs whether `permit.tdec_septic` even applies (`tdec_septic_permit_offset.md` "Skip when. Home is on city sewer."). If on city sewer, pre-con runway compresses from 6 weeks to ~3 weeks anchored on selections/permit only.
2. **Grinder pump — in or out?** Scope explicitly says "Costs associated with septic relocation, replacement, or grinder system are not included and will be addressed via change order." If grinder is going in, that's a CO and a new procurement chain ahead of plumbing rough.
3. **Truss or stick-frame?** Scope is ambiguous ("truss or rafter framed, determined during design phase"). Defaulted to stick-frame per company belief (sub-800-sqft, sub-24'-span, 3/12 pitch). If PM Interview overrides to trusses, add 4–6 week supplier lead and gate framing.roof on it.
4. **LVL — standard or pressure-treated?** 3-ply 14" LVL spanning ~15'-6". Standard = 1 week supplier lead; pressure-treated/custom = 3 weeks. Affects whether procurement.lvl is on-the-critical-path or not.
5. **Windows — stock or custom?** Scope budgets $300/window which suggests stock (~3 weeks). Confirm; custom windows would extend pre-con runway to 4–6 weeks regardless of TDEC.
6. **Existing main service amperage** — scope assumes existing service supports the new 100A subpanel, but says "assumes." `prep.amperage_check` (0.5d, 3 weeks before on-site) must verify; if main service can't support, that's a service-upgrade CO before subpanel install can proceed.
7. **Tankless WH option in or out?** Scope quotes it as a $6,500 optional package. If in, add `procurement.tank` + `plumbing.tank_set` and recompute plumbing rough sequence per dev_rules.md Rule 4H. If out (base scope), existing tank stays — vent extension only, no tank-set predecessor.
8. **Customer-early-item acrylic shower swap — confirm Day 1?** Transcript lines 659–665 say yes, homeowner wanted it before main demo. PM Interview should formally confirm so the schedule emits `early.acrylic_shower_swap` in `site_prep / customer_early_items`, not collapsed into section 16's retrofit bucket.
9. **Closet & cabinet system option ($7,000)** — in or out? Affects cabinets-install duration and procurement chain (custom cabinets = 6–8 weeks lead).
10. **Hall bath repaint sheen + bedroom paint scope** — confirm both fold into the consolidated drywall block + paint phase 1/2 without separate sub-chains.
11. **Concealed roof tie-in inspection** — PM walk before signature to document existing rafter conditions at the tie-in zone. Reduces CO surprise risk on the single biggest schedule hazard.

## Confidence

- **Direct cost subtotal:** **high** — every section line traces to the PM-built CSV breakdown that Will already reviewed in the audit transcript. The negative section 16 material credit is identified and explained, not silently absorbed.
- **Customer total:** **high** — quoted verbatim from scope.pdf "Total Investment."
- **Gap reconciliation:** **medium–high** — mechanical from the scope's `Rates` block; final ~$8–9K residual is plausible PM-overhead + warranty reserve + profit but not itemized.
- **Pre-con runway:** **high** — 6-week TDEC floor is Will's hard number (transcript line 162); only weakens if home turns out to be on city sewer.
- **On-site duration:** **medium–high** — per-section heuristic grounded in editor_rules.md + transcript-confirmed durations (plumbing 4d, drywall 9–11d, shingles 1d, subpanel 1d, mini-split rough 0.5d / install 1d, paint phase 1 = 1d). Variability lives in: concealed roof tie-in CO loop, rough-inspection punch-list iteration count, and tile-shower finish-heavy bump.
- **Critical-path identification:** **high** — TDEC, framing, plumbing rough, bundled inspection, drywall, tile, paint phase 2 are the same items Will walked through in the audit.

Next planning artifact for this job: PM Interview answers (the 11 open questions above), then a TaskGraph generation that bakes the answered scope into a DAG, then a CPM schedule, then PEP.
