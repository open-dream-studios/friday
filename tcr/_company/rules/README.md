# `_company/rules/` — global prescriptive rules

Rules are **prescriptive**: they say what MUST or MUST NOT happen.
They're authored deliberately by humans. The agent can propose a new
rule via the review-gate flow, but rules never auto-merge.

## File shape

One rule per file. Filename = lowercase-with-underscores slug, ending
`.md`. Frontmatter carries machine-readable metadata; body is the prose
the agent reads.

```markdown
---
id: plumbing_rough_min_duration
title: Master bath plumbing rough minimum duration
scope: company
severity: hard            # hard | soft
authored_by: will         # human user_id, or "agent" if proposed
authored_at: 2026-06-22T14:00:00Z
supersedes: null          # id of an older rule this replaces, or null
tags: [plumbing, master_bath, duration]
---

Plumbing rough-in for any job that includes a master bath MUST be
modeled as ≥ 4 working days with a crew of 2.

Rationale: Will's nominal from transcript line 1942. Three days only
works for single half-baths.
```

## Rules of the road

- One claim per rule file. If you find yourself writing "and also...", split it.
- `id` MUST match the filename slug (without `.md`). Easier to grep.
- `scope: company` here is redundant but explicit on purpose — same field
  reads `job_type` or `job` in the other layers, so we can lift/move
  files without re-frontmatter-ing.
- `severity: hard` = the validator rejects generations that violate it.
  `severity: soft` = warning only. Default `hard` unless you mean otherwise.
- `supersedes` is the supersession chain. Old rules don't get deleted,
  they get superseded so history stays intact.

## What does NOT belong in `rules/`

- Anything with confidence < 1.0 → that's a **belief**, put it next door.
- Free-form business notes → that's **knowledge**.
- Numbers harvested from past jobs → that's **actuals**.
