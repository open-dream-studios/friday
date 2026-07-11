# DATA_MODEL — DB rows ↔ trunk paths

Companion to [`BRAIN.md`](./BRAIN.md) and
[`ARCHITECTURE.md`](./ARCHITECTURE.md). This is the row-by-row map
`materializeProject` uses to compose the disk tree.

If you add a new DB entity that must appear on disk, add its
section here first, then extend `materialize.ts` to consume it.

---

## The trunk root

`friday/` (sibling of `dev-cms/`). One git repo. One flat namespace:
each top-level directory is a project.

```
friday/
├── .git/
├── BRAIN.md
├── ARCHITECTURE.md
├── DATA_MODEL.md
└── <project_id>/            # one per row in `projects`
    └── …
```

`<project_id>` = `projects.project_id` (the string ULID form, e.g.
`PROJ-01KEZSFF4BGT67PQ7YJAR6DAM7`).

---

## projects

One row = one top-level directory.

- Source: `projects.project_id`, `projects.id` (= `project_idx`)
- Path: `friday/<project_id>/`
- Contents at the root:
  - `data.json` — see [data.json shape](#datajson-shape) below.
    Derived from DB every materialize. Read-only on disk.
  - `facts.json`, `rules.json`, `beliefs.json` — intel stubs, `{}`
    at first materialize, human/agent-editable afterwards.
  - `app_projects/` — container (see below)
  - `job_definitions/` — container (see below)
  - Loose `<project_folders>/…` — see project_folders section.

Deleting a `projects` row wipes the whole `<project_id>/` subtree
on the next materialize. Container folders never persist without a
parent row.

---

## app_projects

- Source: `app_projects` where `project_idx = <this project>`
- Path: `friday/<project_id>/app_projects/<app_project_id>/`
- Contents:
  - `data.json` — resolved row + customer + lead_employee + profile
  - `facts.json`, `rules.json`, `beliefs.json`
  - `jobs/` — container for this app_project's jobs

Container `app_projects/` is generated when at least one row exists.

---

## jobs

- Source: `jobs` where `entity_type = 'app_project'` and
  `entity_id = <app_project_id>`
- Path: `friday/<project_id>/app_projects/<app_project_id>/jobs/<job_id>/`
- Contents:
  - `data.json` — resolved row + job_definition + scope/breakdown docs
  - `facts.json`, `rules.json`, `beliefs.json`
  - (Downstream generators may write `intelligence/`, `interview/`,
    `inputs/`, `generations/` under here — those are trunk-native
    and preserved through materialize.)

---

## job_definitions

Recursive by `parent_job_definition_id`.

- Source: `job_definitions` where `project_idx = <this project>`
- Path: nested. Root job_definitions live at
  `friday/<project_id>/job_definitions/<job_definition_id>/`. A
  child sits at `.../<parent_id>/<child_id>/`.
- Contents at each level:
  - `data.json` — row + profile + resolved parent_chain
  - `facts.json`, `rules.json`, `beliefs.json`
  - Deeper children.

---

## data.json shape

Every entity folder gets a `data.json` written on every materialize.
It's the entity's typed columns + resolved foreign keys + parsed
`profile` JSON. Purpose: Claude Code (or any agent) opens the entity
folder and has full context in one `Read`, no follow-up joins needed.

**Contract:**

- **Derived, not preserved.** Regenerated from DB on every materialize.
  Never edit by hand — the next run wipes it.
- **FK resolution is safe.** A resolved reference always includes
  the id. If the target row exists, `resolved: true` + the resolved
  fields. If missing (deleted mid-flight), `resolved: false` + the
  fields set to `null`. Never throws.
- **Missing profile → omitted key.** Rows with `profile IS NULL`
  ship data.json without a `profile` field (cleaner than empty
  object).
- **No timestamp fields in data.json.** Freshness = git commit
  time (`git log -1 --format=%aI -- <path>`). Materialize deliberately
  does NOT stamp `data.json` with its run time — that would make every
  materialize appear to touch every entity, drowning the change-log
  in noise. The change-log's `ts` field carries the semantic timing.

### Project root — `PROJ-X/data.json`

```json
{
  "project_id": "PROJ-01KEZSFF4BGT67PQ7YJAR6DAM7",
  "project_idx": 132,
  "name": "Tri Cities Remodeling",
  "short_name": "TCR",
  "backend_domain": "tricitiesremodeling.com",
  "brand": "TCR",
  "image_compression": "FAST",
  "video_compression": "FAST",
  "av1_enabled": false,
  "private_aws": false,
  "profile": {
    "working_hours": { "start": "07:00", "end": "17:00", "tz": "America/New_York" },
    "crew_size": 6,
    "service_area": { "center": "Johnson City, TN", "radius_miles": 45 }
  },
}
```

### App-project — `PROJ-X/app_projects/APPPROJ-Y/data.json`

```json
{
  "app_project_id": "APPPROJ-01KKRDKCHSTDHJTQZYA720ZTDR",
  "name": "Bristol Master Bathroom Renovation",
  "project_type": "remodel_bathroom",
  "address": {
    "line1": "428 Ashe Street",
    "line2": null,
    "city": "Johnson City",
    "state": "Tennessee",
    "postal_code": "37604",
    "country": "US"
  },
  "valuation": null,
  "latest_estimation_total": null,
  "latest_estimation_sent_at": null,
  "notes": null,
  "customer": {
    "id": 4074,
    "customer_id": "CUST-…",
    "name": "Jane Smith",
    "phone": "+1-423-555-0100",
    "email": "jane@example.com",
    "resolved": true
  },
  "lead_employee": {
    "id": 236,
    "employee_id": "EMP-…",
    "name": "John Doe",
    "resolved": true
  },
  "profile": null,
}
```

### Job — `PROJ-X/app_projects/APPPROJ-Y/jobs/JOB-Z/data.json`

```json
{
  "job_id": "JOB-…",
  "entity_type": "app_project",
  "entity_id": "APPPROJ-…",
  "valuation": null,
  "status": "waiting_diagnosis",
  "priority": "medium",
  "scheduled_start_date": "2026-08-01",
  "completed_date": null,
  "notes": null,
  "job_definition": {
    "id": 12,
    "job_definition_id": "JDEF-…",
    "identifier": "bathroom_remodel",
    "type": "bathroom_remodel",
    "resolved": true
  },
  "scope_document": {
    "id": "doc_…",
    "name": "308 Scope.pdf",
    "resolved": true
  },
  "breakdown_document": {
    "id": null,
    "name": null,
    "resolved": false
  },
}
```

### Job definition — `PROJ-X/job_definitions/JDEF-W/data.json`

```json
{
  "job_definition_id": "JDEF-…",
  "identifier": "bathroom_remodel_luxury",
  "type": "bathroom_remodel_luxury",
  "description": "…",
  "parent_chain": [
    { "id": 3, "job_definition_id": "JDEF-…", "identifier": "bathroom_remodel" }
  ],
  "profile": null,
}
```

---

## project_folders (documents scope)

The `project_folders` table drives every folder the user can
navigate in the Documents module (both top-level and per-app-project).

Two families based on `entity_type` / `app_project_root_id`:

### Family A — App-project buckets

- Source: `project_folders` where `scope = 'documents'` and
  `app_project_root_id IS NOT NULL`.
- Every row is a folder under the app-project's documents bucket.
- Path composition: walk `parent_folder_id` up to the row where
  `app_project_root_id IS NOT NULL` (the bucket root itself), then
  emit under
  `friday/<project_id>/app_projects/<app_project_id>/<folder>/<subfolder>/…`.
- The bucket-root row itself is represented as the app_project
  directory — no extra folder for it.

### Family B — Project-wide library

- Source: `project_folders` where `scope = 'documents'`,
  `app_project_root_id IS NULL`, and `parent_folder_id IS NULL` for
  the top level (recursive for children).
- Path: `friday/<project_id>/<folder_name>/<subfolder_name>/…`
- These are the top-level Documents module's folders — the "project
  library." Not tied to any app_project.

Materialize creates every folder from these rows. Human-created
folders on disk that don't correspond to any row are wiped (they'd
be untracked drift).

---

## project_folders (media scope)

Same shape as documents scope but the folder tree is orthogonal —
media has its own hierarchy under
`friday/<project_id>/_media/…` (top-level) and
`friday/<project_id>/app_projects/<app_project_id>/_media/…`
(app-project bucket).

The `_media` prefix is a convention to prevent name collisions with
documents folders. TBD when we sweep media into the materialize
model; documented here so the shape is agreed before we ship.

---

## documents

- Source: `documents` where `project_idx = <this project>` and
  `deleted_at IS NULL` (or however the block soft-deletes).
- Path: `folder_id` → `project_folders` row → composed folder path
  → append `documents.original_name` (or `name` if renamed).
- Bytes: `documents.s3_key` → `ensureCached` → hardlink/copy to
  the target path.
- No `.ref.json` sidecar. Claude Code reads PDFs directly (multimodal).

Examples:
- App-project-scoped doc at bucket root:
  `friday/PROJ-…/app_projects/APPPROJ-…/scope13.pdf`
- App-project-scoped doc in a subfolder:
  `friday/PROJ-…/app_projects/APPPROJ-…/permits/city_permit.pdf`
- Project-library-scoped doc at root:
  `friday/PROJ-…/pricebook_2026.csv`
- Project-library-scoped doc in a subfolder:
  `friday/PROJ-…/templates/scope_template.pdf`

---

## media

- Source: `media` where `project_idx = <this project>`.
- Same folder-resolution rule as documents but under `_media/`
  (see project_folders / media scope above).
- Bytes: `media.url` → cache → hardlink.
- Deferred to a later sweep. Not part of the initial materialize
  implementation; document here so the plan is fixed.

---

## file_link / media_link

These junction tables associate documents/media with entities other
than app_projects — e.g., a document linked to a specific customer
or product.

**These do NOT drive folder placement** in the materialize model.
Folder placement is exclusively `documents.folder_id` →
`project_folders` ancestry. `file_link` remains authoritative for
"which entities can reference this doc" queries in the UI, but the
disk only ever sees the folder path.

App-project scope is a special case: at write-time, the block
resolves `entity_type='app-project'` to the bucket root folder id
(see `documents/server/controllers.ts:520-550`) so the `folder_id`
column already carries the truth. No file_link inspection needed at
materialize time.

---

## Intel + artifact leaves

Not in DB. Trunk-native. Preserved through materialize's wipe/rebuild
cycle by reading their contents into memory before wipe (step 3 of
the materialize function) and writing them back after the tree is
rebuilt (step 6).

Locations:
- Per-entity intel: `facts.json`, `rules.json`, `beliefs.json` at
  every project / app_project / job / job_definition folder.
- Per-entity foundation prose: `CLAUDE.md` at every entity node.
  Boss-authored (or, later, agent-authored via strict review) rich
  context — philosophy, policies, edge cases. See
  [`ARCHITECTURE.md`](./ARCHITECTURE.md#per-entity-claudemd--foundation-prose)
  for the contract.
- Per-job generations + intel: `intelligence/`, `interview/`,
  `inputs/`, `generations/` under a job folder — written by the
  brain agent, preserved verbatim.
- Trunk-root docs: `BRAIN.md`, `ARCHITECTURE.md`, `DATA_MODEL.md`,
  `ROADMAP.md`, `_schemas/*` — never touched by materialize.

---

## .change-log.jsonl

`friday/<project_id>/.change-log.jsonl` — append-only, one line per
materialize event. Preserved through wipe (materialize reads it
into memory before wiping, writes it back after rebuild). Committed
to git alongside the entity changes.

**Line format:**

```jsonl
{"ts":"2026-07-11T01:47:18.920Z","reason":"customer_id changed on APPPROJ-…","actor":"user","entities":[{"kind":"app_project","id":"APPPROJ-…","action":"update"}]}
{"ts":"2026-07-11T01:52:04.100Z","reason":"documents create-from-html doc_01KX…","actor":"user","entities":[{"kind":"document","id":"doc_01KX…","action":"create"}]}
```

Full contract + consumption model in [`ARCHITECTURE.md`](./ARCHITECTURE.md#the-change-log).

---

## What materialize does NOT touch

- `.git/` under the trunk root — history is sacred.
- `BRAIN.md` / `ARCHITECTURE.md` / `DATA_MODEL.md` / other repo-root
  docs — trunk-native.
- Intel leaves at every entity folder — human/agent-authored.
- Job-scoped generations under `<job_id>/generations/` — brain-agent
  output, trunk-native.
- Anything under `~/.friday-cache/` — that's the cache, not the
  trunk.

Anything else under `friday/<project_id>/…` is regenerated on every
materialize pass. Human-created loose files or folders inside the
regenerated subtree WILL be wiped. If you need to add something,
add it via the DB.
