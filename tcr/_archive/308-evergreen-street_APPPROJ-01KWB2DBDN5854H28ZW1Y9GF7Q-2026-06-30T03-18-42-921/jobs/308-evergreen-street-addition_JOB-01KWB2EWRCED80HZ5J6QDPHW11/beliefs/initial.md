---
generation_kind: intelligence_setup_v1
interview_status: needs_more
round: 1
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWB2DBDN5854H28ZW1Y9GF7Q/jobs/308-evergreen-street-addition_JOB-01KWB2EWRCED80HZ5J6QDPHW11/manifest.json
  - _projects/308-evergreen-street_APPPROJ-01KWB2DBDN5854H28ZW1Y9GF7Q/jobs/308-evergreen-street-addition_JOB-01KWB2EWRCED80HZ5J6QDPHW11/inputs/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KWB2DBDN5854H28ZW1Y9GF7Q/jobs/308-evergreen-street-addition_JOB-01KWB2EWRCED80HZ5J6QDPHW11/inputs/files/scope.pdf.txt
  - _projects/308-evergreen-street_APPPROJ-01KWB2DBDN5854H28ZW1Y9GF7Q/jobs/308-evergreen-street-addition_JOB-01KWB2EWRCED80HZ5J6QDPHW11/inputs/files/3725 SIMONS 012226.pdf.txt
  - _projects/308-evergreen-street_APPPROJ-01KWB2DBDN5854H28ZW1Y9GF7Q/jobs/308-evergreen-street-addition_JOB-01KWB2EWRCED80HZ5J6QDPHW11/inputs/files/308_Evergreen_Addition.xlsx - Summary (1).csv.txt
  - _company/rules/dev_rules.md
  - _company/rules/editor_rules.md
  - _company/rules/pep_rules.md
  - _company/knowledge/308_evergreen_wills_audit_transcript.md
  - job_types/addition/rules/addition_rules.md
  - job_types/addition/rules/tdec_septic_permit_offset.md
  - job_types/addition/beliefs/stick_frame_default_for_small_additions.md
last_verified_at: "2026-06-30T01:36:25.328Z"
---

# 308 Evergreen Street — Addition · Intelligence Setup (Round 1)

## What we know

### Customer & job

- Job is a TCR addition at **308 Evergreen Street** (manifest.json `customer`, `project_slug`).
- Job kicked off 2026-06-30 (manifest.json `started_at`); status `in_progress`.
- One peer addition is in flight at this company (9921 Emmerson Ln garage) but its generations are not yet authoritative.

### Scope objective

- **Two-story addition, approximately 30' × 10'**, comprising basement-level storage below and second-floor expansion of the primary bedroom, master bathroom, and walk-in closet (scope.md "Objective").
- Breakdown footprint: 789 sqft project area; drawings show **295 sqft 1st-floor addition + 295 sqft basement addition = 590 sqft net new** (`3725 SIMONS 012226.pdf`).
- Total breakdown grand total: $100,778.92 (`308_Evergreen_Addition...Summary.csv`).

### Existing structure & site

- New 3/12 gable roof **ties into existing 6/12 roof system** (scope §Roof System; drawings show R/V/S/T markers at tie-in). This is the single biggest change-order driver on this job.
- Exterior brick + lap siding to match existing; underlayment, drip edge, ridge vent (scope §Roof System / §Exterior Finishes).
- **Existing heat pump and electrical disconnect** must be relocated; runs in `site_prep / prep_work_before_demo` BEFORE main demo per addition_rules §"Heat pump / HVAC component relocation".
- **Existing gas water heater stays in place** — scope only extends its vent through the new roof. Rule 4H exception applies: NO `procurement.tank` / `plumbing.tank_set` tasks; `plumbing.rough_in` proceeds without a tank predecessor.

### Trades & sequencing (resolved from scope)

- **HVAC is mini-split**, explicitly: "(1) ductless mini-split system. Budget $2,500" (scope §HVAC). MEP rough-in order will follow plumbing → electrical → mini-split per editor_rules.
- **100A subpanel in scope** — triggers addition_rules `prep.amperage_check` task and the mandatory subpanel warning if no service-upgrade scope is verified.
- **Master bathroom** with custom tile shower (~7' × 4'), dual valve diverter, niche + bench, 72" double vanity, two faucets/mirrors/lights, commode, exhaust fan. Plumbing rough-in defaults to **4 working days × 2 crew** per editor_rules + Will's transcript line 1942.
- **W/D relocation** included (water, drain, roof venting). Plus extending vent stacks through the new roof.
- **LVL beam (3-ply 14")** spanning ~15'-6" to open an existing second-story load-bearing wall, with temporary shoring. Standard 3-ply — defaults to `lead_time_days: 14` per addition_rules §LVL beams. Per Will's transcript at this property, the LVL is a retrofit and the new addition's floor system framing depends on basement walls (not the LVL sub-chain) — **needs explicit PM confirmation** (see q.lvl_load_bearing).
- **Drywall** is Level 3 finish on new addition + bedroom remodel + basement storage + hall bath patches → consolidated into one `drywall.consolidated` block per editor_rules §Drywall consolidation.
- **Paint** two-phase per editor_rules §Paint (phase 1 after drywall sand, phase 2 last task gating substantial completion).
- **Mini-split rough** is 0.5d × 1 person; install is 1d × 1 person (editor_rules productivity table).

### Procurement signals

- **(4) windows: (3) 36"×60" double-hung + (1) 3'×1' transom** (scope §Exterior Finishes + drawings §Window Schedule). Sizes look stock but PM should confirm — drives 21d vs 35–49d lead.
- **(1) new exterior door** — 36"×1-3/4" metal panel per drawings door schedule.
- **Future elevator shaft framing only** — 4'×4', no elevator system, plus a dedicated 30A circuit from the subpanel for the future install.
- **Permit** = standard 1-day walk-in per editor_rules §Permits, `pre_construction_offset_working_days: 15`.
- **Mini-split unit** + selections lock 3 weeks before on-site per `checkpoint.selections_finalized`.
- **No long-lead cabinets** in scope (vanity is stock per allowance schedule).
- **Tankless WH is an OPTIONAL package** ($6,500 allowance) — scope main body keeps the existing tank; tankless only fires if the homeowner accepts the optional package.

### Permits

- Standard building permit (Will gets same-day ~90% of the time per editor_rules).
- **TDEC septic** explicitly named in scope: "Coordinate and complete septic inspection with TDEC. Determine feasibility of relocating septic system or installing new septic tank and leach field. Evaluate installation of grinder pump system to connect to available sewer line." → q.septic_tdec is mandatory. If septic, the 6-week TDEC lead governs the realistic start date per `tdec_septic_permit_offset` rule.
- Scope is explicit that **septic relocation / replacement / grinder pump costs are change-order items** — homeowner direction needed.

### Retrofit candidates detected (SCOPE WALK output)

Spatial-ambiguity walk against the addition objective (basement storage + primary bedroom + master bath + walk-in closet) flagged the following sections as retrofit candidates. Each gets its own confirmation question below:

1. **Existing Hall Bathroom Modification** — explicit "Existing Hall Bathroom" header; not in objective; includes removing existing window, framing opening, drywall patch + finish, removing tub/shower combo, installing acrylic shower system, reusing existing valve, repaint. Signal A + B. This matches the canonical 308 example in Will's audit transcript verbatim.
2. **Future elevator shaft** (4'×4', framing only) — the floor plan drawing places the ELEV. column between BTH. 2 / PRMRY. BTH. area and through to the basement near LOUNGE/STORAGE. Not clearly inside the addition footprint as drawn. Signal C ambiguity.
3. **Hallway switch relocation** ("Relocate (1) existing switch in hallway including drywall patch, priming, and painting") — explicit "existing" + "hallway"; minor, will roll into `drywall.consolidated` and `paint.phase_*` per editor_rules.
4. **Concrete walkway sawcut** and **railroad tie removal** — site work, not retrofit; absorbed into site_prep.

### Customer-requested early item — likely

The acrylic shower swap in the existing hall bath is **textbook customer-early-item shape**: the customer wants a working shower in the existing hall bath during the construction window. Will called out this exact pattern on this exact property in the audit transcript (Rule 4V was authored from this case). Pending PM confirmation in q.customer_early_items + q.retrofit_hall_bath, this will be modeled as:

- `early.acrylic_shower_swap` in `site_prep / customer_early_items`, Day 1.
- The remaining hall-bath work (window infill, drywall patch, repaint) in a separate `hall_bath_mod` retrofit Component running parallel to main scope.

### Risks already on the board

- **Concealed roof tie-in** — biggest CO source for this job (3/12 new into existing 6/12). Plan a 2–3 day discovery buffer (`roof.concealed_buffer`) running concurrent with `framing.roof`. PM must open the existing ceiling at the tie-in EARLY in framing.
- **TDEC septic uncertainty** — if on septic, 6-week lead anchors pre-construction.
- **Subpanel without verified service capacity** — the scope notes "assumes existing main electrical service can support new subpanel"; addition_rules requires an `prep.amperage_check` task before contract signing. Risk: service upgrade needed mid-job → schedule + cost blow-up.
- **Grinder pump option** — homeowner decision pending.

## What we're uncertain about

### q.customer_early_items

**Question:** Did the customer ask TCR to handle any work BEFORE the main job starts (e.g., a shower swap, leaky fixture, small demo) — anything they need done so they can live in the home comfortably during construction?
**Category:** sequencing
**Hint:** The hall-bath acrylic shower swap in scope looks like a textbook early-item candidate.
**Choices:**
- yes — list the items in a follow-up
- no — main job starts with site setup
- unsure
**Why:** Customer-requested early items get a dedicated `customer_early_items` Component in `site_prep` and run Day 1 before main demo, off the critical path. Skipping this question is how V10 collapsed the 308 shower swap into mid-job retrofit work (Rule 4V).

### q.retrofit_hall_bath

**Question:** The Existing Hall Bathroom Modification section (remove existing window + frame opening, acrylic shower swap, drywall patch, repaint) sits in an area NOT named in the addition objective. Confirm: is the acrylic shower swap a customer-requested EARLY item (Day 1, before main demo), and is the remaining work (window infill + framing + drywall patch + repaint) retrofit running in parallel with main scope?
**Category:** scope
**Hint:** Two-bucket pattern per Rule 4V: early item in `customer_early_items`, rest in `hall_bath_mod` retrofit Component.
**Choices:**
- yes — shower swap is Day 1 early item; rest is parallel retrofit
- no — all hall-bath work happens together (specify timing)
- only the shower swap is in scope; window infill / framing is not contracted
- unsure
**Why:** Drives whether `early.acrylic_shower_swap` lands Day 1 or gets collapsed into mid-job retrofit. Wrong bucket = customer doesn't get their promised working shower until November.

### q.retrofit_elevator_shaft

**Question:** The future elevator shaft (4'×4', framing only + 30A circuit, no elevator system) appears in the drawings between BTH. 2 / PRMRY. BTH. on the upper level and near the basement LOUNGE/STORAGE area. Is the shaft physically INSIDE the new 30'×10' addition footprint, or is it being cut into the existing house structure?
**Category:** scope
**Choices:**
- inside the new addition footprint
- retrofit into existing house structure
- partial — shaft straddles new and existing
- unsure
**Why:** Drives Component placement and dependencies. Retrofit shaft framing runs in its own Component, NOT gated on new exterior framing; in-addition framing rolls into the standard framing sequence.

### q.roof_framing

**Question:** Is the addition's gable roof framed with engineered trusses (long-lead procurement) or stick-framed on site (next-day lumber)? Scope says "truss or rafter framed, determined during design phase."
**Category:** procurement
**Hint:** Span is ~10' across the addition footprint; default for small additions is stick-frame (no procurement task).
**Choices:**
- stick-frame
- trusses
- unsure — design phase pending
**Why:** Trusses add a 35-day `procurement.trusses` task that gates roof framing. Stick-frame → no procurement task; lumber arrives next-day with the crew. The stick-frame default belief covers this footprint cleanly, but scope ambiguity requires explicit PM acknowledgment.

### q.septic_tdec

**Question:** Is the home on septic or city sewer? If septic, does TCR need to handle TDEC septic permits (scope mentions "coordinate and complete septic inspection with TDEC")? And which direction is the homeowner taking on the grinder-pump option?
**Category:** permits
**Hint:** TDEC is the longest single lead time on an addition — 6 weeks initial contact. Adding a bedroom + bathroom counts against septic capacity.
**Choices:**
- city sewer — no TDEC needed
- septic — TCR handles TDEC (kick off 6 weeks before on-site)
- septic — homeowner / separate contractor handles TDEC
- city sewer via new grinder pump connection (change order pending)
- unsure
**Why:** TDEC is 6 weeks lead and governs realistic on-site start (`permit.tdec_septic`, `lead_time_days: 42`, `pre_construction_offset_working_days: 30`). Grinder pump is an explicit homeowner decision per scope.

### q.concealed_roof_tie_in_ack

**Question:** Acknowledge: the new 3/12 roof tying into the existing 6/12 means existing rafter conditions are concealed until demo opens them up. Hidden damage, undersized rafters, or non-standard framing are real change-order risks. PM accepts a 2–3 day discovery buffer (`roof.concealed_buffer`) running concurrent with `framing.roof`?
**Category:** risk
**Choices:**
- accepted — proceed with buffer
- want to discuss before sign-off
**Why:** Most reliable CO source on additions per addition_rules §"Concealed roof tie-in". Explicit acknowledgment locks the buffer in the schedule and signals the PM should open the ceiling at the tie-in early in `framing.roof`.

### q.electrical_service

**Question:** Has the existing main electrical service been verified to support the new 100A subpanel (typical homes are 200A but may not have capacity / panel space)? Or does the PM need to plan a service-upgrade scope?
**Category:** scope
**Hint:** Scope assumes existing service is adequate but doesn't document a verification. Addition_rules requires `prep.amperage_check` (0.5d, general) in pre_construction.
**Choices:**
- verified adequate — proceed
- upgrade needed — separate scope being added
- unsure — PM will verify before contract
**Why:** Discovering an undersized service mid-job creates a schedule blow-up. The amperage-check task is mandatory; this question tells us whether to expect a service-upgrade sub-chain.

## Open commitments

- None known from current inputs. PM may add committed start dates, sub crew pre-bookings, or fixed-price ceilings on a later round.
