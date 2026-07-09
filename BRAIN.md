# BRAIN — canonical spec

Last revised: 2026-07-08. Supersedes every prior draft.

This is the north-star architecture doc for the Friday brain. It is a
**living spec, not a conversation**. Prior brainstorm transcripts are
archived under `_archive/`. When any doc in the trunk conflicts with
this file, this file wins.

**Companion docs:**
- [`ROADMAP.md`](./ROADMAP.md) — the full 6-series master plan
  (each series → phases → sweeps in deep detail). This is the
  living operational plan; edit here when plans change.
- [`OBSERVABILITY.md`](./OBSERVABILITY.md) — UI design principles +
  flat index of every surface across the plan.
- [`SPRINT_TRACKER.md`](./SPRINT_TRACKER.md) — where we are right now,
  which sweep is next, decisions log.

---

## The one-line thesis

**A generic, transparent, self-correcting brain that maintains coherent
understanding across data, intelligence, and derived work — swappable
across business domains, observable at every layer, and safe to evolve
without silent regressions.**

We are NOT building a construction-industry tool. We are building the
brain infrastructure. Construction (Tri Cities Remodeling) is the first
tenant we prove it on. Every primitive must survive the swap to any
other domain — HR onboarding, legal case management, ops incident
review, customer support — without code changes.

---

## The 3-layer taxonomy

Every piece of information in the brain fits in exactly one of three
layers.

### Layer 1 — Data (authoritative facts)
Facts someone (a human, an external system) decided or observed.
**Not regeneratable.** If we lose it, we cannot recreate it.

Examples:
- Raw uploads: scope PDFs, drawings, breakdown CSVs → S3 (source),
  referenced from DB, mirrored to trunk as `.ref.json` + extracted
  `.txt`.
- Q&A pairs: the PM's actual answers to interview questions → DB
  (source of truth for query + integrity), mirrored to trunk as
  `interview/round-N.md` for AI consumption.
- Manifest fields: scheduled_start_date, customer identity, valuation
  → DB (source), mirrored to trunk `manifest.json`.

### Layer 2 — Intelligence (derived understanding)
The brain's accumulated model of the domain. Grows over time. Needs
vetting before entering the shared understanding. Lives only in the
trunk. Git-versioned markdown is its canonical form.

Three categories:
- **Rules** — human-authored policy. Prescriptive. "MUST" / "MUST
  NOT". Slow-changing. Never auto-merges.
- **Beliefs** — AI-inferred defaults. Descriptive with confidence.
  Auto-merges when high-confidence and non-contradicting; queued for
  PM review otherwise.
- **Patterns** — aggregate observations across many work units.
  "This customer has never signed a change order." Derived by a
  pattern-extraction generator that walks history. Same review gate
  as beliefs.

### Layer 3 — Artifacts (regeneratable outputs)
Expensive to make but deterministic given data + intelligence +
generator prompt. Lives only in the trunk. Never in DB — they'd
bloat rows, hurt diff/history, and the agent needs to Read them as
context anyway.

Examples:
- Extractions: PDF → text.
- Generations: task_graph, schedule, PEP, risks, daily_schedule.
- Snapshots: intel_rebuild outputs.

### The bucket test
- Can it be regenerated deterministically from other layers? → **Artifact**
- Was it decided by a human or provided externally as fact? → **Data**
- Did the AI derive it from data + prior intelligence? → **Intelligence**

---

## The generic scoping model

Each domain declares its own ordered scope dimensions. The
intelligence scope engine matches rules/beliefs/patterns against a
work unit's context by walking those dimensions from broad to
specific. Higher specificity wins on conflict; explicit priority
overrides.

**Generic 4-level pattern** (a domain may use fewer or more):

| Level | Generic name | TCR construction mapping | Example other domains |
|---|---|---|---|
| 0 | **Tenant** | Company (`tcr`) | Firm / Org |
| 1 | **Category** | Job type (`addition`) | Role, case type, incident class |
| 2 | **Context** | AppProject / site | Employee, matter, ticket |
| 3 | **Work unit** | Job (the specific work item) | Onboarding step, motion, resolution attempt |

Trunk folder shape (generic):

```
<tenant>/                             # tenant scope
  _tenant/                            # tenant-scoped intel + knowledge
    rules/  beliefs/  patterns/
    knowledge/
    _catalog/generators.json          # available generators
  _schemas/                           # frontmatter + JSON contracts
  categories/<cat>/                   # category scope
    rules/  beliefs/  patterns/
  _contexts/<ctx-id>/                 # context scope
    rules/  beliefs/  patterns/
    work_units/<wu-id>/               # work unit — the live work surface
      manifest.json                   # data (mirrored from DB)
      inputs/                         # data mirror + hydrated .txt
      interview/round-N.md            # data (Q&A pairs, mirrored)
      intelligence/                   # per-WU derived understanding
        extracted/                    # artifact (from inputs)
        facts.md  confirmed.md  questions.md  applicable_rules.json
        manifest.json                 # intel index + status
      generations/                    # artifact
      rules/  beliefs/  patterns/     # WU-scoped intel (rare)
      events.jsonl                    # audit log
```

The TCR trunk uses **construction-specific labels** (`_company`,
`job_types`, `_projects`, `jobs`) as aliases over this shape. A future
domain declares its own labels in its domain manifest. The engine
reads the labels; nothing else in the code hardcodes them.

---

## Storage rules

One-line rule: **anything the agent needs to read must exist in the
trunk. Anything humans need to query must exist in DB. Blobs go to
S3. Nothing lives in two "source" locations — always one source,
everywhere else is a mirror.**

| Layer | Type | DB | S3 | Trunk |
|---|---|---|---|---|
| Data | Row facts (jobs, contexts, PM answers, manifest) | ✅ source | | ✅ mirror |
| Data | Raw blobs (PDFs, images) | ref only | ✅ source | ✅ text mirror |
| Intelligence | Rules / beliefs / patterns | | | ✅ source |
| Artifacts | Extractions, generations, snapshots | | | ✅ source |

The **DB→trunk mirror** is the load-bearing beam of the whole
architecture. Every time a DB field the AI needs to see changes, the
trunk must reflect it. Silent drift here is the number-one source of
"why is the agent wrong?" bugs. Every one of those bugs so far
traced to a field that didn't propagate. Make the mirror robust and
observable; monitor its health as a first-class concern.

---

## Intelligence lifecycle

Rules are eternal until deprecated. Beliefs and patterns rot.

**Every belief and pattern carries:**
- `id`, `scope`, `content`, `confidence` (0–1)
- `authored_at`, `authored_by` (agent or human user_id)
- `last_verified_at`
- `verified_by_run_ids[]` (which runs cited AND confirmed it)
- `superseded_by` (chain when a newer entry replaces this one)
- `status`: `proposed | active | deprecated`
- `stale: bool` (auto-flagged when `last_verified_at + decay_window`
  passes without recitation)

**Proposal review flow:**
- Every AI-derived intelligence enters the review queue.
- Beliefs auto-approve if `confidence > 0.85` AND no contradicting
  rule OR contradicting active belief exists. Otherwise queued.
- Rules NEVER auto-approve. Human vetting required — rules affect
  every future run.
- Patterns NEVER auto-approve for the same reason.
- Beliefs that contradict a prior PM-confirmed answer → queued.

**Cross-reference index:** maintain a reverse index — "which runs
cited this rule/belief/pattern?" — refreshed post-run. Enables the
"where does this fire?" query and the staleness signal.

---

## What auto-refreshes vs. what needs PM vetting

**Auto (no review):**
- Deterministic transformations (PDF → text, sha256 compute, date
  normalization)
- Fact extraction from source docs when the source is explicit
- Content-hash-driven skips of unchanged stages

**Vet (PM sign-off required):**
- New rule proposals
- New pattern proposals
- Beliefs that contradict existing beliefs or prior PM answers
- Cross-context generalizations
- Any change to a belief the PM previously confirmed

The pattern: **agent PROPOSES, PM DISPOSES**.

---

## Cost + hygiene

Four levers, in order of ROI:
1. **Content-hash inputs, skip unchanged stages.** Every generator
   must be diff-aware.
2. **Prompt caching.** Same rendered context across parallel
   sub-agents = huge cache hit. Preserve this by keeping context
   stable across generators of the same work unit where possible.
3. **Cheap classifier gate.** Before firing an expensive generator,
   a small Sonnet call (~$0.001, ~2K tokens) decides: "did anything
   material change since the last successful run?" If no, skip. Cuts
   50–70% of pointless re-runs.
4. **Debounce + coalesce.** Multiple DB writes within a window → one
   downstream refresh.

**Lazy invalidation:** don't refresh intelligence on every DB change.
Mark the work unit's intelligence layer `dirty` when data changes;
refresh lazily on the next downstream consumer's invocation. Saves a
huge amount of pointless work.

---

## Observability commitments

Every series ships with its own UI per the 6-series plan — see
[`OBSERVABILITY.md`](./OBSERVABILITY.md) for the full index. The
four load-bearing surfaces the brain does NOT run without:

1. **Data Trunk Browser** — files as they are, with rendered-
   context preview ("here's what the agent literally sees").
   Delivered in Series 1 · Phase Echo.
2. **Sync Health Monitor** — per-field DB↔trunk drift monitor.
   Delivered in Series 1 · Phase Foxtrot.
3. **Intelligence Explorer** — every rule, belief, pattern with
   provenance, citations, staleness, supersession chains.
   Delivered in Series 2 · Phase Golf.
4. **Proposals Queue** — unified inbox for rule + belief +
   pattern + generation proposals with diff + evidence.
   Delivered in Series 2 · Phase Hotel.

Reasoning: the failure mode of self-improving systems is silent
regression. Without observability we cannot debug, cannot evolve,
cannot trust the brain. Building infrastructure without observability
is building a black box.

---

## Non-goals + traps

- **Not** a construction tool. Any code that hardcodes construction
  concepts fails the domain-shift test.
- **Not** a single-agent workflow orchestrator. Jake Van Clief's ICM
  is complementary (per-workflow orchestration) but not the whole
  architecture. Individual generators can internally use ICM-style
  stages; the brain-level abstraction is Data + Intelligence + Artifacts.
- **Not** a bag of prompts. Prompts live in generator catalogs;
  intelligence lives in the trunk. Don't mix them.
- **Don't** auto-promote beliefs to rules without human vetting.
- **Don't** conflate proposals with commits. Even auto-approved
  intelligence flows through the proposal gate so the audit log
  stays clean.
- **Don't** put intelligence content in DB. Trunk is its canonical
  form. DB holds at most citation indexes and status flags.
- **Don't** put generations in DB. They belong in the trunk.
- **Don't** ship without the Sync Health Dashboard.

---

## Terminology hygiene

We hold construction-specific labels (Company, Job Type, Project,
Job) as ALIASES over the generic model (Tenant, Category, Context,
Work Unit). Any new code, any new UI, any new agent must render from
the generic primitives with domain-provided labels applied on top.
When ambiguity arises, prefer the generic term.

---

## Doc precedence

When docs conflict:
1. This file (`friday/BRAIN.md`) wins.
2. Then `friday/ROADMAP.md`.
3. Then `_schemas/*.md`.
4. Then trunk READMEs.
5. Everything else is context, not contract.

Update this file when the architecture evolves. Do not append —
rewrite the affected section. This is a canonical spec, not a
transcript.
