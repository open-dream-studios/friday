---
generation_kind: intelligence_rebuild_v2
stage: synthesis
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWFF6ZQ82D651FWRN1RBJA72/jobs/308-evergreen-street-addition_JOB-01KWFF8CWBQKYGA4Z64XF143EY/intelligence/extracted/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KWFF6ZQ82D651FWRN1RBJA72/jobs/308-evergreen-street-addition_JOB-01KWFF8CWBQKYGA4Z64XF143EY/intelligence/extracted/breakdown.md
  - _projects/308-evergreen-street_APPPROJ-01KWFF6ZQ82D651FWRN1RBJA72/jobs/308-evergreen-street-addition_JOB-01KWFF8CWBQKYGA4Z64XF143EY/intelligence/extracted/plans.md
  - _projects/308-evergreen-street_APPPROJ-01KWFF6ZQ82D651FWRN1RBJA72/jobs/308-evergreen-street-addition_JOB-01KWFF8CWBQKYGA4Z64XF143EY/interview/round-1.md
round: 2
interview_status: needs_more
---

# Open Questions — Round 2

Round 1 resolved the big-ticket ambiguities (scope/CSV gap, septic direction, windows, cladding, hall bath early item, tankless WH, door mix, plumbing labor floor). Round 2 cleans up the remaining risk items surfaced by the plans: chimney at the roof tie-in, master shower dimensions, service amperage confirmation, the negative-material Row 25 anomaly, basement layout scope, framing method confirmation, recessed light count, and roof tie-in discovery timing.

### q.chimney_roof_tie_in
**Question:** Plans page 5 shows an existing chimney in the new roof's tie-in path (new 3/12 gable meeting existing 6/12), but scope has no line for chimney flashing, cricket, or masonry counter-flashing. How should we handle it?
**Category:** scope
**Hint:** A cricket on a 3/12 gable meeting a masonry chimney is real labor + sheet-metal material. Silent omission risks a mid-job change order right when the roof is drying in.
**Select:** one
**Choices:**
- Include cricket + counter-flashing in base scope now (add line item, adjust roofing labor +0.5d)
- Handle as change order after field verification (roof-open discovery)
- Existing chimney is being demolished — no tie-in needed
- Existing chimney is far enough from the addition footprint that no tie-in flashing is required
- Other (specify in text)
**Why:** Determines whether roofing labor + material need bumping now and whether a `roofing.chimney_cricket` task belongs in the graph. Directly affects dried-in timeline.

### q.master_shower_dimensions
**Question:** Scope says the master tile shower is "approx. 7'×4'" but the floor plan (p.4) shows a shower footprint closer to ~5'7½"×10' in the primary bath. Which dimensions should procurement use for tile ($3/sqft walls, $6/sqft mosaic floor) and waterproofing?
**Category:** scope
**Hint:** Different footprints mean materially different tile order quantities and shower-substrate labor. Ordering wrong = 2-3 week reorder wait on custom tile.
**Select:** one
**Choices:**
- Scope is correct — 7'×4' footprint (order tile for ~44 sqft walls + ~28 sqft floor)
- Plans are correct — larger footprint, ~10'×5'7½" area (order tile for ~90 sqft walls + ~56 sqft floor)
- Neither — designer has updated dimensions since drawings (provide new dims)
- Other (specify in text)
**Why:** Tile is a 14-21 day custom lead time. Ordering the wrong quantity is a schedule-critical slip.

### q.service_amperage_check_scheduling
**Question:** Company rule `service_amperage_check` requires a `prep.amperage_check` task in pre-construction (0.5d, senior electrician, ~2 weeks before on-site) before ordering the 100A subpanel. Scope assumes existing service supports the new subpanel — but the check is mandatory before we lock the schedule. Confirm we're emitting this task and it's not being deferred.
**Category:** risk
**Hint:** V11 skipped this and it burned. If existing service is undersized, adding an amperage upgrade mid-project = 2-4 wk + $1.5-5k coordination cost.
**Select:** one
**Choices:**
- Emit `prep.amperage_check` at pre_construction_offset_working_days: 10 (standard)
- Already verified via prior visit — skip the task (attach verification note)
- Schedule earlier (offset 15) — want the buffer for a possible utility upgrade
- Other (specify in text)
**Why:** Gates `procurement.panel.order` and `electrical.rough`. Determines whether pre-con needs a 2-4 week utility-upgrade buffer built in.

### q.row_25_negative_material
**Question:** CSV row 25 (Existing Hall Bath Mod + Bedroom Remodel + Closeout) shows −$4,199 material and a −$1,714.20 section total against 72 labor hrs. Negative material with 72 real labor hours is anomalous. What does the −$4,199 credit represent?
**Category:** scope
**Hint:** Common causes: (a) a bundled fixture credit against the master bath allowance, (b) offset for reused hall bath valve/trim, (c) a spreadsheet balancing entry, (d) accidental double-count elsewhere.
**Select:** one
**Choices:**
- Reuse credit — value of reused hall bath valve/trim + fixtures netted out of the material line
- Allowance rebalance — hall bath material was double-counted in another section and this row zeroes it
- Data entry error — should be positive or zero
- Real credit due to salvage / material return
- Other (specify in text)
**Why:** Affects trust in the CSV row-25 labor allocation (72 hrs may or may not truly represent the closeout + hall bath + bedroom scope). Determines whether we split row 25 into three separate task blocks confidently.

### q.basement_addition_layout
**Question:** The floor plan (p.4) labels rooms as "GARAGE / LOUNGE / LIVING / KITCHEN, DINING / STORAGE" at basement level. Scope only describes basement-level 295 sqft as "storage space" (framed, drywalled, painted, lighting fixture, unfinished concrete). Are the garage/lounge/living/kitchen labels EXISTING context that the addition ties into, or are any of them part of the new 295 sqft build?
**Category:** scope
**Hint:** If any of those spaces are actually NEW build inside the 295-sqft basement addition, scope significantly underbids finish work at basement level. If they're EXISTING context, no action.
**Select:** one
**Choices:**
- All labeled rooms (garage/lounge/living/kitchen) are EXISTING — new basement build is storage-only per scope
- Storage is the ONLY new basement space; the other labels are the existing basement being connected to
- Some labels represent new build — need scope revision (please specify)
- Other (specify in text)
**Why:** Determines whether basement finish tasks (drywall / paint / trim / flooring) are scoped for 295 sqft (storage only) or a larger area.

### q.roof_framing_method_confirmation
**Question:** Scope says "truss or rafter framed, determined during design phase" for the new gable roof. Company belief `stick_frame_default_for_small_additions` (small addition, 300 sqft roof, 3/12 pitch, span <24 ft) defaults us to stick-frame with no truss procurement. Confirming so we don't emit a `procurement.trusses` task.
**Category:** structural
**Hint:** Trusses add 4-6 weeks of supplier lead time; stick-frame lumber arrives day-of with framing crew.
**Select:** one
**Choices:**
- Stick-frame — no truss procurement (default)
- Trusses — emit `procurement.trusses` with 28-42 day lead time
- Trusses locally sourced quickly — emit trusses with shorter lead (specify days)
- Other (specify in text)
**Why:** Trusses on this size of job would push pre-construction by ~6 weeks. Confirming stick-frame locks the shorter pre-con window.

### q.recessed_light_count
**Question:** Scope electrical says "approximately (12) recessed lights" but the material allowance schedule reads "Recessed Lights: $25 each, up to 18 fixtures." Should procurement + electrical labor be scoped for 12, or up to 18?
**Category:** procurement
**Hint:** Difference is $150 material and ~1 hr electrical labor. Minor, but should be pinned for the panel + circuit calc anyway.
**Select:** one
**Choices:**
- 12 fixtures (scope prose figure)
- 18 fixtures (allowance ceiling)
- Some other count (specify)
- Other (specify in text)
**Why:** Locks material order quantity and firms up the circuit calc going into electrical rough.

### q.tie_in_discovery_buffer_sizing
**Question:** Job-type rule `retrofit_tie_in_discovery` requires a `framing.tie_in_discovery` task SS with tie-in framing to expose concealed conditions early (LVL wall opening, roof tie-in, two window relocations, chimney zone). How much buffer do you want on the tie-in discovery bar — 2, 3, or 5 working days?
**Category:** risk
**Hint:** More buffer = safer against concealed wiring/plumbing/framing surprises. Less buffer = shorter overall schedule. Default is 3 working days for a normal addition, 5 when the tie-in is unusually complex.
**Select:** one
**Choices:**
- 2 working days — clean tie-in expected
- 3 working days — standard default
- 5 working days — unusually complex tie-in (chimney + LVL + 2 window relocations + roof pitch change all in one wall)
- Other (specify in text)
**Why:** Directly sizes the concealed-condition risk buffer. This is the single biggest schedule risk on the job per plans note "roof tie-in assumes standard integration; additional structural modifications not included."
