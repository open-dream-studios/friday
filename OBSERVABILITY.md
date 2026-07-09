# OBSERVABILITY — UI design principles + surface index

Last revised: 2026-07-08.

Under the 6-series plan, **each UI ships with the series that needs
it**, not as a separate observability phase. Concrete UI definitions
live inside [`ROADMAP.md`](./ROADMAP.md) per series. This file
covers the design principles all UIs must uphold + a flat index of
every surface across the plan.

Read [`BRAIN.md`](./BRAIN.md) first for the architectural context.

---

## Design principles (non-negotiable, every surface)

1. **Generic rendering.** Every surface renders from `Generator`,
   `Artifact`, `Rule`, `Belief`, `Pattern`, `WorkUnit`, `Context`.
   Domain-specific labels come from the domain manifest, never
   hardcoded in UI code.
2. **Deep linking.** Every entity has a stable URL. A run in a
   postmortem links to its citations; a citation links to the rule
   in the Explorer; the rule links back to every run that cited it.
3. **Read-only by default.** Any surface that mutates trunk state
   goes through the proposal review flow. No surface bypasses.
4. **Zero placeholder data.** Every field surfaces a real value or a
   clearly-marked "not-computed-yet" state. No silent nulls.
5. **Test panels are first-class.** Every series' UI ships with a
   Test Panel that triggers integrity checks, writing structured
   results to `friday/_tests/results/`. See ROADMAP for per-series
   test lists.

---

## UI index (which series delivers each)

| UI | Delivered by |
|---|---|
| Data Trunk Browser | Series 1 · Phase Echo |
| Sync Health Monitor | Series 1 · Phase Foxtrot |
| Intelligence Explorer | Series 2 · Phase Golf |
| Proposals Queue | Series 2 · Phase Hotel |
| Scope Match Inspector | Series 3 · Phase Echo |
| Context Preview | Series 4 · Phase Echo |
| Cost + Capacity Monitor | Series 5 · Phase Foxtrot |
| Freshness Dashboard | Series 5 · Phase Golf |
| Tenant Manager | Series 6 · Phase Echo |
| Cross-tenant Meta Explorer | Series 6 · Phase Foxtrot |

Every UI above ships with a matching Test Panel (the last phase of
each series).

---

## What NOT to build (the traps)

- **Don't** build any UI that hardcodes tenant-specific concepts
  (e.g. "job" in the code, "customer" in the code). Use the domain
  manifest's dimension labels.
- **Don't** build write-through admin editors. Mutations flow
  through proposals.
- **Don't** build one giant tabbed super-UI. Each surface is its own
  route with a purpose. Compose via deep links, not tabs.
- **Don't** ship a surface without a Sync Health integration — every
  screen should surface an amber/red banner when the data it's
  showing is drifting.
- **Don't** ship a UI without a Test Panel. Every series' last phase
  is tests. No exceptions.
