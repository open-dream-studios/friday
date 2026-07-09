---
generation_kind: intel_questions_v1
interview_status: needs_more
round: 1
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWBMVXDZH53D4RDD8GTTT3ZC/jobs/308-evergreen-street-addition_JOB-01KWBMWTSWFJ4DHZ5HJ47E8NMZ/generations/_pre/scope.md
  - _projects/308-evergreen-street_APPPROJ-01KWBMVXDZH53D4RDD8GTTT3ZC/jobs/308-evergreen-street-addition_JOB-01KWBMWTSWFJ4DHZ5HJ47E8NMZ/generations/_pre/breakdown.md
  - _projects/308-evergreen-street_APPPROJ-01KWBMVXDZH53D4RDD8GTTT3ZC/jobs/308-evergreen-street-addition_JOB-01KWBMWTSWFJ4DHZ5HJ47E8NMZ/generations/_pre/plans.md
  - _projects/308-evergreen-street_APPPROJ-01KWBMVXDZH53D4RDD8GTTT3ZC/jobs/308-evergreen-street-addition_JOB-01KWBMWTSWFJ4DHZ5HJ47E8NMZ/manifest.json
last_verified_at: "2026-06-30T06:57:23.924Z"
---

## What we know

- **Stage A incomplete.** The required structured rules index
  (`generations/_pre/rules_index.json`, written by `intel_rules_index_v1`)
  is missing from `_pre/`. Only three of the four required Stage A
  summaries are present (`scope.md`, `breakdown.md`, `plans.md`). Without
  the 4-layer rules index, the question agent cannot resolve rule
  applicability or precedence and must not proceed to a full interview
  draft.

## What we're uncertain about

### q.gather_failed

**Question:** Stage A sub-agents did not all complete — re-run Generate plan.
**Category:** scope
**Hint:** The structured rules index (`_pre/rules_index.json`) is missing; re-running the plan regenerates all Stage A intel summaries so the interview can be authored.
**Why:** Without the rules index the question agent cannot resolve the 4-layer rule hierarchy that governs which questions matter; re-running Stage A unblocks the full interview.
