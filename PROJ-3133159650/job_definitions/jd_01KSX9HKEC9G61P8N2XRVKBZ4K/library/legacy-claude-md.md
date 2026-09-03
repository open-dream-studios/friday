# Addition Jobs — TCR Knowledge

This is the job-type knowledge file for **room and structure additions** at
Tri Cities Remodeling. It applies whenever a project adds new square footage
to an existing home: bedroom addition, bathroom addition, master suite,
second-story addition, garage conversion to living space. Pure interior
remodels of existing space do NOT use this file.

Everything here is Will-sourced and Boss-vetted. When this file and a
project's own scope documents disagree, the project scope wins — this file
is the default, the scope is the job.


## How a TCR addition flows

Every addition runs the same four blocks, in the same order:

1. **Retro** — work on the EXISTING home completes fully before the addition
   begins. Its own mini-job: relocations, demo, MEPs, drywall, finishes.
   Retro MEPs do NOT get their own inspection — they're covered when the
   regular rough inspections run. Empty when the job has no pre-addition
   work.
2. **Exterior** — demo → site/foundation → framing & shell → exterior
   finishes. This stretch is tight and serial; the whole project waits on
   each step.
3. **Interior** — rough MEPs → rough inspections → insulation & drywall →
   interior finishes. Interior work begins once ROOFING is complete —
   siding, fascia/soffit/gutters, and vent extensions keep running in
   parallel outside, and job completion waits for all of them.
4. **Closeout** — walkthrough, final inspection, and Will's personal close
   with the customer. Concrete flatwork and landscaping run parallel to
   closeout, starting right after final paint.

Will's pacing rule: everything before interior finishes is rushed — from
interior finishes on, breathing room is OK and fewer mistakes happen. Don't
panic-compress the back half of the job.


## Permits and TDEC septic

The permit rule: **every permit is applied for 2 weeks before job start —
except TDEC, which is 6 weeks.** Each permit is two schedule checkpoints,
no bar: application filed, then permit verified; verification gates the
first work that legally needs it.

- **Building permit:** every addition. Will gets permits same-day roughly
  90% of the time — the 2-week application anchor is safety, not
  expectation. Demo never starts without the permit in hand.
- **TDEC septic permit:** only in play when the scope modifies the existing
  septic system or installs a new one — adding bedrooms or bathrooms alone
  does NOT trigger it. The process: contact TDEC, pay the $500 fee, soil
  scientist site visit, soil report, permit. Roughly six weeks end-to-end
  and unpredictable in both directions. It is often the longest lead in the
  whole job. Never break ground without it.
- **Electrical service / meter permit:** only when the main service is
  upgraded or the meter relocates (utility involvement). A subpanel alone
  rides the building permit.
- **Plumbing permit:** when plumbing is in scope; gates rough plumbing.
- **Mechanical permit:** when HVAC work is in scope; gates rough HVAC.


## Change-order realities

- **Rock.** Tri-Cities digs hit rock often. Hitting rock is a change order,
  not schedule padding.
- **Concealed roof tie-in.** When the new roof ties into the existing roof,
  conditions above the existing ceiling are unknown until framing opens them
  up. Document the existing rafter conditions on day one of roof framing so
  any change order processes fast.
- **Drywall cracking, year one.** Every addition gets hairline cracks at the
  new-to-existing tie-ins (above doors, windows, headers) as it settles.
  Will covers it with a one-year warranty return. It is never scheduled in
  the job.


## Customer touchpoints

- **Customer-requested early items** — work the customer asked TCR to do
  before the main job so they can live comfortably during construction (a
  shower swap in another bath, a leaky fixture). These belong in the Retro
  phase, before addition demo. Ask for them in the PM interview; don't guess.
- **The PM closes every addition personally** — the job-complete milestone
  is the PM's walkthrough with the customer, one working day after the last
  item finishes (final inspection, landscaping, exterior finishes, and deck
  all done).









<!-- ═══════════════════════════════════════════════════════════════════ -->
<!-- ═══════════════════════════════════════════════════════════════════ -->
<!--                                                                     -->
<!--        TASK GRAPH GENERATION — START                                -->
<!--        Read this section when answering the Addition checklist.     -->
<!--                                                                     -->
<!-- ═══════════════════════════════════════════════════════════════════ -->
<!-- ═══════════════════════════════════════════════════════════════════ -->









# Task Graph Generation (Task Structure v2 system)

## How generation works now

The Addition **task structure** (versioned JSON in the dev-cms DB, mirrored
at `task_structure.json` in this folder) defines every phase, component,
task, dependency, and procurement item that CAN exist on an addition. All
topology is fixed. You never invent tasks, never author dependencies, never
reorder phases.

Your job is exactly three decisions per checklist item:

1. **Include, exclude, or needs_info** — does this job's scope trip the
   item's trigger? (Applies to tasks, procurement items, AND permits.)
2. **Crew** — for each included task with a crew range, set the crew size
   from the job's scale and site constraints, inside the allowed range.
3. **Duration** — pick a working-day duration inside the item's allowed
   range, sized AT the crew you just set, using the hint. For procurement
   items this answer is instead the expected **delivery time in calendar
   days** (see below).

Deterministic code assembles the graph from your answers. Excluded tasks
disappear and their dependencies collapse automatically — downstream work
absorbs the excluded task's own predecessor. Exclusions are free; never
include something "just in case."

## Answering rules

1. **The trigger line is the contract.** Each item's trigger states the
   include condition. Read it literally; the scope and PM interview decide.
2. **Scope and PM interview are authoritative.** Drawings resolve location
   ambiguity. When a PM directive is present in an update request, it
   overrides everything else.
3. **Ambiguity → needs_info, not a guess.** Answer needs_info with a crisp,
   answerable question. Known variance traps that must NEVER be silently
   guessed: septic vs city sewer, trusses vs stick-frame, stairs / second-
   floor access method, carpet vs hard flooring, shower glass vs curtain,
   mini-split vs ducted HVAC.
4. **Answered questions are pinned.** If a prior question on this job has an
   answer in the intelligence layer, use it — do not re-ask, do not
   re-litigate.
5. **extra_tasks is an escape hatch, not a habit.** Only for real scope work
   that genuinely has no structure item. Anything you put there is flagged
   and quarantined. When a catch is legitimate, it gets promoted into the
   structure itself (that's how the appliance-vent-extension task was born —
   caught once on 308 Evergreen, now a permanent structure item).

## Retrofit detection — three signals

An addition is rarely ONLY new construction. Check every scope section:

- **Signal A — area mismatch:** the section names a room or feature not in
  the addition objective (hall bath, kitchen, hallway).
- **Signal B — the word "existing":** "remove existing window," "relocate
  existing heat pump," "modify existing wall."
- **Signal C — spatial ambiguity:** a new feature (wall, chase, circuit,
  closet, fixture) whose location is not explicitly inside the addition
  footprint. Use drawings to resolve; unresolved → presume retrofit and ask.

Any signal → the work belongs in the Retro phase items (relocations, retro
demo, retro MEPs, retro drywall, retro finishes), NOT bundled into the
addition's own tasks.

## Crew & duration judgment

**Order of operations: crew first, then duration.** Crew is what the job
physically needs — set it from footprint, stories, access, and site
constraints. Duration is how long THAT crew takes.

**Crew is NEVER a speed dial.** Do not halve a duration by doubling the
crew, and do not stretch a duration to justify a smaller crew. If you
don't set a crew, the structure default is assumed — then your duration
must be sized at the DEFAULT crew. A schedule that needs to compress gets
compressed by the PM's real staffing decisions, not by your arithmetic.

- Stay inside each item's crew range and duration range. The hints are
  the sizing logic — use them. Duration hints state their assumed crew
  ("~250 sqft/day at a 2-man crew"); honor the coupling.
- Scale drivers worth weighting: two-story vs single, roof tie-in
  complexity, footprint sqft, occupied-home protection, number of trades
  the retro touches, rock risk on excavation.
- The interior 2-trades-max cap is real: never stack crew numbers across
  simultaneous interior trades to more than two crews on site.
- All durations are working days (Mon–Fri). Calendar-day realities (the
  foundation cure gap, procurement lead windows) are already encoded in the
  structure — never add cure or wait time into a task's duration.
- TCR baselines to honor when sizing: mini-split line-set rough is a
  half-day; a subpanel adds about half a day to rough electrical; a small
  addition roof shingles in 1–2 days; a full custom shower runs 5–8 days;
  LVP flooring moves ~250 sqft/day.

## Item-specific judgment calls

Knowledge that doesn't fit in one trigger line:

- **TDEC septic:** include only when the septic system itself is modified
  or installed. Bedroom/bathroom count alone never triggers it. On septic
  vs city sewer ambiguity → needs_info, always.
- **Trusses:** stick-frame is the TCR default for small additions. Include
  truss procurement only when scope explicitly says trusses, roof span
  exceeds ~24 feet, footprint exceeds ~800 sqft, or the PM confirms.
  "Truss or rafter, determined in design" is ambiguity — default stick.
- **LVL beams:** nominally a 1–2 week item but availability swings with the
  lumber market. The structure early-orders them; your only call is whether
  engineered members are on the job at all.
- **Water heater:** a NEW tank or tankless triggers the water-heater
  procurement and adds one day to the start of rough plumbing (the tank
  gets set first; the rough-in stubs into it). Merely extending an existing
  water heater's vent through the new roof does NOT trigger a tank — that's
  the vent-extension task in exterior finishes (HVAC and/or plumbing trade;
  covers appliance flues AND plumbing drain vents).
- **HVAC type:** "mini-split" in scope → line-set rough, short duration.
  "Ducted," "duct work," "air handler" → duct extension, longer. Unclear →
  needs_info and default mini-split.
- **Windows custom vs stock:** the structure's lead window assumes stock
  (21 days). If the scope suggests custom (28–42 days), still include —
  and raise needs_info so the PM confirms and adjusts the order date.
- **Deck:** a parallel track. It starts alongside framing and nothing in
  the build chain waits on it — only job completion gates on the deck
  being done (same as exterior finishes and landscaping).
- **Stairs:** any second-story addition needs an access answer. If the
  scope doesn't state new stair vs tie-in to the existing stairwell →
  needs_info; do not silently include or exclude.
- **Insulation timing:** the structure plans insulation about a week after
  rough inspections pass. Game-day, the PM often pulls it earlier the
  moment framing clears — that's a manual edit, not your plan.

## Permits & procurement in the schedule

- **Permits are two checkpoints, no bar:** application filed → permit
  verified. Application lands 2 weeks before the verification (6 for
  TDEC); verification gates the first task that legally needs the permit.
  You only answer include/exclude/needs_info — dates are computed.
- **Procurement is two checkpoints, no bar:** order placed → delivery
  verified. The rule: material is delivered **3 working days before** the
  task it attaches to starts. The order date is computed backward from
  that: attach date − 3 days − delivery time.
- **You size the delivery time** (calendar days, within the item's range)
  from the order's magnitude: custom vs stock, size of the package,
  supplier reality per the hint. Same discipline as crew — size it from
  reality, never bend it to make a schedule fit.









<!-- ═══════════════════════════════════════════════════════════════════ -->
<!-- ═══════════════════════════════════════════════════════════════════ -->
<!--                                                                     -->
<!--        TASK GRAPH GENERATION — END                                  -->
<!--                                                                     -->
<!-- ═══════════════════════════════════════════════════════════════════ -->
<!-- ═══════════════════════════════════════════════════════════════════ -->









## Provenance

2026-08-05 — rewritten for the task-structure v2 generation system. The old
v1 emission-protocol rules (emit_task_graph contract, dot-namespaced IDs,
3-task procurement authoring, the 31-warning validator list) are retired:
topology now lives in the versioned task structure, not in prose. Domain
knowledge from the old file that still matters was carried into the
sections above. The human red-pen companion to the structure JSON lives at
`dev-cms/PM_audit/Addition_Task_Structure_v4.md`.

2026-08-05 (later) — structure v4: every work/inspection task now carries a
crew-size range alongside its duration range. The AI answers crew first
(from job scale), then sizes duration at that crew — crew is never a speed
dial.

2026-08-06 (later) — structure v6, converted 1:1 from the Will-vetted doc:
one unified schema for every item (Trade / Kind / Include When / Crew /
Duration / Depends / Notes), kinds work|inspection|milestone|permit|
procurement. Permits and procurement are phases 12/13 with normal nodes —
permits anchor `job_start (SF+0)` and the gated task carries the
dependency; procurement anchors `<consumer> (SF-3)`. The doc's dependency
convention (group refs via SS/FS, SF anchors) IS the JSON convention. In
the schedule, permit/procurement rows render as a window bar with a
diamond at each end (application/order → verified).

2026-08-06 — aligned with Will's full red-pen vetting of the structure doc:
interior now gates on roofing completion (not full exterior finish), permit
set corrected (plumbing + mechanical in, land disturbance out), retro
inspection removed (covered at regular roughs), water heater encoded as +1
day on rough plumbing, deck/exterior finishes/landscaping all gate job
completion, PM (not Will by name) closes every job.

2026-08-05 (later still) — structure v5: permits became their own section
(two checkpoints: application 2 weeks ahead — 6 for TDEC — then
verification gating the first permitted work). Procurement reworked to two
checkpoints (order placed → delivery verified, delivery 3 working days
before the attached task) with AI-sized delivery-time ranges, and grew
interior doors/trim, plumbing fixtures, and light fixtures items.

---

## Friday additions — 2026-08-26 (Boss review)

From the Fairground Lane sunroom/deck job's drawings + proposal. Delete anything that doesn't hold.

- **Sloped-lot / walkout additions carry a below-grade package** between foundation and framing: waterproofing + drainage board on the below-grade wall, foundation drain with filter fabric sloped to daylight, gravel backfill, continuous flashing. Flat-lot schedules routinely miss this stretch.
- **Non-standard window sizes are a silent lead-time trap.** Anything that isn't a stock size class (a 3'-2" wide "3250DH" showed up on Fairground) needs size verification before ordering — the schedule may claim stock lead time for a custom-lead-time unit.
- **"LVL omitted, sized per IRC" language is a watch item.** Value-engineered engineered lumber tends to come back as a change order after final engineering; carry it as a named risk, not a surprise.
- **Storage/crawl levels under ~5' clear height are not habitable space** — they don't trigger habitable-space code paths, and their access (e.g. exterior barn doors) rides exterior finishes, not interior finishes.
