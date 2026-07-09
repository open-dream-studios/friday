---
generation_kind: intel_questions_v1
interview_status: needs_more
round: 1
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWBHGCAX5JJ5DBH2KTWXP1HZ/jobs/308-evergreen-street-addition_JOB-01KWBHH9ZRQ0NQEED11V2FEQRJ/generations/_pre/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KWBHGCAX5JJ5DBH2KTWXP1HZ/jobs/308-evergreen-street-addition_JOB-01KWBHH9ZRQ0NQEED11V2FEQRJ/generations/_pre/breakdown.md
  - _projects/308-evergreen-street_APPPROJ-01KWBHGCAX5JJ5DBH2KTWXP1HZ/jobs/308-evergreen-street-addition_JOB-01KWBHH9ZRQ0NQEED11V2FEQRJ/generations/_pre/plans.md
  - _projects/308-evergreen-street_APPPROJ-01KWBHGCAX5JJ5DBH2KTWXP1HZ/jobs/308-evergreen-street-addition_JOB-01KWBHH9ZRQ0NQEED11V2FEQRJ/manifest.json
  - _company/rules/dev_rules.md
  - _company/rules/editor_rules.md
  - _company/beliefs/_examples/stick_frame_default_for_small_additions.md
last_verified_at: "2026-06-30T06:01:13.501Z"
---

# 308 Evergreen Street Addition — PM Interview (Round 1)

> **Provenance note:** `generations/_pre/rules_index.json` was not present at read
> time (Stage A did not emit it). The substantive company rule bodies it would have
> indexed are available directly in this brain's context (`_company/rules/dev_rules.md`,
> `_company/rules/editor_rules.md`, and the stick-frame addition belief), so the
> SCOPE WALK and question generation below are fully grounded. Rule citations point at
> the company-layer file paths directly. If a later stage needs the structured index,
> re-running Generate plan will regenerate it.

## What we know

### Customer & job
- Customer is **308 Evergreen Street**, job type **addition**, in Jonesborough, TN 37659 (`manifest.json`; `_pre/scope.md` Customer & Job).
- Objective: a **two-story ~30'×10' addition** (~590 sqft total, 295 sqft/floor) — basement storage below, master bedroom expansion + master bath + walk-in closet above (`_pre/scope.md` Objective / Footprint; `_pre/plans.md` Structural decisions).

### Scope — new construction (named objective areas)
- Foundation is **monolithic** (footings + 4" slab, one pour), standard soil assumed; rock excavation is a change order (`_pre/scope.md` Foundation). This matches TCR's monolithic default (rule: company:`_company/rules/dev_rules.md` §4B).
- Framing is **2×4 @ 16" O.C.**, dimensional floor system, with a **future elevator shaft (~4'×4', framing only)** and a dedicated 30A elevator circuit (`_pre/scope.md` Framing / Electrical).
- A **single 3-ply 14" LVL (~15'6" span)** opens an existing load-bearing wall; includes temporary shoring (`_pre/scope.md` Framing; `_pre/plans.md` LVL beam location).
- Roof is a **3/12 gable tying into the existing 6/12 roof** with multiple valleys at the junction near an existing chimney (`_pre/plans.md` Structural decisions / Roof tie-in).

### Trades
- **HVAC is a ductless mini-split** (1 unit, $2,500 allowance) — type is settled, so MEP rough order is plumbing → electrical → mini-split line set (rule: company:`_company/rules/editor_rules.md` HVAC sequencing). *No HVAC-type question needed.*
- **Plumbing**: master bath (2 lavs, toilet, custom shower w/ dual valve), W/D relocation, vent stacks through roof. Existing gas water heater **stays** — scope covers vent extension only, no tank replacement (`_pre/scope.md` Plumbing L37/L61). Per rule company:`_company/rules/dev_rules.md` §4H this means **no `plumbing.tank_set` task**, and rough-in carries the 4d×2 master-bath floor (rule: company:`_company/rules/editor_rules.md` plumbing productivity).
- **Electrical**: new **100A subpanel**, full rough/finish, ~12 recessed lights, elevator 30A circuit. Scope only *assumes* the existing main service supports the new subpanel (`_pre/scope.md` Electrical L70/L86) — unverified (see q.electrical_service).
- Custom **tile shower** in master bath (7'×4', niche + bench, mosaic floor) — finish-heavy, bump duration (rule: company:`_company/rules/editor_rules.md` tile productivity).

### Sequencing / retrofit signals
- **Roof framing is stick-frame by default** for this footprint: <800 sqft, <24' span, and plans show ridge/slope/valley callouts consistent with stick framing, no truss layout (company belief: `_company/beliefs/_examples/stick_frame_default_for_small_additions.md`; `_pre/plans.md` Discrepancy 4). Scope still defers "truss or rafter — design phase," so confirm (see q.roof_framing).
- Multiple **retrofit / existing-structure** work areas exist outside the addition footprint: existing **hall bath (BTH. 2)** acrylic shower swap + window infill, **primary bedroom remodel** finishes (~12'5"×16'), **two relocated existing windows**, and a **hallway switch relocation** (`_pre/plans.md` Retrofit indicators). These get their own Components, not commingled with new construction (rule: company:`_company/rules/dev_rules.md` §9 retrofit detection, §4V two-bucket pattern).
- **Heat pump + electrical disconnect relocation** are required **before demo** (rule: company:`_company/rules/dev_rules.md` §4K; `_pre/scope.md` Equipment Relocations).

### Procurement
- Windows (count/dims disputed — see below), exterior metal door, LVL beam, mini-split unit, custom tile, vanity, LVT all run the order/wait/arrived pattern (rule: company:`_company/rules/dev_rules.md` §4R). Stick lumber arrives day-of with the framing crew — no truss procurement (rule §4Q).

### Known discrepancies / risk flags (carried for the task graph, not all asked)
- **Brick vs. vinyl on lower level** — plans show "NEW BRICK TO MATCH EXISTING," scope says vinyl (`_pre/plans.md` Discrepancy 1). Asked below — adds a masonry trade + lead time.
- **Window count/dims** — scope says 4 windows incl. 3× 36"×60"; plans schedule shows only 2 (`_pre/plans.md` Discrepancy 2). Asked below.
- **Complex roof tie-in** — multiple valleys, chimney proximity, drawing demands field verification of existing slopes/soffit; concealed-condition change-order risk is real (`_pre/plans.md` Discrepancy 5/6). Folded into q.roof_framing's rationale and tracked as a discovery-buffer risk.
- **Septic / grinder pump** — already documented in scope as change-order contingencies, not budgeted (`_pre/scope.md` L63, `_pre/breakdown.md` Silent Omissions). No question raised; tracked as a known change-order risk.
- **Hall bath negative section total (−$1,714.20)** — likely a credit / fixture reuse, not a data error (`_pre/breakdown.md` Anomaly 1). Not schedule-affecting; tracked as a billing note.

## What we're uncertain about

### q.siding_material_brick_vs_vinyl

**Question:** The elevations show "NEW BRICK TO MATCH EXISTING" at the lower level, but the scope and budget only call for vinyl lap siding — which governs the lower level of the addition?
**Category:** scope
**Hint:** Brick adds a masonry sub, brick procurement lead time, and foundation-edge tie-in — none of which are in the current budget.
**Choices:**
- Vinyl siding throughout (scope governs)
- Brick lower level + vinyl above (plans govern — masonry sub needed)
- unsure — will reconcile with designer
**Why:** Brick introduces a whole masonry trade with its own procurement lead time and a dependency before exterior finish; absent today's budget it changes the exterior critical path.

### q.roof_framing

**Question:** Is the new gable roof stick-framed on site, or built with engineered trusses?
**Category:** procurement
**Hint:** Scope defers this to design phase; plans show valley/slope callouts (no truss layout). Stick framing avoids 4–6 week truss lead time.
**Choices:**
- stick-frame (next-day lumber, default for this footprint)
- trusses (long-lead procurement)
- unsure — design phase pending
**Why:** Trusses add a 28–42 day procurement task to pre-construction; stick framing carries no procurement and the framing crew brings lumber day-of. Also: the 3/12-into-6/12 tie-in with multiple valleys and a nearby chimney is a concealed-condition risk regardless — confirm you accept a discovery buffer there.

### q.customer_early_items

**Question:** Did the customer ask TCR to handle any work BEFORE the main job starts — e.g., the hall bath acrylic shower swap so they have a working shower during construction, a leaky fixture, or small demo?
**Category:** sequencing
**Hint:** Early items get their own site_prep Component running Day 1, off the critical path — separate from any retrofit work in the same room.
**Choices:**
- Yes — hall bath shower swap up front
- Yes — something else (specify)
- No early items
**Why:** A customer early item lands in `site_prep / customer_early_items` on Day 1 (rule §4V); collapsing it into the hall-bath retrofit Component pushes it to mid/late job and breaks the promise to the homeowner.

### q.retrofit_hall_bath

**Question:** The hall bath (BTH. 2) work — acrylic shower swap, window infill, drywall patch, repaint, and a possible "RTRN. BENCH" shown on plans — is this all retrofit work on the existing bath, separate from the new master bath?
**Category:** scope
**Hint:** Hall bath sits outside the 30'×10' addition footprint; plans show a return bench not described in scope.
**Choices:**
- retrofit — separate component, runs parallel to main scope
- part of main addition scope
- unsure
**Why:** Confirms the hall bath is its own retrofit Component (rule §9) gated only by its physical deps (drywall patch, paint phase 2), not by new-construction tasks — and flags whether the unscoped return bench is in or out.

### q.relocated_existing_windows

**Question:** Plans label two "EXISTING WINDOW RELOCATED" on the back/left elevation, but the scope's demo section doesn't mention relocating existing windows — is this window-relocation work in TCR's scope or a change order?
**Category:** scope
**Hint:** Relocating windows means framing modification in the existing wall being integrated with the addition.
**Choices:**
- in scope — TCR relocates them
- change order / out of scope
- unsure — verify with designer
**Why:** Adds existing-wall framing + refit tasks in a retrofit Component; if out of scope it must be excluded so the framing critical path isn't padded.

### q.window_count_and_type

**Question:** Scope lists 4 windows (incl. 3× 36"×60" double-hung + transom) but the plans window schedule shows only 2 (one 3'×3' D.H. + one transom) — what's the correct count/size, and are they stock or custom order?
**Category:** procurement
**Hint:** Count and size drive procurement quantity and lead time; stock is 14–21 days, custom 28–42.
**Choices:**
- 4 windows per scope, stock order
- 2 windows per plans, stock order
- custom order (any count) — confirm dims
- unsure — will reconcile before ordering
**Why:** Window procurement (count, size, stock vs. custom) sets the lead-time on the order/wait/arrived chain that gates `windows.install`, which in turn gates the rough MEPs.

### q.lvl_load_bearing

**Question:** Does the new addition's floor or roof load actually bear on the existing LVL beam location, or does the LVL only carry the existing structure where the load-bearing wall was removed?
**Category:** structural
**Hint:** Determines whether new framing must wait on the LVL install or can run independently.
**Choices:**
- yes — new load bears on the LVL
- no — LVL carries existing structure only
**Why:** If new framing loads the LVL, the LVL install gates that framing; if not, the LVL sub-chain runs independently of new framing (rule: company:`_company/rules/editor_rules.md` trade cheat-sheet, structural mods).

### q.electrical_service

**Question:** Has the existing main electrical service been verified to support the new 100A subpanel (plus the elevator circuit), or does the PM need to plan a service upgrade?
**Category:** scope
**Hint:** Scope only "assumes" the main panel is adequate — an upgrade adds a utility-coordination task and cost.
**Choices:**
- verified adequate
- upgrade needed
- unsure — will verify (amperage check)
**Why:** A service upgrade adds a pre-construction amperage-check + utility-coordination task and can gate the subpanel install; an unverified assumption is a late-discovery schedule risk.

## Open commitments

None recorded this round.
