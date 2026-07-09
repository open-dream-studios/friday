# Rule file schema

A rule is a `.md` file with YAML frontmatter + a markdown body. One
claim per file. Filename = `<id>.md` where `<id>` matches the
frontmatter `id` field exactly.

## Frontmatter contract

```yaml
id: string                # MUST equal filename without `.md`. lowercase_with_underscores.
title: string             # human-readable headline. one sentence.
scope: company | job_type | job
                          # which layer this rule lives at. matches its folder location.
job_type: string | null   # set when scope=job_type (e.g. "addition"). null otherwise.
job_id: string | null     # set when scope=job (the JOB-... id). null otherwise.
severity: hard | soft     # hard = validator rejects violations. soft = warning only.
authored_by: string       # human user_id, or "agent" if agent-proposed.
authored_at: ISO8601      # when this rule was written.
supersedes: string | null # id of an older rule this replaces. null = original.
tags: [string]            # free-form taxonomy. used for grep + agent filtering.
```

## Body

The body is the prose the agent reads. Conventions:

- **Lead** with the directive in one or two sentences.
- **Rationale** paragraph follows ("why this is true / where it came from").
- Optional **examples** or **counter-examples** if the boundary is fuzzy.

## Hard rules about rule files

- One claim per file. If "and also..." creeps in, split.
- `id` = filename. Always. Easier to grep, easier to reason about.
- `scope` MUST match where the file lives in the tree. Lifting/moving a
  rule means updating `scope` in lockstep.
- `supersedes` is the supersession chain. Old rules are never deleted —
  they get a `superseded_by` pointer added (frontmatter field added when
  superseded; not declared in the originating frontmatter).
- `severity: hard` by default unless the rule explicitly says "warn but
  allow."

See `_company/rules/_examples/` for a canonical example.
