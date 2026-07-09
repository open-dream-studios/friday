# `_projects/` — per-AppProject brain state

One folder per AppProject (the home / building site TCR is working on).
Inside each project folder, one subfolder per `jobs/<job_id>/` for
each job at that site.

## Folder naming

Project folder = `<readable-slug>_<APPPROJ-id>`:

```
_projects/
  308-evergreen-addition_APPPROJ-01KKRDKBGY5E38A036W0NCQ3AF/
  willow-creek-kitchen_APPPROJ-01KM...........................XYZ/
```

Job folder = `<readable-slug>_<JOB-id>`:

```
_projects/<project_slug>/
  jobs/
    second-story-addition_JOB-01KV94MXDGHRSP8BRZ3HTMC6XN/
```

The readable slug is human-comfort. The `APPPROJ-…` / `JOB-…` suffix
is the canonical key back to the MySQL row — never edit it by hand.

## Per-job folder shape

```
jobs/<job_id>/
  inputs/                ← human-authored or uploaded source material
    scope.md
    breakdown.json
    notes.md
    files/               ← .ref.json pointers + extracted .txt for uploads
  rules/                 ← job-specific overrides (rare; same shape as company rules)
  beliefs/               ← agent-maintained beliefs for THIS job
  generations/           ← AI outputs (task_graph.json, schedule.json, pep.md)
  conversation.id        ← Claude session resume token (plain text)
  events.jsonl           ← append-only audit log
```

Each subfolder gets its own README laying out the per-job file shapes.
The project folder itself may also hold project-wide files
(`project.md` with site notes that apply to all jobs at the site, etc.)
but the action lives in the per-job folder.

## Authority

A job's `rules/` and `beliefs/` are the **most specific** layer. They
override `job_types/<type>/` and `_company/` for this job only.

## Don't put here

- Anything that applies to all jobs of a type → lift to `job_types/<type>/`.
- Anything that applies to all jobs at TCR → lift to `_company/`.
- Raw binaries — pointer + extracted text only (see top-level README).
