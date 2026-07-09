---
generation_kind: intelligence_rebuild_v2
interview_status: needs_more
round: 1
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWDVJA38HVW0W2JZ62XGQ7R8/jobs/308-evergreen-street-addition_JOB-01KWDVKJ8422ZNMTB2WJ7WYV9W/intelligence/extracted/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KWDVJA38HVW0W2JZ62XGQ7R8/jobs/308-evergreen-street-addition_JOB-01KWDVKJ8422ZNMTB2WJ7WYV9W/intelligence/extracted/breakdown.md
  - _projects/308-evergreen-street_APPPROJ-01KWDVJA38HVW0W2JZ62XGQ7R8/jobs/308-evergreen-street-addition_JOB-01KWDVKJ8422ZNMTB2WJ7WYV9W/intelligence/extracted/plans.md
  - _projects/308-evergreen-street_APPPROJ-01KWDVJA38HVW0W2JZ62XGQ7R8/jobs/308-evergreen-street-addition_JOB-01KWDVKJ8422ZNMTB2WJ7WYV9W/intelligence/applicable_rules.json
---
# Open questions — PM interview round 1

**Cut log:** 14 candidates drafted → 8 final. Merges: q.window_count_reconcile merged into q.window_order_type (single Q covers both count and lead-time). CONTEXT drops (round 1 doesn't need): q.concealed_roof_tie_in_ack (buffer is emitted regardless of PM ack), q.closet_optional_included (informational — closet package doesn't change task graph shape), q.amperage_verification (default = emit `prep.amperage_check`, no PM confirmation needed to include). No forbidden-pattern hits (q.hvac_type would fire but scope explicitly says "ductless mini-split" — already answered by scope).

---

### q.septic_or_sewer

**Question:** Is 308 Evergreen on a septic system, or does it connect to city sewer?

**Category:** permits

**Hint:** Scope mentions both TDEC septic inspection AND a grinder pump to connect to a sewer line. Whichever it is drives whether we need the 6-week TDEC pre-construction gate.

**Choices:**
- Septic (existing tank + leach field) — TDEC required, 6-week pre-con anchor
- City sewer — no TDEC needed, drop the permit chain
- Septic today but planning to convert to sewer via grinder pump this project
- Unsure — property records need to be checked

**Why:** Determines whether `permit.tdec_septic` (42-day lead + `pre_construction_offset_working_days: 30`) is on the critical path. If septic, TDEC anchors the entire schedule left edge; if sewer, we drop the task and save ~6 weeks.

---

### q.roof_framing

**Question:** Should we plan on stick-framing the new gable roof, or ordering trusses?

**Category:** structural

**Hint:** Scope says "truss or rafter framed, determined during design phase." For a ~30' × 10' addition with a 3/12 pitch tying into an existing 6/12, TCR's default is stick-frame (lumber next-day, no procurement gate). Trusses add 4-6 weeks of supplier lead time.

**Choices:**
- Stick-frame (default — lumber arrives with framing crew)
- Trusses (custom order, 28-42 day lead)
- Design phase still open — plan for stick-frame with option to switch
- Other (specify in text)

**Why:** Trusses add a 4-6 week `procurement.trusses` chain to the critical path. Stick-frame requires no procurement task. Getting this wrong shifts on-site start by weeks.

---

### q.customer_early_items

**Question:** Did the homeowner ask us to handle any specific work BEFORE the main job breaks ground so they can live comfortably during construction?

**Category:** scope

**Hint:** These are day-1 items done concurrent with site setup (not part of the retrofit / main scope). Common examples: swap out a shower they need working, fix a leaky fixture, small demo. The hall bath acrylic shower system in this scope is a strong candidate — but confirm.

**Choices:**
- Yes — the hall bathroom acrylic shower swap (Day 1, before main demo)
- Yes — something else (specify in text)
- No customer-requested early items — everything happens on the main schedule
- Not discussed yet — need to ask homeowner

**Why:** If yes, we split into two Components per Rule 4V: `early.<name>` in `site_prep.customer_early_items` (runs Day 1) + the rest of that area's work in the standard retrofit component. Landing an early item mid-project instead of Day 1 is a customer-experience failure.

---

### q.retrofit_hall_bath

**Question:** The existing hall bathroom modification (remove window, drywall patch, acrylic shower swap, repaint) is retrofit work in an existing room. Confirm treatment.

**Category:** scope

**Hint:** Per Rule 4V, retrofit work in an existing area is a separate Component from the new-construction bedroom/bath addition. The acrylic shower swap AND the window infill / drywall patch / repaint are all in the same room but potentially split across two Components (early item + retrofit).

**Choices:**
- Confirmed: acrylic shower swap = Day 1 early item; window infill + drywall patch + repaint = retrofit Component, parallel with main scope
- Confirmed retrofit — but treat as ONE bundle (all together, mid-project)
- Not retrofit — homeowner wants all hall bath work done at the very end alongside closeout
- Other (specify in text)

**Why:** Determines the Component placement and timing for ~72 CSV labor-hours of work. Getting this wrong lands the customer's promised early shower in November instead of Day 1, OR commingles retrofit demo with new-construction demo and breaks the 2-trades-max cap.

---

### q.window_order_type

**Question:** Are the (2) NEW windows (1 transom + 1 DH) stock catalog items or custom-order? Also — the plans schedule shows only 2 windows but scope calls for 4. Reconcile.

**Category:** procurement

**Hint:** Stock = 14-21 day supplier lead. Custom = 28-42 day lead. Plans window schedule lists only 2 new windows (transom + 3'×3' DH); scope says (3) 36" × 60" DH + (1) transom = 4. Elevations show 2 "relocated existing windows" — likely the extra 2.

**Choices:**
- (2) new stock windows only — the other (2) scope windows are relocated existing units
- (2) new custom windows only — the other (2) are relocated existing
- (4) new windows total — scope is authoritative, plans schedule out of date
- Other (specify — quantity, stock/custom split)

**Why:** Drives the procurement lead-time on the critical path (stock = 21d wait, custom = 42d wait), the number of `windows.install` days (0.5d for 2, 1-2d for 4), and whether elevations' "relocated existing" annotations are still valid.

---

### q.lvl_load_bearing

**Question:** For the (1) 3-ply 14" LVL beam spanning ~15'-6" that replaces the existing load-bearing wall — does the new addition's floor system or roof structure actually bear load on this LVL location?

**Category:** structural

**Hint:** Per addition_rules, if the LVL is retrofit-only (opens existing floor plan, no new load bears on it), the LVL sub-chain runs INDEPENDENT of new framing — parallel, faster schedule. If the new floor/roof load actually bears on this beam, then new framing gates on LVL install and the sub-chain is on the critical path.

**Choices:**
- Independent — the LVL opens existing space but the new addition's floor/roof lands on new bearing walls or the new foundation
- Load-bearing — new floor system or roof partially bears on the LVL, so LVL must be in place before new framing can proceed there
- Design still open — need structural engineer's confirmation
- Other (specify in text)

**Why:** Independent LVL sub-chain saves 1-2 days on the schedule by running parallel with exterior framing. Load-bearing LVL forces new framing to wait — needs to be encoded as an FS edge or the graph will be wrong.

---

### q.lvl_type

**Question:** Is the 3-ply 14" LVL beam standard stock or pressure-treated / custom?

**Category:** procurement

**Hint:** Standard LVL = ~1 week supplier lead (default 14-day safety in the procurement task). Pressure-treated or custom = 21 days.

**Choices:**
- Standard stock LVL (14-day procurement safety)
- Pressure-treated LVL (21-day procurement)
- Custom sized / custom species (21+ days, specify in text)
- Design not final — plan for standard, upgrade if needed

**Why:** Sets `wait.lvl` lead_time_days on the LVL procurement chain. 7-day delta between stock (14d) and PT (21d) can shift the LVL install date by a week.

---

### q.tankless_wh_included

**Question:** Is the Optional Tankless Water Heater package in scope for this build, or is the existing gas WH staying (with its vent extended through the new roof)?

**Category:** scope

**Hint:** The CSV template title says "Incl. Tankless WH Option" but scope treats it as an optional package with a $6,500 allowance. HVAC section material ($5,140) does not clearly include the $6,500 tankless allowance. Also — scope's plumbing narrative extends the EXISTING gas WH vent through the new roof, which implies the existing tank stays.

**Choices:**
- Existing gas water heater stays — vent extension only, no tank set task needed
- Tankless WH IS in scope — install the tankless with vent + connections, tank_set FIRST per Rule 4H
- Optional package deferred — customer decides during construction (assume existing stays for planning)
- Other (specify in text)

**Why:** If tankless is in, Rule 4H makes `plumbing.tank_set` a mandatory predecessor of `plumbing.rough_in` and adds a `procurement.tank` chain. If existing stays, we skip both and plumbing rough-in has no tank predecessor.

---
