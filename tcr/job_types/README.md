# `job_types/` — middle-tier knowledge

One subfolder per job type TCR runs. Each holds rules + beliefs that
apply to **every job of that type** but don't belong at the company
level (because other job types do things differently).

## Current job types

- `addition/` — room or floor additions
- `bathroom_remodel/` — bathroom-only interior remodels
- `kitchen_remodel/` — kitchen-only interior remodels

We add more as they come up. To add: create the folder with `rules/`,
`beliefs/`, `reference_jobs/` subfolders, drop a job-type README, and
commit.

## How `job_types/<type>/` is structured

Same shape as `_company/` for the prescriptive vs. descriptive split,
plus `reference_jobs/`:

- `rules/` — type-specific rules (e.g., "additions on septic MUST
  schedule TDEC permit 6 weeks ahead").
- `beliefs/` — type-specific beliefs (e.g., "addition LVL beams default
  to 14-day procurement lead").
- `reference_jobs/` — pointers (NOT copies) to past jobs of this type
  that are particularly illustrative. Hand-curated. Format is a markdown
  list of paths under `_projects/`. Used by the agent as "show me a
  good example of this type."

## Authority hierarchy reminder

`_company/` < `job_types/<type>/` < `_projects/<id>/jobs/<jid>/`

More specific layer wins. The agent walks all three when generating.
