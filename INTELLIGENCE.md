# INTELLIGENCE — the layer's contract

Companion to [`BRAIN.md`](./BRAIN.md), [`ARCHITECTURE.md`](./ARCHITECTURE.md),
and [`DATA_MODEL.md`](./DATA_MODEL.md). This file describes HOW the
intelligence layer works: what it does, when it runs, what it costs,
what it outputs. The intelligence layer sits on top of the data trunk
+ change-log substrate. Do not read this doc first — read the others
first.

---

## The mental model

Intelligence is a **working memory that gets sharper the more the
system is used**. It's not a knowledge base. It's a Socratic loop:
partial understanding → identify gaps → ask or infer → understanding
sharpens → loop.

**Three artifacts, one per entity node**, alongside `data.json` and
`CLAUDE.md`:
- **`facts.json`** — atomic ground-truth knowledge, each with a
  citation and confidence. Map of id → fact.
- **`beliefs.json`** — synthesized understandings derived from
  facts. Each with a falsification test. Map of id → belief.
- **`questions.jsonl`** — open questions, append-only. What we
  don't know yet but should. One line per question.

Schemas: see
[`packages/blocks/brain/shared/{fact,belief,question}.schema.ts`](../dev-cms/packages/blocks/brain/shared/).

---

## Two loops

### Warm loop
Fires from change-log activity. Keeps intelligence current in the
background. Cheap. Sequential. Runs through Claude Code CLI on the
subscription.

Trigger chain:
1. Change-log line lands (from some DB write).
2. Debounce 30s per project. Coalesce bursts.
3. On idle: **classifier gate** — is this material? A tight Sonnet
   call reads the diff since last run + current beliefs. One shot.
4. If material → fire the warm-loop pipeline per affected entity.
5. If not → mark entity clean, no cost.

Warm loop pipeline (per entity):
1. **Extract** — pull new facts from the change-log delta + any
   documents touched. Cite sources. Append to `facts.json`.
2. **Reconcile** — for each new fact, compare against active beliefs.
   Confirms → bump confidence + `last_verified_at`. Extends → append
   detail. Contradicts → open a question OR (if evidence overwhelming)
   supersede the belief.
3. **Question generation** — identify gaps in current understanding.
   Rank by materiality × blast_radius. Append to `questions.jsonl`.
4. **Self-answer step** — before surfacing questions to human, try
   to answer each from the data trunk. If confident → answer becomes
   a fact with `system_answer` citation.
5. **Rank** — sort inbox by materiality × blast_radius × freshness ×
   cost. Top N surface to human.

### Hot loop
Fires when a workflow explicitly requests fresh intelligence.
Blocks the workflow until ready. Bounded by a hard timeout.

Public API:
```ts
await ensureIntelligenceFresh(scope, deadline_ms);
```
- Wakes the pipeline for the scope.
- Runs the same steps as warm but with priority.
- If deadline expires → workflow proceeds on warm state + a
  `stale: true` flag on the result.

First consumer: task graph generation for a specific job. Others
follow.

---

## Model tiering — Claude only

- **Sonnet 4.6** — the workhorse. Classifier, extract, reconcile,
  question generation, ranking, self-answer.
- **Opus 4.7** — reserved for high-stakes reasoning: cross-entity
  synthesis, contradiction resolution when two active beliefs
  disagree with a new fact, question generation before major
  workflows.
- **No Haiku.** Subscription pricing = no cost advantage; Haiku's
  accuracy risk isn't worth the speed win at our cadence.

---

## Dispatch — CLI, not SDK

**Default: Claude Code CLI as a subprocess from server_a1.** Runs
against Boss's subscription. Prompt caching kicks in per-session.
Cost: subscription slots, not per-token.

SDK is fallback only when:
- We need genuine parallelism a single CLI session can't provide, or
- CLI hits subscription rate limits.

Rate-limit ourselves before Anthropic does. Track cumulative token
usage per day. At 70% cap, degrade gracefully. At 90%, only fire
the classifier gate. Never blow the cap mid-workday.

---

## The Q&A channel

Questions get surfaced in a per-entity inbox UI. Each question
carries `materiality`, `why_it_matters`, and (optional) `ui_prompt`.

Two answer paths:
1. **System self-answers** from the data trunk before surfacing.
   Uses Sonnet CLI, reads relevant trunk paths. If confident,
   creates a fact with citation kind `system_answer` and moves the
   question status to `answered_system`. Human never sees it.
2. **Human answers** via the inbox UI. The answer becomes a fact
   with citation kind `human_answer`. Reconcile fires on the entity
   → beliefs update → downstream generations get sharper.

**Interview fatigue is the silent killer.** Never surface more
than 3-5 top-ranked questions at a time. Retire questions that go
un-answered for 30 days AND drop below "high" materiality.

---

## The `derived_from_sha` contract

Every fact, belief, and question carries the change-log sha it was
derived at. This is the intelligence layer's cache-invalidation
key.

Re-vetting:
```
git diff <derived_from_sha>..HEAD -- <relevant paths>
```
- Empty diff → artifact still valid, no work.
- Non-empty diff → send Sonnet ONLY the diff, ask "does this change
  your prior belief?"

Intelligence NEVER regenerates from scratch. It always reasons
incrementally about what changed. That's the speed + accuracy win.

---

## The workflow contract

Any workflow (task graph, PEP, schedule) starts with:
```ts
const result = await ensureIntelligenceFresh(scope, 30_000);
if (result.stale) {
  // Flag on the output; proceed on warm state.
}
```
- Wakes hot loop for the scope.
- Bounded by deadline_ms.
- If fresh → workflow reads current beliefs + facts + CLAUDE.md +
  data.json at every scope it operates in.
- If stale → workflow still runs on warm state, marks output stale.

Never hang forever.

---

## What NOT to do

- Do not put intelligence content in the DB. Trunk is canonical.
  DB has zero opinion on beliefs / facts / questions.
- Do not generate a floating "global intelligence" file. Every
  artifact scopes to an entity.
- Do not surface every question. Rank + throttle. Interview fatigue
  kills the whole system.
- Do not use SDK when CLI works. Subscription is the cost lever.
- Do not skip the falsification test on beliefs. It's the
  confirmation-bias fence.
- Do not treat "Boss disagreed with a belief" as anything other
  than a critical signal. Contradiction from the domain expert
  supersedes an active belief unless the evidence is overwhelming
  and explicit.
- Do not run intelligence work if `derived_from_sha` matches HEAD
  and no new facts arrived. That's the whole cache-invalidation
  point.

---

## Metrics

Three metrics tell you if the system is healthy:
1. **Classifier accuracy** — % of change-log lines correctly marked
   material vs not. Target 95%+. If wrong, cost blows up (false
   positive) OR intel goes stale (false negative).
2. **Median open-question age** — target < 7 days. Rising = system
   asking too much OR human not answering. Falling = healthy.
3. **Workflow hot-hit rate** — % of `ensureIntelligenceFresh` calls
   where warm loop had already made intelligence current. Target
   90%+. If low, warm loop isn't firing enough.

If all three are green, the system works. If any is red, you know
where to look.

---

## Doc precedence for the intelligence layer

When a belief conflicts with data:
1. Facts + change-log (raw truth) win.
2. Boss's explicit answer to a question wins over inferred beliefs.
3. CLAUDE.md wins over auto-derived beliefs when they contradict
   (Boss's prose is authoritative; a belief that contradicts must be
   deprecated OR the fact behind it re-examined).
4. Older beliefs lose to newer beliefs when both cite the same
   fact set.
5. Cross-entity beliefs (Opus-derived) DON'T override per-entity
   beliefs — they layer.

---

## Question lifecycle v2 (2026-08-06)

- **Ceiling: 10 open questions per scope** (was 12; env
  `INTEL_OPEN_QUESTION_CEILING`). Server-enforced at warm-loop merge.
- **Hot surface: top 5** by materiality × blast_radius are marked
  `surfaced` each run (env `INTEL_HOT_SURFACE_COUNT`); the inbox leads
  with them. Ranking gives a +6 boost to `taskgraph_*` concepts —
  questions that resolve a generation `needs_info` outrank everything.
- **Earn-a-slot rule:** every new question must carry `unblocks` — one
  sentence naming what answering it concretely unlocks (a schedule
  item, a cost decision, a checklist answer). Can't state it → record
  a belief instead, don't ask.
- **Displacement:** an incoming critical question that can't fit evicts
  the weakest non-critical open question (to history, never deleted).
- **Ancestor dedupe:** a question whose concept is already open at an
  ancestor scope is dropped at merge — the ancestor question governs.
  Property concerns (site, access, septic-vs-sewer, service capacity)
  are asked ONCE at app_project scope and inherited by every job.
- **Generation reads the cascade:** task-graph interrogation now
  consumes facts/beliefs from job + property + project scopes, labeled
  by scope.
- **Delta manifest:** every warm-loop run records
  `{diff_kind, touched_files, changelog_lines}` in `.runlog.jsonl`
  alongside per-phase timings — the one-line answer to "why did this
  run do work".

---

## Addendum 2026-09-04 — canon storage moved to MySQL

The canonical knowledge layer no longer lives in trunk files. `canon.json` and `proposed.json` are GONE from every scope; MySQL is the source of truth (`canon_groups` / `canon_entries` = human pen, `proposed_entries` = machine pen, keyed by project_idx + scope_kind + scope_id). Each scope\x27s `CLAUDE.md` is still rendered per scope — now from the DB during materialize and on every canon mutation — and remains the ONLY knowledge surface agents read on disk.

- `canon_history` (append-only, before/after JSON + reason + actor) is the audit trail of the human pen; `canon_scopes.revision` is a per-scope monotonic counter bumped by human mutations only — the future freshness token replacing `derived_from_sha`.
- The warm loop\x27s proposed reads/writes go through the DB seam in `server_a1/services/brain/canonFiles.ts` (same function signatures, DB-backed). Prompts and flows unchanged.
- `questions.jsonl` remains trunk-native for now (queued for the next intelligence pass).
