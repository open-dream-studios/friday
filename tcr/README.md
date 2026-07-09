# Tri Cities Remodeling — brain trunk

Last revised: 2026-07-08.

TCR is the first **tenant** of the Friday brain. Every tenant lives
at `friday/<tenant>/`. This one is `friday/tcr/`.

**Read [`friday/BRAIN.md`](../BRAIN.md) first.** It describes the
architecture — the 3-layer taxonomy (Data / Intelligence /
Artifacts), the generic scoping model, and what makes a piece of
code domain-portable vs. domain-hardcoded. This README covers how
*this tenant's* trunk is organized.

## Domain aliases

TCR is a construction domain. The generic scope dimensions have
tenant-specific labels:

| Generic | TCR label | Folder |
|---|---|---|
| Tenant | Company | `_company/` |
| Category | Job type | `job_types/<type>/` |
| Context | AppProject / site | `_projects/<APPPROJ>/` |
| Work Unit | Job | `_projects/<APPPROJ>/jobs/<JOB>/` |

Sprint 7 will migrate to fully-generic folder names (`_tenant`,
`categories`, `_contexts`, `work_units`). For now the
construction-specific labels are aliases over the same shape.

## Layout

```
_company/         ← tenant-scoped knowledge (rules, beliefs, patterns, knowledge)
job_types/<type>/ ← category-scoped (per job type)
_projects/<id>/   ← context-scoped. Inside, jobs/<job_id>/ = the work unit
_schemas/         ← frontmatter + JSON contracts (frozen — dev-only edits)
_archive/         ← superseded contexts and work units (never delete)
manifest.json     ← tenant manifest (display name, storage config)
```

## The 3-layer taxonomy in this trunk

Every file in this trunk fits in exactly one layer. See
[`friday/BRAIN.md`](../BRAIN.md#the-3-layer-taxonomy) for full
definitions.

**Layer 1 — Data (authoritative facts, not regeneratable):**
- `_projects/<id>/jobs/<id>/manifest.json` (mirrored from DB)
- `_projects/<id>/jobs/<id>/inputs/` (raw + hydrated text; blobs on S3)
- `_projects/<id>/jobs/<id>/interview/round-N.md` (PM Q&A pairs)
- `_company/knowledge/` (raw playbooks, transcripts)

**Layer 2 — Intelligence (derived understanding, git-versioned):**
- `rules/` — human-authored policy (at any scope)
- `beliefs/` — AI-inferred defaults with confidence (at any scope)
- `patterns/` — aggregate observations across many work units (at
  any scope) *(new category, populated Sprint 4)*
- `<work_unit>/intelligence/facts.md`, `confirmed.md`,
  `questions.md`, `applicable_rules.json` (per-work-unit derived
  intelligence)

**Layer 3 — Artifacts (regeneratable outputs):**
- `<work_unit>/intelligence/extracted/*.md` (PDF/CSV → distilled
  text)
- `<work_unit>/generations/*` (task_graph, schedule, PEP, risks,
  daily_schedule)
- `<work_unit>/intelligence/manifest.json` (intel index)

## Authority hierarchy (scope precedence)

`_company/` < `job_types/<type>/` < `_projects/<APPPROJ>/` <
`_projects/<APPPROJ>/jobs/<JOB>/`

More-specific layer wins on conflict. `applicable_rules.json` in
each work-unit's `intelligence/` folder encodes the resolved
citation for that work unit.

Higher priority (numeric): tenant=100, category=200, context=300,
work_unit=400. Sprint 1 will replace these ranks with a
domain-declared dimension chain — behavior unchanged, plumbing
generalized.

## File conventions

See [`CONVENTIONS.md`](./CONVENTIONS.md) for slugs, git branch
names, commit tags, and extension usage.

## Who edits what

| Folder           | Primary author             | Notes                                                     |
| ---------------- | -------------------------- | --------------------------------------------------------- |
| `_company/`      | Humans + agent proposals   | Rules NEVER auto-merge; beliefs auto-merge only when confidence ≥ 0.85 AND no contradiction; patterns NEVER auto-merge. |
| `job_types/`     | Humans + agent proposals   | Same gates as `_company/`.                                |
| `_projects/`     | Humans add inputs; agent writes artifacts + WU-scoped intelligence. | Per-work-unit folder is the live surface. |
| `_schemas/`      | Developers only            | Schema changes are breaking changes.                      |
| `_archive/`      | Never edit                 | Superseded contexts and work units. Preserve for audit.   |

## Intelligence layer per work unit

Every work unit under `_projects/<APPPROJ>/jobs/<JOB>/` follows
this shape:

```
INPUTS (Data)  ──→  INTELLIGENCE (Layer 2)  ──→  GENERATIONS (Artifacts)
   ↑                        ↑
 mirrored from DB    PM interview rounds
```

- **`inputs/`** — data mirror. Raw scope, breakdown, plans + their
  extracted `.txt` siblings. Immutable per upload.
- **`interview/round-N.md`** — data. PM's answers to agent
  questions. Append-only.
- **`intelligence/`** — small, structured, pre-distilled "what we
  know." Generators read this instead of raw inputs + all rules.
  Layout:

```
<work_unit>/intelligence/
├── manifest.json             ← sha index + interview_status + round
├── extracted/                ← per-input distillations (Artifact — regenerable)
│   ├── scope.md
│   ├── breakdown.md
│   └── plans.md
├── applicable_rules.json     ← scope-matched rules/beliefs/patterns index
├── facts.md                  ← synthesized "what we know" + citations
├── confirmed.md              ← PM-confirmed facts w/ round provenance
└── questions.md              ← open questions for next PM round
```

- **`generations/`** — planning artifacts (task_graph, schedule,
  baseline, risks, daily_schedule, pep). Fast to produce because
  they read `intelligence/*` (~10-20K tokens) not raw inputs +
  rules (~200K).

## Active generators

Read `_company/_catalog/generators.json` for the canonical catalog
(currently named `generation_kinds.json` — rename lands with the
Sprint 7 generic migration).

Current generators active on this tenant:

| Generator                     | Layer produced   | Notes                                          |
|-------------------------------|------------------|------------------------------------------------|
| `intelligence_rebuild_v2`     | Intelligence     | Map-reduce (4 stage-A + 1 stage-B synthesis).  |
| `intelligence_interview_v2`   | Intelligence     | Single-shot merge of PM answers.               |
| `task_graph_v2`               | Artifact         | Uses server-side .md renderer post-run.        |
| `baseline_v2`                 | Artifact         | Optional advisory.                             |
| `risks_v2`                    | Artifact         | Optional advisory.                             |
| `daily_schedule_v2`           | Artifact         | Optional advisory.                             |
| `pep_v2`                      | Artifact         | Customer-facing; requires PM review before merge. |

Deprecated `v1` generators remain in the catalog with
`deprecated: true` for in-flight legacy work units. New work units
route through v2 exclusively.

## File-handling contract

S3 is canonical for binaries. Trunk is a cache + extracted-text
mirror. Per file:

- `<filename>.ref.json` — pointer (S3 url + content hash + DB row
  id). Always committed.
- `<filename>.txt` — extracted text. Always committed when
  extractable.
- `<filename>` (binary) — fetched on demand, cached outside git,
  never committed.

## What does NOT belong in this trunk

- Secrets, tokens, API keys (use server env)
- Anything > 5 MB raw — store on S3, reference via `.ref.json`
- Anything regeneratable that we don't currently need — recompute
  when needed
- Anything DB-authoritative without a mirror gate — always flow
  through the write-through save

## Freshness + triggers

```
INPUT CHANGED (PM uploads new doc, edits scope in CMS)
  → autoRefreshBrainJobFromDbUpdate mirrors inputs + manifest fields
  → intelligence/* marked dirty (Sprint 4 formalization)
  → next generator invocation refreshes intelligence lazily

PM CLICKS A GENERATOR (or saves an interview round)
  → single brain_job_run
  → proposal branch → auto-approve (most kinds) or PM review (pep_v2)
  → artifact lands; UI invalidates relevant queries
```

Pipeline UI shows `Intel synced · Xm ago` pulled live from
`intelligence/manifest.json.last_run_at`.
