---
generation_kind: baseline_estimate_v1
depends_on:
  - _projects/9921-emmerson-ln-garage_APPPROJ-01KVV3710873M9AW2MH6STQWZB/jobs/9921-emmerson-ln-garage_JOB-01KVV371088TPDJ532ZF8FFJ28/inputs/scope.md
  - _projects/9921-emmerson-ln-garage_APPPROJ-01KVV3710873M9AW2MH6STQWZB/jobs/9921-emmerson-ln-garage_JOB-01KVV371088TPDJ532ZF8FFJ28/manifest.json
  - _company/rules/_examples/plumbing_rough_min_duration.md
  - _company/knowledge/_examples/wills_voice.md
  - _company/knowledge/308_evergreen_wills_audit_transcript.md
last_verified_at: "2026-06-23T20:39:37.837Z"

---

# Baseline estimate — 9221 Emmerson Ln master bath gut

- **Job:** JOB-01KVV371088TPDJ532ZF8FFJ28
- **AppProject:** APPPROJ-01KVV3710873M9AW2MH6STQWZB — 9221 Emmerson Ln
- **Sources:** `inputs/scope.md`, `manifest.json`, `_company/rules/_examples/plumbing_rough_min_duration.md`, `_company/knowledge/_examples/wills_voice.md`, `_company/knowledge/308_evergreen_wills_audit_transcript.md`

## ⚠ Input conflict — must resolve before this baseline is actionable

`manifest.json` says `job_type: addition`, `summary: "Garage Addition"`, `tags: [addition]`. `inputs/scope.md` says **"Master bath full gut. New tile shower, vanity, fixtures. ~6 weeks target."** These describe two different jobs. This baseline is built against `scope.md` because it is the only file describing work content. If the real job is a garage addition, everything below is wrong and the estimate must be regenerated against an addition scope.

## Summary (per scope.md)

Single master-bathroom full gut. Replace tile shower, vanity, and fixtures. Customer-stated calendar target ~6 weeks. Scope provides no square footage, no fixture count beyond "shower + vanity", no plumbing-rerouting language, no electrical or HVAC scope, and no price.

## Cost baseline

**Direct cost subtotal: not derivable from current inputs.**

This job has no `inputs/breakdown.json`, no `inputs/notes.md`, no PM-supplied price, and no peer master-bath actuals under `_company/actuals/` (that folder is P9 territory and is empty today). The only cost-relevant facts available are:

- Master-bath plumbing rough labor floor: **4 working days × crew of 2 = 64 labor-hours minimum** (source: `_company/rules/_examples/plumbing_rough_min_duration.md`, severity `hard`).

That's the only number this baseline can quote with a traceable source. Labor, materials, and equipment subtotals — and therefore the customer total and the customer-vs-direct gap — require either a PM breakdown CSV uploaded to `inputs/` or harvested actuals from a comparable finished master-bath job. Neither exists in this trunk yet.

**What would unblock a real cost line:**

1. Upload PM breakdown (Buildertrend CSV → `inputs/breakdown.csv` → converted to `inputs/breakdown.json`, same flow Will demonstrated in `308_evergreen_wills_audit_transcript.md` lines 47–69).
2. Or: harvest one finished TCR master-bath job into `_company/actuals/` so this baseline can anchor against a real per-sqft or per-fixture number.

Until one of those exists, putting a dollar figure here would be invention, not estimation.

## Duration baseline

Two horizons: pre-construction runway and on-site execution.

### Pre-construction runway (T-3w → T-0)

A single-room interior remodel does **not** carry the addition-style runway. Specifically, the following addition-only items do not apply (source: scope is interior bath only; Will, transcript lines 217–246):

- **TDEC septic** — N/A (no excavation, no septic work).
- **LVL / windows / trusses lead-time** — N/A.
- **Heat-pump / electrical disconnect relocation** — N/A.

What does apply:

| Item | Earliest call | Driver |
|---|---|---|
| Finalize selections | T-3w | Will's "two or three weeks before the project starts" floor for remodel finish materials (transcript line 220). |
| Order finish materials (tile, vanity, fixtures, valves) | T-2w to T-3w | "I want 'em a week or two prior to when we need them" — and on a bath remodel, install is Day 1 of finish (transcript lines 232–234). |
| Building permit (interior alteration) | T-1w | Will: walks in / walks out same day ~90% of the time (transcript lines 132–136). 1-week buffer for the 10% case. |
| Dumpster delivery | T-1d | Day-before-demo rule (transcript line 272). |

**Pre-con runway minimum: 3 weeks**, driven by selections.

### On-site execution

Working-day counts (weekends + federal holidays excluded). Numbers below cite their source; anything without a source is omitted.

| # | Phase | Days | Source |
|---|---|---|---|
| 1 | Demo (gut to studs) | 1–2 | Not in any cited source; carried as range, needs PM confirmation. |
| 2 | Plumbing rough-in (master bath) | **4** | `plumbing_rough_min_duration.md` hard floor: ≥4d × 2 crew. |
| 3 | Electrical rough-in | 1–2 | Will: "100 amp subpanel… one person, one day"; bath electrical at the small end of that (transcript line 474). Carried as range, needs scope clarification on whether new circuits or fixture swap. |
| 4 | HVAC rough-in | 0–1 | Scope is silent on HVAC. If existing vent stays, zero. If mini-split tie-in, half-day per Will (transcript lines 476, 482, 494). |
| 5 | MEP inspections (single visit) | 1 | One inspector covers all three (transcript lines 506–513). |
| 6 | Framing inspection | 1 | Required after MEP rough per code reality, even on a remodel (transcript lines 398–404). |
| 7 | Insulation (if walls opened) | 1 | Not in any cited source; one-day standard for one room. |
| 8 | Drywall + shower waterproofing | 3–5 | Not in any cited source. Range reflects waterproofing + level-3 finish + tie-in cracks Will warns will appear Year 1 (`wills_voice.md`, "Drywall warranty"). |
| 9 | Tile shower install | 4–6 | Not in any cited source. Custom tile is the long pole of any master-bath remodel; carried as range pending tile spec (subway/mosaic, niche, bench). |
| 10 | Vanity, fixture, trim, paint | 3–5 | Not in any cited source. |
| 11 | Punch list + final inspection | 1–2 | MEP punch buffer pattern from transcript lines 530–532 applied at job end. |

**On-site working days: 20–30** (sum of ranges above).

Calendar conversion (5-day weeks, federal holidays excluded): **≈4–6 weeks** front door to handoff.

**Scope-signed to closeout: ≈7–9 weeks** (3-week pre-con + 4–6 weeks on-site).

Customer's stated **~6 weeks** target appears to refer to on-site only, not signed-to-closeout. That fits the on-site high end if materials and selections are already locked at signature. **It does not fit if selections still need to be made** — the 3-week selection runway would push handoff to week 9.

## Critical-path gates

Items where one day of slip = one day of project slip:

1. **Selections locked** — gates material orders, which gate everything tile-related. The dominant pre-con risk.
2. **Plumbing rough completion** — 4-day company-rule floor; gates the MEP inspection.
3. **MEP inspection pass** — gates drywall (per Will, framing inspection can't precede MEP rough; same logic on a remodel).
4. **Shower waterproofing cured** — gates tile, which is the longest finish task.
5. **Tile shower install** — typically the on-site long pole on any master-bath gut.

## Risks

1. **Input conflict (top of doc).** Manifest vs. scope mismatch must be resolved before anything else is actionable.
2. **Scope thinness.** "New tile shower, vanity, fixtures" leaves open: shower dimensions, tile spec (niche/bench/mosaic), vanity width and top material, plumbing reroutes, W/D relocation, electrical scope (circuit count, GFCI, exhaust upgrade), HVAC scope, flooring scope outside the shower, paint and trim scope. Each open question is a CO vector.
3. **No cost baseline.** Without a PM breakdown or actuals, the customer-vs-direct gap (the question this baseline is supposed to answer) cannot be computed. Risk: estimate gets locked at a number derived from gut feel rather than data.
4. **Drywall tie-in cracks Year 1** at the demo perimeter. Per Will (`wills_voice.md`), this is expected, not a defect. Budget the warranty visit, don't expense it as a callback.
5. **Customer 6-week expectation.** If it means "on-site," achievable at the high end. If it means "signed-to-keys," it conflicts with the 3-week selection runway. Confirm before signature.

## Open questions

- **Is this a master bath gut (per scope.md) or a garage addition (per manifest.json, slug, and tags)?** Blocks every other answer.
- **Is selections runway already underway, or does the 3-week clock start at signature?** Decides whether 6-week customer target is realistic.
- **Are walls coming open for plumbing reroutes, or is plumbing staying in existing locations?** Drives whether the 4-day plumbing-rough floor applies (it applies to anything with a master bath per the company rule, but reroute scope changes labor split).
- **HVAC scope.** Existing vent retained, or new mini-split head? Half-day delta either way.
- **Electrical scope.** New circuits / panel work / exhaust upgrade, or fixture swap only?
- **Tile spec.** Shower dimensions, substrate (Schluter or hot-mop), niche/bench, mosaic floor or sheet? This is the on-site long pole and the spec is silent.
- **PM-supplied breakdown.** Required to produce a real direct-cost subtotal. Without it this baseline has no cost line at all.

## Confidence

- Direct cost subtotal: **none** — no source available.
- Customer total: **none** — not in scope.
- Pre-con runway: **medium** — 3-week floor sourced to Will's transcript; assumes selections runway starts at signature.
- On-site duration: **low–medium** — plumbing floor is hard-sourced (4d); other phase ranges are reasonable but only the plumbing line traces to a TCR-specific source. The rest will tighten the moment a PM breakdown or one finished-bath actual exists.
- Critical-path gates: **medium** — gate logic is sound; absolute durations are not.

This is a thin-input first cut. The next planning artifact for this job should be either (a) a request back to the PM for breakdown + scope clarification, or (b) regeneration against a real addition scope if the manifest is the truth and `scope.md` is a placeholder.
