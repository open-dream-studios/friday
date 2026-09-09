---
document_id: doc_01M224WJ3F6RHV4V7AKEWQFD18
version: 2
name: 205 Pawnee Street - Breakdown.xlsx
role: breakdown
content_sha: 7954aad79bc65c3953cf9f36c6e0b3095d6dcd327eaed92347032cb9bde951a6
brief_sha: 838666d1aa30
analyzed_at: 2026-09-08T21:41:45.242Z
analysis_ms: 36632
extracted_blocks: 0
pipeline_version: 3
page_count: 1
---

## Digest

EXTRACTION FAILURE: '205 Pawnee Street - Breakdown.xlsx' (1 page) could NOT be parsed — the pipeline (v3) does not support .xlsx spreadsheet format, and zero text content was recovered. No line items, costs, quantities, labor-hour estimates, or scope descriptions from this file are available for analysis. This means the core task requested — comparing the breakdown's priced items against the anchor scope (the 205 Pawnee Street covered patio/screened-enclosure/fireplace proposal, Estimate 13156915, total $57,745) — CANNOT be performed. No determination can be made about what the breakdown prices that the scope doesn't mention, or what the scope calls for that the breakdown fails to price. This is a hard blocker, not a 'nothing found' result: the document exists and presumably contains the cost/line-item data needed, but it is inaccessible in its current form.

## Brief findings

- [doc_identity] not_found: not addressed in this document — file is .xlsx format, unsupported by extraction pipeline v3; no text content could be extracted (pp 1)
- [scope_inclusions] not_found: not addressed in this document (pp 1)
- [scope_exclusions] not_found: not addressed in this document (pp 1)
- [dimensions_areas] not_found: not addressed in this document (pp 1)
- [structural] not_found: not addressed in this document (pp 1)
- [existing_conditions] not_found: not addressed in this document (pp 1)
- [materials_finishes] not_found: not addressed in this document (pp 1)
- [site_access] not_found: not addressed in this document (pp 1)
- [permits_inspections] not_found: not addressed in this document (pp 1)
- [schedule_dates] not_found: not addressed in this document (pp 1)
- [money] not_found: not addressed in this document (pp 1)
- [responsibilities] not_found: not addressed in this document (pp 1)
- [revisions_conflicts] not_found: not addressed in this document (pp 1)
- [phase_procurement] not_found: not addressed in this document (pp 1)
- [phase_permits] not_found: not addressed in this document (pp 1)
- [phase_retrofit] not_found: not addressed in this document (pp 1)
- [phase_demolition] not_found: not addressed in this document (pp 1)
- [phase_site_foundation] not_found: not addressed in this document (pp 1)
- [phase_framing_shell] not_found: not addressed in this document (pp 1)
- [phase_exterior_finishes] not_found: not addressed in this document (pp 1)
- [phase_rough_trades] not_found: not addressed in this document (pp 1)
- [phase_rough_inspections] not_found: not addressed in this document (pp 1)
- [phase_insulation_drywall] not_found: not addressed in this document (pp 1)
- [phase_interior_finishes] not_found: not addressed in this document (pp 1)
- [phase_concrete_landscaping] not_found: not addressed in this document (pp 1)
- [phase_closeout] not_found: not addressed in this document (pp 1)
- [procurement_signals] not_found: not addressed in this document (pp 1)

## Cross-page notes

- Single-page document; the sole page returned only a pipeline error message ('format .xlsx not supported by pipeline v3'), no substantive content.
- The document's filename and stated PURPOSE (a cost/line-item breakdown) strongly imply it should contain granular pricing (labor hours, materials, sub costs) that would normally be checked against the anchor proposal's single lump-sum line item ('Deck | Build Deck as Above | $57,745.00') — but none of that granular data was retrievable.
- RECOMMENDATION: re-export or convert the .xlsx to a supported format (CSV, PDF, or plain text) and resubmit so the actual breakdown content can be checked against the anchor scope.

## Uncertainties (unread or ambiguous — never guess at these)

- p1: format .xlsx not supported by pipeline v3
