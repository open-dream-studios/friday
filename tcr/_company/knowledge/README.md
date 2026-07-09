# `_company/knowledge/` — raw business context

Free-form, human-authored business knowledge. No schema, no frontmatter
required. This is where Will's playbook, meeting transcripts, scope
templates, and similar reference material live.

The agent reads `knowledge/` files when it needs deeper context than a
rule or belief alone provides. Knowledge files are often the `supports`
target for belief frontmatter.

## What to put here

- `wills_playbook.md` — Will's voice, his patterns, his preferences.
- `scope_template_addition.md` — boilerplate the PM uses when writing a
  new addition scope.
- `meeting_transcripts/2026-05-15_will_pm_sync.md` — raw transcripts.
- `definitions/septic_tdec.md` — long-form explanation of how the TDEC
  process actually works, with links and references.

## What NOT to put here

- Anything that reduces cleanly to a single claim → make a rule or belief.
- Per-project files → those live under `_projects/<id>/`.
- Binaries → upload to S3, reference via a `.ref.json` next to the
  extracted `.txt`.

## Subfolder freedom

You can nest however you want here. `knowledge/playbook/`,
`knowledge/transcripts/`, `knowledge/templates/` — agent navigates by
reading filenames + README files. Be reasonable.
