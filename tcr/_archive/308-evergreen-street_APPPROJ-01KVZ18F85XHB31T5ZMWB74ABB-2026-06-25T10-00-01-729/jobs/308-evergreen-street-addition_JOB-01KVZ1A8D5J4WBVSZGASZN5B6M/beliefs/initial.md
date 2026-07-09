---
generation_kind: intelligence_setup_v1
last_verified_at: "2026-06-25T09:29:53.637Z"
depends_on:
  - _company/rules/README.md
  - _company/rules/dev_rules.md
  - _company/rules/editor_rules.md
  - _company/rules/pep_rules.md
  - _company/beliefs/README.md
  - _company/beliefs/_examples/stick_frame_default_for_small_additions.md
  - _company/knowledge/README.md
  - _company/knowledge/_examples/wills_voice.md
  - _company/knowledge/308_evergreen_wills_audit_transcript.md
  - _company/_catalog/generation_kinds.json
  - job_types/addition/README.md
  - job_types/addition/rules/addition_rules.md
  - job_types/addition/rules/tdec_septic_permit_offset.md
  - job_types/addition/beliefs/stick_frame_default_for_small_additions.md
  - _projects/308-evergreen-street_APPPROJ-01KVZ18F85XHB31T5ZMWB74ABB/jobs/308-evergreen-street-addition_JOB-01KVZ1A8D5J4WBVSZGASZN5B6M/manifest.json
  - _projects/308-evergreen-street_APPPROJ-01KVZ18F85XHB31T5ZMWB74ABB/jobs/308-evergreen-street-addition_JOB-01KVZ1A8D5J4WBVSZGASZN5B6M/inputs/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KVZ18F85XHB31T5ZMWB74ABB/jobs/308-evergreen-street-addition_JOB-01KVZ1A8D5J4WBVSZGASZN5B6M/inputs/files/scope.pdf.ref.json
  - _projects/308-evergreen-street_APPPROJ-01KVZ18F85XHB31T5ZMWB74ABB/jobs/308-evergreen-street-addition_JOB-01KVZ1A8D5J4WBVSZGASZN5B6M/inputs/files/308_Evergreen_Addition.xlsx - Summary (1).csv.ref.json
  - _projects/308-evergreen-street_APPPROJ-01KVZ18F85XHB31T5ZMWB74ABB/jobs/308-evergreen-street-addition_JOB-01KVZ1A8D5J4WBVSZGASZN5B6M/inputs/files/3725 SIMONS 012226.pdf.ref.json
---

# Intelligence Setup — 308 Evergreen Street addition

Seed file for the per-job intelligence layer. Grounds every downstream
generation (baseline, risks, task_graph, schedule, daily_schedule, PEP)
and feeds the PM Interview questions.

## What we know

### Customer / Job

- Address is **308 Evergreen Street**; job_type is **addition**; the
  job kicked off **2026-06-25** with status `in_progress` (`manifest.json`).
- Parent AppProject is `APPPROJ-01KVZ18F85XHB31T5ZMWB74ABB`; canonical
  job id is `JOB-01KVZ1A8D5J4WBVSZGASZN5B6M` (`manifest.json`).
- One peer job exists at TCR — a Garage Addition at 9921 Emmerson Ln
  (`JOB-01KVV371088TPDJ532ZF8FFJ28`) — also in_progress. Useful as a
  reference-shape for addition-type generations; not the same physical
  job (cross-job index).

### Scope (canonical text NOT YET HYDRATED — see uncertainty)

- The authoritative scope is the uploaded **scope.pdf** (91 KB,
  `inputs/files/scope.pdf.ref.json`). `inputs/scope.md` is a pointer
  stub that defers to the extracted `scope.pdf.txt`, which does NOT
  yet exist in the trunk at time of this run — extraction is pending
  (`inputs/scope.md` instructions; `ls inputs/files/` confirms only
  the `.ref.json` is present).
- A breakdown CSV is uploaded: **308_Evergreen_Addition.xlsx —
  Summary (1).csv** (2.2 KB,
  `inputs/files/308_Evergreen_Addition.xlsx - Summary (1).csv.ref.json`).
  Also pending text extraction.
- A third document is uploaded: **3725 SIMONS 012226.pdf** (761 KB,
  `inputs/files/3725 SIMONS 012226.pdf.ref.json`). Likely
  architectural / engineering drawings given the size and filename
  pattern; NOT yet text-extracted (also pending hydration).

### Scope (from Will's audit transcript of an earlier AI schedule for THIS job)

The trunk contains
`_company/knowledge/308_evergreen_wills_audit_transcript.md`, an
ElevenLabs-transcribed walkthrough where Will reviews an earlier
AI-generated schedule for **this exact job**. The transcript is the
authoritative interim source-of-truth until scope.pdf finishes
extracting.

- The project is a **two-story addition** (Will: "this is the second
  story where we're taking out that wall", transcript lines 370–376).
- Footprint is approximately **30' × 10'** including basement-level
  storage below and second-floor expansion of the **primary bedroom,
  master bathroom, and walk-in closet** (`addition_rules.md`
  retrofit-detection example explicitly cites this scope verbatim;
  matches transcript geometry).
- The roof ties into the existing 6/12 roof with a new **3/12 gable**
  (transcript line 384 mentions roof framing dependency; pep_rules.md
  example day-block also names "Stick-frame 3/12 gable roof, tie into
  existing 6/12" as the 308 Evergreen pattern).
- HVAC is **mini-split** (not ducted) — Will: "because it's a mini
  split system, we can do HVAC last" (transcript line 458). MEP rough
  order is therefore **plumbing → electrical → mini-split**
  (transcript line 458, editor_rules.md HVAC sequencing).
- **Tankless gas water heater** is in scope; rough-in includes
  extending vent stacks through the new roof (transcript line 484).
- A **100-amp subpanel** feeds the new addition (transcript line 474).
- An **LVL beam** replaces an existing load-bearing wall on the
  second story to open up to the new space (transcript lines 370–384,
  385–395). Will treats this as an **independent retrofit sub-chain**
  — the LVL temp shoring is not blocked by new floor/wall framing
  (transcript lines 376–395).
- The project includes an **elevator shaft** to frame (transcript
  line 396), located off the addition footprint — Will explicitly
  flags this as **retrofit work**: "the elevator is over here ...
  it's not even close to the addition over here ... it's a retrofit
  item" (transcript lines 388–395).
- A **hall bath retrofit** is part of the contract — likely window
  infill / drywall patch / repaint per the standard 308 pattern
  encoded in `addition_rules.md` and `editor_rules.md` Rule 4V worked
  example (Rule 4V uses 308 explicitly as the canonical example).
- The customer asked for a **hall bath acrylic shower swap** as a
  customer-requested early item, BEFORE main demo, so the homeowner
  has a working shower during construction (`addition_rules.md`
  "Customer-requested early items" → "308 example: hall bath acrylic
  shower swap, customer wanted a fresh shower before the job broke
  ground"; `editor_rules.md` worked example also names this).
- An existing heat pump and/or electrical disconnect needs to be
  **relocated before main demo** — Will's review explicitly fixed the
  earlier graph for ordering this in `site_prep` not `demo_and_protection`
  (transcript lines 270–286).
- TDEC septic IS in play for this job — Will: "the TDEC thing, that
  definitely needs to be early" (transcript line 150).

### Sequencing / authoritative decisions Will made on the earlier schedule

- **Permit walk-in is same-day ~90% of the time**; schedule it as a
  1-day work task **3 weeks** before on-site start (transcript lines
  130–148; `editor_rules.md` Rule 4A; `dev_rules.md` Rule 4A).
- **TDEC initial contact is 6 weeks before on-site start** (transcript
  lines 156–172). End-to-end TDEC permit window is 4–6 weeks
  (`addition_rules.md` §TDEC).
- **Customer selections must be locked 3 weeks before on-site start**
  (transcript line 192; `dev_rules.md` Rule 4P; `editor_rules.md`
  general_conditions template).
- **Foundation is monolithic** — footings + slab same day, one
  inspection covers both (transcript lines 308–328; `editor_rules.md`
  Foundation; `dev_rules.md` Rule 4B). Will: "95% of the time. It's
  going to be very rare that I don't do monolithic" (transcript
  line 326).
- **Windows install IMMEDIATELY after roof is framed**, in parallel
  with roofing underlayment — not after the dried-in milestone
  (transcript line 424; `addition_rules.md` Windows install;
  `dev_rules.md` Rule 4J).
- **Rough MEPs gate on `roofing.underlayment` + `windows.install`,
  NOT on the dried-in milestone** (transcript lines 444–457;
  `addition_rules.md` MEPs gated on underlayment + windows;
  `dev_rules.md` Rule 4I).
- **Framing inspection comes AFTER rough MEP inspections, bundled
  with them** — plumbers / electricians drill the framing during
  rough-in (transcript lines 398–417; `dev_rules.md` Rule 4C).
- All **rough inspections happen on ONE day with ONE inspector**;
  same pattern for finals (transcript lines 506–514, plus
  `editor_rules.md` Inspection-Punch-Loop).
- **2-day punch-list buffer minimum** after each rough inspection
  before the next trade enters (transcript line 530; `dev_rules.md`
  Rule 4D).
- **Mini-split rough = 0.5 day, 1 person**; mini-split install =
  1 day, 1 person (transcript lines 472–494; `editor_rules.md` HVAC
  defaults).
- **Plumbing rough-in = 4 days × 2 crew** for this job (master bath
  + tankless + vent stacks through new roof) — Will's nominal
  (transcript line 484; `editor_rules.md` plumbing default).
- **Tank set BEFORE plumbing rough-in** (transcript lines 484–490;
  `dev_rules.md` Rule 4H). Tank-set and first day of plumbing
  rough-in can run concurrently via SS (transcript line 488).
- **100A subpanel install = 1 day, 1 person** (transcript line 474;
  `editor_rules.md` electrical productivity).
- **Equipment (dumpster, saw, skid steer, mini-ex, scaffolding) lands
  the day BEFORE the consuming phase**; coordination checkpoint 2
  weeks out (transcript lines 256–273; `editor_rules.md` equipment
  day-before rule; `dev_rules.md` Rule 4O).
- **TCR uses one same-crew exterior block** for roofing / siding /
  trim / fascia-soffit / gutters by default (transcript lines
  430–438; `editor_rules.md` Same-crew exterior pattern). Will: "I'm
  not the type of company that brings in a siding guy, and that
  brings in a roofer ... I just bring in the guy that can do all of
  it" (transcript lines 430–432).
- **Max 2 interior trades concurrent** (hard cap during interior
  finishes); HVAC staggers AFTER electrical when 3+ would overlap
  (`editor_rules.md` crew concurrency + 3-finish-trade overlap;
  `dev_rules.md` Rule 4N).
- **Paint is always two phases**; paint phase 2 is the last work task
  on site and gates substantial completion (`dev_rules.md` Rules 4E,
  4F; `editor_rules.md` Paint two phases).
- **Will's personal final walkthrough is the LAST task** on every
  addition, 1 working day after `inspect.final_bundled`
  (`addition_rules.md` Will's walkthrough).

### Procurement (from rules + transcript)

- **Standard LVL: 1 week supplier lead; safety default 14 days** —
  Will: "LVLs, like, a week before we start is fine" → default 3
  weeks in case pressure-treated or custom (transcript lines
  198–202; `addition_rules.md` §LVL beams).
- **Stick-frame default** for this footprint (under 800 sqft, span
  under 24 ft) — no `procurement.trusses` task needed
  (`job_types/addition/beliefs/stick_frame_default_for_small_additions.md`;
  `addition_rules.md` §Roof trusses CONDITIONAL).
- **Mini-split unit + tankless water heater ordered at or near
  dried-in**, NOT at project start (transcript lines 202–214;
  `addition_rules.md` Material ordering for additions;
  `editor_rules.md` Will's universal rule).
- **Standard fixtures, vanity, LVT flooring, paint** follow the
  use-date-minus-1-week rule (transcript line 244;
  `editor_rules.md` Will's universal rule).
- **Long-lead cabinets (42–56 supplier days) and custom tile (14–21
  supplier days)** must be ordered at structural sign-off if in scope
  (`addition_rules.md` Material ordering).
- All procurement uses the **3-task pattern** (order / wait /
  arrived) and lives in the dedicated **`procurement_long_leads`
  phase**, NOT in `pre_construction` (`addition_rules.md` §CRITICAL:
  do NOT put procurement chains in pre_construction; `dev_rules.md`
  Rule 4R).

### Known risks for additions (TCR baseline)

- **Concealed roof tie-in** is the single biggest schedule risk on a
  roof-tie-in addition — existing rafter / truss conditions are
  hidden until demo opens the ceiling (`addition_rules.md` §Concealed
  roof tie-in). Model a 3-day discovery buffer concurrent with
  `framing.roof`.
- **Year-1 drywall cracking** at addition tie-ins is inherent and
  covered under TCR's standard 1-year warranty return (NOT scheduled
  work) (`addition_rules.md` §Drywall cracking; Will's voice in
  `_company/knowledge/_examples/wills_voice.md`).
- **TDEC variance** — Will: "can take a long time, can go pretty
  quick" — the 6-week budget is the safety number (transcript line
  166; `addition_rules.md`).

## What we're uncertain about

The PM Interview will pull from these. The most load-bearing ones are
flagged with WHY they matter so the downstream task_graph can make a
real decision once answered.

- **q.scope_pdf_hydrated**: Has `scope.pdf` (and the breakdown CSV
  and `3725 SIMONS 012226.pdf`) finished text-extraction yet? If not,
  re-run intelligence_setup_v1 once the hydration consumer has
  populated `inputs/files/*.txt`. Without the extracted scope text we
  are working off Will's audit transcript and the addition_rules.md
  example — both consistent, but the canonical line-item scope can
  only come from the PDF.

- **q.on_septic_or_sewer**: Confirm 308 Evergreen is on **septic**
  (TDEC applies, ~6-week permit window) versus city sewer (TDEC
  skipped entirely). The transcript treats TDEC as in-play; we need
  an explicit confirmation before locking the pre-construction
  window. Drives whether `permit.tdec_septic` is emitted with
  `pre_construction_offset_working_days: 30`.

- **q.target_on_site_start_date**: What's the target on-site start
  date? The schedule's pre-construction window (TDEC 6 weeks, permit
  3 weeks, selections 3 weeks) is anchored backward from this date.
  No date is yet recorded in the trunk.

- **q.tdec_status**: Has the **TDEC initial contact** already been
  made / fee paid / soil scientist scheduled? If steps 1–3 are
  already underway, the 6-week budget shrinks accordingly.

- **q.permit_status**: Has the **building permit application** been
  assembled or submitted? Affects placement of `general.permitting`
  in the pre-construction window.

- **q.selections_status**: Are customer selections (tile, paint,
  fixtures, flooring, vanity, door style) **locked**? If not, what's
  outstanding? Drives `checkpoint.selections_finalized` and gates
  finish-material procurement.

- **q.existing_service_amperage**: What is the existing main service
  amperage at 308 Evergreen? A 100A subpanel is in scope (transcript
  line 474) — confirm the main has capacity, or flag a
  service-upgrade scope addition. Triggers `prep.amperage_check`.

- **q.heat_pump_relocation_needed**: Are the existing **heat pump
  or electrical disconnect** physically in the path of the new
  addition footprint (requiring `prep.heat_pump_relocate` /
  `prep.electrical_disconnect_relocate` BEFORE main demo)? Will's
  audit assumed yes; confirm for this exact site.

- **q.lvl_load_bearing_on_new_framing**: Does the **new floor or
  roof load** of the addition actually bear on the LVL location? If
  yes, gate new framing on LVL install completion. If no (Will's
  default reading of the 308 condition: independent retrofit),
  framing runs in parallel with the LVL sub-chain.

- **q.lvl_standard_or_custom**: Is the LVL beam **standard / off the
  shelf** (1 week, default 14d safety) or **pressure-treated /
  custom** (21+ days)? Affects procurement lead time.

- **q.windows_stock_or_custom**: Are the new windows **stock**
  (14–21 supplier days) or **custom** (28–42 days)? Drives the
  windows procurement lead.

- **q.tankless_replaces_existing**: The tankless water heater is in
  scope — is it **replacing an existing water heater** (apply Rule
  4H: tank set FIRST, before plumbing rough-in) or is it a **new
  install** with no existing tank to remove (same Rule 4H sequence)?
  Either way the tank-set-first rule applies, but the procurement
  lead time and PM coordination differ.

- **q.customer_early_items_confirmed**: Confirm the **hall bath
  acrylic shower swap** as a customer-requested early item (Rule 4V
  trigger). Any OTHER early items the customer asked for before main
  demo (leaky fixture fix, small demo, prep work)? These land in
  `site_prep / customer_early_items` Day 1, NOT bundled with
  retrofit work.

- **q.hall_bath_retrofit_scope**: Confirm the **hall bath retrofit**
  scope (window infill framing, drywall patch, repaint). Rule 4V
  requires this to live in its OWN component (`hall_bath_mod` under
  `interior_finishes`) separate from the customer-early-item
  acrylic-shower swap. Are there other rooms with retrofit work?

- **q.elevator_scope_full**: The elevator shaft framing is the
  only known elevator-related task (transcript line 396). Confirm
  full elevator scope (any mechanical, electrical, finish work
  related to the elevator). Confirm location is **off the new
  addition footprint** (Will treats it as retrofit per transcript
  line 388–395).

- **q.roof_tie_in_known_conditions**: Are there any **known
  structural conditions** at the existing roof tie-in point
  (rafter / truss sizes, hidden damage, prior modifications)? Or
  is it strictly a discovery-on-day-1-of-framing exercise? Sizing
  the concealed-roof-tie-in change-order budget.

- **q.architectural_plans_uploaded**: Is `3725 SIMONS 012226.pdf`
  the architectural / engineering drawing set for 308 Evergreen?
  The filename pattern doesn't match the address — confirm it's
  the right document (could be a misfiled upload from another job).

- **q.equipment_reservation_status**: Which equipment (dumpster,
  concrete saw, skid steer / mini-ex, scaffolding) is already
  reserved versus pending? Drives the
  `checkpoint.equipment_confirmed_*` placement and the day-before
  delivery tasks.

- **q.weather_or_customer_end_date**: Is there a customer-imposed
  completion deadline (move-in date, seasonal constraint, event)?
  And is any portion of the exterior work (roof, siding) in a
  weather-sensitive window worth flagging in `assumptions[]`?

## Open commitments

None recorded in the trunk yet. The PM Interview should capture any
verbal start-date promise, fixed-price ceiling, or sub crew
pre-booking made to the customer.
