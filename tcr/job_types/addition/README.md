# `job_types/addition/` — addition-specific knowledge

Rules + beliefs that apply to every addition job at TCR. Covers room
additions, floor additions, and similar new-construction jobs that
tie into an existing structure.

## Subfolders

- **`rules/`** — addition-specific prescriptive rules. Same file shape
  as `_company/rules/` (see that README), with `scope: job_type` in
  frontmatter.
- **`beliefs/`** — addition-specific descriptive beliefs. Same shape as
  `_company/beliefs/`, with `scope: job_type`.
- **`reference_jobs/`** — hand-curated pointers to past addition jobs
  that are useful examples. One markdown file per pointer or a single
  `index.md` listing them. Pointers are relative paths under
  `_projects/`, not copies.

## What lives here vs. `_company/`

- Lives here: anything that only makes sense for additions. TDEC septic
  rules, LVL handling, roof tie-in concealed-condition buffer, MEPs
  gated on underlayment + windows.
- Lives in `_company/`: anything that's true regardless of job type.
  Will's walkthrough at closeout, Will's preferred subcontractors,
  general drywall consolidation.

When in doubt: if a different job type would do it differently → here.
If a different job type would do it the same way → `_company/`.
