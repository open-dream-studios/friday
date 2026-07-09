# `_company/beliefs/` — global descriptive beliefs

Beliefs are **descriptive with confidence**. They say what the brain
currently understands to be true, sourced from something specific. The
agent writes here freely (on proposal branches) and auto-merges when
there's no conflict with an existing belief.

## File shape

One belief per file. Filename = lowercase-with-underscores slug.

```markdown
---
id: stick_frame_default_for_small_additions
scope: company
confidence: 0.92          # 0.0–1.0
supports:                 # files / inputs this belief was derived from
  - _company/knowledge/wills_playbook.md#truss-vs-rafter
  - _projects/308-evergreen-addition_APPPROJ-01KKR.../jobs/.../events.jsonl
source_signature: sha256:abc123…   # hash of supporting inputs at write-time
recorded_at: 2026-06-22T14:00:00Z
recorded_by: agent        # "agent" or human user_id
supersedes: null
stale: false              # flipped true when a `supports` file changes
tags: [framing, roof, additions]
---

For additions under ~800 sqft with a roof span < 24 ft, TCR defaults to
stick-framing the roof rather than ordering trusses. Lumber arrives
just-in-time with the framing crew; no procurement.trusses task needed.

Override the default only when scope explicitly says "trusses" OR when
PM Interview confirms.
```

## Rules of the road

- Every belief has `supports[]` — what it was derived from. Without
  provenance the belief is unverifiable; the validator will reject it.
- `confidence` is the agent's read on how settled this is. Humans
  authoring a belief manually default to 1.0.
- `source_signature` is a hash of the supports' content at write-time.
  When the hash drifts, staleness detection (P10) flips `stale: true`
  and a re-derivation is queued.
- `supersedes` chains the history. Never delete a belief; supersede it.
- One claim per file. Same as rules.

## When does a belief become a rule?

When it gets stable enough that we want to enforce it. A human (not the
agent) promotes it: write a rule file with the same claim, mark the
belief `supersedes` the rule, archive. Rare event.

## What does NOT belong in `beliefs/`

- Things with confidence = 1.0 by authoritative human assertion →
  consider whether it's a **rule** instead.
- Raw business docs → **knowledge**.
- Anything without `supports[]` — every belief MUST trace to a source.
