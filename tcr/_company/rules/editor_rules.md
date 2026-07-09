# Editor rules — Tri Cities Remodeling scheduling knowledge

This document is the TCR playbook. It captures how TCR runs a job
generically: the standard phase spine, default crew sizes and
productivity, typical lead times, the TN inspection sequence, the trade
dependency cheat-sheet, and the overlap and ordering rules Will applies
across every job regardless of type. Job-specific knowledge (what an
addition needs that a bathroom does not, etc.) lives in the matching
job-type doc, not here.

Edit freely as real-world numbers sharpen. The next TaskGraph generation
picks up your changes automatically.


## The TCR phase spine

Every TCR job moves through the same general spine. Skip a phase that
doesn't apply rather than inventing a new phase. Fewer phases is always
better than more — phases are constraints, not categories.

| order | phase id                  | name                                                | pre-construction |
|------:|---------------------------|-----------------------------------------------------|------------------|
|     0 | `pre_construction`        | Permits, ordering, planning                         | yes              |
|     1 | `site_prep`               | Dumpster, equipment delivery, site protection       | no               |
|     2 | `demo_and_protection`     | Demolition, abatement if needed, haul-out           | no               |
|     3 | `structural_and_shell`    | Excavation, foundation, framing, roof dry-in        | no               |
|     4 | `rough_trades`            | Rough plumbing, electrical, HVAC                    | no               |
|     5 | `rough_inspections`       | Bundled rough MEP + framing inspections             | no               |
|     6 | `insulation_and_drywall`  | Insulation, drywall, prime                          | no               |
|     7 | `interior_finishes`       | Tile, flooring, trim, cabinets, paint coat 2        | no               |
|     8 | `finish_trades`           | Plumbing finish, electrical finish, HVAC finish     | no               |
|     9 | `closeout`                | Punch list, final clean, final inspection           | no               |


## Permits — fast, schedule 3 weeks ahead

Permits are NOT a long-lead item. Will walks in with documentation and
walks out with a permit ~90% of the time. The TaskGraph should model
permits as:

- `general.permitting`:
  - `kind: work`
  - `duration_days: 1`
  - `crew_size: 1`
  - `trade: general`
  - `pre_construction_offset_working_days: 15` (3 weeks before on-site start)
  - `depends_on: []`

Do NOT use `lead_time` with a 14-day calendar wait. That's the old wrong
default. The 3-week-ahead slot is for safety margin (in case of a fluke),
not actual permit-clearance wait time.

The `pre_construction_offset_working_days` field is what tells the
scheduler exactly when to land the task. Without it the scheduler dumps
the task at the leftmost edge.


## Material ordering — Will's universal rule

**Materials must be on site 1 week before they are installed.** That is
the only universal timing rule. It applies regardless of project type
(addition, remodel, bathroom).

Mechanical equipment (mini-split, tankless water heater, regular tank
water heater) is an exception: order it tied to **dried-in or just-about-
dried-in**, not to project start. It's installed late in the job, but
selections still happen up front.

Long-lead items (cabinets 42-56d, custom tile 14-21d, trusses 28-42d,
custom windows 28-42d) still need early procurement triggers — Will
calls these out as the items that drive critical path.

DO NOT default all procurement to "order at permit submittal" or "order
at project start." Tie procurement to the dependent install task's
start.


## Procurement pattern — order / wait / arrived (THE 3-TASK SHAPE)

DO NOT emit a single `kind: procurement` task with a multi-week
`lead_time_days`. That hides intent and produces a Gantt bar that
spans weeks but represents zero real PM action.

Instead, every procurement decomposes into THREE tasks:

```
order.<item>          — kind: work, duration: 0.5d
                        "PM places the order today"
wait.<item>           — kind: lead_time, lead_time_days: N
                        the supplier's delivery wait window
checkpoint.<item>_arrived — kind: milestone, duration: 0
                        "PM confirms the item is on site"
└─ <item>.install     — depends on checkpoint.<item>_arrived (FS lag 0)
```

Why this is right:
- `order.<item>` is a real day on the PM's calendar. They can check it
  off. The PEP narrative reads "Mon Aug 3 — Place windows order today."
- `wait.<item>` is the supplier delay. Shows as a lead-time bar on the
  Gantt so the PM SEES the procurement window without it being a
  pretend "work task."
- `checkpoint.<item>_arrived` is the PM's confirmation gate. Without
  this, the PM doesn't know if procurement actually happened. Tied
  via FS to the install — install can't start until checkpoint fires.

The scheduler backward-schedules the whole chain from the install
task. A 21-day windows order with install on Aug 24:
- `order.windows` → ~Aug 3
- `wait.windows` → Aug 3 → Aug 23 (lead_time bar)
- `checkpoint.windows_arrived` → Aug 23
- `windows.install` → Aug 24

Use this pattern for: windows, doors, LVL, electrical panel, mini-split
unit, water heater (if applicable), tile (custom), cabinets, custom
countertops, glass shower enclosure, custom trim — anything with a
supplier wait.

DO NOT use this pattern for:
- Items shipped via the framing crew (lumber arrives day-of, no order
  step needed)
- Items the PM picks up locally same-day (paint can be ordered as a
  simple 1-day work task right before paint phase 1)

For very short supplier waits (≤ 7 days, like stock paint or simple
fixtures), you may collapse the pattern to just `order.<item>` placed
1 week before install, no separate wait/checkpoint needed.


## Pre-construction free-floating tasks — `pre_construction_offset_working_days`

Some pre-construction tasks have NO downstream install task to pull
them backward. Examples: permit walk-in (1d work), selections-finalized
checkpoint (milestone), equipment-confirmed checkpoint (milestone),
amperage-check (0.5d work). For these tasks, the agent MUST set the
`pre_construction_offset_working_days` field so the scheduler knows
exactly where to land them.

Typical values:
- 15 (3 weeks): permit walk-in, selections finalized, amperage check
- 10 (2 weeks): equipment-confirmed checkpoints (saw, mini-ex,
  scaffolding)
- 5 (1 week): final selections approvals

Without this field, the scheduler falls back to anchoring the task so
it ENDS at on-site start (day 0). For short free-floating tasks
(permit walk-in, selections checkpoint, equipment checkpoint), that
fallback puts the task on the day before on-site — almost always too
late. Set the offset.

**Long-lead permits and procurement chains are different.** A
`kind: lead_time` or `kind: procurement` task with a real
`lead_time_days` value (e.g. TDEC septic permit at 42 calendar days,
custom cabinets at 49 calendar days) ANCHORS ITSELF: the lead naturally
backs up from on-site start. Do NOT set
`pre_construction_offset_working_days` on these. Do NOT emit a
`checkpoint.<X>_complete` after them. The END of the lead_time IS the
completion. If a real on-site task gates on the lead (e.g. excavation
gates on TDEC septic), wire that consumer explicitly — it's more
precise — but it's optional. The fallback gets the timing right
either way.


## Lead-up windows — `lead_up_working_days` (the prep window)

A schedule shows when a task LANDS. It does not show when the PM has
to start working toward that landing date. For some tasks the gap is
real — the PM can't just walk in on the deadline cold. Examples:

- `checkpoint.selections_finalized` lands 3 weeks before on-site, but
  the customer back-and-forth that makes it land happens over the
  ~5 working days leading in.
- `general.permitting` is a 1-day walk-in, but the package itself
  takes ~2 working days to assemble.
- `order.<item>` is the day the PM presses purchase, but verifying
  the spec / confirming vendor pricing took 2 working days prior.

For these, populate `lead_up_working_days` on the task with the
number of working days of prep that lead in. The field is
**informational only** — the scheduler does NOT use it to shift the
task. It is consumed by:

1. The **PEP generator** — surfaces "Preparing: {task}" entries on
   the lead-up days so the PM sees the prep window in their day-by-day
   agenda, not just on the deadline.
2. The **schedule UI** — when the PM clicks a task, draws a low-opacity
   "prep" bar to the left of the main bar covering the lead-up window.

Default table (the agent should apply unless scope says otherwise):

| Task                                       | lead_up |
|--------------------------------------------|--------:|
| `checkpoint.selections_finalized`          |       5 |
| `general.permitting`                       |       2 |
| `permit.tdec_septic` / other formal permit |       2 |
| `prep.amperage_check`                      |       1 |
| `checkpoint.equipment_confirmed_*`         |       2 |
| `order.<item>` (vendor confirm needed)     |       2 |
| `order.<item>` (stock, in-house)           |       0 |
| `checkpoint.<item>_arrived`                |       0 |
| `wait.<item>` (any `kind: lead_time`)      |       0 |
| Major phase-start work (demo, framing, drywall) |  2 |
| Continuation work bars within a phase      |       0 |
| Inspections                                |       1 |
| `milestone.*`                              |       0 |

Tasks preceded by a `wait.*` chain (e.g. `checkpoint.windows_arrived`
after `wait.windows`) MUST keep `lead_up_working_days: 0` — the wait
already encodes the lead window.

Weekends and holidays are skipped when consumers walk back from
`scheduled_start` to compute the lead-up start date, so a value of
5 working days always means 5 actual workdays of PM time.


## Equipment on site — the day-before rule

Define equipment as: dumpster, porta-john, concrete saw, skid steer,
mini-ex, scaffolding, scaff lifts, backhoe.

Each piece of equipment gets a 0.5-day equipment task (`trade: general`)
that lands **the day before** the phase that consumes it. Specifically:

- Dumpster arrives the day before demo begins.
- Second dumpster (or swap) lands the day before drywall hangs.
- Concrete saw, skid steer, mini-ex on site the day before demo /
  excavation.
- Scaffolding lands the day before the roof or siding phase starts.

Add a coordination checkpoint **2 weeks before** the equipment phase
called `checkpoint.equipment_confirmed_<phase>` (`duration_days: 0`,
`kind: milestone`, `pre_construction_offset_working_days: 10`) so the
PM has confirmed the equipment is reserved / available. 1 week minimum.

The `pre_construction_offset_working_days: 10` is what tells the
scheduler to land it 2 weeks before on-site start. Don't skip this
field — without it the scheduler dumps it at the leftmost edge.

Equipment that costs money (rented or owned) shouldn't sit on site
unused.


## Default crew sizes and productivity

Starting numbers the agent uses to translate `labor_hours` into duration.
Override per section if the breakdown clearly implies a different staffing
level. Keep these honest as actuals come in.

| Trade           | Default crew | Productivity                                                                 |
|-----------------|--------------|------------------------------------------------------------------------------|
| general         | 2            | Permitting / site PM tasks                                                   |
| demo            | 3            | ~150 sqft/day for selective interior demo                                    |
| abatement       | 2 (cert.)    | Asbestos/lead removal — gates demo; subbed to certified contractor           |
| excavation      | 2 + machine  | ~30 cy/day with mini-ex                                                      |
| concrete        | 4            | Monolithic pour (footings + slab) ~1 day for typical addition                |
| masonry         | 2            | Brick ~150 brick/day; stone slower; chimneys ~1 day each                     |
| framing         | 3            | Walls ~250 sqft/day; floor systems ~300 sqft/day                             |
| roofing         | 3            | Shingle: up to 6,000 sqft in 1 day for residential. Trim/flashing similar.   |
| siding          | 3            | ~250 sqft/day for lap siding                                                 |
| windows_doors   | 2            | ~3 windows/day install incl. flashing                                        |
| glazing         | 2            | Shower glass enclosures ~0.5 day install; templating + fab adds 1–2 weeks    |
| electrical      | 2            | Subpanel = 1 day, 1 person. Rough-in ~1–1.5 days for typical addition.      |
| plumbing        | 2            | Rough-in: **default 4 days** × 2 crew for any job with master bath / 2+ bath fixtures / W/D relocation. 3 days only for a single half-bath. Per Will (transcript line 1942): "four days for two guys, that's fine for this kind of job." |
| hvac            | 2            | Mini-split rough = 0.5 day, 1 person. Mini-split install = 1 day. Ducted: varies. |
| insulation      | 2            | ~400 sqft/day batts. Typical addition = 1 day install.                       |
| drywall         | 3            | Consolidated hang/tape/sand = 9–11 days for a typical addition               |
| paint           | 2            | Two-phase. See "Paint two phases" section.                                   |
| flooring        | 2            | LVP/LVT ~250 sqft/day; tile slower                                           |
| tile            | 2            | Wall tile ~30 sqft/day; floor tile ~50 sqft/day                              |
| trim_carpentry  | 2            | Base/case ~150 lf/day                                                        |
| cabinets        | 2            | Kitchen install ~1.5 days; vanities 0.5 day                                  |
| countertops     | 2            | Templating + install, 2 visits                                               |
| appliances      | 1–2          | Delivery + install; coordinate with cabinets, plumbing finish, electrical    |
| landscaping     | 2            | Site restoration / final grading; sod ~1000 sqft/day                         |
| cleanup         | 2            | Final clean — ~0.5–1 day bathroom; 1–2 days whole-house                      |
| inspector       | 1            | 0.5-day blocks, requires scheduling lead time                                |


## Lead-time items (procurement)

Each becomes a `procurement` task with `lead_time_days` in calendar days
(not working days), `crew_size = 0`, `duration_days = 0`. The task's
purpose is to gate the downstream install task via FS.

For procurement, use the 3-task pattern (order / wait / arrived). The
`lead_time_days` on the WAIT task = the supplier's actual delivery
window in calendar days. The 1-week on-site buffer is captured by
landing the `checkpoint.<item>_arrived` task 1 working day before the
install — not by padding `lead_time_days`.

Permits use a different pattern (see below).

| Item                     | Supplier days (wait.X lead_time_days) | Order trigger                            |
|--------------------------|---------------------------------------|------------------------------------------|
| Permits                  | walk-in (no wait task)                | 3 weeks before on-site start (offset 15) |
| Windows (stock)          | 14–21                                 | Backward from windows.install            |
| Windows (custom)         | 28–42                                 | Backward from windows.install            |
| Exterior doors (custom)  | 21–28                                 | Backward from door install               |
| LVL beams (standard)     | 7 (use 14 for safety)                 | Backward from LVL install                |
| LVL beams (pressure-treated/custom) | 14–21                       | Backward from LVL install                |
| Roof trusses (custom)    | 28–42                                 | Backward from truss install              |
| Mini-split unit          | 7–14                                  | Backward from mini-split install         |
| Tankless water heater    | 7–14                                  | Backward from tank install               |
| Regular tank water heater | 7–14                                 | Backward from tank install               |
| Custom cabinets          | 42–56                                 | Backward from cabinets.install           |
| Countertops (slab)       | 14 from template                      | Backward from countertops install        |
| Tile (custom)            | 14–21                                 | Backward from tile install               |
| Tile (stock)             | 7                                     | Backward from tile install               |
| Electrical panel         | 7–14                                  | Backward from subpanel install           |
| Glass shower enclosure   | 7–14 from template                    | After tile shower complete               |
| LVT flooring (stock)     | 7                                     | Backward from flooring install           |
| Vanity / fixtures (stock) | 7                                    | Backward from plumbing finish            |
| Paint                    | 1–2 (collapse to 1d order task)       | 1 week before paint phase 1              |

For items with `≤ 7 supplier days`, you may collapse the 3-task pattern
to a single 1-day `order.<item>` work task placed 1 week before
install. Doesn't need a separate wait/checkpoint.


## TN residential inspections — the Inspection-Punch-Loop

Inspections are gates AND they spawn punch lists. The schedule has to
model BOTH. Get this wrong and you'll have field crew sitting on site
between inspections.

### The bundled rough inspection

All four rough inspections — **rough electrical, rough plumbing, rough
HVAC, and framing** — happen on **ONE day** with **ONE inspector**. The
framing inspection cannot be done before the MEP inspections because
plumbers and electricians drill and notch the framing during their
rough-in; the framer's work is not "final" until MEPs are in.

Model the bundle as a single `inspection` task:

- `inspect.rough_bundled` — `kind: inspection`, `duration_days: 0.5`,
  `trade: inspector`, `crew_size: 1`, predecessor `FS lag_days: 1`
  scheduling lead

Or as four separate `inspection` tasks all sharing the same
predecessor wall and the same scheduled day. Either is acceptable as
long as the bundle is co-scheduled.

NOTE: PM should be physically present at every MEP inspection — capture
photos, spray-paint flagged items, get verbal pass/fail same day. Don't
model this as a separate task; note it in the PEP narrative.

### The 2–4 day punch-list buffer (loop)

After EVERY rough inspection, expect at least one trade to fail. The
schedule must reserve **2 to 4 working days of no other trade activity**
to:

1. Get the plumber / electrician / HVAC tech back on site
2. Fix the flagged items
3. Schedule the **second inspection**
4. If clean, move to framing inspection (often same inspector, but
   sometimes a different qualified inspector — flag this)
5. If framing fails, another 2–3 day lull while the framer comes back
6. Then the FINAL framing inspection

Model the buffer using `lag_days: 2` (minimum) on the edge from the
inspection to its downstream consumer (typically `insulation.air_seal`
or `insulation.install`).

For projects where Will explicitly wants more cushion (large jobs,
unfamiliar inspector, finicky scope) use `lag_days: 4`. Default `2`.

### Insulation inspection

The insulation inspection uses the same inspector as the framing
inspection in most jurisdictions, but it's a **separate visit** because
insulation has to be physically installed first. It's procedural and
almost always passes first try.

- `inspect.insulation`: 0.5d, `lag_days: 1` to drywall, no extra buffer.

### Material delivery tied to inspection date

A unique TCR rule: **insulation material should be on site the day the
first MEP inspections happen.** Reason: while the 2–4 day punch-list
loop runs, the insulation crew has the materials staged and ready, so
once the inspections clear they can install immediately without waiting
for a separate delivery.

Model as `equipment.insulation_material_arrival` (`general` trade,
`duration_days: 0.5`) scheduled the SAME day as `inspect.rough_bundled`.

### Final inspections — one day, one inspector

Same pattern as rough. All three finals (final electrical, final
plumbing, final HVAC, plus the final building inspection) happen on
ONE day with ONE inspector. Schedule for the day paint phase 2 finishes.

### Drywall start: penciled, not hard-dated

After insulation inspection, the schedule has too many unknowns to
hard-date the drywall start. Will pencils the drywall but calls the
drywall crew **when the first insulation inspection is scheduled** (not
after it passes — insulation inspection almost always passes). That
gives the drywall crew a 3-day-out target.

This is a PM behavior; the schedule still uses an FS dependency from
the insulation inspection to drywall hang.


## Trade dependency cheat-sheet

| Trade                          | Must finish before this trade starts          | This trade gates                    |
|--------------------------------|-----------------------------------------------|-------------------------------------|
| Demolition                     | Project start, after permits + heat pump relocation + equipment | All structural work |
| Excavation                     | Demo + site prep                              | Foundation                          |
| Foundation (monolithic)        | Excavation; ONE footing inspection            | Framing (after cure)                |
| Structural mods (LVL/shoring)  | Existing structure exposed                    | Floor/roof loading above (only if load actually bears on LVL) |
| Framing                        | Foundation cured                              | Roofing, exterior, rough trades     |
| Roofing framing                | Foundation cured + walls                      | Underlayment, dry-in                |
| Underlayment                   | Roof framing + sheathing                      | Windows install + MEPs              |
| Windows/exterior doors         | Roof framed (NOT dried-in milestone)          | Insulation, weather barrier         |
| Exterior siding                | Windows installed + underlayment              | None for interior critical path     |
| Rough electrical               | Underlayment + windows installed              | Bundled rough inspection            |
| Rough plumbing                 | Tank set + underlayment + windows installed   | Bundled rough inspection            |
| Rough HVAC (if ducted)         | Underlayment + windows installed              | Bundled rough inspection            |
| Mini-split rough (line set)    | Underlayment + windows installed              | Mini-split install (later)          |
| Bundled inspection             | All rough trades                              | Insulation (after 2-4d buffer)      |
| Insulation                     | Bundled inspection passes                     | Insulation inspection → drywall     |
| Drywall                        | Insulation inspected                          | Paint phase 1                       |
| Paint phase 1 (prime + ceil.)  | Drywall sanded                                | Flooring, electrical finish, tile substrate |
| Flooring                       | Paint phase 1 + shower pan set (if wet area)  | Trim carpentry                      |
| Trim carpentry                 | Flooring                                      | Paint phase 2                       |
| Paint phase 2 (final)          | ALL finish trades done (trim, flooring, cabinets, tile grout, plumbing finish, electrical finish, mini-split install) | Substantial completion |
| Cabinets                       | Floor + drywall + paint phase 1               | Countertops, plumbing finish        |
| Countertops                    | Cabinets installed                            | Plumbing finish (sink hookup)       |
| Plumbing finish                | Bath shower done + flooring + cabinets        | Final inspection                    |
| Electrical finish              | Paint phase 1 (NOT paint 2)                   | Final inspection                    |
| Final inspections (bundled)    | All trades complete + paint phase 2           | CO / closeout                       |


## Overlap rules — when SS or negative lag is correct

Rough electrical, rough plumbing, and rough HVAC can run in parallel
using SS. Paint touch-ups can start before drywall finish completes —
`FS lag_days: -1`.

Roofing under-layment can start as soon as roof framing is sheathed,
and **windows/exterior doors install immediately after roof is framed**
(in parallel with the underlayment). Both keep the building dry.

Exterior siding can start as soon as underlayment is done — it does NOT
need to wait for the "dried-in" milestone.


## Crew concurrency — Will's HARD interior limit

Inside the building, **a maximum of TWO trades work concurrently** in
the interior finish phase. This is a hard cap. The space gets cramped
and crews trip over each other, and finish trades scuff each other's
work. Outside, there's no such limit — siding, landscaping, and
exterior paint can all run alongside interior trades.

The schedule must enforce this. If your parallelism framework wants to
overlap three or more interior trades, **pick the two most schedule-
critical** and stagger the third. Emit a `warnings[]` entry explaining
the stagger choice.

### The standard 3-finish-trade overlap — the HVAC stagger rule

The single most common 3-trade overlap on TCR jobs is the finish
cluster: `electrical.finish`, `plumbing.finish`, and HVAC finish
(`hvac.minisplit_install` for mini-split jobs, `hvac.finish` for
ducted). They tend to fall off the same upstream cluster (paint
phase 1, flooring, cabinets) with no internal serial edges, which
means CPM lands them on the same days = 3 trades on site.

**Default stagger:** HVAC serializes AFTER electrical finish.

```
hvac.minisplit_install: depends_on includes electrical.finish (FS)
```

Why HVAC and not the others:
- Electrical finish and plumbing finish are typically on the critical
  path and dependency-rich (sink hookup needs plumbing finish, which
  needs cabinets + flooring + tile grout).
- HVAC finish on a mini-split job is **1 day, 1 person**. It's the
  fastest of the three and the least dependency-bound. Lowest cost
  to slide.
- Slipping HVAC by 1 day after electrical preserves electrical +
  plumbing as the parallel critical-path pair and caps interior
  trade count at 2.

Emit a `warnings[]` entry citing this stagger:
"interior_finishes 3-trade overlap detected (electrical + plumbing +
HVAC) — applied default HVAC-after-electrical stagger per Rule 4N."

Override only when scope dictates HVAC sequence (e.g. an exterior
condenser install gating something), and emit a `warnings[]` entry
explaining the override choice.

When in doubt on any other 3-trade overlap, ask the PM at interview:
"max interior trades concurrent?" The default is 2.


## Same-crew exterior pattern

TCR's exterior crew typically does siding, trim, fascia/soffit, and
gutters as **one continuous same-crew block**. Run those four as a
single contiguous sequence from the same crew. Do not insert lead time
between them; do not gate gutters on a separate procurement task unless
gutters are explicitly custom.

Some PMs may use a separate roofer and siding sub. Default behavior:
treat as one crew block. If the PM specifies a different roofer, the
roof and siding can run in parallel.


## Customer early items — the TWO-BUCKET pattern

Customer-requested early items live in their OWN Component
(`customer_early_items` under `site_prep` phase), run on Day 1 BEFORE
main demo, and have NO dependency on retrofit / new-construction work.

**The trap:** when the customer's early item is in the SAME physical
area as retrofit work (very common — hall bathroom with both an
acrylic shower swap AND window infill, drywall patch, repaint), the
agent tends to lump them together. **Do not.**

The two buckets:

| | Component | Phase | Timing | What it contains |
|---|---|---|---|---|
| Bucket 1 | `customer_early_items` | `site_prep` | Day 1, before demo | The early item ONLY (e.g. `early.acrylic_shower_swap`) |
| Bucket 2 | `<area>_mod` (retrofit) | `interior_finishes` / similar | Parallel with main scope | Window infill, framing, drywall patch, repaint |

Same room. Two buckets. Two phases. Two scheduled windows. The customer
gets the convenience item ON DAY 1 (the whole point), and the rest of
the area's work runs whenever its physical dependencies allow.

**Concrete example — hall bath:**

```
Bucket 1 (site_prep / customer_early_items):
  early.acrylic_shower_swap                    1d, plumbing, Day 1

Bucket 2 (interior_finishes / hall_bath_mod):
  retrofit.hall_bath_window_infill_framing     0.5d, framing, parallel with main framing
  retrofit.hall_bath_insulation                0.5d, insulation, after infill framing
  retrofit.hall_bath_drywall_patch             (consolidated into drywall.consolidated per rule)
  retrofit.hall_bath_repaint                   0.5d, paint, after paint.phase_1
```

**Test before emitting:** if the PM Interview's `customer-requested
early item` answer named a specific physical action (e.g. "acrylic
shower swap", "leaky fixture replace", "small demo"), the emitted
graph MUST contain a task with id starting `early.` in the
`site_prep` phase under `customer_early_items` Component. If it
doesn't, you missed the early-item bucket — go back and add it.

**Do NOT** rename it `retrofit.<X>` and push to interior_finishes.
That's the V10 bug.


## Paint — two phases, mandatory

Paint is ALWAYS two phases. Never collapse into one.

### Paint phase 1 (ONE day, immediately after drywall sand)

`paint.phase_1` runs as ONE working day, ONE paint crew:

- AM: Spray prime entire space (walls + ceilings)
- Mid-day: Lunch / dry time
- PM: Spray + roll finish coat on **ceilings only**
- Optionally: One roll-only coat on walls (PM's call based on whether
  subs vs in-house crew will be tracking through the space)

Reason: primer seals drywall dust so other trades don't track it through
the customer's house. Finish-coat ceilings means the ceilings are DONE —
no ladders later, no paint drips on finished flooring.

Crew leaves walls in primer-only or primer + one roll. PM decides per
job.

`paint.phase_1` gates:
- Flooring installation (LVT)
- Electrical finish (trim-out)
- Tile substrate
- Anything that touches walls

### Paint phase 2 (ONE day, at the very end — AFTER all finish trades)

`paint.phase_2` is the FINAL coat AND the LAST work task on site
before substantial completion. It runs AFTER every finish trade has
finished and left the building.

- AM/PM: Cut in walls, second/final roll on walls
- Ceilings are usually fine from phase 1 unless an electrician left
  fingerprints around can lights — touch up if so

`paint.phase_2` predecessors MUST include EVERY finish trade:

- `trim.install` (trim is done)
- `flooring.install` (LVT down — protected during paint 2 with drops)
- `cabinets.install` (vanity / cabinets in)
- `tile.grout_seal` (master bath wet area complete) — if wet area
- `plumbing.finish` (fixtures, faucets, shower trim done)
- `electrical.finish` (devices, recessed lights, fan/light done)
- `hvac.minisplit_install` (for mini-split jobs) OR `hvac.finish` (for
  ducted jobs)

Why: paint phase 2 IS the moment substantial completion fires. If any
finish trade hasn't completed, the home is not substantially complete —
the customer can't use it. Paint 2 is also the last thing because finish
trades scuff walls, so painters need to do final cut-in + roll AFTER
everyone else is off the site.

### Substantial completion = paint phase 2 end

`milestone.substantial_completion` is FS-after `paint.phase_2` ONLY.
Because paint.phase_2 is gated on every finish trade, this milestone
naturally fires at the right moment — when the building is functionally
complete and the customer can use it.

It is NOT dependent on punch list. Punch list happens AFTER substantial
completion (during closeout).


## Foundation — monolithic by default

For TCR's typical foundation work, **monolithic pour is the default**.
Footings + 4" slab pour the same day, after one inspection.

Sequence:
1. `excavation.dig`
2. `foundation.form_and_prep` — form footings, gravel base, vapor
   barrier, rebar. All in ONE component, runs continuously.
3. `inspect.footing` — 0.5d, `FS lag_days: 1` after form
4. `foundation.monolithic_pour` — 1d, pour footings + slab together
5. `foundation.cure` — `kind: lead_time`, `lead_time_days: 2` (calendar)
6. NO secondary "slab inspection" — the footing inspection covers it
   when monolithic

Only split into separate footing-pour + cure + foundation-wall-pour +
slab-pour sequence if the scope **explicitly** says "stem walls,"
"foundation walls," or "CMU foundation." This is rare.

When pouring monolithic, this is a one-day pour for everything. Slab
cure is 2 days minimum before framing can start; some PMs build the
next day, but 2 days is the safe rule.


## HVAC sequencing — ducted vs mini-split

The MEP rough order depends on whether the HVAC system is ducted or
mini-split. **Detect from scope:**

- Scope mentions "mini-split" → MEP order is **plumbing → electrical →
  mini-split rough (line set)**. Mini-split is small and last because it
  doesn't fight other trades for space.
- Scope mentions "ducted," "duct work," or "heat pump and air handler"
  → MEP order is **HVAC → plumbing → electrical**. Big ducts go first
  because they're bulky and inflexible; plumbers and electricians work
  around them.

If HVAC type is unclear from scope, ask the PM at interview AND emit a
`warnings[]` entry. Default to mini-split if forced to guess (most TCR
addition work is mini-split).

Mini-split install (after dried-in, after drywall, after paint 1) is
**1 day, 1 person**. Don't budget more.


## Plumbing — tank set FIRST, always (when a tank is in scope)

**Scope condition:** the tank-set sequence applies ONLY when scope
INSTALLS or REPLACES a water heater. If scope describes vent
extension of an existing water heater (e.g. "extend existing gas WH
vent through new roof") and nothing else, the existing tank stays —
DO NOT emit `procurement.tank` or `plumbing.tank_set`. Plumbing
rough-in proceeds without any tank predecessor.

When a new or replacement water heater IS in scope (tankless or tank),
the tank is set BEFORE plumbing rough-in begins. The rough-in stubs
into the already-set tank.

Mandatory sequence (only when scope adds/replaces a WH):
1. `procurement.tank` — `kind: procurement`, lead time per table
2. `plumbing.tank_set` — 0.5d, `FS after procurement.tank`
3. `plumbing.rough_in` — 3–4d, `FS after plumbing.tank_set`

The tank-set day and the first day of plumbing rough-in CAN run
concurrently (the plumber can work on other supply lines while the tank
goes in). Use SS lag 0 or SS lag 1 on the rough-in if the PM is
specifically running concurrent.

DO NOT make plumbing rough-in a predecessor of tank set. That's
backwards.

### Plumbing rough-in duration — Will's nominal

`plumbing.rough_in` defaults to **4 working days × 2 crew** for any job
with: master bath, 2+ bath fixture counts, W/D relocation, full kitchen,
or any "extend vent stacks through roof" scope. This is Will's nominal
(transcript line 1942: "four days for two guys, that's fine for this
kind of job").

3 days only for a single half-bath rough-in with no other plumbing.
Anything below 3 days for an addition with a bathroom is wrong.

DO NOT shave plumbing duration to compress the schedule — the trade has
fixture-count + venting + supply/waste branches, and 4 days × 2 crew is
the floor for any non-trivial bath addition.


## Drywall consolidation

Drywall is a hang, tape, sand cycle with cure waits between steps. Model
those cure waits as FS `lag_days`, not as duration.

**For multi-zone jobs (addition + retrofit hall bath + basement storage)
consolidate drywall into ONE hang block and ONE finish block.** Send the
crew once, not twice. The breakdown may have separate retrofit drywall
sections; the agent should roll them into the consolidated tasks.

Typical addition drywall (consolidated): 9–11 days total. Use 9 for
small additions, 11 for larger.

When patching retrofit drywall (hall bath window infill, etc.), include
that work in the consolidated drywall block — don't make it a separate
sub-chain.


## Interior finish dependencies — the rewrite

This is where the AI gets confused the most. The rules:

1. **Flooring** depends on **paint phase 1 done** + **shower pan set
   (if wet area)**. NOT paint finish.
2. **Tile shower substrate + tile install + grout/seal** can run
   concurrent with flooring after the pan is set. Tile and flooring are
   the only two finish trades that can share interior space (the cap is
   2 interior trades concurrent, see crew concurrency).
3. **Trim/casing/baseboard** depends on **flooring done**. NOT paint.
4. **Cabinets/vanities** depend on **flooring + paint phase 1 done**.
5. **Electrical finish (trim-out, recessed lights, devices)** depends on
   **paint phase 1 done**. NOT paint finish.
6. **Plumbing finish (fixtures, faucets, shower trim)** depends on
   **cabinets done + tile complete (if wet area) + flooring done**.
7. **Paint phase 2** depends on **EVERY finish trade complete**: trim,
   flooring, cabinets/vanity, tile grout/seal, plumbing finish,
   electrical finish, and mini-split install (or HVAC finish for ducted).
   It's the LAST work task on site.
8. **Substantial completion** = `FS after paint.phase_2` only. Because
   paint phase 2 is gated on every finish trade, this milestone fires
   when the home is truly usable.


## Closeout — punch list workflow

The closeout phase runs AFTER substantial completion. It contains:

1. `closeout.client_walkthrough` — PM walks through with the homeowner.
   Uses Will's punch-list SOP form. PM points out at least 2 items the
   customer didn't see (builds trust). Customer SIGNS the punch list at
   the end so it's locked.
2. `closeout.punch_list_returns` — 1–3 days, trades come back briefly.
3. `closeout.final_clean` — 0.5–1d cleaning crew
4. `inspect.final_bundled` — all 3 finals + final building in ONE day,
   ONE inspector. Schedule for paint phase 2 finish date.
5. `milestone.co_handoff` — CO milestone

Each punch-list trade return is its own short task in `finish_trades`
or `closeout`, NOT bundled into one "punch list" monolith.


## Section → task decomposition templates (job-agnostic)

When the agent sees a `section_id` in the input breakdown, use the matching
template below as a starting point, then tune durations to the actual
`labor_hours` in the breakdown. Job-type docs supply additional templates
for sections that are specific to that job type.

### general_conditions

- `general.permitting` (`kind: work`, 1d, `general` trade,
  `pre_construction_offset_working_days: 15`)
- `general.pre_construction_walkthrough` (0.5d, `general`,
  `pre_construction_offset_working_days: 15`)
- `checkpoint.selections_finalized` (`kind: milestone`, `duration_days: 0`,
  `pre_construction_offset_working_days: 15`) — 3 weeks before on-site
  start. Anchors finish-material procurement. PM has confirmed all
  customer selections (tile, paint colors, fixtures, flooring, vanity,
  door style) are locked.
- `general.site_setup` (1d, `general`) — signage, porta-john, staging.
  On-site task, runs day 1.

### demolition_site_work

- `equipment.dumpster_arrive` (0.5d, `general`, day before demo)
- `equipment.demo_machines_arrive` (0.5d, `general`, day before demo) —
  concrete saw, skid steer, mini-ex, scaffolding
- `prep.heat_pump_relocate` (1d, `hvac`) — BEFORE demo (NOT in demo
  phase). If existing heat pump or HVAC components are in the way of the
  new footprint, they MUST be relocated 3+ days before demo crew starts.
- `prep.electrical_disconnect_relocate` (0.5d, `electrical`) — same
  rule, before demo.
- `demo.protection` (1d, `demo`) — floor protection, dust walls
- `demo.selective_demo` (2–4d depending on labor_hours, `demo`)
- `demo.haul_out` (1d, `demo`)

### excavation_foundation

- `excavation.dig` (1–2d, `excavation`)
- `foundation.form_and_prep` (1–2d, `concrete`) — form footings, gravel
  base, vapor barrier, rebar, ALL in one continuous task
- `inspect.footing` (0.5d, `inspector`, FS lag 1 after form_and_prep)
- `foundation.monolithic_pour` (1d, `concrete`, FS after inspect.footing)
  — pour footings AND 4" slab same day
- `foundation.cure` (`kind: lead_time`, lead_time_days: 2 calendar)
- (NO secondary slab inspection — covered by footing inspection)

Split into separate footing-pour and slab-pour ONLY if scope explicitly
says "stem walls" or "foundation walls."

### structural_modifications

- `structural.shore_existing` (1d, `framing`)
- `structural.install_lvl` (1–2d, `framing`)
- `structural.remove_temp_shoring` (0.5d, `framing`)

This sub-chain runs INDEPENDENTLY of new framing unless the new floor or
roof load bears on the LVL location. See addition rules.

### framing

- `framing.basement_walls` (2d, `framing`, FS after foundation cure)
- `framing.floor_system` (2d, `framing`, FS after **basement_walls**) —
  NOT dependent on LVL temporary shoring
- `framing.exterior_walls` (3d, `framing`, FS after floor_system)
- `framing.interior_walls` (2d, `framing`, SS lag 1 after exterior_walls)
- `framing.roof` (2–3d, `framing`)
- `framing.sheathing` (1d, `framing`)

`inspect.framing` does NOT go here. It lives in `rough_inspections` as
part of the bundled inspection that runs AFTER rough MEPs.

### roof_framing_roofing

- `roofing.underlayment` (1d, `roofing`, FS after `framing.sheathing`)
  — synthetic underlayment, drip edge, flashing
- `roofing.shingles` (1d, `roofing`) — up to 6,000 sqft in one day for
  residential. Most TCR additions = 1 day.
- `milestone.dried_in` (`kind: milestone`, duration 0) — set when
  underlayment + windows are both done; this milestone does NOT gate
  MEPs (see below)

### exterior_finishes (siding/trim/gutters/fascia-soffit)

Run as ONE same-crew block. Internal order can vary.

- `siding.install` (3–5d, `siding`, FS after `roofing.underlayment` +
  `windows.install`)
- `siding.trim_fascia_soffit` (2d, `siding`)
- `siding.gutters` (1d, `siding`)

These run in parallel with rough trades — exterior crew doesn't count
against the 2-interior-trades cap.

### windows_doors_weatherproofing

- `procurement.windows` (`kind: procurement`, lead_time per table)
- `windows.install` (1–3d, `windows_doors`, **FS after `framing.roof`**
  — NOT after the dried-in milestone). Runs in parallel with
  `roofing.underlayment`.

### electrical

- `procurement.electrical_panel` (`kind: procurement`, 14–21 days)
- `electrical.subpanel_install` (1d, `electrical`, crew 1) — just one
  person, one day
- `electrical.rough_in` (1–1.5d, `electrical`, crew 2, FS after
  `roofing.underlayment` + `windows.install`) — runs in parallel with
  plumbing rough-in via SS
- `electrical.finish` (2–3d, `electrical`, FS after `paint.phase_1`) —
  NOT after paint finish

### plumbing

- `procurement.tank` (`kind: procurement`, lead_time per table)
- `plumbing.tank_set` (0.5d, `plumbing`, FS after `procurement.tank`)
- `plumbing.rough_in` (3–4d, `plumbing`, FS after `plumbing.tank_set`
  AND `roofing.underlayment` + `windows.install`, SS with
  `electrical.rough_in`)
- `plumbing.finish` (2d, `plumbing`, FS after countertops if applicable,
  flooring, cabinets, tile complete)

### hvac

- `procurement.hvac_equipment` (`kind: procurement`, lead_time per
  table) — order at dried-in
- For MINI-SPLIT jobs:
  - `hvac.minisplit_rough` (0.5d, `hvac`, crew 1, FS after
    `roofing.underlayment` + `windows.install`) — line set
  - `hvac.minisplit_install` (1d, `hvac`, FS after drywall + paint
    phase 1)
- For DUCTED jobs:
  - `hvac.duct_rough_in` (2–3d, `hvac`, FIRST among MEPs)
  - `hvac.finish` (1–2d, `hvac`, FS after drywall)

### rough_inspections (bundled)

- `inspect.rough_bundled` (0.5d, `inspector`, crew 1, FS lag 1
  scheduling lead after the last rough trade) — this single inspection
  covers rough electrical, rough plumbing, rough HVAC (if ducted), AND
  framing
- `buffer.post_rough_inspection` (`kind: lead_time`, lead_time_days: 2
  to 4 working days) — represents the punch-list loop. Default 2.

OR use the equivalent 4-separate-task pattern co-scheduled on the same
predecessor.

### insulation_air_sealing

- `equipment.insulation_material_arrival` (0.5d, `general`) — same day
  as `inspect.rough_bundled`
- `insulation.air_seal` (0.5d, `insulation`, FS after buffer)
- `insulation.install` (1d, `insulation`) — typical addition is 1 day
- `inspect.insulation` (0.5d, `inspector`, FS lag 1) — procedural,
  almost always passes

### drywall

Consolidate addition + retrofit + basement storage into one block.

- `drywall.consolidated` (9–11d, `drywall`, FS after `inspect.insulation`)
  — hang + tape/mud + sand + prime all-in-one bar. Internal cure days
  are baked into the duration.

Alternatively split into:
- `drywall.hang` (3d, `drywall`)
- `drywall.tape_mud` (4d, `drywall`)
- `drywall.sand_prime` (2d, `drywall`)

Either format is acceptable. Consolidated is preferred per Will.

### interior_finish

- `paint.phase_1` (1d, `paint`, FS after drywall sand) — see Paint
  section
- `flooring.install` (2–4d, `flooring`, FS after `paint.phase_1` AND
  tile shower pan if wet area)
- `tile.shower_substrate` (1d, `tile`, FS after `paint.phase_1`)
- `tile.shower_install` (3–5d, `tile`, FS after substrate)
- `tile.grout_seal` (1d, `tile`)
- `cabinets.install` (varies, `cabinets`, FS after `flooring.install`)
- `countertops.template_install` (varies, `countertops`, FS after
  cabinets)
- `trim.install` (2–3d, `trim_carpentry`, FS after `flooring.install`)
- `electrical.finish` (2–3d, `electrical`, FS after `paint.phase_1`)
- `plumbing.finish` (2d, `plumbing`, FS after cabinets + flooring +
  tile)
- `paint.phase_2` (1d, `paint`, FS after `trim.install`)
- `milestone.substantial_completion` (`kind: milestone`, FS after
  `paint.phase_2`)

### closeout

- `closeout.client_walkthrough` (0.5d, `general`, FS after
  `milestone.substantial_completion`) — PM walks through with homeowner,
  punch list signed
- `closeout.punch_list_returns` (1–3d, multi-trade, FS after walkthrough)
- `closeout.final_clean` (0.5–1d, `cleanup`)
- `inspect.final_bundled` (0.5d, `inspector`) — all finals + final
  building in one inspector visit
- `milestone.co_handoff` (`kind: milestone`, FS after final inspection)


## Worked duration examples (sanity checks)

Framing, labor_hours=146, crew=3 → heuristic 6.1d → round to 6d. For a
2-story addition: split into `basement_walls` (2d), `floor_system` (2d),
`exterior_walls` (3d), `interior_walls` (2d), `roof` (3d),
`sheathing` (1d).

Drywall, labor_hours=159, crew=3, consolidated → 9–11 working days
total covering hang + tape + sand + prime (cure days baked in).

Tile, labor_hours=88, crew=2 → 5.5d. Bump up — tile always takes longer
than labor accounting says. Split: `substrate` (1d), `install` (4–5d),
`grout_seal` (1.5d).

Roofing shingles for a 30x10 addition (300 sqft) — 1 day. Don't budget
more.

Subpanel install — 1 day, 1 person. Don't budget more.

Mini-split rough-in (line set) — 0.5 day, 1 person.

Mini-split install — 1 day, 1 person.


## TODO — areas where these numbers need ongoing refinement

These are placeholders pending continued calibration against actuals:
crew sizes in the productivity table (industry-typical, not yet
TCR-measured at scale), all lead times (heavily supplier-dependent),
productivity rates (sqft/day, lf/day numbers), required inspections and
order (varies by TN county), and which trades TCR subs out versus
self-performs (affects parallelism).

The agent's output should call out anything that relies on a placeholder
above by mentioning it in `assumptions[]`.
