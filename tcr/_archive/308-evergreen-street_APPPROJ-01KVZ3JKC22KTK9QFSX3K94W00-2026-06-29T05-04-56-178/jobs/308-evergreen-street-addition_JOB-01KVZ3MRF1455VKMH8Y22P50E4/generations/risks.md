---
generation_kind: risk_review_v1
depends_on:
  - _company/rules/editor_rules.md
  - _company/rules/dev_rules.md
  - _company/rules/pep_rules.md
  - _company/knowledge/308_evergreen_wills_audit_transcript.md
  - _company/knowledge/_examples/wills_voice.md
  - _company/beliefs/_examples/stick_frame_default_for_small_additions.md
  - job_types/addition/rules/addition_rules.md
  - job_types/addition/rules/tdec_septic_permit_offset.md
  - job_types/addition/beliefs/stick_frame_default_for_small_additions.md
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/manifest.json
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/inputs/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/inputs/files/308_scope.pdf.txt
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/inputs/files/308_Evergreen_Addition.xlsx - Summary (1).csv.txt
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/beliefs/initial.md
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/beliefs/interview-2026-06-26T20-55-11-049.md
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/beliefs/interview-2026-06-26T21-02-50-651.md
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/beliefs/interview-2026-06-26T21-10-42-369.md
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/beliefs/interview-2026-06-26T21-18-26-782.md
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/generations/baseline.md
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/generations/task_graph.json
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/generations/schedule.json
last_verified_at: "2026-06-27T00:19:42.003Z"
---

# 308 Evergreen Street — Risk Register

Sizing all schedule slips against the baseline (~75 working days on-site + 6-cal-week TDEC PC anchor = ~21 weeks contract-to-handoff per `baseline.md`). Sizing all dollar exposures against the $100,778.92 TCR direct cost / $173,850 customer total (~42% gross margin) per `baseline.md`. Severity floor for HIGH: quoted/promised numbers move materially OR ≥1-week schedule slip OR contractual exposure.

## Severity scoring

- **HIGH** = quoted/promised numbers move materially OR multi-week schedule slip OR contractual exposure to TCR or homeowner.
- **MED** = sub-week slip OR margin compression contained inside the rate ladder (labor markup, material +15%, sub +30%).
- **LOW** = nuisance, surfaces in punch or warranty return; no schedule impact.

---

## Top 5 Risks

### R1. TDEC septic permit variance — HIGH

**Trigger conditions (observable):**
- TDEC clock has NOT started (Round 2 interview: "PM will kick off TDEC call within 1 working day of signed agreement / deposit"). Clock starts at contract signing.
- Soil scientist visit dates and report turnaround are queue-dependent; per Will (transcript line 166): *"TDEC is the most non-typical thing. Like, they can take a long time. They can go pretty quick."* Per Will (`knowledge/_examples/wills_voice.md` "TDEC" section): *"Six weeks. It can come in faster, it can drag — depends on the soil scientist and the review queue."*
- Observable signal of slip: no soil scientist visit scheduled within 2 weeks of TDEC call (per `addition_rules.md` step 2 expected timeline).

**Impact:**
- **Schedule:** 1:1 slip on contract-to-on-site-start date for every day TDEC drags past the 42-cal-d budget. Realistic range: 0 to +2 weeks (Will plans for 6 wk as the safety floor; 7–8 wk is the realistic high tail). `excavation.dig` is FS-gated on `permit.tdec_septic`, so no excavation until TDEC closes.
- **Dollar:** $0 direct cost (PC work is fixed allowances). Indirect: if homeowner committed to a calendar move-out / move-in date based on a verbal start estimate, TCR's relationship exposure grows with each week of slip.
- **Customer expectation:** Round 2 PM interview confirms no verbal calendar date was committed to homeowner — exposure is currently contained, but every week the contract is unsigned, the implicit "we'll be done by X" date drifts.

**Mitigation (concrete PM actions):**
- **Day of signing:** PM places TDEC call AND pays the $500 permit fee within 1 working day (per Round 2 commitment). Record the kickoff date in events.jsonl so the 42-cal-d countdown is tracked.
- **T+10 cal-d post-kickoff:** PM phones TDEC to confirm soil scientist site visit scheduled. If not yet scheduled, escalate.
- **T+21 cal-d post-kickoff:** PM confirms soil scientist visit complete AND report status. Per `addition_rules.md` step 3, the report typically returns in 1–2 weeks after initial contact; absence at T+21 is the slip signal.
- **Recurring weekly** until permit-in-hand: PM tracks soil scientist + TDEC review queue status in events.jsonl. Surface to homeowner WEEKLY any slip from baseline — `baseline.md` open-commitments §: *"if a contract-signing target slips by more than a week from the PM's current expectation, the realistic on-site start moves with it — surface that to the homeowner before the slip is in their head as a delay."*
- **Contractual fallback:** if TDEC's soil scientist returns a finding requiring relocation / new tank / grinder pump, those become a separate CO (scope §"Pre-Construction & Design Phase": *"Costs associated with septic relocation, replacement, or grinder system are not included and will be addressed via change order"*). This is R3 below.

---

### R2. Concealed roof tie-in to existing 6/12 — HIGH

**Trigger conditions (observable):**
- Scope (`308_scope.pdf` p.2): *"Construct new gable roof system... Roof pitch approx. 3/12 tying into existing 6/12 roof system."*
- Per `addition_rules.md` §"Concealed roof tie-in": *"the structural conditions ABOVE the existing ceiling are concealed until demo opens them up... This is the most reliable source of change orders on an addition with a roof tie-in."*
- Observable signal: PM opens existing ceiling at the tie-in on Day 25 (`framing.roof` Day 1, Wed Jul 29 per `schedule.json`) and finds (a) existing rafters undersized for new load, (b) hidden damage / rot, or (c) framing geometry that doesn't permit a clean tie-in.

**Impact:**
- **Schedule:** Baseline reserves `roof.concealed_buffer` (3 cal-d `lead_time`, SS lag 1 after `framing.roof`) per Round 1 PM acceptance. Buffer absorbs typical findings (0–3 cal-d). Major findings (undersized existing rafters requiring sister-up or rebuild) push 5–10 working days through framing → underlayment → MEP gate → drywall.
- **Dollar:** typical $500–$5,000 CO; if structural rebuild needed (rare but documented) could exceed $5k. Per baseline §"Open questions / sensitivities" #4.

**Mitigation:**
- **Day 25 (Wed Jul 29), AM:** Per `task_graph.json` `roof.concealed_buffer.derived_from.reasoning`: *"PM opens existing ceiling early on day 1 of framing.roof."* This is non-negotiable. Open early, document with photos.
- **Day 25 (Wed Jul 29), EOD:** PM logs findings in events.jsonl. If anything outside baseline, generate CO same-day. Per Will's audit (transcript lines ~518-522), inspectors with shitty reports + no phone answer make late documentation impossible — same logic applies here for concealed conditions.
- **Day 25-27 buffer window:** Reserve 3 cal-d (Wed Jul 29 → Mon Aug 3 covering weekend) for discovery + CO generation + homeowner approval. Do NOT schedule any other roof or MEP work that consumes the buffer's float.
- **Pre-emptive:** at PC walkthrough (Thu Jun 4, `general.pre_construction_walkthrough`), PM photo-documents the existing tie-in zone from below to set a baseline for the CO conversation.

---

### R3. Septic relocation / grinder pump CO — HIGH

**Trigger conditions (observable):**
- Scope (`308_scope.pdf` p.1–2): *"Coordinate and complete septic inspection with TDEC. Determine feasibility of relocating septic system or installing new septic tank and leach field. Evaluate installation of grinder pump system to connect to available sewer line. Costs associated with septic relocation, replacement, or grinder system are not included and will be addressed via change order."*
- Triggered by what TDEC's soil scientist finds (R1 dependency).
- Observable signal: soil scientist's report flags existing septic as inadequate for new fixture count (master bath dual lav + toilet + W/D relocation + custom shower).

**Impact:**
- **Schedule:** New tank + leach field install = 2–3 weeks. Grinder pump + sewer tie = 2–4 weeks of additional pre-excavation work. Per baseline §"Open questions / sensitivities" #6: *2–6 weeks if grinder pump is required.* On-site start moves 1:1.
- **Dollar:** $5k–$25k CO range per baseline. The wide spread reflects (a) septic relocation alone is on the low end, (b) full new tank + leach field is mid-range, (c) grinder pump + utility sewer tie + permit is high end.
- **Contractual exposure:** scope explicitly carves this out as CO, so TCR is contractually protected. Homeowner exposure is real-dollar surprise — must be communicated BEFORE TDEC findings come in.

**Mitigation:**
- **Pre-contract:** PM verbally walks homeowner through the scope carve-out language at signing so the CO possibility is not a surprise.
- **TDEC kickoff (T+0):** PM asks TDEC to indicate likely outcome based on existing septic age + fixture count addition, even before soil scientist visit. Don't wait for the final report.
- **Soil scientist visit (T+1–2 wk):** PM is on site for the visit. Asks the scientist verbal on-site impressions before formal report.
- **Findings + report received (T+3–6 wk):** if relocation / grinder triggers, PM drafts CO same day, presents to homeowner within 48h. CO approval BEFORE excavation Day 10 (Wed Jul 8) — once excavation starts, schedule rebaselining gets messier.

---

### R4. Selections lock cascade — MED

**Trigger conditions (observable):**
- Round 2 interview: tile, LVT, paint base palette LOCKED. Still TBD: 72" vanity model, faucets, vanity mirrors + lights, mini-split aesthetic, interior + pocket door styles, exterior door.
- `checkpoint.selections_finalized` is anchored at PC Day 15 (Thu Jun 4) with 5-wd lead-up (Fri May 29 → Thu Jun 4) per `task_graph.json`.
- Observable signal: at lead-up Day -1 (Thu Jun 4 AM), one or more selections still unanswered by homeowner.

**Impact:**
- **Most lead-critical: special-order tile.** Per Round 4 + `task_graph.json`, `order.tile` is FS-gated on `checkpoint.selections_finalized` and runs into a 14-cal-d `wait.tile` → `checkpoint.tile_arrived` → gates `tile.shower_substrate`. Tile lock slip of N days = tile arrival slip of N days = `tile.shower_substrate` slip of N days IF the substrate task has zero float. Per `schedule.json` `checkpoint.tile_arrived.float_days: 41.5` — current float absorbs ~8 working weeks of tile-only slip. **Tile alone is not the bottleneck unless slip exceeds float.**
- **Real cascade risk: vanity + faucets + mirrors + lights + interior doors.** These have stock 7-d suppliers (collapsed 1-day orders), but the install dates feed `vanity.install`, `trim.install`, `plumbing.finish`, `electrical.finish` — all near critical path in the interior finishes window (Days 54–61). If selections slip past PC Day 15, the per-Will-universal-rule "materials on site 1 week before install" window compresses for these stock items.
- **Exterior door** is on the critical-path-adjacent windows install (Day 28–29). Per `task_graph.json` `order.exterior_door.float_days: 26`. Tolerates ~5 weeks of slip; beyond that, `windows.install` gates Day 28 underlayment/MEPs.
- **Mini-split aesthetic** is least lead-critical — `order.minisplit` is FS-gated on `milestone.dried_in` (Day 30) anyway, so selections lock by Day 30 is sufficient.
- **Schedule:** typical cascade is 1–5 working days; only catastrophic homeowner non-responsiveness pushes into HIGH.
- **Dollar:** $0 within scope. Indirect: weekend / overtime callbacks if the PM tries to compress interior finishes to compensate.

**Mitigation:**
- **PC Day 10 (Mon Jun 1):** PM kicks off selections check-in cycle per `pep_rules.md` Rule 4T defaults (5-wd lead-up: Fri May 29 → Thu Jun 4). Verb-phrase progression per `pep_rules.md` worked example: kick off → push → press → lock.
- **PC Day 12 (Wed Jun 3):** PM sends written summary of outstanding selections to homeowner. Track every unanswered item by name.
- **PC Day 14 (Thu Jun 4 AM):** Hard cutoff. Any selection still TBD → PM lands a backup choice from supplier catalog so chains can fire. Document in events.jsonl that homeowner accepted PM-selected fallback.
- **Per-item-fallback authority:** at contract signing, get homeowner written authorization for PM to make backup picks within $X allowance if selections aren't locked by PC Day 15. This removes the cascade lever entirely.
- **Tile is the canary:** `order.tile` is the longest selection-locked chain (14 cal-d). If it slips, all stock-7-d items have already slipped silently.

---

### R5. Existing main electrical service amperage check — MED

**Trigger conditions (observable):**
- Scope (`308_scope.pdf` p.3): *"Assumes existing main electrical service can support new subpanel."* Not verified.
- Per Round 1 interview + `addition_rules.md` §"Existing electrical service": typical homes have 200A service but may not have space to accept a 100A subpanel without a service upgrade.
- `prep.amperage_check` is scheduled PC Day 15 (Thu Jun 4) per `schedule.json`.
- Observable signal: PM's amperage check on Thu Jun 4 reveals (a) existing service < 200A, (b) panel slot exhaustion, or (c) main breaker rating insufficient for added 100A load.

**Impact:**
- **Schedule:** if check fails AND triggered BEFORE contract signing, the entire schedule re-baselines — minimal slip because we're still in PC. If check fails AFTER signing, the service upgrade becomes a CO and adds ~5–10 working days for service-upgrade scoping, utility coordination, and install (electrical service upgrades are utility-coordination-bound and often require POCO scheduling 1–2 weeks out).
- **Dollar:** $1,500–$3,500 CO for typical 200A service upgrade per baseline §"Open questions / sensitivities" #3.
- **Contractual exposure:** scope assumption shifts the risk to homeowner via CO, but only if check happens AT the right time. Late discovery (mid-job) creates relationship friction.

**Mitigation:**
- **PC Day 15 (Thu Jun 4):** Per `task_graph.json` `prep.amperage_check.depends_on: []` + `pre_construction_offset_working_days: 15` + `lead_up_working_days: 1`. PM confirms electrician scheduled on Wed Jun 3 (T-1); check done Thu Jun 4 AM.
- **Check result documented same day** in events.jsonl. If pass, route to `electrical.subpanel_install` gate (Day 30). If fail, immediately draft service-upgrade CO.
- **If CO triggered:** PM presents to homeowner within 48h. CO approval BEFORE contract signing (if not yet signed) or before electrical rough Day 30 (Wed Aug 5). Coordinate POCO service upgrade scheduling on the same call.
- **Belt-and-suspenders:** at PC walkthrough (Thu Jun 4 AM, paired with amperage check), PM photo-documents existing panel, breaker count, available slots. Surfaces panel-slot issues even if amperage is adequate.

---

## Watch List (PM monitors, does not pre-empt)

### W1. Shower glass enclosure template timing — MED

Per Round 4 + `task_graph.json`, `shower.glass_template` (0.5d, glazing) is FS after `tile.grout_seal` (Day 60–61), then `wait.shower_glass` (10 cal-d fab) → `shower.glass_install` (0.5d) → gates `paint.phase_2`. Per baseline §"Open questions / sensitivities" + initial.md "Risks tracked": *"If template slips by even 2–3 days, install lands inside the `paint.phase_2` predecessor wall and pushes substantial completion."* Per `schedule.json`, `shower.glass_install` IS on the critical path (`paint.phase_2` is FS after `shower.glass_install` plus every other finish trade). **Watch action:** PM confirms glass supplier templating slot on Day 55 (Wed Sep 9, ~1 week before grout cures). Verify supplier can template Thu Sep 17 AM following Wed Sep 16 grout cure. **Schedule impact if mismanaged:** 1–3 working days (substantial completion slip).

### W2. Drywall multi-zone duration — MED

Baseline budgets 11 working days for `drywall.consolidated` (multi-zone: addition + existing primary bedroom retrofit + hall bath patch + basement storage finish) vs. 6.6d at 159h ÷ crew 3. Per baseline §"Open questions / sensitivities" #7: *"If hall bath retrofit demo opens a worse-than-expected wall condition (concealed pipe, prior fire damage, etc.), drywall could push to 12–13 days."* **Watch action:** PM logs any retrofit wall condition surprises during `demo.selective_demo` (Days 6–8, Thu Jul 2 → Mon Jul 6) and `retrofit.hall_bath_window_infill_framing` (Day 9 AM, Tue Jul 7). **Schedule impact:** 1–2 working days; absorbable by interior finish float in current `schedule.json`.

### W3. Tankless WH option re-opened mid-job — MED

Round 1: homeowner declined the $6,500 tankless WH optional package; existing gas WH stays with vent extension only. Per baseline §"Open questions / sensitivities" #5: *"If accepted post-contract: adds `procurement.tank` (7-14 cal-d) + `plumbing.tank_set` (0.5d) + tank install + plumbing rough sequence change per Rule 4H."* **Watch action:** any homeowner mention of "we should do tankless after all" → PM evaluates BEFORE plumbing rough date (Day 30, Wed Aug 5). After that date, the schedule reorder is meaningfully more expensive. **Schedule impact:** minimal if ordered before plumbing rough; +0.5–1d if ordered after.

### W4. Selections "lock" silently drifts post-checkpoint — MED

Even after `checkpoint.selections_finalized` fires (Thu Jun 4), homeowners commonly come back 1–2 weeks later with "actually we wanted X instead." Per Will's voice in `wills_voice.md` (TDEC section pattern repeats for selections): unpredictable variance is the constant. **Watch action:** PM logs every post-checkpoint selection request in events.jsonl with delta cost + delta schedule. If aggregate post-lock changes exceed $1,500 OR 2 working days, formal CO. **Schedule impact:** typically 0–3 days; recoverable from interior finish float.

### W5. Concealed conditions in primary bedroom remodel — MED

Scope §"Primary Bedroom Remodel (~12'5" × 16')" — existing primary bedroom is being remodeled and merged into the addition via LVL opening per Round 1 interview. Per `addition_rules.md` §"Retrofit detection": *"Concealed wiring, plumbing, or structural irregularities encountered during demolition will be addressed via change order."* (Echo of `308_scope.pdf` p.1 standard carve-out.) **Watch action:** PM photo-documents existing bedroom walls + floor + ceiling during `demo.protection` (Day 5). Surfaces concealed wiring / plumbing routes that need re-routing. **Schedule impact:** 0–2 days; $0–$2k CO typical.

### W6. Hall bath two-bucket pattern collision — LOW

Per Rule 4V two-bucket: `early.acrylic_shower_swap` is Day 2 (Fri Jun 26, customer's "working shower" promise) and `retrofit.hall_bath_window_infill_framing` is Day 9 (Tue Jul 7) → `retrofit.hall_bath_repaint` is Day 54 (Tue Sep 8). These share a physical room across a 10-week span. **Watch action:** PM ensures the acrylic shower install on Day 2 is plumbed in a way that survives the Day 9 window demo + Day 54 repaint (i.e. don't tile/seal anything that gets disturbed by the window infill). **Schedule impact:** 0 days if respected; 1–2 days for rework if shower is damaged in retrofit work.

### W7. Drywall hairline cracking warranty return — LOW

Per `addition_rules.md` §"Drywall cracking" + `wills_voice.md` "Drywall warranty" section: *"Year one you'll get cracks at the tie-ins. Always. We come back and fix them. It's part of the job, not a callback."* **Watch action:** none required during build; surfaces 6–12 months post-handoff. **Schedule impact:** $0 on this job (warranty visit is internal cost; ~1d crew labor budgeted as standard TCR addition practice per baseline assumptions).

### W8. 2-interior-trade cap holds in practice — LOW

Per Rule 4N + `task_graph.json` HVAC stagger (`hvac.minisplit_install` FS after `electrical.finish`), the cap is enforced by the graph. **Watch action:** PM physically verifies on Days 54–58 that no more than 2 interior trades on site simultaneously (per Will's hard rule). If a sub shows up to "knock out a small thing" off-schedule, stack-up exceeds cap and finish work scuffs. **Schedule impact:** 0–1 day if cap breaks; not financially material but quality risk.

---

## What this register doesn't cover

This register intentionally excludes risk categories where TCR has no actuals harvested or where coverage lives outside the brain:

1. **Insurance events** (fire, theft, vandalism, water damage to homeowner property during construction). Covered by TCR's GL policy + builder's risk; not a scheduling/cost risk for this register.
2. **Customer payment risk.** Scope §"Rates" p.7 specifies weekly invoicing + deposit + balance due at completion. Collections risk is not scheduling-impacting and is owned by finance, not PM.
3. **Weather days.** Per `dev_rules.md` §12: *"v0.1 does not model weather days."* The job has roofing (Day 28–30), underlayment (Day 29), siding (Days 30–34), exterior paint touchpoints — all weather-sensitive. The schedule has zero weather-day buffer. Sizing impact requires `_company/actuals/` weather-day frequency data (P9 territory, currently empty). For now, treat each exterior bar as +1 day at-risk per per-region rain frequency; not quantified here.
4. **Subcontractor reliability variance.** TCR self-performs most work per Will's audit (line 432): *"the only way I work."* Subcontracted trades on this job (likely glazing for shower glass; possibly tile install crew) carry per-vendor reliability risk. Without actuals harvested, no baseline. Tracked as W1 (glazing) for the one identified sub-bound risk.
5. **Material market price spikes** post-contract. Lumber, copper, asphalt shingles all have shown 10–30% spikes on 30-day windows historically. Scope §"Rates" p.7 specifies materials at "discounted cost + 15%" — TCR carries that exposure for any pre-signed quote period. Not quantified without actuals.
6. **Field labor injury / OSHA event.** Outside the scheduling brain; insurance-policy domain.
7. **Code-violation findings from existing structure** discovered during inspection (e.g. inspector flags existing 1990s electrical that should be brought to current code). Possible but rare; would be a CO carve-out, similar to R3 mechanics but in a different domain. Not in baseline.
8. **Crew availability** (a sub goes out for medical, a foreman quits mid-job). TCR mitigates via cross-trained internal crew; not currently sized.

---

*All severity ratings, dollar ranges, and schedule slip sizes trace to a specific scope clause, audit transcript line, rule, belief, or interview answer cited inline. Idempotent on re-run with the same inputs.*
