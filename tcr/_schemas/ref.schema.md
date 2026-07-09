# `.ref.json` pointer schema

Every uploaded binary that the agent should be able to discover has a
sibling `.ref.json` pointer file committed to the trunk. The pointer is
the single source of truth tying a trunk slot to its canonical S3 object
+ DB row.

Naming: `<filename>.ref.json` next to (optional) `<filename>.txt`
(extracted text) and (never committed) `<filename>` (the binary itself,
fetched on demand to an out-of-git cache).

## Pointer contract

```json
{
  "id": "ref_<ulid>",
  "kind": "ref",
  "filename": "scope2.pdf",
  "mime": "application/pdf",
  "size_bytes": 482183,
  "content_hash": "sha256:abc123…",
  "s3": {
    "bucket": "open-dream-prod",
    "key": "tcr/projects/<id>/jobs/<jid>/scope2.pdf",
    "region": "us-east-1"
  },
  "db": {
    "table": "documents",
    "id": "doc_01KKR..."
  },
  "extracted_text": {
    "path": "./scope2.pdf.txt",
    "extracted_at": "2026-06-22T14:00:00Z",
    "extractor": "pdf-parse@1.1.1"
  },
  "uploaded_at": "2026-06-22T14:00:00Z",
  "uploaded_by": "user_01KKR..."
}
```

## Hard rules

- `content_hash` is sha256 of the canonical binary on S3 at upload time.
  If the underlying object ever changes (it shouldn't — uploads are
  immutable), staleness detection flips dependent beliefs.
- `extracted_text.path` is relative to the pointer file's location.
  Always points to the sibling `.txt`. Omit the whole `extracted_text`
  block when the binary isn't text-extractable (large images, video).
- The actual binary is NEVER committed. Only the pointer + the
  extracted text. The harness fetches the binary from S3 to a local
  cache when an agent tool requests it.
- DB `table` + `id` lets the harness round-trip back to the row that
  originated this upload, for any UI surfacing.

## Why this shape

S3 = canonical. DB = index. Trunk = cache + extracted text. The pointer
is what makes those three stay in agreement without coupling them at
write-time. See `friday/BRAIN.md` (file-handling locked decision).
