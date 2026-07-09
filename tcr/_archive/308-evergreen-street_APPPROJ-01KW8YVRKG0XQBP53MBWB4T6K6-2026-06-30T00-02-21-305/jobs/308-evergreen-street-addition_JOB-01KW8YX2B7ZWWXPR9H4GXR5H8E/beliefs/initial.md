---
generation_kind: intelligence_setup_v1
interview_status: needs_more
round: 8
depends_on:
  - _company/rules/dev_rules.md
  - _company/rules/editor_rules.md
  - _company/rules/pep_rules.md
  - _company/rules/README.md
  - _company/rules/_examples/plumbing_rough_min_duration.md
  - _company/beliefs/README.md
  - _company/beliefs/_examples/stick_frame_default_for_small_additions.md
  - _company/knowledge/README.md
  - _company/knowledge/_examples/wills_voice.md
  - _company/knowledge/308_evergreen_wills_audit_transcript.md
  - _company/actuals/README.md
  - CONVENTIONS.md
  - README.md
  - _projects/308-evergreen-street_APPPROJ-01KW8YVRKG0XQBP53MBWB4T6K6/jobs/308-evergreen-street-addition_JOB-01KW8YX2B7ZWWXPR9H4GXR5H8E/manifest.json
  - _projects/308-evergreen-street_APPPROJ-01KW8YVRKG0XQBP53MBWB4T6K6/jobs/308-evergreen-street-addition_JOB-01KW8YX2B7ZWWXPR9H4GXR5H8E/inputs/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KW8YVRKG0XQBP53MBWB4T6K6/jobs/308-evergreen-street-addition_JOB-01KW8YX2B7ZWWXPR9H4GXR5H8E/inputs/files/scope.pdf.txt
  - _projects/308-evergreen-street_APPPROJ-01KW8YVRKG0XQBP53MBWB4T6K6/jobs/308-evergreen-street-addition_JOB-01KW8YX2B7ZWWXPR9H4GXR5H8E/inputs/files/3725 SIMONS 012226.pdf.txt
  - _projects/308-evergreen-street_APPPROJ-01KW8YVRKG0XQBP53MBWB4T6K6/jobs/308-evergreen-street-addition_JOB-01KW8YX2B7ZWWXPR9H4GXR5H8E/inputs/files/308_Evergreen_Addition.xlsx - Summary (1).csv.txt
  - _projects/308-evergreen-street_APPPROJ-01KW8YVRKG0XQBP53MBWB4T6K6/jobs/308-evergreen-street-addition_JOB-01KW8YX2B7ZWWXPR9H4GXR5H8E/beliefs/interview-2026-06-29T22-28-31-469.md
  - _projects/308-evergreen-street_APPPROJ-01KW8YVRKG0XQBP53MBWB4T6K6/jobs/308-evergreen-street-addition_JOB-01KW8YX2B7ZWWXPR9H4GXR5H8E/beliefs/interview-2026-06-29T22-38-34-530.md
  - _projects/308-evergreen-street_APPPROJ-01KW8YVRKG0XQBP53MBWB4T6K6/jobs/308-evergreen-street-addition_JOB-01KW8YX2B7ZWWXPR9H4GXR5H8E/beliefs/interview-2026-06-29T22-38-48-342.md
  - _projects/308-evergreen-street_APPPROJ-01KW8YVRKG0XQBP53MBWB4T6K6/jobs/308-evergreen-street-addition_JOB-01KW8YX2B7ZWWXPR9H4GXR5H8E/beliefs/interview-2026-06-29T22-41-05-593.md
  - _projects/308-evergreen-street_APPPROJ-01KW8YVRKG0XQBP53MBWB4T6K6/jobs/308-evergreen-street-addition_JOB-01KW8YX2B7ZWWXPR9H4GXR5H8E/beliefs/interview-2026-06-29T22-41-14-235.md
  - _projects/308-evergreen-street_APPPROJ-01KW8YVRKG0XQBP53MBWB4T6K6/jobs/308-evergreen-street-addition_JOB-01KW8YX2B7ZWWXPR9H4GXR5H8E/beliefs/interview-2026-06-29T22-42-15-947.md
  - _projects/308-evergreen-street_APPPROJ-01KW8YVRKG0XQBP53MBWB4T6K6/jobs/308-evergreen-street-addition_JOB-01KW8YX2B7ZWWXPR9H4GXR5H8E/beliefs/interview-2026-06-29T22-44-18-533.md
last_verified_at: "2026-06-29T22:52:40.121Z"
---

# Initial intelligence — 308 Evergreen Street addition (round 8)

## What we know

### Customer & project
- Customer is the Simons family at 308 Evergreen Street (manifest.json; architectural plans titled "Simons Addition" by Greyscale Design / Rebecca Lineberry, NCIDQ, dated 2026-01-22, in `3725 SIMONS 012226.pdf.txt`).
- Job type is `addition` (manifest.json).
- TCR storage mode is `project` — TCR's own AWS account for project_idx=132 (company manifest).

### Scope shape
- Two-story addition, approximately 30′ × 10′, ~590 sqft addition area (295 basement + 295 first-floor expansion per `308_Evergreen_Addition.xlsx - Summary (1).csv.txt`). Overall affected footprint per breakdown summary is 789 sqft — consistent with retrofit work spilling into adjacent existing rooms (now confirmed by PM — see "Primary bedroom" below).
- Basement level = new storage space. Upper level = expansion of the primary bedroom, master bath, and walk-in closet (scope.md "Objective").
- 17-section labor breakdown total: $45,167.59 labor / $52,171.33 material / $3,440 equipment = $100,778.92 grand total; ~1,287 labor hours. Contract investment quoted at $173,850 (scope.md footer).
- Plans show 2 new windows in the addition (one 3′0″×3′0″ DH + one 3′0″×1′0″ transom), 2 existing windows being relocated, one new exterior door (36″ metal), new brick to match existing on the back/right elevations, and a ridge tie-in via valleys to the existing 6/12 roof system.
- The "Existing Hall Bath Mod, Bedroom Remodel & Closeout" breakdown row has a negative material total (-$4,199). That's a credit / scope-reduction line item (Will manually adjusted material per the audit transcript pattern), not negative scope. Labor hours = 72, so real work is present; expect material allowance reconciliation.

### Sequencing / trades — derived from scope + Will's audit transcript
- HVAC system is **mini-split** (scope.md HVAC section: "ductless mini-split system. Budget $2,500"). Per `editor_rules.md` HVAC sequencing, MEP rough order is **plumbing → electrical → mini-split**. Mini-split rough = 0.5d / 1 person; install = 1d / 1 person (transcript lines 476, 482, 494).
- **Existing gas water heater stays** in the baseline scope — only the existing WH vent is extended through the new roof (scope.md "Selective Demolition & Site Work" + "Plumbing"). Per Rule 4H, **no `procurement.tank` and no `plumbing.tank_set`** apply in baseline. The optional Tankless WH package ($6,500) would flip this — q.tankless_wh_optional is still open this round.
- **Heat pump must be relocated before demo** (scope.md "Selective Demolition & Site Work"). Per Rule 4K, this lives in `site_prep / prep_work_before_demo`, NOT in the demo phase, scheduled ≥ 3 working days before demo. Transcript line 274 confirms this is THE 308 expectation.
- **Customer-requested early item — hall bath acrylic shower swap** is a Day-1 task in `site_prep / customer_early_items`, off the critical path, before main demo. PM answered q.customer_early_items in `interview-2026-06-29T22-28-31-469.md`. Modeled as `early.acrylic_shower_swap` — 1d, plumbing, depends_on `general.site_setup` (FS). The rest of the hall bath retrofit (window infill, drywall patch, repaint) is a SEPARATE component (`hall_bath_mod`) running in parallel with main scope per Rule 4V two-bucket pattern.
- **Hallway switch relocation** (existing hall, scope.md "Electrical") is retrofit — drywall patch + paint included.
- **W/D relocation** including water, drain, and roof venting is in scope (scope.md "Plumbing"). Treat as retrofit unless a future round narrows the destination to inside the addition footprint.

### Structural / framing — derived + PM-confirmed
- Foundation is monolithic by default per Rule 4B and confirmed in Will's transcript (line 326: "95% of the time. It's going to be very rare that I don't do monolithic"). Scope describes 12″×12″ continuous footings + 4″ slab with gravel/vapor/rebar — straight monolithic case. ONE pour task; one footing inspection covers both; 2-day cure.
- **Roof framing is stick-framed** (PM confirmed — see "Interview-state notes" for the decoding). ~300 sqft per floor footprint, ~10 ft max wall length, 3/12 pitch — falls inside the editor-rules stick-frame default for sub-800 sqft / sub-24 ft span additions. **NO `procurement.trusses` task.** Lumber arrives day-of with the framing crew. Roof framing itself = 2-3 days at crew 3; shingles = 1 day per Will's transcript line 420.
- One 3-ply 14″ LVL beam, ~15′-6″ span, "to open existing load-bearing wall including temporary shoring" (scope.md). Per Will's transcript (lines 369–382), the LVL is on the second story where an existing wall is being removed to merge the existing house with the new addition. **LVL is a retrofit item, independent of new addition framing** — temporary shoring → LVL install → remove shoring is its own sub-chain that does NOT gate new framing. Standard 3-ply 14″ = 14 calendar day procurement lead per editor_rules table.
- New gable ties into existing at a valley. Concealed roof tie-in risk remains — scope.md explicitly disclaims "Roof tie-in assumes standard integration; additional structural modifications not included." Per Will's transcript, this is the single largest CO source on additions. Schedule will carry a 2-3 working day discovery buffer SS-lagged off `framing.roof` (default); explicit PM acknowledgment can be captured in a later round.

### Spatial / Component placement — PM-confirmed in rounds 4-6 (see decoding notes)
- **Primary bedroom remodel is a combined retrofit + new build, treated as ONE continuous primary suite** (PM answer, decoded). The existing primary bedroom is being opened up via the LVL beam removal and merged with the new addition footprint into one master suite (bedroom + bath + walk-in closet). The scope's "Primary Bedroom Remodel (~12′5″ × 16′)" line covers BOTH the existing footprint finishes AND the new addition footprint finishes. **No separate retrofit Component for primary bedroom** — all primary-suite finishes flow through the main interior_finishes chain, gated by `drywall.consolidated` + paint phases per Rules 4E / 4L.
- **Elevator shaft is retrofit, NOT inside the addition footprint** (PM answer, decoded). The 4′ × 4′ shaft framing + the dedicated 120V/30A circuit live in the existing house, "not even close to the addition" per Will's audit transcript line 388-392. **Elevator shaft framing and its 30A circuit live in their own retrofit Component** (`elevator_shaft_retrofit`), running in parallel with main scope; no dependency on new addition framing or new MEP rough. Gates only on its own demo/access and on `drywall.consolidated` for the patch-up.
- **Hall bath retrofit (window infill, drywall patch, repaint)** stays a separate `hall_bath_mod` Component running in parallel with main scope, distinct from the Day-1 `customer_early_items` shower swap (Rule 4V two-bucket).

### Windows / doors — derived
- 4 windows: (3) 36″×60″ DH + (1) 3′0″×1′0″ transom (scope.md + plans page 4). All listed as stock-typical sizes; no callout for custom. Default assumption: stock → 14–21 calendar day lead (editor_rules procurement table). Still open — see q.window_order_type below.
- 1 new exterior door: 36″×1-3/4″ exterior metal door (plans door schedule). Stock-typical.
- 4 interior doors: 1 pre-hung + 2 pocket door systems (scope notes 4 total but specifies 3 — the 4th type is "to be confirmed during design phase"). Pocket-door systems need pre-rough-in framing dimensions.

### Pre-construction items — derived
- Permits = `general.permitting`: 1d work task, `pre_construction_offset_working_days: 15`, NOT a 14-day lead_time (Rule 4A; transcript line 134: "I walk in there with documentation, I walk out with a permit").
- TDEC septic coordination is **explicitly in scope** (scope.md "Pre-Construction & Design Phase"). Septic relocation, new tank/leach field, and grinder pump install are explicit change-order placeholders. Per Will's transcript (lines 156–170), TDEC is the most unpredictable lead time — plan 6 weeks (~42 calendar days) total. **Still the single biggest open question** — see q.septic_tdec_handling below.
- `checkpoint.selections_finalized` at `pre_construction_offset_working_days: 15` is mandatory per Rule 4P. Material list per scope: LVT $3/sqft, tile (wall $3, floor mosaic $6), vanity ($1,000), fixtures, mini-split. Per Will's transcript (lines 174–176), latest acceptable is 3 weeks before on-site.
- Equipment coordination checkpoint 2 weeks ahead, equipment on site day before consuming phase (transcript lines 261–269): dumpster, concrete saw, mini-ex, skid steer.

### Optional packages (priced separately, off the baseline schedule until accepted)
- Closet & cabinet system: $7,000 allowance (labor + material). Baseline assumes accepted (vanity / cabinets show up in interior finishes regardless); if homeowner declines, drop the closet-system component.
- Tankless WH: $6,500 allowance. **q.tankless_wh_optional remains open** — accepted vs declined flips Rule 4H ON or OFF for plumbing rough-in.

### Interview-state notes (rounds 1 → 7 with decoding)
The PM has submitted 7 interview rounds. Several answers landed in the wrong question slot (most likely a copy-paste habit or a UI input-routing issue). Decoding what the PM clearly INTENDED, based on answer content vs question text:

- **Round 1** (28-31): q.customer_early_items answered correctly — hall bath acrylic shower swap, Day 1, off critical path. ✓
- **Round 2** (38-34): q.roof_framing slot received the verbatim hall-bath text — misrouted, treated as no-op.
- **Round 3** (38-48): q.roof_framing slot received the same hall-bath text (misrouted again); q.septic_tdec_handling slot received the "Stick-framed on site. ~300 sqft/floor footprint, ~10′ max wall length, 3/12 pitch — all inside the sub-800 sqft / sub-24′ default" text. **That text is the answer to q.roof_framing, not q.septic.** Decoded → q.roof_framing = STICK-FRAME (folded into "Structural / framing" above). q.septic_tdec_handling is still unanswered.
- **Round 4** (41-05): same pattern continues. q.tankless_wh_optional slot received "Retrofit + new combined. The existing primary bedroom is being remodeled and merged into the addition via LVL wall removal..." — that text is the answer to q.primary_bedroom_remodel_scope, not tankless. **Decoded → q.primary_bedroom_remodel_scope = BOTH retrofit + new, treated as one continuous suite** (folded into "Spatial / Component placement" above). q.tankless_wh_optional is still unanswered.
- **Round 5** (41-14): duplicate save 9 seconds after round 4 — same answer set, no new content.
- **Round 6** (42-15): q.primary_bedroom_remodel_scope slot received "I cliI click" (a mis-click during submit). Treated as no-op — the PM's intended answer was already captured in the round-4 tankless slot. q.elevator_shaft_location was answered correctly this round → RETROFIT, not in addition footprint (folded into "Spatial / Component placement" above).
- **Round 7** (44-18): **byte-identical to round 6 — zero new content.** Same 5 question slots, same answers including the same "I cliI click" misclick on q.primary_bedroom_remodel_scope. The PM either re-submitted without changing anything (UI confusion / accidental re-save) or hit a UI snag that prevented entering new text. No new information to fold in.

**Net effect after round 7:** four CRITICAL/HIGH questions remain confirmed (customer_early_items, roof_framing, primary_bedroom_remodel_scope, elevator_shaft_location). The same three questions from rounds 3-6 remain genuinely unanswered: septic_tdec, tankless_wh_optional, window_order_type.

**Round 8 strategy.** Re-asking the same three open questions but with sharper hints to nudge the PM past whatever is blocking them. The choice lists are preserved verbatim — these are exactly the questions Will's downstream task graph needs answers to. Each hint now opens with a one-line reminder that this question is for THIS topic only (in case the misrouting is a copy-paste habit). If round 8 yields no new progress either, the responsible next move is to escalate the UI issue rather than continue spawning interview rounds; the PM's time is more valuable than the marginal cost of running on assumed defaults.

Safe defaults if these stay unanswered (so a baseline draft can still proceed):
- q.septic_tdec_handling → assume septic + TCR handles TDEC (42 cal-day lead in pre-construction). Adds ~6 weeks to PC; conservative.
- q.tankless_wh_optional → assume declined (baseline scope). Cheapest, simplest plumbing rough.
- q.window_order_type → assume stock (14-21 cal-day lead). Cheaper procurement.

## What we're uncertain about

### q.septic_tdec_handling

**Question:** Is the home on septic or city sewer? If septic, will TCR handle the full TDEC application + soil scientist scheduling, or is the homeowner driving that piece?
**Category:** permits
**Hint:** ⚠ This is the SEPTIC question — please type your answer for septic/sewer here (rounds 3-7 received roof-framing text in this slot by accident). TDEC is the single biggest schedule unknown right now; the on-site start date can't be fixed until this is answered.
**Choices:**
- City sewer — TDEC line in scope is a leftover, no action needed
- Septic — TCR handles full TDEC pipeline (apply, pay $500/permit, schedule soil scientist)
- Septic — homeowner handles TDEC, TCR coordinates only
- Septic — pending site assessment; not yet known
**Why:** TDEC is a 42-calendar-day lead time that anchors the realistic on-site start date. If TCR is driving, we need `permit.tdec_septic` (kind: lead_time, lead_time_days: 42) in pre-construction with `lead_up_working_days: 2`. If sewer, drop the whole branch and the on-site start moves up by ~6 weeks.

### q.tankless_wh_optional

**Question:** Did the homeowner accept the optional Tankless Water Heater package ($6,500 allowance — remove existing WH, install tankless with new vent + connections), or are we staying with the existing gas water heater (vent-extension only)?
**Category:** scope
**Hint:** ⚠ This is the TANKLESS WATER HEATER question — yes/no decision only (rounds 4-7 received primary-bedroom text in this slot by accident). Baseline scope keeps the existing WH and only extends the vent through the new roof.
**Choices:**
- Declined — existing gas WH stays (vent-extension only)
- Accepted — install tankless (new procurement + tank-set sequence before plumbing rough)
- Pending homeowner decision — assume declined for now
**Why:** If accepted, Rule 4H fires: we need `procurement.tank` (kind: procurement, lead_time 7-14 calendar days) AND `plumbing.tank_set` (0.5d) BEFORE `plumbing.rough_in`. If declined, plumbing rough-in proceeds without any tank predecessor (the common case). Wrong call = plumbing rough sequenced incorrectly and a procurement task either missing or unnecessary.

### q.window_order_type

**Question:** Are the windows stock-size or custom-order? Scope lists (3) 36″×60″ DH + (1) 3′×1′ transom — those sound stock-typical, but worth confirming with the vendor before procurement timing locks.
**Category:** procurement
**Hint:** Default assumption is stock (14–21 cal-day lead). Custom flips to 28–42 cal-days, which can push the on-site start.
**Choices:**
- Stock (14–21 supplier days)
- Custom (28–42 supplier days)
- Unsure — will confirm with vendor
**Why:** Windows generate an `order.windows → wait.windows → checkpoint.windows_arrived` chain per Rule 4R, backward from `windows.install` (which is FS-after `framing.roof` per Rule 4J). Stock vs custom doubles the procurement window and shifts the pre-construction start by 1-3 weeks.

## Open commitments

- Customer has been promised the hall bath acrylic shower swap will be done Day 1, BEFORE main demo, so they can live in the home during construction (confirmed by PM in `interview-2026-06-29T22-28-31-469.md`). This commitment locks the `early.acrylic_shower_swap` task into `site_prep` — it cannot slip into a later phase.
