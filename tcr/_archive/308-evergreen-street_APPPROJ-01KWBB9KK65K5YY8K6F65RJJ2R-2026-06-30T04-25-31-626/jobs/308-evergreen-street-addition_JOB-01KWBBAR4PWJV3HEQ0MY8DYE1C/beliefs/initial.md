---
generation_kind: intel_questions_v1
interview_status: needs_more
round: 1
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWBB9KK65K5YY8K6F65RJJ2R/jobs/308-evergreen-street-addition_JOB-01KWBBAR4PWJV3HEQ0MY8DYE1C/manifest.json
  - _projects/308-evergreen-street_APPPROJ-01KWBB9KK65K5YY8K6F65RJJ2R/jobs/308-evergreen-street-addition_JOB-01KWBBAR4PWJV3HEQ0MY8DYE1C/generations/_pre/MANIFEST.md
  - _projects/308-evergreen-street_APPPROJ-01KWBB9KK65K5YY8K6F65RJJ2R/jobs/308-evergreen-street-addition_JOB-01KWBBAR4PWJV3HEQ0MY8DYE1C/generations/_pre/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KWBB9KK65K5YY8K6F65RJJ2R/jobs/308-evergreen-street-addition_JOB-01KWBBAR4PWJV3HEQ0MY8DYE1C/generations/_pre/breakdown.md
  - _projects/308-evergreen-street_APPPROJ-01KWBB9KK65K5YY8K6F65RJJ2R/jobs/308-evergreen-street-addition_JOB-01KWBBAR4PWJV3HEQ0MY8DYE1C/generations/_pre/plans.md
  - _projects/308-evergreen-street_APPPROJ-01KWBB9KK65K5YY8K6F65RJJ2R/jobs/308-evergreen-street-addition_JOB-01KWBBAR4PWJV3HEQ0MY8DYE1C/generations/_pre/rules_index.md
last_verified_at: "2026-06-30T04:16:32.069Z"
---

## What we know

### Customer & job

- Customer / site: **308 Evergreen Street** (manifest.json `customer`); job_type `addition`.
- Project label per breakdown: "Simons Addition – 30'x10' Two-Story + Bedroom Remodel" (_pre/breakdown.md §header).
- Plan-set header reads "3725 SIMONS / 647 AA DEAKINS RD, JONESBOROUGH, TN 37659" — address discrepancy with manifest customer (_pre/plans.md §"address mismatch").

### Scope — new construction (objective areas)

- **30' × 10' two-story addition, 590 sqft total** (1st floor 295 sqft + basement 295 sqft); ceiling height 8' (_pre/scope.md §Footprint).
- 1st floor addition: primary bedroom + master bath (His/Hers vanity split, bench, LINEN) + walk-in closet zone; plans confirm layout (_pre/scope.md §Special features; _pre/plans.md §Structural).
- Basement addition: storage finish (frame + drywall walls, L3 + paint, 1 light fixture) (_pre/scope.md L136-140).
- 4'×4' elevator shaft framed inside addition footprint (future-equip), with rough-in for dedicated 30A/120V circuit (_pre/plans.md §Structural; _pre/scope.md L55, L85, L153-155).
- Foundation: continuous 12"×12" footings + 4" slab on gravel + vapor barrier + rebar; NO CMU, NO foundation walls → monolithic-pour compatible (_pre/scope.md §Foundation; rules_index 4B).
- Framing: 2×4 @ 16" O.C. throughout; (1) 3-ply 14" LVL ~15'-6" span opening existing load-bearing wall (temp shoring required) (_pre/scope.md §Framing).
- Roof: NEW 3/12 gable tying into existing 6/12; architectural shingles + synthetic underlayment + drip edge + flashing + ridge vent (_pre/scope.md §Framing).

### Scope — retrofit (existing-area work)

- **Primary bedroom remodel (~12'5" × 16')**: modify framing, L3 drywall, prime + paint, new LVT, full trim (_pre/scope.md §Special features). Explicitly retrofit — separate Component.
- **Existing hall bath modification**: remove existing window + frame infill + insulate/drywall/finish + repaint; remove existing tub/shower combo + install acrylic shower system ($1,000 allowance for pan+walls); reuse existing valve & trim; PVC trim (_pre/scope.md L141-149). Explicitly retrofit.
- **Existing windows + doors**: multiple "relocated existing" windows called out on Left/Back/Right elevations; W/D relocation (water/drain/roof vent); existing door relocations in primary-bedroom area (_pre/plans.md §Retrofit indicators).

### Site & sequencing

- **Pre-demo prep required**: existing heat pump relocation + existing electrical disconnect relocation BEFORE demo crew arrives (_pre/scope.md L36; rules_index 4K).
- Vent extensions through new roof: gas WH vent extension, plumbing vent stacks, dryer vent, bath-fan vent (_pre/scope.md §MEP highlights).
- Roof tie-in geometry: plans reveal **multiple valleys + ridges + transitions + existing chimney to navigate**; scope L64 calls tie-in "standard integration" but drawing geometry is non-trivial (_pre/plans.md §"Things plans show that scope doesn't mention").
- Material mismatch: scope L67 says "vinyl siding to match existing"; elevations show "NEW LAP SIDING" upper + "NEW BRICK TO MATCH EXISTING" lower band (_pre/plans.md §"Things plans show…").

### Trades & sizing

- **HVAC: ductless mini-split**, $2,500 unit budget (_pre/scope.md §MEP) → mini-split MEP order applies (plumbing → electrical → mini-split rough 0.5d/1 person) (rules_index 4G).
- **Plumbing**: full rough (supply/waste/vent) + master bath (2 lavs, 1 toilet, 1 custom shower w/ dual-valve diverter) + W/D relocation + vent stacks through roof. CSV labor only 40 lh — well below the editor-rules 4d × 2 crew floor for master bath / W/D / vent extension (_pre/breakdown.md §"Notes / weird lines"; editor_rules §Plumbing rough-in duration). Agent will override duration to floor.
- **Electrical**: (1) new 100A subpanel; full rough + finish; ~12 recessed @ $25 ea; vanity + bath fan/light; GFCI/AFCI; dedicated 30A/120V circuit reserved for future elevator (_pre/scope.md §MEP).
- **Insulation**: R13 walls, R30 attic, R30 floor between basement and living (_pre/scope.md §Insulation) — typical addition = 1d install per editor rules.
- **Drywall**: 3-coat L3 sanded; CSV bundles addition + bedroom remodel (159 lh) — consolidate into one hang/finish block per editor rules (also fold hall-bath patch + basement storage in).

### Procurement (3-task pattern targets)

- Windows: 4 total — Win 01 = 3'×1' transom (qty 1), Win 02 = 3'×3' DH (qty 1), plus 2 relocated existing reinstalls (_pre/plans.md §Schedule). Order-type (stock vs custom) NOT yet confirmed.
- Exterior door: 1× 36" 1-3/4" exterior METAL door (Door D); allowance $500 (_pre/scope.md §Allowances; _pre/plans.md §Schedule).
- LVL beam: 3-ply 14" engineered, ~15'-6" span. Standard size per editor-rules table → 7d (14d safety).
- Subpanel: 100A panel.
- Mini-split unit: $2,500 budget; supplier 7-14d.

### Permits & jurisdiction

- Permit per local jurisdiction; modeled as 1-day general work, offset 15 wd (rules_index 4A).
- Plans designer: Rebecca Lineberry NCIDQ / Greyscale Design LLC; plan date Jan 22 2026 (_pre/plans.md §Drawing set).
- Septic / TDEC: scope L25-30 defers TDEC inspection + feasibility + grinder-pump-to-sewer to a CO; base scope excludes the cost. Whether home is on septic vs city sewer NOT stated.

### Pricing structure

- CSV grand total **$100,778.92** (labor $45,167.59 / material $52,171.33 / equipment $3,440); scope.md L179 quotes "Total Investment $173,850" — **~$73k discrepancy** not yet reconciled (_pre/breakdown.md §"Project totals"). Not task-graph blocking, but worth a PM eye.
- CSV header says "Incl. Tankless WH Option"; scope lists tankless as $6,500 OPTIONAL allowance — inclusion status UNCLEAR (_pre/breakdown.md §"Optional packages").
- Hall bath section CSV line is **-$1,714.20 with 72 lh** (template offset / credit) (_pre/breakdown.md §"Notes / weird lines").

### Defaults the agent will apply (per rules_index)

- Stick-frame the roof (footprint 590 sqft < 800, depth 10' < 24', scope ambiguous) — NO `procurement.trusses` task (rules_index 4Q + stick-frame belief).
- Monolithic foundation pour (footings + slab same day, ONE footing inspection) (rules_index 4B).
- Bundled rough MEP + framing inspection; 2-wd punch-list buffer to insulation air-seal (rules_index 4C/4D).
- Two-phase paint, mandatory; paint phase 2 gates on every finish trade (rules_index 4E/4F).
- HVAC stagger after electrical finish in interior-finishes cluster (rules_index 4N).
- Tank-set sequence EXCEPTION fires for base scope (existing WH vent extension only, no new WH) → no `procurement.tank` / `plumbing.tank_set` unless tankless opt-in confirmed (rules_index 4H).
- Two-bucket the hall bath: customer_early_items (acrylic shower swap) vs hall_bath_mod (window infill + drywall patch + repaint) — pending PM confirmation that swap is wanted Day 1 (rules_index 4V).

## What we're uncertain about

### q.vague_address_mismatch

**Question:** The construction plans (5 sheets, Greyscale Design, Jan 22 2026) are headed "3725 SIMONS / 647 AA DEAKINS RD, JONESBOROUGH, TN 37659", but this job is filed against customer "308 Evergreen Street". Is this the correct plan set for this site, or did a different plan set get uploaded by mistake?
**Category:** scope
**Hint:** Address on plans must match the build site. If wrong plans, everything downstream is invalid.
**Choices:**
- Correct plan set — address on header is a designer typo / legacy address; site is 308 Evergreen.
- Correct plan set — site is actually 3725 Simons / 647 AA Deakins; manifest customer label is the project nickname.
- Wrong plan set uploaded — please re-upload the correct drawings before proceeding.
**Why:** If plans don't match the site, the entire scope, dimensions, and structural assumptions are invalid — the task graph and all procurement chains have to wait until this is resolved.

### q.customer_early_items

**Question:** Did the customer ask TCR to handle the **hall bath acrylic shower swap** (or any other work) BEFORE the main job starts — so they have a working shower / functional bath during construction?
**Category:** sequencing
**Hint:** Acrylic shower swap is in the hall bath retrofit scope; if it's also a customer early-item it lives in a separate Day-1 bucket.
**Choices:**
- Yes — acrylic shower swap (and/or other items) are early items, run Day 1 before main demo.
- No — hall bath retrofit (shower swap + window infill + repaint) all runs in parallel with main scope.
- Yes — but a DIFFERENT item, not the shower swap (please name).
**Why:** Customer-requested early items get their own Component in `site_prep / customer_early_items` and run Day 1 before main demo (Rule 4V). Mis-bucketing means the customer doesn't get a working shower when they expect it.

### q.roof_framing

**Question:** Scope says "truss OR rafter framed, determined during design phase" for the new 3/12 gable. Is the roof being stick-framed on site (next-day lumber), or are engineered trusses being ordered (4-6 week supplier lead)?
**Category:** procurement
**Hint:** Footprint 590 sqft and 10' depth → stick-frame is the small-addition default; confirm so we can skip a long-lead procurement task.
**Choices:**
- Stick-frame on site — no truss procurement needed.
- Engineered trusses — long-lead procurement chain required.
- Unsure — design phase still pending.
**Why:** Trusses are 28-42 calendar-day lead time; stick lumber arrives with framing crew. The wrong call here is the single largest procurement risk on the schedule.

### q.vague_tankless_wh_inclusion

**Question:** The CSV header says "Incl. Tankless WH Option", but scope lists the tankless as a $6,500 OPTIONAL allowance separate from base. Is the tankless water heater IN the priced scope being delivered, or is the existing gas WH staying (only its vent extended through new roof)?
**Category:** scope
**Hint:** This changes the plumbing sequence: tank-set BEFORE plumbing rough if a new tank is installed.
**Choices:**
- Tankless WH IS included — install new tankless + venting, swap out existing.
- Tankless NOT included (base scope only) — existing gas WH stays, only the vent is extended through new roof.
- Customer hasn't decided yet — flag as open scope.
**Why:** Rule 4H requires `procurement.tank` + `plumbing.tank_set` BEFORE `plumbing.rough_in` whenever scope installs/replaces a water heater. Whether it fires changes the plumbing predecessor chain.

### q.septic_tdec

**Question:** Is the home on **septic** or **city sewer**? If septic, does the customer/TCR need TDEC permits handled, or is that purely a homeowner / change-order issue?
**Category:** permits
**Hint:** Scope L25-30 defers TDEC inspection + grinder-pump feasibility to a change order; need to know baseline status.
**Choices:**
- City sewer — no TDEC scope.
- Septic — TCR handles TDEC permits (42 cal-day lead, gates excavation).
- Septic — homeowner / their consultant handles TDEC; TCR awaits paperwork.
- Unsure — needs site verification.
**Why:** TDEC septic permits are a 42-day calendar lead and can gate excavation; if TCR owns the permit, it becomes a pre-construction critical-path item.

### q.electrical_service

**Question:** Has the existing main electrical service been verified to support the new 100A subpanel, or does TCR need to plan a service upgrade as part of pre-construction?
**Category:** scope
**Hint:** Scope L86 says "assumes existing main electrical service can support new 100A subpanel" — explicitly UNVERIFIED.
**Choices:**
- Verified adequate — no upgrade work.
- Upgrade needed — utility coordination + service-upgrade tasks required.
- Unsure — TCR will run an amperage check during pre-construction.
**Why:** Service upgrades add utility-coordination weeks. Pre-construction amperage-check task fires whether or not an upgrade is needed; whether the upgrade itself fires materially shifts the schedule.

### q.window_order_type

**Question:** Are the new windows (3'×1' transom + 3'×3' DH) **stock** or **custom order**?
**Category:** procurement
**Hint:** Standard sizes suggest stock, but custom finishes / glazing change the lead.
**Choices:**
- Stock — 14-21 cal-day supplier lead.
- Custom — 28-42 cal-day supplier lead.
- Unsure — will confirm with supplier at order time.
**Why:** Windows install gates on `framing.roof` AND `procurement.windows` (Rule 4J). Custom adds ~3 weeks of procurement and is often the critical-path pre-construction item.

### q.concealed_roof_tie_in_ack

**Question:** Plans show the roof tie-in zone has **multiple valleys + ridges + an existing chimney to navigate** — scope L64 calls it "standard integration" but the drawing geometry is non-trivial. Acknowledge that existing rafter conditions are concealed until demo opens them up, and accept a 2-3 day discovery buffer in the framing phase?
**Category:** risk
**Hint:** This is the single biggest schedule risk on the job — change-order territory.
**Choices:**
- Accepted — bake in the 2-3 day discovery buffer.
- Want to discuss before locking — PM will review with Will.
**Why:** Without a buffer, a tie-in surprise pushes every downstream trade by 2-5 days and forces a hot change order. Cheaper to reserve the time than to chase the slip.

## Open commitments

- No verbal commitments / customer-imposed dates captured yet — none surfaced in scope or breakdown. PM to flag in Round 2 if any exist (deposit pacing, weekly-invoice cadence per scope.md L199, sub-crew pre-bookings).
- Cost reconciliation: scope.md L179 "Total Investment $173,850" vs CSV grand total $100,778.92 — ~$73k gap is not task-graph blocking but flagged for PM awareness; the optional Closet System ($7k) + Tankless WH ($6.5k) + TDEC/septic CO budget could explain part of it.
