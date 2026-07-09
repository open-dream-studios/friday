---
generation_kind: intelligence_rebuild_v2
stage: synthesis
round: 1
interview_status: needs_more
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWHNZ9SX3T48DZS1YPB87SRA/jobs/308-evergreen-street-addition_JOB-01KWHP1G1HG8C26X6GPS0EXGBR/intelligence/extracted/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KWHNZ9SX3T48DZS1YPB87SRA/jobs/308-evergreen-street-addition_JOB-01KWHP1G1HG8C26X6GPS0EXGBR/intelligence/extracted/breakdown.md
  - _projects/308-evergreen-street_APPPROJ-01KWHNZ9SX3T48DZS1YPB87SRA/jobs/308-evergreen-street-addition_JOB-01KWHP1G1HG8C26X6GPS0EXGBR/intelligence/extracted/plans.md
  - _projects/308-evergreen-street_APPPROJ-01KWHNZ9SX3T48DZS1YPB87SRA/jobs/308-evergreen-street-addition_JOB-01KWHP1G1HG8C26X6GPS0EXGBR/intelligence/applicable_rules.json
---

# Open questions — round 1

### q.scope_vs_csv_total_reconciliation
**Question:** The scope quotes a Total Investment of $173,850 but the CSV grand total is $100,778.92 — a gap of $73,071 (72.5%). How should we treat this?
**Category:** scope
**Hint:** Rule scope_vs_csv_total_reconciliation flagged this. Even after the two optional packages ($7k closet + $6.5k tankless = $13.5k), ~$60k is still unexplained.
**Select:** one
**Choices:**
- Scope figure includes contingency / OH+P / soft costs the CSV excludes — CSV is authoritative for procurement/scheduling
- CSV is missing entire sections (masonry brick, septic work, etc.) — need reprice before proceeding
- Scope figure includes both optional packages plus a margin/markup — clarify structure
- Signed change order pending — CSV total is authoritative
- Other (specify in text)
**Why:** Without reconciling, procurement runs on the wrong budget and billing schedule misfires. Blocks the interview from completing.

### q.septic_direction
**Question:** Which septic direction is base scope vs change-order for this job?
**Category:** scope
**Hint:** Scope treats all three (existing capacity, TDEC-approved new septic, grinder pump to sewer) as change-order. Direction drives whether we emit `permit.tdec_septic` at +30 working-day offset, and whether excavation gates on it.
**Select:** one
**Choices:**
- Existing septic has adequate capacity — no TDEC permit, no extra excavation
- Relocate existing septic tank — TDEC permit required, adds to excavation
- New septic tank + leach field — TDEC permit required, adds ~1 week of dig
- Grinder pump to sewer main — sewer connect permit, no TDEC
- Unresolved — treat as CO and proceed without in base schedule
- Other (specify in text)
**Why:** Wrong answer moves the on-site start date. TDEC is a 6-week lead if triggered.

### q.tankless_wh_in_base_or_option
**Question:** Is the tankless water heater the base scope, or the $6,500 optional package (customer-declined by default)?
**Category:** procurement
**Hint:** CSV row 20 title says "Tankless WH" but the $5,140 material total doesn't cover the $6,500 optional-package allowance. Scope's Special Features says the base scope extends the EXISTING gas WH vent through the new roof — implying existing tank stays.
**Select:** one
**Choices:**
- Existing gas WH stays — vent extension only; no tank procurement, no tank_set
- Optional tankless package is IN — add procurement.tank, plumbing.tank_set, rework plumbing rough sequence
- Existing tank being replaced with a new standard tank — different procurement pattern
- Other (specify in text)
**Why:** Determines whether Rule 4H tank-set sequence fires or the exemption applies. Changes plumbing rough order by ~1 day.

### q.exterior_masonry_brick_in_scope
**Question:** Are we installing NEW brick masonry on the basement-level exterior, or is that plans-only and out of scope?
**Category:** trades
**Hint:** Plans elevations explicitly label "NEW BRICK TO MATCH EXISTING" on the lower level. Scope only lists vinyl siding. Masonry is a distinct trade with its own crew, lead time, and cost — currently absent from CSV.
**Select:** one
**Choices:**
- Brick is in — need to add masonry sub, ~$4-6k material + labor, ~3-5 days
- Vinyl siding only, plans need to be revised
- Brick as change order pending customer decision
- Other (specify in text)
**Why:** Materially affects exterior schedule, sub coordination, and budget. If yes, we need a masonry procurement + install pair.

### q.window_count_and_size_reconciliation
**Question:** How many windows and at what sizes are we actually installing?
**Category:** scope
**Hint:** Scope: 4 windows total = (3) 36"×60" DH + (1) transom. Plans schedule: 2 windows total = (1) transom 3'×1' + (1) D.H. 3'×3'. Elevations visually suggest 3+ new-window openings. Discrepancy affects allowance ($300 ea × 4 = $1,200) and framing.
**Select:** one
**Choices:**
- 4 windows per scope (3× 36"×60" + 1 transom) — plans schedule is incomplete
- 2 windows per plans schedule — scope is stale
- Some middle number — specify count and sizes in text
- Other (specify in text)
**Why:** Wrong count changes procurement (windows are 21-day lead), rough opening framing, and exterior flashing labor.

### q.customer_early_item
**Question:** Did the customer ask TCR to handle any work BEFORE main demo starts (working shower during construction, small pre-move fixes, etc.)?
**Category:** scope
**Hint:** Rule 4V — the existing-hall-bath acrylic shower swap looks like a classic customer-early-item: it lives in an existing area that also has retrofit work (window infill, drywall patch, repaint). If confirmed, it lives in `site_prep / customer_early_items` on Day 1, NOT in interior_finishes with the retrofit work.
**Select:** one
**Choices:**
- Yes — hall bath acrylic shower swap needs to happen Day 1 so homeowner has a working shower during construction
- Yes — some other early item (specify in text)
- No early item — hall bath acrylic shower runs whenever its dependencies allow
- Other (specify in text)
**Why:** Determines whether we emit `early.acrylic_shower_swap` in site_prep Day 1 (Rule 4V two-bucket pattern) or fold it into the hall_bath_mod retrofit component only.

### q.interior_doors_pocket_vs_panel
**Question:** Which of the 4 interior doors are pocket doors vs pre-hung panel doors, and where do they go?
**Category:** scope
**Hint:** Scope says "(1) pre-hung + (2) pocket door systems" = 3 accounted for; total is (4). Plans door schedule lists 4 interior panel doors (A×2, B, C) with NO pocket-door callouts. Pocket doors need thicker wall framing.
**Select:** one
**Choices:**
- Scope is right: 1 prehung + 2 pocket + 1 more (specify type in text)
- Plans are right: 4 pre-hung panel doors, no pockets
- Different mix — specify in text
- Other (specify in text)
**Why:** Pocket doors require deeper wall framing and specific rough-opening prep; affects framing sequence and door-procurement selection.

### q.roof_tie_in_discovery_risk
**Question:** How much buffer do you want on the concealed roof tie-in (new 3/12 into existing 6/12 with 3+ valleys)?
**Category:** risk
**Hint:** Plans p.5 shows 3+ valleys where the new gable meets the existing 6/12 — a non-trivial tie-in. Scope disclaims "additional structural modifications not included." Job-type rule retrofit_tie_in_discovery mandates a discovery SS window; question is duration.
**Select:** one
**Choices:**
- Default 3 calendar-day discovery SS buffer — expose tie-in early during roof framing
- Extended 5-7 calendar-day buffer — customer expects zero surprises, willing to pay for margin
- Minimal 1-day sanity check — Will trusts the tie-in geometry
- Other (specify in text)
**Why:** Sets the SS lag on framing.tie_in_discovery and shapes the change-order threshold.
