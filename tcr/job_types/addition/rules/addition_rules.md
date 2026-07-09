# Addition rules — TCR job-type knowledge for room and structure additions

This document is the addition-specific layer on top of the editor rules.
It captures what an addition needs that other job types do not: the
permitting realities, the long-lead structural items, the retrofit
patterns that almost always show up, the customer-requested early items
that show up at the front of every addition, and the change-order risks
unique to tying new construction into existing structure.

Use this document when the project scope describes adding new square
footage to an existing home (bedroom addition, bathroom addition, master
suite addition, second-story addition, garage conversion to living
space). For pure interior remodels of existing space, use the editor
rules baseline without this layer.


## Septic — TDEC, the long-lead permit

For additions where the project adds a bedroom, a bathroom, or any
other fixture that the TDEC (Tennessee Department of Environment and
Conservation) counts against septic capacity, the septic permit process
is the longest single lead time and often determines the realistic
start date — but ONLY if the home is on septic (not city sewer).

The TDEC process:

1. **Initial contact with TDEC — 6 weeks before job start** (Will's
   number). TCR calls TDEC to schedule, pays the $500 permit fee.
2. TDEC schedules a soil scientist to come do a site test.
3. A soil scientist's report comes back, typically 1–2 weeks after
   initial contact.
4. TDEC review and permit issuance.

End-to-end: typically 4–6 weeks from first contact to permit-in-hand.
Treat as a `lead_time` task in `pre_construction`:

- `permit.tdec_septic` (`kind: lead_time`, `lead_time_days: 42`
  calendar — 6 weeks)
- **MANDATORY: `pre_construction_offset_working_days: 30`**

The offset is non-negotiable. Without it, CPM backward-schedules TDEC
from its consumer (`excavation.dig`, which lands ~7 working days into
on-site after demo phase), and TDEC's start drifts to ~4 weeks before
on-site instead of the full 6 weeks. PMs actually file TDEC at the
START of pre-construction, not as-late-as-possible, so the offset
anchors it correctly. Use `30` working days (~6 weeks calendar) so the
permit window starts when the pre-construction phase starts and ends
right when excavation is ready.

Wire it to `excavation.dig` via the standard FS edge so the schedule
still enforces "no excavation until permit in hand," but the offset
controls placement.

TDEC is the most non-typical thing in the project. It can take a long
time, it can go pretty quick — you can't really predict. Will's number
of 5-6 weeks is the safety budget.

**Only include this task if:**
- Scope explicitly mentions TDEC, septic, soil scientist, leach field,
  or grinder pump, OR
- Scope adds a bedroom/bathroom AND PM Interview confirms the property
  is on septic (not city sewer)

If the home is on city sewer, omit the TDEC task entirely.


## Structural long-lead items

The two structural items that drive critical path for additions:

### Roof trusses (custom) — CONDITIONAL

DO NOT emit `procurement.trusses` by default. Will defaults to
**stick-frame** for small additions. Only emit the trusses procurement
task when one of these conditions is true:

1. Scope EXPLICITLY says "trusses" (not "truss or rafter framed,
   determined during design phase" — that's design ambiguity, default
   to stick-frame).
2. The addition's roof span is greater than 24 feet (large enough that
   stick framing isn't practical).
3. The addition's footprint is greater than 800 sqft.
4. The PM Interview explicitly confirms trusses.

When trusses ARE needed: 4–6 weeks supplier lead time. Order at
structural sign-off, well before framing starts. Trusses can land
weeks before they're installed without issue. Procurement task
`lead_time_days: 35` default.

When stick-framing (the common case for small additions): no
procurement.trusses task needed. Lumber is on the next-day delivery
from local supplier and arrives just-in-time with the framing crew.

If none of the trusses-needed conditions trip but the scope is
ambiguous ("truss OR rafter framed"), default to stick-frame and emit
a `warnings[]` entry: "scope ambiguous on truss vs rafter framing —
defaulted to stick-frame for small addition. PM Interview should
confirm."

### LVL beams

**Standard LVL: 1 week supplier lead** but default the procurement task
to `lead_time_days: 14` (≈3 weeks safety) in case it's pressure-treated
or custom. LVL availability fluctuates with lumber market conditions
and "next week" can quietly become "three weeks" without notice. Better
to early-order and have the beam waiting than to halt framing.

LVL beams are usually readily available standard items. Don't treat
them as critical-path-driving unless the PM specifically says custom.

**Pressure-treated or custom LVL: 21 days.** Ask PM at interview.


## Windows — order tied to install date, NOT permit submittal

Old rule said "order at permit submittal." That's wrong. Apply the
universal material-ordering rule: windows arrive 1 week before
`windows.install` start.

Stock windows: 14–21 supplier days → `lead_time_days: 21–28`.
Custom windows: 28–42 supplier days → `lead_time_days: 35–49`.

Verify if windows are custom or stock via PM Interview.


## Windows install — IMMEDIATELY after roof framed

For additions specifically, **windows and exterior doors install AS SOON
AS the roof is framed**, in parallel with `roofing.underlayment`. Both
keep the building dry.

DO NOT make windows install depend on the `dried_in` milestone. That's
the old wrong dependency.

Override the editor rule for additions:

- `windows.install` (1–3d, `windows_doors`) — `FS after framing.roof`
  AND `FS after procurement.windows`. Runs in parallel with
  `roofing.underlayment`.


## MEPs gated on underlayment + windows — NOT on dried-in

For additions, the MEPs (rough electrical, rough plumbing, rough HVAC)
start as soon as the building is weatherproof from the elements. The
building is weatherproof when:

1. Roof underlayment is installed (`roofing.underlayment` done)
2. Windows and exterior doors are installed (`windows.install` done)

Note: This is BEFORE the `dried_in` milestone (which traditionally
means shingles + windows + siding underlayment). MEPs do NOT need to
wait for shingles.

Override the default editor rule:

- `electrical.rough_in` — FS after `roofing.underlayment` AND
  `windows.install`
- `plumbing.rough_in` — FS after `plumbing.tank_set` AND
  `roofing.underlayment` AND `windows.install`
- `hvac.minisplit_rough` (or `hvac.duct_rough_in` for ducted) — same
  predecessors

The `dried_in` milestone fires later (after underlayment + windows +
shingles + siding underlayment) and gates exterior siding work, but it
does NOT gate the MEPs.


## Heat pump / HVAC component relocation — BEFORE demo

If the existing house has a heat pump, HVAC condenser, or electrical
disconnect in the way of the new addition's footprint, those components
MUST be relocated BEFORE the demo crew starts the main demolition phase.

- `prep.heat_pump_relocate` (1d, `hvac`) — minimum 3 working days before
  demo begins
- `prep.electrical_disconnect_relocate` (0.5d, `electrical`) — same rule

These are NOT in the demo phase — they're in `site_prep` or a dedicated
"prep work before demo" component. The old generated graph put heat
pump relocation at the END of demo, which is wrong.

Also coordinate temporary cooling/heating for the existing house during
the relocation window if the relocation takes more than a day. Note in
`assumptions[]`.


## Retrofit detection — the HARD heuristic

It is rare for an addition project to be ONLY new construction. The
addition almost always disturbs existing space. The agent MUST detect
this and isolate retrofit work.

### Step 1: Extract the addition objective

The scope has an OBJECTIVE section (usually the first paragraph). For
example: "Construct a two-story addition approximately 30' x 10' to
include basement-level storage space and second-floor expansion of the
primary bedroom, master bathroom, and walk-in closet."

The objective names the AREAS that are being added/modified: basement
storage, primary bedroom, master bathroom, walk-in closet.

### Step 2: Three signal checks per section

For every section in the breakdown, check:

**Signal A: Area mismatch.** Does the section's name or scope describe
work on an area or feature NOT named in the objective? Examples:

- Section mentions a room ("hall bath," "hallway," "kitchen") that
  isn't named in the addition objective → signal hit.
- Section describes work on a feature that the objective doesn't
  reference → signal hit.

**Signal B: The word "existing."** If the section uses the word
"existing" anywhere ("remove existing window," "relocate existing heat
pump," "modify existing wall"), that's a strong retrofit signal.

**Signal C: Spatial ambiguity.** For every section that describes
**building, framing, or installing a feature** (any feature, of any
type), extract or infer its physical location. If the scope does NOT
explicitly place the feature inside one of the addition objective's
named areas, the feature is a retrofit candidate. New construction
whose location is not stated in the addition objective is presumed
to be in existing structure — confirm with PM at interview.

Common spatial-ambiguity patterns to watch for (this list is
illustrative, not exhaustive — any feature without explicit placement
triggers):

- New shafts, chases, or partition walls in a structural section
  without a stated room.
- A new circuit, fixture, or outlet in a section that doesn't name
  the room.
- A "future" feature with no placement detail.
- A demo or removal whose target room isn't named.
- A new closet, niche, or built-in whose location isn't specified.

Signal C is the most subtle of the three. Use uploaded architectural
plans / drawings (if provided) to resolve location ambiguity BEFORE
flagging — a drawing that shows the feature inside the new addition
footprint resolves the ambiguity. If no drawings are provided AND the
scope text is silent on location, ASSUME retrofit and verify with PM.

### Step 3: If ANY signal triggers

1. Place the work in its own Component, NOT commingled with the
   new-construction Components in the same phase.
2. Do NOT gate the retrofit on new-construction dependencies that don't
   physically apply (a hall bath modification is not waiting on the new
   exterior framing of a bedroom addition).
3. Retrofit work can run in PARALLEL with new construction wherever
   trade and crew constraints allow (subject to the 2-interior-trades
   cap).
4. Emit a `warnings[]` entry naming the section and the suspected
   reason ("section X mentions 'existing hall bath' — flagging as
   retrofit; not gating on addition framing").
5. The PM Interview should ASK to confirm retrofit candidates.

### Common retrofit patterns

- New bedroom addition → existing hall bath modified for layout or
  code.
- New master suite → existing master closet repurposed or hallway
  reframed.
- Second-story addition → existing first-floor electrical panel upgraded
  for new load.
- Garage-to-living conversion → existing HVAC or panel modified to feed
  the new conditioned space.
- Any project with an "elevator" that's physically separate from the
  addition footprint.

### Retrofit drywall consolidates into main drywall block

Important: retrofit drywall (e.g. hall bath window infill patch + tape
+ paint) IS consolidated into the main `drywall.consolidated` block,
not modeled as a separate sub-chain. The crew does retrofit and new
drywall in the same visit. See editor rules drywall consolidation.


## Customer-requested early items — a separate concept from retrofit

This is distinct from retrofit work. **Customer-requested early items**
are work the customer asked TCR to do BEFORE the main job starts so
they can live in the house comfortably during construction.

Examples Will gave:
- 308 example: hall bath acrylic shower swap, customer wanted a fresh
  shower before the job broke ground.
- A leaky fixture the customer wants fixed up front.
- A small demo or removal the customer wants done so they can prep.

These are flagged in PM Interview ("any items the customer asked you to
handle before the main job begins?") and modeled separately from main-
scope retrofit work.

When detected:

1. Create a dedicated `customer_early_items` Component in `site_prep` or
   a dedicated early phase.
2. Schedule them BEFORE main demo begins (concurrent with prep work
   like heat pump relocation, equipment delivery).
3. Do NOT gate them on retrofit dependencies.
4. Emit an `assumptions[]` entry: "section X assumed to be
   customer-requested early item, scheduled before main demo per
   homeowner preference."

The PM Interview is the primary mechanism — the agent should ASK rather
than guess for these items.


## Concealed roof tie-in — change order risk

When the addition's new roof ties into the existing roof, the structural
conditions ABOVE the existing ceiling are concealed until demo opens
them up. The existing rafters or trusses may not be sized to accept the
new load, may have hidden damage, or may be framed in a way that
doesn't permit a clean tie-in.

This is the most reliable source of change orders on an addition with a
roof tie-in.

Model:
- 2-3 day buffer immediately after the existing-ceiling area is opened.
  Use `roof.concealed_buffer` (`kind: lead_time`, `lead_time_days: 3`,
  `SS lag_days: 1` after `framing.roof`).
- Emit a `warnings[]` entry: "Concealed roof tie-in — PM must document
  existing rafter conditions on day 1 of framing.roof so any change
  order can be processed fast."
- The buffer runs concurrent with framing, NOT before it. The PM opens
  the ceiling early in `framing.roof` and uses the discovery window.


## Existing electrical service — amperage check before subpanel

If the addition's electrical scope includes a subpanel feeding the new
space, the existing main service amperage MUST be verified. Typical
homes have a 200A service but may not have space to accept the
subpanel without a service upgrade.

The amperage check is a 0.5-day task in `pre_construction`
(`general` trade), and its result drives whether the project needs an
added service-upgrade scope.

- `prep.amperage_check` (0.5d, `general`, `pre_construction`)

If the breakdown includes a subpanel but no service-upgrade section,
emit a `warnings[]` entry: "subpanel scope present, no existing-service
amperage verification — flag for PM to confirm main service capacity
before signed contract."


## LVL temporary shoring — independent retrofit

When the project requires an LVL beam to replace an existing
load-bearing wall (very common in additions that open up the existing
floor plan to the new space), the temporary shoring + LVL install +
permanent shoring removal is its OWN sub-chain.

This sub-chain is gated by demo (the wall has to be exposed) but it is
**NOT gated by new-construction framing**, UNLESS the new addition's
floor or roof load actually bears on the LVL location.

Sequence:

1. `demo.expose_bearing_wall` (1d, `demo`)
2. `structural.temp_shoring` (0.5–1d, `framing`)
3. `structural.install_lvl` (1–2d, `framing`, FS after
   `procurement.lvl`)
4. `structural.remove_temp_shoring` (0.5d, `framing`)
5. Covered by the bundled framing inspection (NOT a separate inspection)

This sub-chain can run in parallel with new exterior framing. Do NOT
gate `framing.floor_system` on `structural.temp_shoring`. The floor
system depends only on the basement walls (or whatever the new floor
sits on), NOT on the LVL retrofit.

PM Interview question: "Does the new floor or roof load actually bear
on the existing LVL beam location?" If yes, then gate new framing on
LVL completion. If no (most cases), independent.


## Material ordering for additions — interior finishes wait

The universal rule (materials on site 1 week before install) applies to
additions, but the implication is different from a bathroom remodel.
For an addition, there's a 4-6 week gap between project start and the
interior finish phase, taken up by foundation, framing, and roof
dry-in. So interior finish materials (tile, cabinets, fixtures,
flooring) DO NOT need to arrive at project start.

For additions specifically:
- Long-lead cabinets (42-56 supplier days) ordered at structural
  sign-off to hit cabinet install date.
- Long-lead tile (custom, 14-21 supplier days) ordered ~3 weeks before
  tile install starts.
- Standard items (paint, flooring, trim, standard fixtures, mini-split,
  tank, vanities) follow the use-date-minus-1-week rule.

Mechanical equipment (mini-split, tankless, regular tank) ordered at
**dried-in**, NOT at project start.

### CRITICAL: do NOT put procurement chains in `pre_construction`

Every `order.X / wait.X / checkpoint.X_arrived` trio MUST live in the
dedicated **`procurement_long_leads`** phase — NOT in `pre_construction`.

Reason: procurement timing is install-date-driven (order = install date
minus supplier lead), not pre-construction-driven. Many procurement
chains schedule mid-build (windows order after framing.roof, paint
order ~1 week before paint.phase_1, etc.). When these are tagged
`phase_id: pre_construction` but CPM places them after on-site start,
the Gantt grouping breaks and the PM sees procurement work scattered
across the schedule labeled as pre-construction.

**Procurement phase emission rule:**

When generating the TaskGraph, emit this phase BEFORE the on-site phases:

```
{ "id": "procurement_long_leads", "name": "Procurement & Long Leads",
  "order_index": 1, "is_pre_construction": false }
```

(Shift `site_prep`, `demo_and_protection`, etc., order_indexes by +1
to make room. Or insert at `order_index: 0.5` semantically — the
absolute integer doesn't matter for scheduling, only the relative
ordering for display.)

Within `procurement_long_leads`, group by material type into
sub-components: `procurement_windows`, `procurement_lvl`,
`procurement_subpanel`, `procurement_minisplit`, `procurement_tile`,
`procurement_lvt`, `procurement_paint`, `procurement_vanity`,
`procurement_fixtures`, etc.

**What STAYS in `pre_construction`:** only the genuinely
pre-construction-anchored work — `general.permitting`,
`general.pre_construction_walkthrough`, `permit.tdec_septic`,
`prep.amperage_check`, `checkpoint.selections_finalized`,
`checkpoint.equipment_confirmed_demo`. These all need to land
BEFORE on-site start and have `pre_construction_offset_working_days`
set.

**Why this matters:** with the procurement phase reassignment, the
Gantt now shows three distinct lanes pre-on-site (real pre-con work),
a procurement lane spanning the whole project (material flow), and the
on-site phases as before. PMs scan all three independently.


## Addition-specific phase additions / components

When generating the TaskGraph for an addition, add these
phases/components on top of the editor rules spine when applicable:

- `pre_construction.tdec_septic` Component — if septic-impacting
  fixture is added AND home is on septic. (TDEC stays in
  pre_construction; procurement does NOT — see procurement phase rule above.)
- `pre_construction.amperage_check` Component — if subpanel is in
  scope.
- `procurement_long_leads` Phase — order/wait/checkpoint trios for
  every material with a non-trivial supplier lead. See the
  "CRITICAL: do NOT put procurement chains in pre_construction" rule
  above for the per-material component breakdown.
- `site_prep.prep_work_before_demo` Component — heat pump relocation,
  electrical disconnect, customer early items.
- `site_prep.customer_early_items` Component — customer-requested
  items.
- `structural_and_shell.lvl_subchain` Component — independent LVL
  retrofit work.
- `structural_and_shell.roof_tie_in` Component — concealed-condition
  buffer attached.
- `demo_and_protection.retrofit_zones` Component — retrofit demo
  (e.g. hall bath demo).
- `insulation_and_drywall.retrofit_drywall` — DO NOT create this. Roll
  retrofit drywall into `drywall.consolidated`.


## Drywall cracking — 1-year warranty assumption

Every TCR addition gets drywall cracking in year 1 at the tie-ins
between new and existing structure (above doors, windows, headers).
This is inherent — settling on a new addition where studs are slightly
off causes hairline cracks.

Will offers a one-year warranty return to repair these. NOT in the main
schedule.

Emit an `assumptions[]` entry: "1-year warranty return budgeted for
drywall cracking at addition tie-ins (standard TCR addition practice)."


## Will's walkthrough — final closeout

For ALL addition jobs, the very last task in the schedule is **Will's
personal final walkthrough with the customer**, scheduled one working
day after `inspect.final_bundled` passes.

- `closeout.wills_walkthrough` (0.5d, `general`, FS lag 1 after
  `inspect.final_bundled`)

This is Will's personal touchpoint with the customer. It is the actual
end of the project from TCR's standpoint.


## Mandatory addition warnings

In addition to the base mandatory warnings in dev rules, emit these
when the conditions apply:

1. **TDEC septic candidate but not modeled** — Scope adds a bedroom or
   bathroom and home is on septic, but no `permit.tdec_septic` task
   present.
2. **Roof tie-in buffer missing** — Roof tie-in to existing structure
   is in scope, but no `roof.concealed_buffer` is reserved.
3. **Subpanel without amperage check** — Subpanel is in scope, but no
   `prep.amperage_check` task is present.
4. **Retrofit-and-new commingled** — A section flagged as probable
   retrofit (via the heuristic above) is placed in a Component with
   non-retrofit work.
5. **Truss/LVL procurement missing** — Breakdown includes framing that
   requires trusses or LVL but procurement tasks are missing.
6. **Heat pump relocation timing** — Demo phase contains a heat pump
   relocation task. It should be in `prep_work_before_demo`, not in
   demo.
7. **MEP gated on dried-in milestone** — Any rough MEP task gated on
   `milestone.dried_in` instead of `roofing.underlayment` +
   `windows.install`.
8. **Windows install gated on dried-in milestone** — Should be gated
   on `framing.roof` complete + procurement, not the milestone.
