# Task graph JSON schema

`<job>/generations/task_graph.json` — the structured machine-readable
twin of `task_graph.md`. Both files are emitted by the agent in the
same run of `task_graph_v1`. The JSON is the canonical contract for
the deterministic CPM scheduler (which produces `schedule.json`) and
the Project Planner UI's Gantt + TaskGraph views.

The JSON shape conforms exactly to the existing TypeScript types in
`@open-dream/packages/modules/project_planner/shared/types/task_graph`.
Keep them in lockstep — when you edit this schema, update the TS
types in the same commit (or vice versa).

## Top-level shape

```json
{
  "project_id": "string",
  "generated_from": {
    "breakdown_hash": "string",
    "rules_version": "string"
  },
  "tasks": [Task],
  "phases": [Phase],
  "components": [Component],
  "warnings": ["string"],
  "assumptions": ["string"]
}
```

- `project_id` — set to the job's `manifest.json.job_id`.
- `generated_from.breakdown_hash` — sha256 of `generations/breakdown.json` at
  write-time if it exists, OR sha256 of `inputs/scope.md`, OR empty
  string when neither is derivable. The PP UI uses this to detect
  drift between task_graph and its source breakdown.
- `generated_from.rules_version` — the brain trunk's commit sha at
  write-time. Stand-in for the prior PP `rules.md` versioning.
- `phases`, `components`, `warnings`, `assumptions` — optional but
  strongly preferred. Phase / Component grouping powers the PP Gantt's
  3-layer hierarchy.

## Task

```json
{
  "id": "framing.walls.exterior",
  "section_id": "framing",
  "name": "Frame exterior walls",
  "trade": "framing",
  "kind": "work",
  "duration_days": 3,
  "crew_size": 2,
  "depends_on": [
    { "predecessor_id": "framing.floor_system", "type": "FS", "lag_days": 0 }
  ],
  "can_overlap_with": ["framing.interior_walls"],
  "lead_time_days": 0,
  "derived_from": {
    "section_id": "framing",
    "rule_ids": ["plumbing_rough_min_duration"],
    "reasoning": "follows from `lvl_load_bearing_for_new_framing` belief"
  },
  "phase_id": "framing",
  "component_id": "framing_walls_roof",
  "pre_construction_offset_working_days": null,
  "lead_up_working_days": 0
}
```

### Field requirements

- `id` — stable snake_case dotted slug, unique per task graph.
- `section_id` — FK to a `breakdown.json.sections[].id` when breakdown
  exists; otherwise a synthetic slug derived from the task's logical
  bucket. NEVER empty.
- `name` — human-readable; what appears on the Gantt label.
- `trade` — one of the `Trade` enum values (see "Trade enum" below).
- `kind` — one of `work | inspection | lead_time | milestone | procurement`.
- `duration_days` — working days. Fractional allowed (0.5 = half day).
- `crew_size` — people needed concurrently.
- `depends_on` — array of `Dependency` objects (see below). Can be `[]`.
- `derived_from` — provenance. Even when the breakdown is empty, set
  `section_id` to the task's bucket slug, list any `rule_ids` /
  `belief_ids` you applied (trunk paths or just slugs), and add a
  one-line `reasoning` so future agents can see why this task exists.

### Optional fields

- `can_overlap_with` — string array of task ids the scheduler may
  overlap if calendar allows. Soft hint.
- `lead_time_days` — calendar days. ONLY for `kind: procurement` or
  `kind: lead_time`.
- `phase_id` / `component_id` — assigns the task into a Phase/Component
  for the 3-layer hierarchy. Reference the ids from the top-level
  `phases` / `components` arrays.
- `pre_construction_offset_working_days` — for free-floating
  pre-construction tasks (e.g. "permit walk-in"). Working days BEFORE
  on-site start where the task should pin. Common values:
  - `15` ≈ 3 weeks (typical permit / selections checkpoint)
  - `10` ≈ 2 weeks (equipment-confirmation)
  - omit / `null` for tasks with downstream consumers (scheduler
    chains them automatically).
- `lead_up_working_days` — informational PM prep window. Doesn't
  shift the schedule; PP UI draws a low-opacity bar to the left of the
  main bar for the lead-up days. Common: `5` for selections, `2` for
  permits.

## Dependency

```json
{
  "predecessor_id": "string",
  "type": "FS" | "SS" | "FF" | "SF",
  "lag_days": 0
}
```

CPM semantics:

- `FS` — successor.start ≥ predecessor.finish + lag (default; most common)
- `SS` — successor.start ≥ predecessor.start + lag
- `FF` — successor.finish ≥ predecessor.finish + lag
- `SF` — successor.finish ≥ predecessor.start + lag

`lag_days` is in WORKING days. Negative lag = overlap allowed.

## Phase

```json
{
  "id": "framing",
  "name": "Framing",
  "order_index": 5,
  "is_pre_construction": false
}
```

- `order_index` ordering is strict — Phase N can't overlap with Phase
  M when M ≠ N.
- `is_pre_construction: true` means tasks in this phase get
  BACKWARD-scheduled to finish by on-site start.

### PHASE GRANULARITY — MANDATORY

**Every distinct construction stage is its own PHASE.** Do NOT collapse
multiple stages into one `on_site_execution` mega-phase — that is a
quality failure. A PM reading the Gantt should see color-banded phases
that match the natural construction cadence, not one giant bar with
tasks buried underneath as components.

Typical phase list for a TCR addition — target **9–11 phases**:

| order_index | id | name | is_pre_construction |
|---|---|---|---|
| 0 | `pre_construction` | Pre-construction (permits, checkpoints, TDEC, amperage check) | true |
| 1 | `procurement` | Procurement + long-lead orders | true |
| 2 | `site_prep` | Site prep + customer early items | false |
| 3 | `demo` | Demolition | false |
| 4 | `foundation_structural` | Foundation + structural (footings, slab, LVL install) | false |
| 5 | `framing` | Framing (walls, roof framing, tie-in discovery) | false |
| 6 | `shell` | Shell (roofing, windows, doors, siding, exterior finish) | false |
| 7 | `mep_rough` | MEP rough (plumbing → electrical → HVAC + bundled rough inspection + punch buffer) | false |
| 8 | `drywall_finish` | Insulation + drywall + paint phase 1 (primer + ceilings) | false |
| 9 | `interior_finish` | Interior finish (tile, flooring, electrical trim, HVAC install, plumbing finish, trim, paint phase 2) | false |
| 10 | `closeout` | Closeout (punch list + final clean + final inspection + substantial completion) | false |

For a **bathroom remodel**: `pre_construction, procurement, demo,
plumbing_relocation, framing_prep, shell (waterproof + tub / shower
install), mep_rough, drywall_finish, tile_flooring, interior_finish,
closeout` — same principle, adapted cadence.

For a **kitchen remodel**: `pre_construction, procurement, demo,
framing_prep, mep_rough, drywall_finish, cabinet_install,
countertop_template, countertop_install, appliance_install,
closeout`.

**Anti-pattern (DO NOT DO):** one giant `on_site_execution` phase with
12 components crammed under it. That reduces the Gantt to a single
color band and blinds the PEP / daily-schedule narrative to phase
transitions. Every downstream artifact reads phases when it groups
tasks — flat phase = flat narrative.

## Component

```json
{
  "id": "customer_early_items",
  "phase_id": "site_prep",
  "name": "Customer early items"
}
```

Components live UNDER phases as a finer grouping — one or two per
phase where the tasks naturally cluster (e.g. under `mep_rough`,
components might be `plumbing_rough`, `electrical_rough`,
`hvac_rough`, `rough_inspection`). If a phase has more than 4
components you're probably packing too much into one phase — split
it.

Components within the same phase MAY overlap in wall time. They're a
cognitive grouping; the scheduler still enforces hard dependencies on
top.

## Trade enum

Pick the closest match. Don't invent values — the PP UI's color
palette is keyed off this list.

```
general | demo | abatement | excavation | concrete | masonry |
framing | roofing | siding | windows_doors | glazing | electrical |
plumbing | hvac | insulation | drywall | paint | flooring | tile |
trim_carpentry | cabinets | countertops | appliances | landscaping |
cleanup | inspector | pm
```

## TaskKind enum

- `work` — crew doing labor (most tasks)
- `inspection` — gates downstream; usually short duration; trade = `inspector`
- `lead_time` — calendar wait on materials/permits; no crew
- `milestone` — zero-duration marker ("dried-in", "rough-in complete")
- `procurement` — order placed → arrived

## Hard rules

1. **Both files are emitted in one commit.** `task_graph.md` (the
   narrative for human review) and `task_graph.json` (the structured
   contract for the scheduler + UI) must agree on every task's id /
   name / trade / depends_on / duration. The narrative cites the
   structured data; never invent in the prose.

2. **Every id is unique within the file.** Duplicate ids break the
   scheduler. Use dotted snake_case namespacing
   (`framing.walls.exterior`) to keep ids stable across iterations.

3. **Dependency `predecessor_id` MUST reference an existing task in
   the same file.** Forward references are fine; the topo sort
   handles them.

4. **Acyclic.** No dependency cycles. The CPM scheduler rejects cyclic
   graphs.

5. **No fabricated provenance.** `derived_from.rule_ids` lists rule
   slugs you actually applied (look them up in `_company/rules/` or
   `<job>/rules/`). Empty array is fine when no rule matched.
