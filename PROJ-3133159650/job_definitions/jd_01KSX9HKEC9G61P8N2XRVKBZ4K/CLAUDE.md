# CANON - Addition Scope (Priority Level 2/4)
<!-- AUTO GENERATED from canon.json data via a script - READ ONLY -->

## Permits & Septic

- POLICY: TDEC septic trigger: TDEC septic permitting applies only when the job modifies or installs a septic system — added bedrooms or bathrooms alone do not trigger it; never break ground while TDEC is pending.

## Structure & Site

- DEFAULT: Framing method: Stick-frame for small additions
    Condition: If Unless scope explicitly specifies trusses, roof span exceeds ~24 ft, footprint exceeds ~800 sqft, or the PM confirms trusses
- DEFAULT: Below-grade package: A below-grade package runs between foundation and framing: waterproofing and drainage board on the below-grade wall, foundation drain with filter fabric sloped to daylight, gravel backfill
    Condition: If Sloped-lot or walkout addition — unless engineering specifies otherwise

## Mechanical, Electrical & Plumbing

- POLICY: Electrical service capacity: Existing main-service capacity is verified before any subpanel or HVAC equipment order is placed; a subpanel rides the building permit, a main-service upgrade is its own permit.

## Proposed (machine-derived, UNVETTED — canon above wins on any conflict)

- DEFAULT: Addition job cost breakdowns are built from a repurposed Basement-Remodel template: This was observed on one job's breakdown document, which self-declared 'Template Anchor: Basement_Remodel_Breakdown_Locked_Template_v1.xlsx' — treated as evidence of a company-wide practice, not confirmed across other Addition jobs. (Unvetted, Confidence 50%)
    Condition: If When reviewing or auditing an internal cost-breakdown spreadsheet for an Addition job against its scope-of-work.
    Notes: If a future Addition job's breakdown total looks unexplainably low relative to its scope, check first whether septic and roof-framing-method costs were folded into a generic bucket (e.g. 'General Conditions') or omitted entirely, before assuming the scope itself changed.
- DEFAULT: Treat job.notes dimensional/spec claims as unverified until cross-checked against scope and drawings: job.notes reflects a human's shorthand/paraphrase and may contain transcription errors (e.g. typos), not a superseding instruction (Unvetted, Confidence 50%)
    Condition: If If job.notes states a dimension, material choice, or scope detail that conflicts with the anchor scope-of-work or drawings on an Addition job
    Notes: Single-incident evidence so far; raise confidence if the same pattern (note vs. concurring documents) recurs on future Addition jobs.
- DEFAULT: Verify drawing-set title block/address against job site address before treating as authoritative: Treat the drawing set as unconfirmed for this job (do not drive procurement/framing decisions from it) until a human confirms it is the correct set, even when scope content otherwise appears to match. (Unvetted, Confidence 45%)
    Condition: If If an attached architectural/drawing document's project title, author address, or site address differs from the job's recorded site address
    Notes: Raise confidence if the same identity-mismatch pattern recurs on a future job's drawing set.
- DEFAULT: Flag pre-contract scope/proposal documents carrying T&M or hourly billing language before contract execution: The document likely carries a stale or wrong template and needs correction to fixed-price/25% milestone terms before a contract is signed; do not assume the signed contract will inherit the T&M language. (Unvetted, Confidence 40%)
    Condition: If If a pre-contract scope/estimate document (anchor) states an hourly rate schedule, labor differentials, or a non-25%-milestone deposit alongside (or instead of) a fixed total
    Notes: If this recurs, consider it a sales-template defect worth fixing at the source rather than a per-job anomaly.
