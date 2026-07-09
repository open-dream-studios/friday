---
generation_kind: intel_questions_v1
interview_status: needs_more
round: 1
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWB8K5NMMZV87339275BVY2Q/jobs/308-evergreen-street-addition_JOB-01KWB8YT0FMGEJH22DS9ZXSEYZ/manifest.json
  - _projects/308-evergreen-street_APPPROJ-01KWB8K5NMMZV87339275BVY2Q/jobs/308-evergreen-street-addition_JOB-01KWB8YT0FMGEJH22DS9ZXSEYZ/generations/_pre/MANIFEST.md
  - _projects/308-evergreen-street_APPPROJ-01KWB8K5NMMZV87339275BVY2Q/jobs/308-evergreen-street-addition_JOB-01KWB8YT0FMGEJH22DS9ZXSEYZ/generations/_pre/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KWB8K5NMMZV87339275BVY2Q/jobs/308-evergreen-street-addition_JOB-01KWB8YT0FMGEJH22DS9ZXSEYZ/generations/_pre/breakdown.md
  - _projects/308-evergreen-street_APPPROJ-01KWB8K5NMMZV87339275BVY2Q/jobs/308-evergreen-street-addition_JOB-01KWB8YT0FMGEJH22DS9ZXSEYZ/generations/_pre/plans.md
  - _projects/308-evergreen-street_APPPROJ-01KWB8K5NMMZV87339275BVY2Q/jobs/308-evergreen-street-addition_JOB-01KWB8YT0FMGEJH22DS9ZXSEYZ/generations/_pre/rules_index.md
last_verified_at: "2026-06-30T03:34:13.067Z"
---

## What we know

**Customer**
- 308 Evergreen Street, job type `addition` (manifest.json). Project name in breakdown: "Simons Addition – 30'×10' Two-Story + Bedroom Remodel".
- Drawings by Greyscale Design, LLC — Rebecca Lineberry NCIDQ, dated 01/22/2026 (_pre/plans.md Source).

**Scope — addition footprint**
- Two-story addition ~30' × 10' tying into existing structure; total new addition area 590 sqft (295 basement + 295 first-floor) (_pre/scope.md Footprint; _pre/plans.md sheet 4).
- 8'-0" ceilings both levels; 1'-0" rim/band at ceiling joint (_pre/plans.md elevations).
- Workbook total footprint 789 sqft includes retrofit areas (hall bath + bedroom remodel) (_pre/scope.md Footprint).

**Scope — addition contents**
- Master bath (2 lavs, 1 toilet, custom tile shower ~7'×4' with bench/niche, 72" double vanity) (_pre/scope.md MEP + Finishes; _pre/plans.md sheet 4 confirms layout).
- Primary bedroom remodel ~12'5" × 16' (_pre/scope.md Finishes).
- Basement storage (framed/drywalled/painted, single light, unfinished concrete) (_pre/scope.md Finishes).
- (1) future elevator shaft 4'×4' — framing + 30A circuit only, equipment NOT in scope; per plans this sits INSIDE the addition footprint (new construction) (_pre/plans.md Structural decisions).

**Foundation & framing**
- Continuous 12"×12" footings + 4" gravel + vapor barrier + reinforcement + 4" slab; NO CMU/foundation walls (_pre/scope.md Foundation) → monolithic pour default applies (Rule 4B per _pre/rules_index.md).
- (1) 3-ply 14" LVL spanning ~15'-6" to open existing load-bearing wall, with temporary shoring (_pre/scope.md Framing).
- Walls 2x4 @ 16" O.C. throughout (_pre/scope.md Framing).
- Roof: NEW 3/12 gable tying into existing 6/12 with multiple ridges/valleys at tie-in (_pre/scope.md Framing; _pre/plans.md sheet 5).
- Existing chimney shown near tie-in zone on roof plan (_pre/plans.md Retrofit indicators).

**Trades — fixed by scope**
- HVAC: ductless mini-split, $2,500 allowance (_pre/scope.md MEP). MEP rough order = plumbing → electrical → mini-split (Rule 4G).
- Existing gas water heater STAYS — only its vent is extended through the new roof; tank-set sequence (Rule 4H) does NOT apply to base scope (_pre/scope.md Special features; _pre/rules_index.md confirms).
- Electrical: new 100A subpanel, full rough+trim, 12 recessed, (1) 30A circuit for future elevator (_pre/scope.md MEP).
- Plumbing: master bath + W/D relocation + vent stack extensions; 40h section total (_pre/breakdown.md Trade totals) is borderline tight vs Will's 4d×2 nominal — see assumptions.

**Sequencing — pre-demo prep**
- Existing heat pump + electrical disconnect relocation required BEFORE main demo (_pre/scope.md Special features) → emit `prep.heat_pump_relocate` and `prep.electrical_disconnect_relocate` in `site_prep / prep_work_before_demo` (Rule 4K).
- Sawcut + remove existing concrete walkway; remove railroad ties (_pre/scope.md Special features) — site work before demo.

**Procurement — known long-leads**
- (1) 3-ply 14" LVL beam (lead-time defaults to 14 cal-d standard, 21 cal-d if custom/PT — see q.lvl_type if asked).
- Windows: $300/each allowance suggests stock (21 cal-d default); plans show 1 DH + 1 transom but scope says 4 — discrepancy noted, selections process will reconcile (_pre/plans.md Discrepancies).

**Retrofit zones identified**
- Hall bath (BTH. 2) sits in EXISTING structure per plans — scope has BOTH acrylic shower swap ($1,000 pan+walls allowance) AND window-infill/drywall/repaint work (_pre/scope.md Special features). Two-bucket pattern (Rule 4V) presumed.
- Bedroom 3: plans show new partition + new door + relocated existing window labeled "BDRM. 3" in existing structure; scope only names "Primary Bedroom Remodel" — could be same room or two distinct zones (_pre/plans.md Things plans show that scope doesn't mention; Discrepancies summary).
- Multiple "RELOCATED EXISTING WINDOW" annotations on left + back elevations — retrofit demo/reframe scope not separately itemized in CSV.

**Breakdown anomalies / silent omissions**
- "Existing Hall Bath Mod, Bedroom Remodel & Closeout" section has $-4,199 material total (= credit, likely customer-supplied acrylic shower system) bundled with $2,484.80 labor over 72h (_pre/breakdown.md Notes/anomalies). Section combines hall bath + bedroom + closeout — decomposition will need to split.
- TDEC septic permit fee + amperage check + concealed roof tie-in buffer are all silently absent from breakdown (_pre/breakdown.md Silent omissions). Each triggers a Stage-B question below.
- Tankless WH and closet/cabinet system are Optional Packages explicitly NOT in primary CSV totals.

**Rules layer (already indexed)**
- `_pre/rules_index.md` enumerates 30+ rules that apply. Notable defaults the PM doesn't need to be asked about: stick-frame default for <800 sqft + <24 ft span additions (per company belief stick_frame_default_for_small_additions.md, confidence 0.92 — though scope is explicitly ambiguous so PM confirmation still warranted via q.roof_framing); paint two-phase mandatory; bundled rough inspection; HVAC stagger for the 3-finish-trade cluster.

## What we're uncertain about

### q.customer_early_items

**Question:** Did the customer ask TCR to handle any work BEFORE the main job starts (e.g., the hall bath acrylic shower swap so they have a working shower during construction, a leaky fixture, small demo)?
**Category:** sequencing
**Hint:** The hall bath shower swap with the $1,000 pan+walls allowance fits the canonical early-item pattern in addition_rules. Confirm whether the customer expects it pre-demo or as part of the main hall bath retrofit timing.
**Choices:**
- Yes — hall bath acrylic shower swap is pre-demo (Day 1)
- Yes — different early item (PM will specify in notes)
- No — all hall bath work runs in normal retrofit timing
**Why:** Early items get their own Component (`customer_early_items`) in `site_prep` and run Day 1 BEFORE main demo (Rule 4V). Getting this wrong means the homeowner loses the working shower they expected.

### q.retrofit_hall_bath

**Question:** The hall bath (BTH. 2 per plans) sits in the existing structure and scope covers a shower swap, window-infill/reframe, drywall patch, insulation, and repaint. Confirm all of this is retrofit work (not part of the new addition envelope)?
**Category:** scope
**Hint:** If "yes retrofit", the non-early-item portion goes in its own `hall_bath_mod` Component in `interior_finishes` and runs parallel to main scope — gated by `drywall.consolidated` for patches and `paint.phase_1` for repaint.
**Choices:**
- Yes — all hall bath work is retrofit (two-bucket with the early item)
- No — hall bath work is part of main addition timing
- Mixed — PM will clarify in notes
**Why:** Triggers Rule 4V two-bucket pattern and pulls the hall bath work out of the addition critical path.

### q.retrofit_bedroom_scope

**Question:** Scope names "Primary Bedroom Remodel (~12'5" × 16')" but plans show a "BDRM. 3" with a new partition, new door, and relocated existing window. Are these the same room, or are there TWO bedroom retrofit zones (the primary bedroom AND a separate bedroom 3 partition/door change)?
**Category:** scope
**Hint:** This affects whether you have one bedroom retrofit Component or two — and whether bedroom 3 partition work was budgeted in the CSV's "Bedroom Remodel" line.
**Choices:**
- Same room — "Primary Bedroom" and "BDRM. 3" refer to the same physical space
- Two rooms — primary bedroom AND a separate bedroom 3 with partition/door changes (both in scope)
- Two rooms but bedroom 3 work is OUT of scope (change order if needed)
- Unsure — PM will field-verify with drawings
**Why:** Determines retrofit Component count and whether the breakdown's $2,484.80 labor / -$4,199 material section covered one room or two.

### q.roof_framing

**Question:** Is the new 3/12 gable roof framed with engineered trusses (28-42 cal-d lead time) or stick-framed on site (next-day lumber)?
**Category:** procurement
**Hint:** Scope says "truss OR rafter framed, determined during design phase." Company default (belief 0.92) is stick-frame for additions under 800 sqft with spans under 24 ft — this addition fits that profile. Confirming locks the call.
**Choices:**
- Stick-frame (lumber day-of, no procurement task)
- Trusses (emit procurement chain, 28-42 cal-d lead)
- Unsure — design phase still pending
**Why:** Trusses procurement (Rule 4Q) drives the longest pre-construction lead and changes the critical path. Default stick-frame skips it entirely.

### q.septic_tdec

**Question:** Is 308 Evergreen on city sewer or septic? If septic, does TCR need to pull the TDEC septic permit, or is the homeowner handling it? (Scope mentions TDEC coordination + septic feasibility + grinder pump option but excludes the work from base contract.)
**Category:** permits
**Hint:** Adding the master bath fixtures increases TDEC capacity load. If septic and TCR pulls the permit, that's a 42-cal-d lead at PC offset 30 working days — anchors the whole pre-construction schedule.
**Choices:**
- City sewer (no TDEC, no septic permit task)
- Septic — TCR pulls TDEC permit (emit `permit.tdec_septic` 42d lead, offset 30)
- Septic — homeowner handles permit (assume cleared by on-site start; flag risk)
- Unsure — PM will field-verify
**Why:** TDEC septic permit at 42 cal-d is the longest single lead item if it applies. Wrong call here means either a ghost 6-week PC anchor or a missed permit that stops excavation.

### q.lvl_load_bearing

**Question:** The (1) 3-ply 14" LVL opens an existing load-bearing wall. Does the NEW addition's floor or roof structure ABOVE bear on the LVL location — or is the LVL purely retrofitting the existing structure?
**Category:** structural
**Hint:** If the new addition's floor/roof bears on it, the LVL becomes a hard predecessor for `framing.floor_system` (Rule 4: structural_modifications gating). If purely retrofit, the LVL/shoring chain runs independent of new framing.
**Choices:**
- Yes — new addition loads bear on the LVL (LVL gates new framing)
- No — LVL is purely retrofit of existing structure (runs independent)
- Partial — PM will explain in notes
**Why:** Determines whether `structural.install_lvl` is on the critical path or an independent retrofit chain. Wrong call wastes 1-2 days on incorrect shoring sequencing.

### q.electrical_service

**Question:** Has the existing main electrical service been verified to support the new 100A subpanel? Scope assumes it can — does the PM need an amperage-check task and a service upgrade contingency?
**Category:** scope
**Hint:** Breakdown is silent on `prep.amperage_check`; addition_rules makes it mandatory. If service is undersized, an upgrade is a several-thousand-dollar change order and a multi-day on-site delay.
**Choices:**
- Verified adequate (existing main supports 100A subpanel — no upgrade)
- Upgrade needed (carry as change order; emit upgrade tasks)
- Unsure — emit `prep.amperage_check` and resolve at pre-con
**Why:** Drives whether `prep.amperage_check` lands in pre-construction and whether a service-upgrade change-order reserve is needed.

### q.vague_siding_material

**Question:** Scope says "vinyl siding to match existing as closely as possible" but the drawings call out "NEW BRICK TO MATCH EXISTING" on lower-level elevations with lap siding above. Which is correct — vinyl-only, brick+lap, or another combination?
**Category:** scope
**Hint:** Brick adds a masonry trade not currently in the CSV ($0 masonry line). Material + labor delta is significant; siding crew sequence (Rule "Same-crew exterior pattern") also changes if a masonry sub is added.
**Choices:**
- Vinyl only (per scope, drawings will be amended)
- Brick lower + lap siding upper (per plans, add masonry trade)
- All lap siding (no vinyl, no brick)
- Unsure — PM will resolve with customer + designer
**Why:** Adds or removes the masonry trade entirely. Wrong call either drops 3-5 days of brick work from the schedule or invents trades that aren't happening.

## Open commitments

(None recorded yet — PM Interview round 1 still pending. Capture any verbal start-date, fixed-ceiling, or pre-booked sub commitments in round 2 answers if applicable.)
