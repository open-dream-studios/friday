# events.jsonl schema

Last revised: 2026-07-08. Added pattern + belief lifecycle kinds.

Per-work-unit append-only audit log. Lives at
`_projects/<context>/jobs/<work_unit>/events.jsonl`. One JSON object
per line. Never edit or delete a line. Adding a correction is itself
an event.

## Line shape

```json
{
  "id": "evt_<ulid>",
  "ts": "2026-07-08T14:00:00Z",
  "kind": "<event_kind>",
  "actor": "agent" | "<user_id>",
  "subject": { "path": "relative/path/in/trunk", "ref": null },
  "summary": "one-line human-readable description",
  "details": { /* event-specific payload */ },
  "git": { "branch": "main" | "proposal-...", "commit": "sha-or-null" }
}
```

## `kind` catalog

**Work unit lifecycle:**
| kind                   | When fired                                           |
| ---------------------- | ---------------------------------------------------- |
| `work_unit_created`    | A new work-unit folder spun up.                      |
| `work_unit_archived`   | A work unit was moved to `_archive/`.                |

**Data (mirrored inputs):**
| kind                   | When fired                                           |
| ---------------------- | ---------------------------------------------------- |
| `input_added`          | A file was added to `inputs/`.                       |
| `input_updated`        | An existing input changed (content or pointer).      |
| `input_removed`        | An input was removed.                                |
| `manifest_synced`      | The work-unit manifest was refreshed from DB.        |
| `interview_saved`      | A PM interview round was written.                    |

**Intelligence lifecycle — beliefs:**
| kind                   | When fired                                           |
| ---------------------- | ---------------------------------------------------- |
| `belief_proposed`      | Agent proposed a belief; entered review queue.       |
| `belief_auto_approved` | Belief passed auto-approval gates; `status: active`. |
| `belief_accepted`      | PM approved a queued belief; `status: active`.       |
| `belief_rejected`      | PM rejected a queued belief; `status: deprecated`.   |
| `belief_edited`        | PM edited a belief in place; new supersession row.   |
| `belief_verified`      | A run cited this belief AND the observation held.    |
| `belief_marked_stale`  | Staleness detection flipped `stale: true`.           |
| `belief_superseded`    | A belief got replaced by a successor.                |

**Intelligence lifecycle — rules:**
| kind                   | When fired                                           |
| ---------------------- | ---------------------------------------------------- |
| `rule_proposed`        | Agent proposed a rule (PM-review only).              |
| `rule_accepted`        | Human merged a proposed rule.                        |
| `rule_rejected`        | PM rejected a proposed rule.                         |
| `rule_edited`          | PM edited a rule; new supersession row.              |
| `rule_deprecated`      | Rule superseded or explicitly retired.               |

**Intelligence lifecycle — patterns:**
| kind                   | When fired                                           |
| ---------------------- | ---------------------------------------------------- |
| `pattern_proposed`     | Extraction generator proposed a pattern.             |
| `pattern_accepted`     | PM approved a queued pattern; `status: active`.      |
| `pattern_rejected`     | PM rejected a queued pattern.                        |
| `pattern_reverified`   | Re-extraction confirmed the pattern still holds.     |
| `pattern_marked_stale` | Re-extraction detected material drift.               |
| `pattern_superseded`   | A pattern got replaced by a successor.               |

**Artifacts (generations):**
| kind                    | When fired                                           |
| ----------------------- | ---------------------------------------------------- |
| `generation_started`    | Agent began producing an artifact.                   |
| `generation_completed`  | Artifact landed on a proposal branch.                |
| `generation_accepted`   | Proposal merged; artifact lives on main.             |
| `generation_rejected`   | PM rejected; branch discarded.                       |
| `pm_edited_generation`  | PM hand-edited an accepted generation.               |

**Cross-cutting:**
| kind                    | When fired                                           |
| ----------------------- | ---------------------------------------------------- |
| `conflict_flagged`      | Agent flagged contradictions between two paths.      |
| `sync_drift_detected`   | Sync Health noticed DB↔trunk drift on a field.       |
| `note`                  | Free-form. Use sparingly. `details.body` carries it. |

New kinds are added as new event types are needed. Adding a kind is
a schema-evolution event — bump the changelog at the bottom of this
file.

## Hard rules

- Append-only. Never edit, never delete. Corrections are new events
  with `kind: "note"` or a kind-specific revision event.
- One event per line. No newlines inside the JSON object.
- `id` MUST be a fresh ULID. Never reuse.
- `ts` MUST be ISO8601 UTC.
- `details` shape varies by `kind`. Validators check the shape
  per-kind.

## Changelog

- **2026-07-08** — added pattern lifecycle kinds
  (`pattern_proposed`, `pattern_accepted`, `pattern_rejected`,
  `pattern_reverified`, `pattern_marked_stale`,
  `pattern_superseded`); belief lifecycle kinds
  (`belief_auto_approved`, `belief_accepted`, `belief_rejected`,
  `belief_edited`, `belief_verified`); rule lifecycle kinds
  (`rule_accepted`, `rule_rejected`, `rule_edited`,
  `rule_deprecated`); sync + interview kinds
  (`sync_drift_detected`, `interview_saved`, `manifest_synced`);
  renamed `belief_merged` → `belief_accepted` for consistency;
  renamed `rule_merged` → `rule_accepted`; renamed `job_created` →
  `work_unit_created`. Old kinds honored on read for backward
  compatibility.
- **2026-06-22** — initial schema.
