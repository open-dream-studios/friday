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
   begins. Its own mini-job: relocations, demo, MEPs, inspection, drywall,
   finishes. Empty when the job has no pre-addition work.
2. **Exterior** — demo → site/foundation → framing & shell → exterior
   finishes. This stretch is tight and serial; the whole project waits on
   each step.
3. **Interior** — rough MEPs → rough inspections → insulation & drywall →
   interior finishes. Interior work begins only when the exterior is FULLY
   finished (siding, roofing, fascia, soffit all done) — current TCR
   practice.
4. **Closeout** — walkthrough, final inspection, and Will's personal close
   with the customer. Concrete flatwork and landscaping run parallel to
   closeout, starting right after final paint.

Will's pacing rule: everything before interior finishes is rushed — from
interior finishes on, breathing room is OK and fewer mistakes happen. Don't
panic-compress the back half of the job.


## Permits and TDEC septic

- **Building permit:** Will gets permits same-day roughly 90% of the time.
  The 14-day window in the structure is safety, not expectation. Demo never
  starts without the permit in hand.
- **TDEC septic permit:** only in play when the scope modifies the existing
  septic system or installs a new one — adding bedrooms or bathrooms alone
  does NOT trigger it. The process: contact TDEC, pay the $500 fee, soil
  scientist site visit, soil report, permit. Roughly six weeks end-to-end
  and unpredictable in both directions. It is often the longest lead in the
  whole job. Never break ground without it.


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
- **Will closes every addition personally** — the job-complete milestone is
  Will's walkthrough with the customer, one working day after the last item
  (final inspection AND landscaping) finishes.









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

Your job is exactly two decisions per checklist item:

1. **Include, exclude, or needs_info** — does this job's scope trip the
   item's trigger?
2. **Duration** — for each included task, pick a working-day duration inside
   the item's allowed range, using its hint.

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

## Duration judgment

- Stay inside each item's range. The hint is the sizing logic — use it.
- Scale drivers worth weighting: two-story vs single, roof tie-in
  complexity, footprint sqft, occupied-home protection, number of trades
  the retro touches, rock risk on excavation.
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
  procurement, and the tank gets SET before plumbing rough begins — the
  rough-in stubs into the already-set tank. Merely extending an existing
  water heater's vent through the new roof does NOT trigger a tank — that's
  the vent-extension task in exterior finishes.
- **HVAC type:** "mini-split" in scope → line-set rough, short duration.
  "Ducted," "duct work," "air handler" → duct extension, longer. Unclear →
  needs_info and default mini-split.
- **Windows custom vs stock:** the structure's lead window assumes stock
  (21 days). If the scope suggests custom (28–42 days), still include —
  and raise needs_info so the PM confirms and adjusts the order date.
- **Deck:** a pure leaf. It starts alongside framing and nothing downstream
  ever waits on it. Never let deck work gate anything.
- **Stairs:** any second-story addition needs an access answer. If the
  scope doesn't state new stair vs tie-in to the existing stairwell →
  needs_info; do not silently include or exclude.
- **Insulation timing:** the structure plans insulation about a week after
  rough inspections pass. Game-day, the PM often pulls it earlier the
  moment framing clears — that's a manual edit, not your plan.









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
`dev-cms/PM_audit/Addition_Task_Structure_v3.md`.
