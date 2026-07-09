---
generation_kind: intelligence_setup_v1
interview_status: needs_more
round: 8
depends_on:
  - _company/rules/dev_rules.md
  - _company/rules/editor_rules.md
  - _company/rules/pep_rules.md
  - _company/rules/README.md
  - _company/beliefs/_examples/stick_frame_default_for_small_additions.md
  - _company/beliefs/README.md
  - _company/knowledge/_examples/wills_voice.md
  - _company/knowledge/308_evergreen_wills_audit_transcript.md
  - _company/knowledge/README.md
  - _company/actuals/README.md
  - _company/_catalog/generation_kinds.json
  - job_types/addition/rules/addition_rules.md
  - job_types/addition/rules/tdec_septic_permit_offset.md
  - _projects/308-evergreen-street_APPPROJ-01KWAY4TXJ4QZ83TBVD123VB48/jobs/308-evergreen-street-addition_JOB-01KWAYWPR491ATYA1KM1W2GNDK/manifest.json
  - _projects/308-evergreen-street_APPPROJ-01KWAY4TXJ4QZ83TBVD123VB48/jobs/308-evergreen-street-addition_JOB-01KWAYWPR491ATYA1KM1W2GNDK/inputs/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KWAY4TXJ4QZ83TBVD123VB48/jobs/308-evergreen-street-addition_JOB-01KWAYWPR491ATYA1KM1W2GNDK/inputs/files/scope.pdf.ref.json
  - _projects/308-evergreen-street_APPPROJ-01KWAY4TXJ4QZ83TBVD123VB48/jobs/308-evergreen-street-addition_JOB-01KWAYWPR491ATYA1KM1W2GNDK/inputs/files/scope.pdf.txt
  - _projects/308-evergreen-street_APPPROJ-01KWAY4TXJ4QZ83TBVD123VB48/jobs/308-evergreen-street-addition_JOB-01KWAYWPR491ATYA1KM1W2GNDK/inputs/files/3725 SIMONS 012226.pdf.ref.json
  - _projects/308-evergreen-street_APPPROJ-01KWAY4TXJ4QZ83TBVD123VB48/jobs/308-evergreen-street-addition_JOB-01KWAYWPR491ATYA1KM1W2GNDK/inputs/files/3725 SIMONS 012226.pdf.txt
  - _projects/308-evergreen-street_APPPROJ-01KWAY4TXJ4QZ83TBVD123VB48/jobs/308-evergreen-street-addition_JOB-01KWAYWPR491ATYA1KM1W2GNDK/inputs/files/308_Evergreen_Addition.xlsx - Summary (1).csv.ref.json
  - _projects/308-evergreen-street_APPPROJ-01KWAY4TXJ4QZ83TBVD123VB48/jobs/308-evergreen-street-addition_JOB-01KWAYWPR491ATYA1KM1W2GNDK/inputs/files/308_Evergreen_Addition.xlsx - Summary (1).csv.txt
  - _projects/308-evergreen-street_APPPROJ-01KWAY4TXJ4QZ83TBVD123VB48/jobs/308-evergreen-street-addition_JOB-01KWAYWPR491ATYA1KM1W2GNDK/beliefs/interview-2026-06-30T00-52-17-722.md
  - _projects/308-evergreen-street_APPPROJ-01KWAY4TXJ4QZ83TBVD123VB48/jobs/308-evergreen-street-addition_JOB-01KWAYWPR491ATYA1KM1W2GNDK/beliefs/interview-2026-06-30T00-53-08-891.md
  - _projects/308-evergreen-street_APPPROJ-01KWAY4TXJ4QZ83TBVD123VB48/jobs/308-evergreen-street-addition_JOB-01KWAYWPR491ATYA1KM1W2GNDK/beliefs/interview-2026-06-30T01-05-26-788.md
  - _projects/308-evergreen-street_APPPROJ-01KWAY4TXJ4QZ83TBVD123VB48/jobs/308-evergreen-street-addition_JOB-01KWAYWPR491ATYA1KM1W2GNDK/beliefs/interview-2026-06-30T01-06-03-618.md
  - _projects/308-evergreen-street_APPPROJ-01KWAY4TXJ4QZ83TBVD123VB48/jobs/308-evergreen-street-addition_JOB-01KWAYWPR491ATYA1KM1W2GNDK/beliefs/interview-2026-06-30T01-16-06-125.md
  - _projects/308-evergreen-street_APPPROJ-01KWAY4TXJ4QZ83TBVD123VB48/jobs/308-evergreen-street-addition_JOB-01KWAYWPR491ATYA1KM1W2GNDK/beliefs/interview-2026-06-30T01-16-24-153.md
  - _projects/308-evergreen-street_APPPROJ-01KWAY4TXJ4QZ83TBVD123VB48/jobs/308-evergreen-street-addition_JOB-01KWAYWPR491ATYA1KM1W2GNDK/beliefs/interview-2026-06-30T01-16-29-989.md
last_verified_at: "2026-06-30T01:20:37.078Z"
---

# Intelligence setup — 308 Evergreen Street Addition

## What we know

### Customer & job

- Customer is 308 Evergreen Street; job type is `addition`; job started 2026-06-30 per `manifest.json`.
- Architectural drawings credited to Greyscale Design (Rebecca Lineberry, NCIDQ), dated 2026-01-22, labeled "Simons Addition" per `inputs/files/3725 SIMONS 012226.pdf.txt`.
- Seven prior interview rounds have answered the round-1 question set — all CRITICAL questions are now resolved with PM input (see PM-confirmed sub-section).

### Scope shape

- Two-story addition approximately 30' × 10' (≈ 300 sqft per floor) per `inputs/scope.md` objective.
- New construction adds: basement-level storage below; second-floor expansion of the primary bedroom, master bathroom, and walk-in closet above.
- Architectural drawings show: 1st-floor addition 295 sqft + basement addition 295 sqft = 590 sqft new footprint. Workbook lists "Overall Footprint SF 789" — that includes the existing-area remodel scope (primary bedroom retrofit + hall bath mod) on top of the 590 sqft addition.
- Total customer investment per scope: $173,850 base + optional packages (closet/cabinet $7,000, tankless WH $6,500). Breakdown CSV grand total: $100,778.92 direct cost.

### PM-confirmed (from interview rounds 1-7)

- **Customer early item (q.customer_early_items):** Hall bath acrylic shower swap. Emit as `early.acrylic_shower_swap` (1d, plumbing) on Day 1 in `site_prep / customer_early_items`, OFF the critical path, BEFORE main demo. The customer needs a working shower while construction runs.
- **Primary bedroom retrofit (q.retrofit_primary_bedroom):** Retrofit + new COMBINED. Existing primary bedroom merges into the addition via LVL wall removal; finishes treated as one continuous primary suite. Both areas gate on `drywall.consolidated` + the paint phases.
- **Elevator shaft (q.retrofit_elevator_shaft):** Retrofit, NOT inside addition. Per Will's audit transcript ("the elevator is over here and it's not even close to the addition over here, it's a retrofit item"). 4'×4' framing + dedicated 30A 120V circuit go in the existing house — own Component, runs in parallel with main scope.
- **Roof framing (q.roof_framing):** Stick-framed on site. ~300 sqft/floor, ~10' max wall length, 3/12 pitch — solidly inside the sub-800 sqft / sub-24' default per `stick_frame_default_for_small_additions.md`. NO `procurement.trusses`; lumber arrives day-of with the framing crew.
- **Septic / TDEC (q.septic_or_sewer):** Home is on septic. TCR handles the full TDEC application + soil-scientist scheduling as part of pre-construction. Treat as a ~6-week (42 calendar day) pre-con anchor. The clock starts at signed agreement / deposit — **on-site start is FLOATING until the contract is signed**. Anchor the schedule so on-site start = TDEC kickoff + 6 calendar weeks + 1 week buffer. Tank relocation / grinder pump install is a separate CO if the soil report requires it.
- **Electrical service (q.electrical_service_verified):** Pending verification. Add `prep.amperage_check` (0.5d, electrical) to pre-construction with `pre_construction_offset_working_days: 15`. If the existing main can't support the new 100A subpanel, the service upgrade becomes a separate CO. Flag in `warnings[]` until verified on-site.
- **Tankless WH option (q.tankless_wh_optional):** NOT accepted. Existing gas WH stays; only its vent gets extended through the new roof. Per Rule 4H scope condition, NO `procurement.tank` and NO `plumbing.tank_set` in the graph. Plumbing rough-in proceeds with no tank predecessor.
- **Concealed roof tie-in (q.concealed_roof_tie_in_ack):** Accepted. Bake a 2-3 day `buffer.concealed_roof_tie_in` behind `framing.roof` with SS lag 1 so any CO on concealed rafter / load conditions doesn't slip interior trades.

### Trades — already pinned by scope

- **HVAC is mini-split** — scope states "Install (1) ductless mini-split system. Budget $2,500." Per Rule 4G and editor_rules.md, MEP rough-in order is plumbing → electrical → mini-split rough (line set). Mini-split rough = 0.5d × 1 person; mini-split install = 1d × 1 person.
- **Plumbing rough = 4d × 2 crew** per editor_rules.md (Will's nominal). Driven by scope: master bath (2 lav + toilet + custom shower with dual valve diverter), W/D relocation with roof venting, extended vent stacks through new roof.

### Structural

- **LVL beam: 3-ply 14"** engineered LVL spanning ~15'-6" to open an existing load-bearing wall, with temporary shoring (scope.md). Per Will's audit transcript on THIS job (lines 360-394, 380-396): the LVL is for the second-story opening on the existing primary-bedroom side; "you can have the entire building built. Does not, this does not matter." The LVL temporary shoring + install run as an INDEPENDENT retrofit sub-chain — not gating new framing.
- New gable roof at 3/12 pitch tying into existing 6/12 — concealed roof tie-in present and acknowledged (see PM-confirmed q.concealed_roof_tie_in_ack).
- Foundation: continuous 12"×12" perimeter footings + 4" slab with vapor barrier + rebar — fits the editor_rules.md "monolithic by default" pattern (one pour, footings + slab same day, one footing inspection per Rule 4B).

### Procurement (defaults inferred; PM follow-ups pending)

- **Windows: 4 total** — (3) 36"×60" double-hung + (1) 3'×1' transom per drawings. Scope budget is $300/window, which strongly suggests stock — but type (stock vs custom) is not yet PM-confirmed. See q.window_order_type below.
- **LVL beam (3-ply 14")** — standard if not pressure-treated, supplier days 7-14 (`lead_time_days: 14` default for safety per addition_rules.md). Pressure-treated bumps to 21d. See q.lvl_type below.
- **100A subpanel** electrical panel: 7-14 supplier days per editor_rules.md.

### Site / retrofit prep

- Existing heat pump and existing electrical disconnect both need relocation per scope. Per addition_rules.md "Heat pump / HVAC component relocation — BEFORE demo", these go in `site_prep / prep_work_before_demo` ≥ 3 working days before main demo.
- Existing hall bathroom modification (window infill, drywall patch, repaint) is EXPLICITLY retrofit work and lives in its own `hall_bath_mod` Component under `interior_finishes`. The hall-bath acrylic shower swap is the SEPARATE customer-early-item bucket per Rule 4V (PM-confirmed).
- Hallway switch relocation with drywall patch + paint rolls into the consolidated drywall block.

### Risk register

- **Concealed roof tie-in** — existing 6/12 rafters meeting new 3/12 gable. Biggest CO source on this job per addition_rules.md. PM-accepted 2-3 day buffer reserved.
- **Electrical service amperage** — assumption per scope; `prep.amperage_check` task gates the subpanel install.
- **Septic CO risk** — soil scientist report may require tank relocation / grinder pump install (separate CO, not in scope).
- **Floating start** — on-site start tied to TDEC kickoff + 6 weeks + 1 week buffer, anchored on contract signing. The PEP narrative must surface this dependency prominently.

## What we're uncertain about

Three remaining procurement / scope questions before declaring the interview complete.

### q.window_order_type

**Question:** Are the 4 windows (3× 36"×60" double-hung + 1× 3'×1' transom) stock from a local supplier, or custom-ordered?
**Category:** procurement
**Hint:** Scope budget of $300/window strongly suggests stock — but worth confirming. Drives `wait.windows` lead time (14-21 days for stock vs 28-42 days for custom).
**Choices:**
- stock — readily available from local supplier
- custom — special-order from a manufacturer
- unsure — will check with supplier
**Why:** Sets `wait.windows.lead_time_days` for the procurement 3-task chain. Custom adds 2-3 weeks to the pre-con window, which on a TDEC-anchored start may not change critical-path but DOES change the PM's order-by date.

### q.lvl_type

**Question:** Is the 3-ply 14" LVL beam a standard engineered LVL, or pressure-treated / custom?
**Category:** procurement
**Hint:** Scope says "engineered LVL beam (3-ply 14")" — typical stock product if not PT. Will called this out in the audit transcript: "LVLs, like, a week before we start is fine ... unless we're getting pressure treated ones or something like that ... If you wanna set a rule for it, set it three weeks prior."
**Choices:**
- standard 3-ply 14" engineered LVL
- pressure-treated or custom-spec
- unsure
**Why:** Drives `wait.lvl_beam` lead time: 7-14 calendar days for standard vs 14-21 for PT/custom. Affects when the PM presses purchase.

### q.closet_cabinet_optional

**Question:** Is the optional Closet & Cabinet System package ($7,000 allowance — "Design and installation of custom shelving, rods, and closet organization system") included in the contract, or has the customer opted out?
**Category:** scope
**Hint:** This is a labor + materials item that lives in interior_finishes if accepted. Custom closet systems typically have a 21-day procurement lead and a 0.5-1d install in the walk-in closet.
**Choices:**
- included — full closet system in primary suite
- not included — basic shelving / rods only (no separate task)
- unsure — customer decision pending
**Why:** If included, adds (a) a `procurement.closet_system` 3-task chain and (b) a `closet.install` finish task gated on flooring + paint phase 1. If excluded, no graph changes. PM needs to lock this so the order doesn't slip past selections-finalized.

## Open commitments

- On-site start is **floating** until the contract is signed (PM-confirmed via q.septic_or_sewer). The schedule's anchor is TDEC kickoff + 6 calendar weeks + 1 week buffer.
- PM accepts a 2-3 day concealed-roof-tie-in discovery buffer (q.concealed_roof_tie_in_ack).
- PM accepts that the existing main service amperage is unverified — verification scheduled via `prep.amperage_check` 3 weeks before on-site (q.electrical_service_verified).
