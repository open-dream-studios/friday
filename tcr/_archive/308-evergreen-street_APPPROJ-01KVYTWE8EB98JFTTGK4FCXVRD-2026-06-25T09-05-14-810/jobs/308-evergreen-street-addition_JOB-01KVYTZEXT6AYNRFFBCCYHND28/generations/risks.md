---
generation_kind: risk_review_v1
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KVYTWE8EB98JFTTGK4FCXVRD/jobs/308-evergreen-street-addition_JOB-01KVYTZEXT6AYNRFFBCCYHND28/inputs/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KVYTWE8EB98JFTTGK4FCXVRD/jobs/308-evergreen-street-addition_JOB-01KVYTZEXT6AYNRFFBCCYHND28/inputs/files/scope.pdf.ref.json
  - _projects/308-evergreen-street_APPPROJ-01KVYTWE8EB98JFTTGK4FCXVRD/jobs/308-evergreen-street-addition_JOB-01KVYTZEXT6AYNRFFBCCYHND28/inputs/files/308_Evergreen_Addition.xlsx - Summary (1).csv.ref.json
  - _projects/308-evergreen-street_APPPROJ-01KVYTWE8EB98JFTTGK4FCXVRD/jobs/308-evergreen-street-addition_JOB-01KVYTZEXT6AYNRFFBCCYHND28/inputs/files/3725 SIMONS 012226.pdf.ref.json
  - _projects/308-evergreen-street_APPPROJ-01KVYTWE8EB98JFTTGK4FCXVRD/jobs/308-evergreen-street-addition_JOB-01KVYTZEXT6AYNRFFBCCYHND28/manifest.json
  - _projects/308-evergreen-street_APPPROJ-01KVYTWE8EB98JFTTGK4FCXVRD/jobs/308-evergreen-street-addition_JOB-01KVYTZEXT6AYNRFFBCCYHND28/generations/baseline.md
  - _company/rules/editor_rules.md
  - _company/rules/dev_rules.md
  - _company/knowledge/308_evergreen_wills_audit_transcript.md
  - _company/knowledge/_examples/wills_voice.md
  - _company/beliefs/_examples/stick_frame_default_for_small_additions.md
  - _company/actuals/README.md
  - job_types/addition/rules/addition_rules.md
  - job_types/addition/rules/tdec_septic_permit_offset.md
last_verified_at: "2026-06-25T07:42:59.135Z"
---

# Risk register — 308 Evergreen Street two-story addition

- **Job:** JOB-01KVYTZEXT6AYNRFFBCCYHND28
- **AppProject:** APPPROJ-01KVYTWE8EB98JFTTGK4FCXVRD — 308 Evergreen Street
- **Sized against:** `generations/baseline.md` — $173,850 customer total, $100,778.92 direct cost, 6-week TDEC-anchored pre-con + 58–65 working-day on-site (≈18–19 weeks signed-to-handoff).

Every risk below cites a specific scope clause, transcript line range, rule, or belief. Severity uses the prompt's ladder: HIGH = quoted numbers move materially OR multi-week slip OR contractual exposure; MED = sub-week slip OR margin compression contained inside the rate ladder; LOW = nuisance, surfaces in punch or warranty.

---

## Top 5 risks

### R1 — TDEC septic outcome (relocation / new tank / leach field / grinder pump)
**Severity: HIGH** (dollar exposure unbounded; multi-week schedule risk)

- **Trigger:** Site test comes back saying the existing septic cannot absorb the added master-bath fixture + W/D relocation load. Three downstream paths (in scope as CO placeholders): (a) relocate existing septic, (b) install new septic tank + leach field, (c) install grinder pump to tie into sewer.
- **Sources:**
  - `inputs/files/scope.pdf.txt` (via scope.pdf.ref.json), Pre-Construction & Design Phase section: *"Determine feasibility of relocating septic system or installing new septic tank and leach field. Evaluate installation of grinder pump system to connect to available sewer line. Costs associated with septic relocation, replacement, or grinder system are not included and will be addressed via change order."*
  - `job_types/addition/rules/tdec_septic_permit_offset.md` (severity `hard`).
  - `job_types/addition/rules/addition_rules.md` § "Septic — TDEC, the long-lead permit": *"TDEC is the most non-typical thing in the project. It can take a long time, it can go pretty quick — you can't really predict."*
  - Transcript lines 154–171: Will — *"T-deck, we have to call them … pay $500 per permit … report from a soil scientist. Six weeks … you can't really predict."*
  - `generations/baseline.md` § "Critical-path summary" item #1 and § "Open questions" #1–#2.
- **Impact:**
  - **Dollar:** A new tank + leach field on a typical TN residential lot runs $8K–$18K labor+material; a grinder pump install $3K–$7K; full septic relocation can clear $20K. None of this is in the $173,850 base. The CO will be billed at the scope's standard cost+15% (material) / +30% (sub) / labor at the rate ladder — within TCR's normal markup envelope, but the customer is being asked to absorb a number they have not yet seen.
  - **Schedule:** Worst case (full new system) adds 3–4 weeks calendar to the pre-con runway because excavation cannot begin until TDEC is finalized. Best case (existing system passes) trims the 6-week runway to 3–4 weeks if the soil scientist's report turns fast.
- **Mitigation:**
  - **Pre-signature (before contract):** Confirm in PM Interview whether the home is on septic at all (baseline open-question #1). If on city sewer, the entire risk vanishes and the TDEC task drops from the schedule per `tdec_septic_permit_offset.md` § "Skip when."
  - **Day 0 of contract:** PM places the TDEC call same-day. `permit.tdec_septic` is `kind: lead_time`, `lead_time_days: 42` (calendar), `pre_construction_offset_working_days: 30`. Anchored at start of pre-con — not backward-pulled from excavation.
  - **At soil-scientist report (~PC week 2):** If report calls for relocation/new tank/grinder, surface the CO range to homeowner immediately with three priced options. Do NOT let the customer learn the CO scope at excavation start — that creates a "we promised X, you delivered Y" optics problem.
  - **Contract language:** Verify the signed agreement carries forward the scope.pdf's "addressed via change order" clause verbatim. This is the contractual shield; without it TCR is exposed.

### R2 — Concealed roof tie-in into existing 6/12 structure
**Severity: HIGH** (per addition rules, "the most reliable source of change orders on an addition with a roof tie-in")

- **Trigger:** PM opens the existing ceiling/rafter zone at the tie-in line (where the new 3/12 gable meets the existing 6/12 roof) early in `framing.roof`. Existing rafters are undersized for the new combined load, or framed in a way that doesn't permit a clean tie-in, or there is hidden water damage or rot.
- **Sources:**
  - `job_types/addition/rules/addition_rules.md` § "Concealed roof tie-in — change order risk": *"This is the most reliable source of change orders on an addition with a roof tie-in."* Mandates 2–3 day buffer with `roof.concealed_buffer` (`kind: lead_time`, `lead_time_days: 3`, SS lag 1 after `framing.roof`).
  - `inputs/files/scope.pdf.txt` Roof System: *"Roof pitch approx. 3/12 tying into existing 6/12 roof system … Roof tie-in assumes standard integration; additional structural modifications not included."*
  - `inputs/files/scope.pdf.txt` General Conditions: *"Assumes standard framing conditions within existing walls; concealed conditions including wiring, plumbing, or structural irregularities encountered during demolition will be addressed via change order."*
  - `generations/baseline.md` § "Critical-path summary" item #3.
- **Impact:**
  - **Dollar:** A typical rafter-sister + sheathing-patch CO is $1.5K–$4K labor+material. A full tie-in re-design (engineer letter + sister rafters + new ridge fasteners) can push $6K–$10K. Engineered-letter turnaround on its own is 1–2 weeks if a structural engineer is needed.
  - **Schedule:** 3-day buffer per addition rule absorbs the routine discovery. A real re-design loop is +1 to +2 weeks (engineer + lumber resupply + crew rescheduling). This is on the critical path between `framing.roof` and the MEP rough start gated on `roofing.underlayment` + `windows.install`, so slip propagates 1:1 into project end date.
- **Mitigation:**
  - **Schedule encoding:** Emit `roof.concealed_buffer` as `lead_time_days: 3`, SS lag 1 after `framing.roof` (NOT FS after — runs concurrent, per addition rule).
  - **Day 1 of `framing.roof`:** PM physically opens existing ceiling at the tie-in zone BEFORE the framing crew commits to the new ridge layout. Document rafter sizes + spacing + species + visible defects in photos. If anything looks marginal, call structural engineer same-day; don't wait until the framers hit the obstruction.
  - **Pre-construction prep:** During the `general.pre_construction_walkthrough` (PC Day ~15, 3 weeks out), PM should crawl the attic and shoot photos of the tie-in zone from below. Early visibility shrinks the CO-processing window from "discovered Wednesday, billed Friday" to "discovered weeks ago, customer already saw the contingency line."
  - **Customer expectations:** Set up-front at signature that the tie-in is the single biggest unknown. The scope's CO clause covers TCR; the customer relationship still benefits from naming the risk pre-signing.

### R3 — Concealed-condition COs in demo (wiring, plumbing, structural irregularities)
**Severity: HIGH** (explicit CO clause in scope; pattern across every addition)

- **Trigger:** Demo crew opens existing walls/floor/ceiling for: heat-pump relocation, LVL retrofit (3-ply 14" beam, ~15'-6" span replacing existing load-bearing wall), hall-bath window infill, primary-bedroom remodel, vent-stack extension. ANY of these can expose wiring routed where it shouldn't be, plumbing that needs rerouting, or framing that doesn't match plan assumptions.
- **Sources:**
  - `inputs/files/scope.pdf.txt` General Conditions: *"Assumes standard framing conditions within existing walls; concealed conditions including wiring, plumbing, or structural irregularities encountered during demolition will be addressed via change order."*
  - `inputs/files/scope.pdf.txt` Framing: *"Install (1) engineered LVL beam (3-ply 14") spanning approx. 15'-6" to open existing load-bearing wall including temporary shoring."*
  - `inputs/files/scope.pdf.txt` Existing Hall Bathroom Modification: window removal, drywall, acrylic shower swap, reuse existing valve.
  - `job_types/addition/rules/addition_rules.md` § "LVL temporary shoring — independent retrofit"; § "Retrofit detection — the HARD heuristic."
  - Transcript lines 274–278: Will — heat pump relocation must precede demo by minimum 3 working days.
  - Transcript lines 657, 689–693: Will calling out "existing" as the retrofit flag; hall-bath retro work tied to drywall.
- **Impact:**
  - **Dollar:** Routine concealed-condition COs run $500–$3K each. The LVL exposure is the most expensive single risk in this bucket — if the existing bearing wall has a hidden plumbing stack or HVAC duct in the path of the new beam, the reroute is $2K–$6K and adds a day. Multiple small finds during demo (the more common pattern) compound: 4–6 finds at $500 each = $2K–$3K margin compression if TCR absorbs them, or 4–6 individual CO conversations with the customer if billed through.
  - **Schedule:** Each routine find adds 0–1 days inside the demo / structural / framing phases. Severe finds (LVL-blocking plumbing reroute, undersized existing service, asbestos in old wall finishes) can add 3–7 days. None propagate to project end as cleanly as R2 because parallelism in the structural phase absorbs small slips.
- **Mitigation:**
  - **Pre-construction walkthrough (PC Day ~15):** PM walks the LVL line + heat-pump line + hall-bath wall + vent-stack route with the homeowner. Document existing conditions in photos. Note any obvious red flags (visible drywall patches over old plumbing, mystery wires).
  - **CO processing standard:** Train PM to process small COs within 48 hrs of discovery — same-day photo, next-day priced CO email to homeowner, signed approval before crew touches it. Slow CO processing creates field idle time, which compounds the dollar hit.
  - **Demo-phase float:** The current baseline budgets demo at 2–3 working days. Hold the lower bound (2 days) loosely — concealed-condition discoveries push routinely to 3 days even on clean scopes.
  - **LVL specifically:** PM Interview question (baseline open-question #4): is the existing wall's interior face visible from the basement or other side? If yes, do a pre-demo inspection of what's actually inside the wall before pricing the LVL retrofit.

### R4 — Existing main service amperage insufficient for new 100A subpanel
**Severity: MED** (sub-week slip if caught early; HIGH if discovered late)

- **Trigger:** `prep.amperage_check` (0.5d, 3 weeks before on-site per addition rules) finds the existing main service does not have 100A of headroom for the new subpanel. Outcome paths: (a) main service upgrade to 200A (most common), (b) load calc forces smaller subpanel, (c) full service rebuild.
- **Sources:**
  - `inputs/files/scope.pdf.txt` Electrical: *"Install (1) new 100-amp subpanel … Assumes existing main electrical service can support new subpanel."* The word "Assumes" is the explicit risk flag.
  - `job_types/addition/rules/addition_rules.md` § "Existing electrical service — amperage check before subpanel": *"Typical homes have a 200A service but may not have space to accept the subpanel without a service upgrade … If the breakdown includes a subpanel but no service-upgrade section, emit a warnings[] entry."*
  - `generations/baseline.md` § "Pre-construction runway estimate" — `prep.amperage_check` at 3 weeks before on-site.
  - The 308 breakdown does NOT include a service-upgrade section. This matches the addition rule warning #3.
- **Impact:**
  - **Dollar:** Service upgrade to 200A: $2.5K–$5K labor+material, billed as CO (not in base scope). Discovered EARLY (PC week 3): handled inside the pre-con runway with no schedule slip. Discovered LATE (electrician arrives at rough-in and finds no panel headroom): the rough-in phase halts, electrician sequences out, service-upgrade lead time is 1–2 weeks for utility coordination, then the bundled rough inspection slips. Cascade: 1–2 week schedule slip + electrician trip-charge + customer trust hit.
- **Mitigation:**
  - **Non-negotiable:** `prep.amperage_check` must land 3 weeks before on-site per addition rule, with `pre_construction_offset_working_days: 15`. Do not let CPM backward-pull this from subpanel install — it must anchor on PC start.
  - **PM Interview (baseline open-question #6):** Confirm electrician will do a panel-side walk during the pre-con walkthrough (PC Day 15). Sticker check of existing service tag is 5 minutes.
  - **If insufficient:** Process the service-upgrade CO same-day. Coordinate with utility (1-week lead typical for meter swap). Keep schedule slip absorbed inside the 6-week TDEC runway — they overlap.

### R5 — Customer-requested early item (acrylic shower swap) collapsed into mid-job retrofit
**Severity: MED** (customer experience hit; minor dollar; no schedule slip but optics damage)

- **Trigger:** TaskGraph emission collapses the acrylic shower swap (existing hall bath) into the section 16 "Existing Hall Bath Mod" retrofit bucket and schedules it in `interior_finishes` phase — landing the work in approximately month 3 of construction. Customer expects the work BEFORE main demo starts (Day 1 of the on-site phase).
- **Sources:**
  - Transcript lines 659–665: Will — *"This item, remove the acrylic shower insert and replace it, the customer wanted that done before we even broke ground on the job … So that way the customer had a fresh shower before we started this job. That's what they want."*
  - `_company/rules/editor_rules.md` § "Customer early items — the TWO-BUCKET pattern" and § "Customer early items — a separate concept from retrofit."
  - `_company/rules/dev_rules.md` Rule 4V "Customer early items and retrofit work in the SAME area are SEPARATE components" — explicitly cites this 308 case as the V10 anti-pattern.
  - `_company/rules/dev_rules.md` Warning #31: *"A customer-requested early item identified in the PM Interview was NOT emitted as a task with id `early.<name>` in `site_prep / customer_early_items` component."*
  - `inputs/files/scope.pdf.txt` Existing Hall Bathroom Modification section co-locates the shower swap with the window infill / drywall / repaint retrofit work — naturally invites the collapse error.
  - `generations/baseline.md` § "Open questions" item #8.
- **Impact:**
  - **Dollar:** Direct labor for the acrylic swap (~1 day × 2-person plumbing crew per section 16 line items) is small (~$700–$1K loaded). The real hit is downstream: customer experience and trust during the rest of the 12–13 week on-site phase. A customer who agreed to a shower swap "before you break ground" and instead is bathing at a relative's house for 3 months is the customer who escalates every later concern.
  - **Schedule:** Zero. The early-item bucket runs concurrent with `general.site_setup` on Day 1.
- **Mitigation:**
  - **TaskGraph emission:** Per Rule 4V, emit `early.acrylic_shower_swap` as a task with `component_id: customer_early_items`, `phase_id: site_prep`, `depends_on: [general.site_setup]` (FS). Do NOT prefix with `retrofit.` or place in `interior_finishes`.
  - **PM Interview confirmation:** The interview's `customer-requested early item` answer should name this work explicitly so the agent doesn't need to infer. Baseline open-question #8 documents this.
  - **Verification gate:** Before publishing the schedule to the customer, search the emitted graph for any task id starting `early.` in `site_prep / customer_early_items`. If none present, the early item was collapsed — go back and emit it.
  - **Customer-facing:** PEP Day 1 narrative names the shower swap explicitly so homeowner sees their request honored on the published schedule before crew arrives.

---

## Watch list

Items the PM should monitor but not pre-empt with material schedule changes.

### W1 — Rough-inspection punch-list loop blows the 2-day buffer
**Severity: MED**

`_company/rules/dev_rules.md` Rule 4D mandates a 2-day buffer after `inspect.rough_bundled`. Transcript lines 530–532: Will — *"anywhere from a two to a four-day, saying, 'No, I'm not scheduling any trade after the inspection.'"* Default is 2; large/finicky jobs use 4. Risk is a multi-cycle loop (plumber fails → fixes → re-inspect → fails on another item → fixes → re-inspect). Each cycle is a working day plus inspector availability lag. PM should mentally budget 4 days for this job (master bath + W/D relocation + vent stack extension = more inspection surface than typical) and not be surprised if a second cycle is needed.

### W2 — Plumbing rough hard floor (4d × 2 crew) cannot be compressed
**Severity: MED**

`_company/rules/editor_rules.md` § "Plumbing rough-in duration — Will's nominal" + transcript line 484: *"four days for two guys, that's fine for this kind of job."* Master bath + W/D relocation + vent stack extension all hit this floor. If schedule-compression pressure appears late in the project, do not lean on plumbing rough. Soft targets are tile (4–5d, finish-heavy bump) and drywall consolidated (9–11d, the longer bound is conservative).

### W3 — Truss vs stick-frame scope ambiguity
**Severity: MED**

Scope line 55: *"Construct new gable roof system (truss or rafter framed, determined during design phase)."* Defaulted to stick-frame per `_company/beliefs/_examples/stick_frame_default_for_small_additions.md` and `job_types/addition/rules/addition_rules.md` § "Roof trusses (custom) — CONDITIONAL" (sub-800-sqft, sub-24'-span, 3/12 pitch — all conditions satisfied). PM Interview question (baseline open-question #3) confirms. If PM overrides to trusses, add 4–6 week supplier lead and `procurement.trusses` (`lead_time_days: 35`), and gate `framing.roof` on truss arrival. Pre-con runway extends to 6+ weeks regardless of TDEC outcome.

### W4 — LVL pressure-treated or custom availability
**Severity: MED**

Scope line 48: *"Install (1) engineered LVL beam (3-ply 14") spanning approx. 15'-6"."* Transcript lines 798–806: Will — *"a week before we start is fine for LVL beams. Um, they're usually readily available, unless we're getting pressure treated ones or something like that."* `addition_rules.md` § "LVL beams" defaults procurement to `lead_time_days: 14` for safety. PM Interview (baseline open-question #4) confirms spec. If pressure-treated, push procurement to `lead_time_days: 21` and order at structural sign-off. LVL is on the LVL retrofit sub-chain, which is parallel-to-main-framing — slip only matters if it exceeds main framing duration.

### W5 — Custom vs stock windows
**Severity: MED**

Scope line 66: *"Install (4) windows including (3) 36" x 60" and (1) transom window."* Material allowance schedule budgets $300/window which suggests stock. PM Interview (baseline open-question #5) confirms. If stock: `procurement.windows` `lead_time_days: 21`. If custom: 35–49 calendar days, which can push the pre-con runway past TDEC's 6-week floor and become the new long pole.

### W6 — Section 16 negative material credit ($-4,199) absorbs into reported margin
**Severity: LOW** (margin only; transcript-confirmed manual edit)

CSV section 16 "Existing Hall Bath Mod, Bedroom Remodel & Closeout" has a $-4,199 material line — Will's manual "10% material reduction." Transcript lines 42–46: *"Wills modification, 10% reduction in material … I shouldn't have, I'll just roll with it anyway."* Per `_company/rules/dev_rules.md` §12, negative section totals are credits, not work — handled correctly by the baseline. Risk is margin: if real material cost recovers the $4,199 reduction (i.e. nothing actually came in 10% cheaper), TCR eats it. No customer-facing impact because total investment is unchanged.

### W7 — 3-trade interior overlap (electrical + plumbing + HVAC finish)
**Severity: LOW** (Rule 4N stagger default catches this)

`_company/rules/dev_rules.md` Rule 4N requires HVAC to serialize AFTER electrical finish when the standard 3-finish-trade overlap occurs (electrical + plumbing + mini-split install all chain off paint phase 1 / flooring / cabinets). Risk: TaskGraph emission skips the HVAC stagger and lands 3 trades concurrent in `interior_finishes`. Verify in the generated graph that `hvac.minisplit_install.depends_on` includes `electrical.finish` (FS). If not, manually edit per Rule 4N.

### W8 — Drywall consolidated 10-day block has no compression lever
**Severity: LOW** (predictable; just budget for it)

`_company/rules/editor_rules.md` § "Drywall consolidation" gives 9–11 days for a typical addition. Baseline plans 10. Bedroom remodel drywall + hall-bath patch are rolled in per `job_types/addition/rules/addition_rules.md` § "Retrofit drywall consolidates into main drywall block." This is the longest single block in the on-site phase. There is no labor compression available without doubling crew (and doubling crew triggers other site-coordination issues per Will's 2-interior-trades cap). PM must budget the full 10 days; no PEP framing of "we'll catch up here" is realistic.

### W9 — Customer add-on creep during closeout walkthrough
**Severity: LOW** (Will's signed-punch-list SOP handles this)

Transcript lines 3162–3170: Will — *"the reason we do that is some customers they just keep going, and going, and going. And you do the punch list and then they find more stuff and it's like, 'No, we have to draw a line somewhere.'"* Risk is PM skipping the customer-signature step at the punch-list walkthrough. Mitigation is procedural: PM uses Will's punch-list SOP form, points out 2 items the customer didn't see (trust builder), gets signature before crew schedules returns.

### W10 — Mini-split unit selection / late ordering
**Severity: LOW**

Scope budgets mini-split at $2,500 (allowance). Order at dried-in per `_company/rules/editor_rules.md` § "Material ordering — Will's universal rule." Supplier lead 7–14 days. Risk is over-spec'ing the unit (homeowner wants brand X, allowance assumed brand Y) and discovering the lead time after dried-in. Mitigation: lock mini-split brand/model at `checkpoint.selections_finalized` (3 weeks before on-site) even though the order itself fires later.

### W11 — Drywall tie-in cracks in Year 1
**Severity: LOW** (expected, not a defect)

`job_types/addition/rules/addition_rules.md` § "Drywall cracking — 1-year warranty assumption" + transcript lines 3226–3242: Will — *"Every single addition that we build always has drywall cracking. Every single one of them. Above the doors, windows, or headers … we come back and we take care of that for free. That's part of our jobs."* Not on the project schedule. Warranty return budgeted as standard TCR addition practice. Risk is misclassifying the return visit as a callback (margin hit) rather than warranty (planned cost).

### W12 — Optional packages confusion (closet system / tankless WH)
**Severity: LOW**

Scope lists two optional packages outside the $173,850: closet & cabinet system ($7,000 allowance) and tankless water heater ($6,500 allowance). Risk is mid-build customer assumes one or both is included and is surprised by the CO at install time. Mitigation: PM Interview (baseline open-questions #7 and #9) confirms in/out status at signature. If tankless is added, recompute plumbing rough sequence per `_company/rules/dev_rules.md` Rule 4H (`procurement.tank` → `plumbing.tank_set` → `plumbing.rough_in`). Otherwise the existing tank stays and only the vent extension is in scope.

---

## What this register doesn't cover

Risk categories deliberately out of scope:

- **Weather days.** `_company/actuals/README.md` says actuals harvesting is P9 territory and the folder is empty. There is no TCR base-rate for weather slip by month. Roofing + siding + exterior trim are exposed (the addition has a same-crew exterior block of 5–6 days), but sizing the risk would require fabricated numbers. Per `_company/rules/dev_rules.md` §12, the agent should call out exterior-heavy projects in `assumptions[]` — already handled by baseline.
- **Insurance events on site.** Fire, theft, water-line strike, vehicle damage. Standard contractor's GL covers these; not a project-planning risk.
- **Customer payment risk.** $20,000 deposit at signature, weekly invoicing thereafter (scope Rates block). Default risk on a weekly cycle is real but not bounded by this scope's content — handled by TCR's collections process, not by the brain.
- **Subcontractor unavailability.** Plumber, electrician, HVAC tech, drywaller, tile setter no-shows. TCR's `_company/knowledge/` does not yet capture sub-roster reliability data. Day-of slip from a no-show is real (1–3 days typical) but un-priced.
- **Material price escalation between signature and ordering.** Lumber and steel both move on industry cycles. Materials at cost+15% (scope Rates) means escalation passes through to customer as a CO, contractually — but the conversation can still strain the relationship. No mitigation modeled.
- **Permitting curveballs from non-TDEC jurisdictions.** Building permit walk-in is ~90% same-day per Will (transcript line 134). The other 10% can be 1–2 weeks. The 3-week pre-con offset on `general.permitting` absorbs this; no separate risk entry needed.
- **Quality risks downstream of TCR (homeowner finish-material spec deviations from allowance schedule).** If homeowner picks $8/sqft tile against a $3/sqft allowance, the over-allowance is a CO at signed time, not a construction risk. Out of scope here.

---

## How to use this register

- **R1 (TDEC septic) is the single biggest dollar+schedule risk.** Close baseline open-questions #1 and #2 (city sewer? grinder in/out?) at PM Interview. Then either retire R1 (city sewer) or work the mitigation sequence in order.
- **R2 and R3 are demo/framing-phase execution risks.** The mitigation is operational discipline (early ceiling-open + photo documentation), not pre-con planning. Brief the PM at scope handoff.
- **R4 is closed by the `prep.amperage_check` task landing 3 weeks before on-site.** If TaskGraph emission drops that task, R4 escalates from MED to HIGH.
- **R5 is closed by correct TaskGraph emission of `early.acrylic_shower_swap` in `site_prep / customer_early_items`.** Verification step is mechanical — search the graph for `early.` prefix.
- **Watch list W1–W12 shape PEP narrative and schedule discipline.** Most are encoded in addition/editor rules already; this register names them so the PM has a single place to scan during execution.
