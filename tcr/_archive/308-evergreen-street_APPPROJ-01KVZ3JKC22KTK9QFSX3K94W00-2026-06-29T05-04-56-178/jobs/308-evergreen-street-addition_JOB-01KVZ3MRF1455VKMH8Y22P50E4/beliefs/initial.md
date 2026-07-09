---
generation_kind: intelligence_setup_v1
interview_status: complete
round: 5
depends_on:
  - _company/rules/editor_rules.md
  - _company/rules/dev_rules.md
  - _company/rules/pep_rules.md
  - _company/beliefs/_examples/stick_frame_default_for_small_additions.md
  - _company/knowledge/308_evergreen_wills_audit_transcript.md
  - _company/knowledge/_examples/wills_voice.md
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/manifest.json
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/inputs/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/inputs/files/308_scope.pdf.txt
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/inputs/files/308_Evergreen_Addition.xlsx - Summary (1).csv.txt
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/beliefs/interview-2026-06-26T20-55-11-049.md
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/beliefs/interview-2026-06-26T21-02-50-651.md
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/beliefs/interview-2026-06-26T21-10-42-369.md
  - _projects/308-evergreen-street_APPPROJ-01KVZ3JKC22KTK9QFSX3K94W00/jobs/308-evergreen-street-addition_JOB-01KVZ3MRF1455VKMH8Y22P50E4/beliefs/interview-2026-06-26T21-18-26-782.md
last_verified_at: "2026-06-26T21:22:38.281Z"
---

# 308 Evergreen Street — Intelligence Setup (Round 5 · Interview COMPLETE)

Rounds 1-4 resolved every CRITICAL, HIGH-priority, CONTEXT-dependent, and procurement-chain question. Round 4 confirmed (a) the master bath shower will have a frameless glass enclosure (10-day fab chain template-then-install) and (b) the picked tile is special-order with a 14-day full 3-task procurement chain anchored at `checkpoint.selections_finalized`. With those answers in hand, every procurement chain, every sequencing gate, and every retrofit Component placement decision is now grounded. The interview status moves to **complete** — downstream generations (task graph, schedule, PEP) can now draft with high confidence.

## What we know

### Customer & Job

- **Customer:** 308 Evergreen Street (manifest.json `customer`).
- **Job type:** Addition (manifest.json `job_type`; addition rules apply).
- **Job status:** in_progress, opened 2026-06-25 (manifest.json).

### Scope summary (from scope.pdf)

- **Footprint:** Two-story addition, ~30' × 10' (300 sqft per floor, ~600 sqft total). Basement-level storage below; second-floor expansion of primary bedroom + master bathroom + walk-in closet above.
- **Foundation:** 12"×12" continuous footings + 4" slab. No CMU / stem-wall language → monolithic pour per Rule 4B and editor_rules "Foundation — monolithic by default" (one footing inspection, single one-day pour, 2-day cure).
- **Framing:** 2x4 walls @ 16" O.C. New gable roof, 3/12 pitch tying into existing 6/12 roof. **Stick-framed** (PM confirmed q.roof_framing in round 2): no `procurement.trusses` task — framing crew brings lumber day-of.
- **HVAC:** (1) mini-split system, $2,500 allowance. Scope contains no "ducted" / "air handler" / "duct work" language → MEP rough order per Rule 4G is plumbing → electrical → mini-split. Mini-split rough = 0.5d/1 person; install = 1d/1 person.
- **Electrical:** New 100A subpanel, ~12 recessed cans, full rough-in + trim-out, GFCI/AFCI to code, dedicated 30A 120V circuit for the future elevator shaft, switch relocation in existing hallway with drywall patch + repaint.
- **Plumbing:** Full rough-in, master bath (dual lav, toilet, custom shower w/ dual-valve diverter), W/D relocation, vent stacks extended through new roof. Scope counts as multi-fixture / master-bath / W/D-relocation → `plumbing.rough_in` = 4 days × crew 2 (Will's nominal, transcript line 1942; rule `plumbing_rough_min_duration`).
- **Master bath finishes:** Custom tile shower ~7'×4' with niche + bench, dual-valve diverter, 72" double vanity, exhaust fan/light.
- **Hall bath (existing):** Window removal + frame infill + insulate/drywall/finish PLUS acrylic shower swap. Per Rule 4V two-bucket: the shower swap is the early item (Day 1); the window infill + drywall patch + repaint is the retrofit Component running in parallel with main scope.
- **Future elevator shaft:** 4'×4' framing only (no elevator). Per Will's audit transcript (line ~390): *"the elevator is over here and it's not even close to the addition over here, it's a retrofit item."* → retrofit Component, independent of new addition framing.
- **LVL beam:** 3-ply 14" spanning ~15'-6" to open existing load-bearing wall at the second-story tie-in. Per Will's audit transcript (~line 344, 352, 376): the LVL is a retrofit for the wall removal, the temporary shoring is independent, and `framing.floor_system` does NOT depend on the shoring — only on `framing.basement_walls`.

### Confirmed from PM Interview Round 1 (2026-06-26T20:55Z)

- **Customer early item (q.customer_early_items):** Hall bath acrylic shower swap. Schedule as `early.acrylic_shower_swap` (1d, plumbing) Day 1 in `site_prep / customer_early_items`, OFF the critical path, BEFORE main demo. Customer wants a working shower before we break ground.
- **Tankless WH (q.tankless_wh_scope):** NOT in scope. Existing gas WH stays; only its vent gets extended through the new roof. Per Rule 4H scope condition, NO `procurement.tank` or `plumbing.tank_set` in the graph. Plumbing rough-in proceeds with no tank predecessor.
- **Septic / TDEC (q.septic_grinder_scope):** TCR handles TDEC septic inspection + feasibility eval as part of pre-construction. Treat TDEC as a ~6-week (42 calendar day) pre-con anchor. Actual relocation / new tank / grinder pump install is a separate CO if needed.
- **Primary bedroom (q.retrofit_primary_bedroom):** Retrofit + new combined — existing primary bedroom is being remodeled and merged into the addition via the LVL wall removal. Component is retrofit + new combined, gated on `drywall.consolidated` + paint phases.
- **Roof tie-in risk (q.concealed_roof_tie_in_ack):** Accepted. Bake a 2-3 day `buffer.concealed_roof_tie_in` discovery buffer behind `framing.roof` with SS lag 1 so a CO doesn't slip interior trades.
- **Windows (q.window_order_type):** Stock. Use `wait.windows` lead_time_days = 21 calendar days.
- **LVL (q.lvl_type):** Standard 3-ply 14" — readily available. Use `wait.lvl` lead_time_days = 14 calendar days. Order one week before the LVL retrofit install.
- **Electrical service (q.electrical_service_verified):** Pending verification. Add `prep.amperage_check` (0.5d, electrical) to pre-construction with `pre_construction_offset_working_days: 15`. If amperage is insufficient, service upgrade becomes a separate scope / CO.

### Confirmed from PM Interview Round 2 (2026-06-26T21:02Z)

- **Roof framing (q.roof_framing):** Stick-frame confirmed. ~300 sqft/floor footprint, ~10' max wall length, 3/12 pitch — all inside the sub-800 / sub-24' default per `addition_rules.md`. No `procurement.trusses` task. Lumber arrives day-of with the framing crew.
- **TDEC kickoff (q.tdec_kickoff_status):** PENDING — the 6-week clock has NOT started. PM will kick off the TDEC call within 1 working day of signed agreement / deposit. **On-site start is FLOATING until contract signs.** Anchor schedule so on-site start = TDEC kickoff + 6 calendar weeks + 1 week buffer. The PEP narrative should treat the realistic on-site start as a function of contract-signing date, not a fixed calendar date.
- **Selections lock status (q.selections_locked_status):** PARTIAL — tile, LVT, paint base palette already picked. Still TBD: 72" vanity model, faucets, vanity mirrors + lights, mini-split unit aesthetic, interior door + pocket door styles, exterior door. `checkpoint.selections_finalized` lands at PC Day 15 (3 weeks before on-site) with `lead_up_working_days: 5` — real PM follow-up work over those 5 days. Finish-material procurement risk for vanity / faucets / mirrors / lights / doors — eventual task graph should flag in `warnings[]` that these procurement chains depend on PM landing the homeowner's lock.
- **Exterior match (q.exterior_match_status):** Verified. Vinyl siding profile matched against supplier stock (existing double-4 lap). Shingle product is GAF Timberline HDZ "weathered wood" — confirmed in stock at supplier. No special-order timing. Treat exterior finish supply as routine; no procurement risk to flag.

### Confirmed from PM Interview Round 3 (2026-06-26T21:10Z)

- **Closet & Cabinet System Optional (q.closet_cabinet_optional):** NOT accepted. Same silent-omission pattern as the tankless WH optional — scope lists the $7,000 allowance but breakdown CSV doesn't include it. Master walk-in closet finishes are paint + LVT + trim only, covered by base interior finishes. NO `closet.system_install` task and NO `wait.closet_system` procurement chain in the eventual graph.

### Confirmed from PM Interview Round 4 (2026-06-26T21:18Z)

- **Shower glass enclosure (q.shower_glass_enclosure):** Frameless 3/8" tempered glass door + fixed return panel. Template AFTER `tile.grout_seal` (~0.5d task by glass supplier), 10 calendar-day fabrication from local glass supplier, install ~0.5d. The eventual graph emits THREE master-bath shower-glass tasks:
  - `shower.glass_template` (0.5d, `glazing` trade, FS after `tile.grout_seal`).
  - `wait.shower_glass` (`kind: lead_time`, `lead_time_days: 10` calendar, FS after `shower.glass_template`).
  - `shower.glass_install` (0.5d, `glazing` trade, FS after `wait.shower_glass`, then becomes a predecessor of `paint.phase_2`).
  - Sits in interior finishes phase. Off critical path so long as template fires promptly after tile grout cures.
- **Tile lead-time category (q.tile_lead_time_category):** SPECIAL ORDER. Homeowner picked a coordinated wall tile (~30 sqft, 3"x12" subway) + mosaic floor combo from supplier's catalog, NOT warehouse stock. 14-day lead. Use the FULL 3-task procurement chain per Rule 4R (NOT the ≤7-day collapsed pattern):
  - `order.tile` (0.5d, `general` trade, FS after `checkpoint.selections_finalized` — anchors the chain into pre-construction zone so the 14-day wait fits before `tile.shower_substrate`).
  - `wait.tile` (`kind: lead_time`, `lead_time_days: 14` calendar, FS after `order.tile`).
  - `checkpoint.tile_arrived` (`kind: milestone`, FS after `wait.tile`, gates `tile.shower_substrate`).
  - Because tile must arrive before substrate prep, the chain is backward-pulled from `tile.shower_substrate` start date. With substrate landing in the mid-job interior finishes window, the order needs to fire ~3 weeks before substrate — which lands `order.tile` cleanly in the pre-construction zone right after selections lock.

### Sequencing & trade-stack implications (from rules + Will's audit)

- **MEP gates:** `roofing.underlayment` + `windows.install` — NOT `milestone.dried_in` (Rule 4I). Windows install immediately after `framing.roof` in parallel with underlayment (Rule 4J).
- **Heat pump + electrical disconnect relocation:** Scope includes "Relocate existing heat pump and electrical disconnect" — per Rule 4K, `prep.heat_pump_relocate` (1d, hvac) and `prep.electrical_disconnect_relocate` (0.5d, electrical) live in `site_prep / prep_work_before_demo`, NOT inside the demo phase. Minimum 3 working days before demo begins.
- **Rough inspections:** Bundle all four (rough electrical, rough plumbing, mini-split line set, framing) into ONE inspector visit on ONE day (Rule 4C). Insert `buffer.post_rough_inspection` 2 working days for the punch-list loop (Rule 4D).
- **Interior trade cap:** Max 2 trades concurrent in interior finishes (Rule 4N). With mini-split install, electrical finish, and plumbing finish all converging post-paint-phase-1, default stagger serializes `hvac.minisplit_install` AFTER `electrical.finish`.
- **Paint:** Two phases (Rule 4E + 4F). Phase 1 after `drywall.consolidated` (1d covering primer walls+ceilings AM + ceiling finish coat PM same day). Phase 2 is the LAST work task, gated on every finish trade (trim, flooring, vanity, tile grout, plumbing finish, electrical finish, mini-split install, **and now `shower.glass_install` per round 4**). `milestone.substantial_completion` = FS after `paint.phase_2` only.
- **Drywall consolidation:** Per breakdown line "Drywall – New Addition & Existing Bedroom" plus hall-bath patch + basement storage finish, drywall consolidates into ONE hang/tape/sand block (default 11d given multi-zone scope).

### Procurement landscape (confirmed)

- **Windows:** 3× 36"×60" double-hung + 1 transom + 1 exterior door. Stock. `wait.windows` = 21 calendar days.
- **LVL beam:** 3-ply 14". Standard. `wait.lvl` = 14 calendar days. Backward-pulled from `structural.install_lvl`.
- **Electrical 100A subpanel:** 7-14 supplier days (Rule 4R 3-task pattern). Backward-pulled from `electrical.subpanel_install`.
- **Mini-split unit:** Per editor_rules "mechanical equipment is an exception: order it tied to dried-in" — `order.minisplit` placed when structure is at/near dried-in (NOT at PC start). 7-14 supplier days. **Aesthetic selection still TBD per q.selections_locked_status — gates on `checkpoint.selections_finalized`.**
- **TDEC septic eval:** ~6 calendar weeks (42d) pre-con anchor. Clock starts at contract signing per q.tdec_kickoff_status. On-site start is the floating output of that clock.
- **Permits:** 1-day walk-in scheduled 15 working days before on-site start (Rule 4A). Per Will's audit transcript (~line 134): *"a lot of times I can get them, like I walk in there with documentation, I walk out with a permit... 90% of the time."*
- **Selections finalized checkpoint:** 15 working days (3 weeks) before on-site start (Rule 4P). Lead-up window = 5 working days of PM follow-up (Rule 4T). Real PM work — homeowner still owes vanity / faucets / mirrors / lights / mini-split aesthetic / interior + exterior doors.
- **Trusses:** NOT needed (q.roof_framing → stick-frame).
- **Vinyl siding / asphalt shingles:** Routine supplier pickup, no procurement chain needed (q.exterior_match_status verified).
- **Closet & Cabinet System:** Excluded (q.closet_cabinet_optional → NOT accepted). No procurement chain.
- **Master bath tile (q.tile_lead_time_category):** SPECIAL ORDER — 14 calendar days. Full 3-task chain (`order.tile` → `wait.tile` → `checkpoint.tile_arrived`) anchored after `checkpoint.selections_finalized`, gates `tile.shower_substrate`.
- **Master bath shower glass enclosure (q.shower_glass_enclosure):** Frameless 3/8" tempered + return panel. 10 calendar-day fab AFTER tile-grout cure. Three-task chain (`shower.glass_template` → `wait.shower_glass` → `shower.glass_install`), feeding into the master-bath finish stack as a predecessor of `paint.phase_2`.

### Risks tracked

- **Concealed roof tie-in to existing 6/12 roof:** PM accepted the 2-3 day buffer. Tracked.
- **Electrical service capacity:** Pending verification — could become a CO if 200A is insufficient. Tracked via `prep.amperage_check`.
- **TDEC eval timing:** Clock starts at contract signing — until then on-site start is floating. Tracked.
- **Finish-material procurement vs. selections lock:** Vanity / faucets / mirrors / lights / mini-split unit / interior + exterior doors all still TBD with homeowner. If selections slip past PC Day 15, the dependent procurement chains (1-week-before-install delivery target per Will's universal rule) cascade. Tile is now the most lead-critical of these — special-order 14-day chain MUST fire promptly after `checkpoint.selections_finalized`. Tracked; the eventual task graph should emit a `warnings[]` entry.
- **Shower glass template timing:** Glass fab can't start until tile grout cures and template fires. If template slips by even 2-3 days, install lands inside the `paint.phase_2` predecessor wall and pushes substantial completion. Tracked; ensure `shower.glass_template` fires same day or day after `tile.grout_seal`.

## What we're uncertain about

*Interview complete — no further questions.* All CRITICAL (HVAC type, customer early items, retrofit areas, roof framing), HIGH-priority (TDEC/septic, LVL type, LVL load-bearing independence, window order type, electrical service capacity, selections lock state, exterior match), CONTEXT-dependent (concealed roof tie-in risk acknowledgment, closet/cabinet optional package), and procurement-chain sharpener questions (shower glass enclosure vs. curtain, tile stock vs. special-order) have been answered.

Residual uncertainty around homeowner-pending selections (vanity model, faucet model, mirror/light models, interior + pocket door styles, exterior door, mini-split aesthetic) is captured by `checkpoint.selections_finalized` at PC Day 15 with a 5-working-day lead-up window — that is PM-driven follow-up work, not interview-resolvable. The task graph generation can proceed.

## Open commitments

PM noted in round 2 that on-site start is FLOATING until the contract signs and the TDEC clock starts. No verbal calendar date committed to the homeowner. If a contract-signing target slips by more than a week from the PM's current expectation, the realistic on-site start moves with it — surface that to the homeowner before the slip is "in their head" as a delay.
