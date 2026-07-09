---
generation_kind: risks_v2
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWFF6ZQ82D651FWRN1RBJA72/jobs/308-evergreen-street-addition_JOB-01KWFF8CWBQKYGA4Z64XF143EY/intelligence/facts.md
  - _projects/308-evergreen-street_APPPROJ-01KWFF6ZQ82D651FWRN1RBJA72/jobs/308-evergreen-street-addition_JOB-01KWFF8CWBQKYGA4Z64XF143EY/intelligence/confirmed.md
  - _projects/308-evergreen-street_APPPROJ-01KWFF6ZQ82D651FWRN1RBJA72/jobs/308-evergreen-street-addition_JOB-01KWFF8CWBQKYGA4Z64XF143EY/intelligence/applicable_rules.json
  - _projects/308-evergreen-street_APPPROJ-01KWFF6ZQ82D651FWRN1RBJA72/jobs/308-evergreen-street-addition_JOB-01KWFF8CWBQKYGA4Z64XF143EY/intelligence/extracted/plans.md
  - _projects/308-evergreen-street_APPPROJ-01KWFF6ZQ82D651FWRN1RBJA72/jobs/308-evergreen-street-addition_JOB-01KWFF8CWBQKYGA4Z64XF143EY/intelligence/extracted/breakdown.md
  - _projects/308-evergreen-street_APPPROJ-01KWFF6ZQ82D651FWRN1RBJA72/jobs/308-evergreen-street-addition_JOB-01KWFF8CWBQKYGA4Z64XF143EY/generations/task_graph.json
  - _projects/308-evergreen-street_APPPROJ-01KWFF6ZQ82D651FWRN1RBJA72/jobs/308-evergreen-street-addition_JOB-01KWFF8CWBQKYGA4Z64XF143EY/generations/schedule.json
last_verified_at: "2026-07-01T18:53:28.191Z"
---

# Risk register — 308 Evergreen Street Addition

Cost anchor: CSV grand total $100,778.92 raw cost basis; scope Total Investment $173,850 fully-loaded (extracted/breakdown.md — Trade totals; confirmed.md q.scope_vs_csv_total_reconciliation). Schedule anchor: on-site start 2026-07-01, end 2026-10-05 (~67 working days) per schedule.json; nominal critical-path sum ≈ 32 wd (task_graph.md). No `generations/baseline.md` present at time of authoring — cost impacts sized against CSV section totals and rate ladder ($70/hr GL, subs cost+30%, materials cost+15%).

## Top 5 risks (severity HIGH / MED / LOW)

### R1. Retrofit roof tie-in discovery — chimney flashing, valley/slope transition, existing conditions

- **Severity: HIGH**
- **Trigger conditions:** Roof plan p.5 shows existing chimney inside new roof envelope + multiple valleys + a 3/12↔6/12 slope transition; scope calls the tie-in "standard integration" (extracted/plans.md — Structural decisions, Discrepancies §Roof complexity). Plans carry "CONTRACTOR TO VERIFY EXISTING ROOF SLOPES AND SOFFIT DEPTH BEFORE CONSTRUCTION" as a risk-transfer note (extracted/plans.md — Retrofit indicators). No chimney flashing / cricket line item exists in the CSV (extracted/breakdown.md — Silent omissions #9). Rule `job_types/addition/rules/retrofit_tie_in_discovery.md` (rank 200) already fires and the graph carries a 2d `framing.tie_in_discovery` SS+2 buffer (task_graph.json), but that buffer sizes ~standard tie-in labor, not a chimney cricket + slope-transition combo.
- **Impact:** $2,500–$6,000 in unbudgeted framing + flashing labor and materials (custom chimney flashing + cricket + valley pans). Schedule: 2–5 working days beyond the built-in `framing.tie_in_discovery` buffer if field conditions worse than plans imply. Pushes critical path (framing.roof → roofing.underlayment) directly.
- **Mitigation:**
  1. Before demo (~C-day −3): PM on-site verification of existing roof slopes, soffit depth, and chimney flashing condition. Photo-document.
  2. Add explicit chimney flashing + cricket line to procurement list at `checkpoint.selections_finalized` (2026-06-10 target), lead time 7–14 cal-d.
  3. Pre-write a change-order template for "roof tie-in field conditions" before framing.roof starts (~2026-07-31) — invoke automatically if `framing.tie_in_discovery` exceeds 2 crew-days.
- **Rule:** `job_types/addition/rules/retrofit_tie_in_discovery.md` (rank 200); `_company/rules/dev_rules.md` §4Q (rank 100).

### R2. Scope-vs-CSV total gap — $73K unexplained, contractual exposure on $173,850 quote

- **Severity: HIGH**
- **Trigger conditions:** Scope Total Investment $173,850, CSV grand total $100,778.92 — a 42% gap (extracted/breakdown.md — Scope-vs-CSV total gap). PM confirmed in round 1 that $173,850 is the fully-loaded customer price (materials cost+15%, subs cost+30%, plus margin) and $100,778 is raw cost basis (confirmed.md q.scope_vs_csv_total_reconciliation). BUT: applying cost+15% to CSV materials ($52,171 → $60,000) + cost+30% to any subs portion of labor ($45,167) leaves the fully-burdened figure well short of $173,850 without a large margin add. If the $73K "gap" is largely margin, then any CSV under-scoping (silent omissions, plumbing repricing already ate 24 hrs, potential chimney/veneer/relocation labor) directly compresses margin — not a customer-price risk, but a profitability risk. Rule `_company/rules/scope_vs_csv_total_reconciliation.md` (rank 100) explicitly fires for gaps ≥5%.
- **Impact:** Margin compression $5,000–$15,000 if silent omissions (breakdown.md #1–#12) materialize into real labor/material draws that come out of the burden markup rather than a change order. No customer-facing $ move — this is TCR's margin at risk.
- **Mitigation:**
  1. PM to reconcile scope $173,850 line-by-line against CSV cost + markup arithmetic before baseline_v2 sign-off. Explicitly identify the margin dollar figure.
  2. Pre-flight the 12 silent-omission line items (extracted/breakdown.md — Silent omissions) into either a CSV row or a documented change-order trigger — no unallocated draws.
  3. Weekly labor-hours actuals vs CSV 1,311-hr revised total; flag at 15% burn deviation.
- **Rule:** `_company/rules/scope_vs_csv_total_reconciliation.md` (rank 100); `_company/rules/dev_rules.md` §11 (rank 100).

### R3. Electrical service capacity — new 100A subpanel + mini-split on unknown existing service

- **Severity: HIGH**
- **Trigger conditions:** Scope assumes existing main service can support new 100A subpanel (extracted/scope.md — MEP; scope.md L86). Rule `_company/rules/service_amperage_check.md` (rank 100) fires and requires `prep.amperage_check` in pre-con before panel order + rough — task graph carries that 0.5d task at 15wd pre-con offset (task_graph.json T3). If the amperage check finds the existing service is 100A total (common on older TN residential), adding a 100A subpanel + mini-split condenser + future elevator 30A circuit forces a service upgrade to 200A — not scoped, not budgeted, and utility coordination adds real calendar time.
- **Impact:** $2,500–$5,000 for service upgrade (panel swap, meter base, utility drop coordination, POCO fees). Schedule: 5–15 working days if utility coordination + inspection required. Blocks `procurement.subpanel.order` (currently 2026-07-31) and `electrical.rough` (2026-08-13) — this IS the on-site critical path predecessor cluster.
- **Mitigation:**
  1. Execute `prep.amperage_check` in first pre-con week (~2026-06-10 window). If existing service <200A, immediately trigger utility coordination + POCO contact.
  2. If service upgrade needed, PM issues change order BEFORE `checkpoint.equipment_confirmed` (2026-06-17) so subpanel order can proceed accurately.
  3. Escalation date: if amperage check not complete by 2026-06-24 (10wd pre-con), pause `procurement.subpanel.order`.
- **Rule:** `_company/rules/service_amperage_check.md` (rank 100).

### R4. Basement-level "walk-out vs below-grade" ambiguity — waterproofing/drainage scope

- **Severity: MED**
- **Trigger conditions:** Scope specifies 2×4 stick-framed basement walls on slab-on-grade with no CMU / no full-height foundation wall (extracted/scope.md — Foundation). Elevations show 8'-0" basement wall height with what was originally brick veneer at grade (extracted/plans.md — Discrepancies §Foundation type). Combined with the brick-veneer removal (confirmed.md q.brick_veneer_scope), the "basement" is effectively an at-grade / walk-out level with framed walls on slab. Scope explicitly excludes French drains, foundation waterproofing, drainage improvements (extracted/scope.md — Water Management; scope.md L151-152). If customer expected a below-grade basement with waterproofing, mismatch surfaces at framing or first rain.
- **Impact:** $1,500–$4,000 in change orders for drainage / vapor barrier / weather-resistive barrier upgrades if lower level exhibits moisture issues. Schedule: 2–4 working days if waterproofing has to be added post-framing. Also risks customer relationship if expectations misaligned.
- **Mitigation:**
  1. PM to walk site with customer BEFORE 2026-07-01 on-site start and re-confirm "basement" = walk-out / at-grade framed lower level, not a waterproofed below-grade space. Photo + written acknowledgement.
  2. Verify site grading around addition footprint during `foundation.excavate` (2026-07-09); if grade slopes toward addition, flag drainage change order before slab pour (2026-07-13).
- **Rule:** `_company/rules/dev_rules.md` §4B monolithic-foundation default (rank 100); confirmed.md q.brick_veneer_scope.

### R5. Plumbing labor floor + W/D roof venting + WH vent extension — undercosted trade

- **Severity: MED**
- **Trigger conditions:** CSV row 19 plumbing = 40 labor hrs; company rule `plumbing_rough_min_duration` mandates ≥64 hrs (4d × 2 crew) for master bath + W/D relocate jobs. PM elected the reprice — added ~24 labor-hrs to plumbing budget (confirmed.md q.plumbing_rough_labor_floor). Plumbing rough is on the critical path (task_graph.md T42 ★). Additional exposure: (a) dryer vent + W/D drain roof venting through new roof (extracted/plans.md — Retrofit indicators); (b) existing gas WH vent extension through new roof (extracted/scope.md L37); (c) vent-stack extensions through new roof — none of these are itemized as separate lines and all interact with `roofing.underlayment` timing on the critical path.
- **Impact:** $1,500–$3,500 additional labor + roof-penetration materials if any of the three roof-venting items encounter existing-condition surprises (rot, framing conflicts, code-clearance issues). Schedule: 1–2 wd on critical path if roof-venting cluster runs long during `plumbing.rough` (2026-08-11 to 2026-08-14).
- **Mitigation:**
  1. Pre-plumbing site walk (~2026-08-04, ~1wd before rough start): plumber to locate + mark all vent-stack + WH vent + dryer vent roof penetrations against framing layout.
  2. Coordinate roof penetration cluster with roofer during `roofing.underlayment` (2026-08-06) — one visit for all penetration flashings.
  3. Track plumbing burn against 64-hr revised floor; escalate at 56 hrs (~87.5%).
- **Rule:** `_company/rules/dev_rules.md` §4G (rank 100); `plumbing_rough_min_duration` (referenced by confirmed.md); `_company/rules/editor_rules.md` (rank 100).

## Watch list (W1..Wn, MED / LOW)

### W1. Window/door relocation labor — no discrete CSV line

- **Severity: MED** — Plans show 2 windows relocated + 1 door relocated (extracted/plans.md — Retrofit indicators); PM confirmed and requested a relocate-labor line (confirmed.md q.window_count_and_relocation). Task graph adds +1d to `windows.install` for relocation labor. If openings don't line up cleanly during framing, add another 0.5–1d. Impact: $400–$1,200 labor; ≤1 wd slip. Mitigate at `framing.tie_in_discovery` field verification. Rule: `retrofit_tie_in_discovery.md` (rank 200).

### W2. Row 25 negative section total (−$1,714, 72 labor hrs)

- **Severity: MED** — CSV row 25 bundles hall bath acrylic swap + primary bedroom remodel + closeout with a −$4,199 material credit. `dev_rules.md` §11 warning #8 fires (negative section total, labor >40 hrs). Not a scheduling blocker (task_graph splits work into `early.acrylic_shower_swap` + `hall_bath.finish` + `punch.closeout`) but the material credit needs PM reconciliation before baseline budget close. Impact: $1,500–$3,000 cost-basis uncertainty. Rule: `_company/rules/dev_rules.md` §11 (rank 100).

### W3. Recessed light count — 12 planned vs 18 allowance cap

- **Severity: LOW** — Scope: "approximately (12) recessed lights"; allowance schedule caps at 18 @ $25 each (extracted/scope.md — MEP; extracted/breakdown.md — Allowances). If PM elects 18, +$150 materials + ~2 hrs additional electrical.finish labor. LOW because it stays inside the allowance envelope; PM decides at `checkpoint.selections_finalized`.

### W4. Vendor slip on long-lead procurement (windows, tile, doors, mini-split, subpanel, LVL)

- **Severity: MED** — Six procurement chains, all 7–21 cal-d supplier windows (extracted/breakdown.md — Allowances; applicable_rules.json rank 100 `editor_rules`). Windows (18-day lead) and tile (14-day) have zero float on schedule.json — any vendor slip lands directly on critical path. Mitigate: PM places all orders within 2 working days of respective checkpoint gates; call vendors weekly for status starting 5 cal-d before promised delivery. Rule: `dev_rules.md` §4R (rank 100).

### W5. TDEC septic inspection outcome

- **Severity: LOW** — PM confirmed existing septic stays; TDEC does inspection-only, no install (confirmed.md q.sewer_septic_direction). Rule `tdec_septic_permit_offset.md` does NOT fire for inspection-only. LOW residual risk: if TDEC finds capacity insufficient for the added bedroom + bath, the "existing septic stays" decision reverses and grinder-pump / relocation change-order territory opens (scope.md L28-31 already carves this out). Track `prep.tdec_septic_inspection` outcome (currently 2026-06-10). Rule: `job_types/addition/rules/tdec_septic_permit_offset.md` (rank 200).

### W6. Weather-sensitive exterior sequence — roofing.shingles, siding.install, exterior paint

- **Severity: LOW** — Roofing shingles (2026-08-07 to 2026-08-10) and siding (2026-08-11 to 2026-08-13) run mid-August TN — thunderstorm season. Same 2-person crew serialized (`_company/beliefs/roof_and_siding_same_crew.md`, rank 100). Rain days push both. Impact: 1–3 rain days over the window is typical, absorbed by the ~36-day float on siding/exterior.trim_gutters (schedule.json). LOW because float exists. Rule: `dev_rules.md` §12 weather-sensitive flag (rank 100).

### W7. Elevator shaft framed only + 30A circuit — future coordination risk

- **Severity: LOW** — 4'×4' shaft framed + 120V/30A rough-in circuit installed for future 101 Mobility elevator install (extracted/scope.md — Special features; scope.md L154-155). If customer engages elevator vendor mid-construction, field-fit issues can surface. Not a base-scope schedule risk. LOW.

### W8. Drywall soft-schedule slip

- **Severity: LOW** — `_company/beliefs/drywall_soft_schedule.md` (rank 100) — drywall crew committed only after insulation inspection calendared. Task graph shows drywall.hang_finish on critical path (T49 ★) with 6d duration. If insulation inspection (2026-08-25) slips, drywall crew booking window compresses. Mitigate: PM calls drywall sub ~1wd after `inspect.insulation` clears. LOW because rule already embeds the soft-gate.

## What this register doesn't cover

- **Insurance events** — fire, theft, jobsite injury, vandalism. Handled by GL/WC policies outside brain scope.
- **Customer payment risk** — $20K deposit at signing + weekly invoicing (extracted/scope.md — Customer & Job). AR aging + collection is finance's domain, not planning risk.
- **Weather days beyond typical mid-August TN thunderstorm exposure** — no `_company/actuals/` dataset present at time of authoring to statistically anchor weather-day distributions. W6 flags the exposure qualitatively.
- **Concealed conditions during demolition (wiring, plumbing, structural)** — scope explicitly carves these to change-order (extracted/scope.md L19-21). Change-order process is contractual, not a planning risk.
- **Rock excavation / unsuitable soils** — scope carves to change-order (extracted/scope.md L16-18).
- **Customer selection velocity risk** — `checkpoint.selections_finalized` slip is tracked in the task graph as a pre-con checkpoint (T4); if PM can't get selections by 2026-06-10, procurement cascade slips. Owned by PM workflow, not this register.
- **Rate-ladder volatility** — labor $70/hr, sub cost+30%, materials cost+15% are contract-locked for this job.
