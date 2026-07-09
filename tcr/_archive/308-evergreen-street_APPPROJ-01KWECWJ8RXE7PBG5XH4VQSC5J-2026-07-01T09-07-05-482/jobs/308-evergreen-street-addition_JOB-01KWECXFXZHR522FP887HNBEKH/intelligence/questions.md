---
generation_kind: intelligence_rebuild_v2
stage: synthesis
round: 1
interview_status: needs_more
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWECWJ8RXE7PBG5XH4VQSC5J/jobs/308-evergreen-street-addition_JOB-01KWECXFXZHR522FP887HNBEKH/intelligence/facts.md
  - _projects/308-evergreen-street_APPPROJ-01KWECWJ8RXE7PBG5XH4VQSC5J/jobs/308-evergreen-street-addition_JOB-01KWECXFXZHR522FP887HNBEKH/intelligence/extracted/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KWECWJ8RXE7PBG5XH4VQSC5J/jobs/308-evergreen-street-addition_JOB-01KWECXFXZHR522FP887HNBEKH/intelligence/extracted/breakdown.md
  - _projects/308-evergreen-street_APPPROJ-01KWECWJ8RXE7PBG5XH4VQSC5J/jobs/308-evergreen-street-addition_JOB-01KWECXFXZHR522FP887HNBEKH/intelligence/extracted/plans.md
---

# Open questions — Round 1

### q.exterior_cladding

**Question:** Is the addition's exterior finish vinyl siding only, or is it brick base + lap siding above per the elevation drawings?
**Category:** scope
**Hint:** Scope says "vinyl siding to match existing." All three plan elevations show "NEW BRICK TO MATCH EXISTING" on the lower band + "NEW LAP SIDING" above. Brick means a masonry crew + brick lead time.
**Choices:**
- Vinyl lap siding only (drawings wrong / to be revised)
- Brick base + vinyl lap siding above (scope wrong — add masonry line)
- Brick base + fiber-cement/wood lap siding above
- Other (specify in text)
**Why:** Determines whether we emit a masonry Component (crew, brick procurement 14–21d, mortar cure) or a siding-only exterior block. Materially changes exterior cost + schedule length.

### q.tankless_wh

**Question:** Is the tankless water heater in the base scope, or is it the optional $6,500 add-on?
**Category:** scope
**Hint:** CSV row 21 header reads "HVAC – Mini Split, Tankless WH & Relocations," but scope lists tankless as an **optional package**. If tankless is in, the existing gas WH is removed and the "extend existing WH vent through new roof" line is stale.
**Choices:**
- Tankless IS in base scope (remove existing tank; drop the vent-extension task)
- Tankless is an OPTIONAL add-on, not yet accepted (keep existing tank + vent extension)
- Tankless is an OPTIONAL add-on and homeowner has ACCEPTED it (treat as in)
- Other (specify in text)
**Why:** Drives (a) procurement.tank + plumbing.tank_set sequence per Rule 4H, (b) whether roof phase includes a WH-vent extension task, and (c) $6,500 to Grand Total. Also resolves the CSV-vs-scope grand-total gap partly.

### q.upstairs_bedrooms

**Question:** Are BDRM. 2 and BEDRM. 3 shown upstairs on the floor plan new rooms in this addition, or existing rooms drawn for context?
**Category:** scope
**Hint:** Scope objective lists only "primary bedroom, master bathroom, walk-in closet" upstairs. The floor plan shows BDRM. 2 and BEDRM. 3 labeled on the upper level. Signal C (spatial ambiguity) per Rule 9.
**Choices:**
- Both are EXISTING rooms shown for context — addition is only primary suite
- Bedroom 2 is new (in addition footprint), Bedroom 3 is existing
- Both are NEW rooms inside the addition footprint
- Other (specify in text)
**Why:** If new, upstairs framing / drywall / paint / LVT / trim / electrical scope roughly doubles. Also affects window/door count and HVAC load. Big schedule impact.

### q.roof_framing_method

**Question:** For the 3/12 gable addition roof, will you stick-frame it or order trusses?
**Category:** structural
**Hint:** Scope says "truss or rafter — determined during design phase." Belief `stick_frame_default_for_small_additions` applies (789 sqft, span < 24 ft). Trusses add 28–42d procurement lead; stick-frame lumber arrives day-of.
**Choices:**
- Stick-frame (default — no procurement.trusses task)
- Trusses (add procurement.trusses at 28–42 calendar days)
- Not decided yet — treat as stick-frame default for now
- Other (specify in text)
**Why:** Trusses vs stick-frame is a 4–6 week pre-construction lead time difference and drives whether Rule 4Q emits `procurement.trusses`.

### q.septic_direction

**Question:** For the septic/sewer decision — is the existing septic staying, is TDEC septic replacement/relocation happening, or is the grinder pump going in?
**Category:** permits
**Hint:** Scope calls out TDEC septic inspection + feasibility of relocation OR grinder pump. All three are excluded cost-wise but one path must be chosen before plumbing rough. TDEC septic permit is 30+ working days pre-construction offset per applicable rule.
**Choices:**
- Existing septic stays (no TDEC permit, no grinder pump — plumbing rough proceeds as-is)
- TDEC septic replacement/relocation (add permit.tdec_septic with offset 30, change order for install)
- Grinder pump to available sewer (add procurement.grinder_pump + install task, change order)
- Not decided yet — TDEC feasibility still in progress
- Other (specify in text)
**Why:** Gates plumbing rough-in. Wrong assumption here can delay the schedule by weeks or invalidate the rough sequence. Also determines whether we emit permit.tdec_septic.

### q.customer_early_item

**Question:** Did the customer ask TCR to handle any work in the hall bathroom BEFORE main demo starts (e.g. the acrylic shower swap so they have a working shower during construction)?
**Category:** sequencing
**Hint:** Rule 4V splits customer early items (site_prep, Day 1) from retrofit work (interior_finishes, parallel with main scope). Row 26 conflates both. Very common pattern: acrylic shower swap = early item; window infill + drywall patch + repaint = retrofit.
**Choices:**
- Yes — acrylic shower swap runs BEFORE main demo (Day 1 customer_early_items)
- No — hall bath work all runs in normal sequence with main job
- Yes but different item (specify in text)
- Other (specify in text)
**Why:** If yes, we emit `early.acrylic_shower_swap` in site_prep and SEPARATE retrofit tasks in interior_finishes per Rule 4V. If no, everything collapses into the retrofit component. This is the exact bug Rule 4V exists to prevent.

### q.total_investment_gap

**Question:** The scope quotes "Total Investment $173,850" but the CSV grand total is $100,778.92 — how should we treat the ~$73k gap?
**Category:** scope
**Hint:** Candidate explanations: material +15% and sub +30% markups not yet applied inside CSV totals; the two optional packages ($13,500); change-order-eligible items; brick masonry if drawings are correct.
**Choices:**
- CSV is base labor+material at cost; $173,850 is post-markup + optional packages accepted
- $173,850 is stale (older bid); CSV is the current authoritative number
- Gap represents work not yet itemized (brick masonry, upstairs bedrooms, etc.) that must be added
- Other (specify in text)
**Why:** Determines whether the schedule needs to add uncosted tasks (brick, extra upstairs rooms, etc.) or whether the CSV represents the full scope. Affects trade sizing and phase durations.

### q.window_count

**Question:** How many NEW windows on the addition — 4 (scope) or 2 (plans schedule)?
**Category:** procurement
**Hint:** Scope says (3) 36"×60" DH + (1) transom = 4 new. Plans window schedule shows only (2) new: one 3'×1' transom + one 3'×3' DH, plus (2) relocated existing.
**Choices:**
- 4 new (scope is correct; plans schedule is truncated/incomplete)
- 2 new + 2 relocated existing (plans are correct; scope over-counts)
- Different count entirely (specify in text)
- Other (specify in text)
**Why:** Window procurement quantity + supplier lead time (stock 14–21d, custom 28–42d) is on the critical path for weatherproofing. Also affects Rule 4J (windows install right after roof framed).
