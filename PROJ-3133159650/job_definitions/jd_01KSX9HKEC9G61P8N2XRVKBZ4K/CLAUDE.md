# CANON - Addition Scope (Priority Level 2/4)
<!-- AUTO GENERATED from canon.json data via a script - READ ONLY -->

## Permits & Septic

- POLICY: Permit lead times: Every permit application is filed 2 weeks before job start — except TDEC septic, which is filed 6 weeks before; demo never starts without the building permit in hand.
- POLICY: TDEC septic trigger: TDEC septic permitting applies only when the job modifies or installs a septic system — added bedrooms or bathrooms alone do not trigger it; never break ground while TDEC is pending.

## Structure & Site

- DEFAULT: Framing method: Stick-frame for small additions
    Condition: If Unless scope explicitly specifies trusses, roof span exceeds ~24 ft, footprint exceeds ~800 sqft, or the PM confirms trusses
- DEFAULT: LVL-omitted risk: Carry it as a flagged change-order risk — value-engineered engineered lumber tends to come back as a change order after final engineering
    Condition: If Structural documents contain "LVL omitted, sized per IRC" language — unless final engineering is already complete
- DEFAULT: Below-grade package: A below-grade package runs between foundation and framing: waterproofing and drainage board on the below-grade wall, foundation drain with filter fabric sloped to daylight, gravel backfill
    Condition: If Sloped-lot or walkout addition — unless engineering specifies otherwise
- POLICY: Roof tie-in photos: Existing conditions are photo-documented on day one of roof framing.
    Condition: If The new roof ties into or over-frames the existing roof
- REFERENCE: Habitable space threshold
    Label: Non-habitable clear height | Value: Under ~5 ft | Context: No habitable-space code paths; access (e.g. exterior barn doors) rides in exterior finishes, not interior
    Notes: Source: IRC practice

## Mechanical, Electrical & Plumbing

- DEFAULT: HVAC type: Mini-split — short line-set rough, no separate rough-in phase
    Condition: If Unless scope says "ducted", "duct work", or "air handler" (duct-extension path applies); if still ambiguous, ask rather than guess
- POLICY: Electrical service capacity: Existing main-service capacity is verified before any subpanel or HVAC equipment order is placed; a subpanel rides the building permit, a main-service upgrade is its own permit.
- REFERENCE: Water heater plumbing delay
    Label: Added delay | Value: 1 | Unit: Working day | Context: Tank is set before rough-in stubs into it; merely extending an existing heater's vent adds nothing
    Condition: If Scope includes a new tank or tankless water heater

## Procurement & Lead Times

- POLICY: Window ordering: Windows and exterior doors are ordered at permit submittal; any non-stock size is verified for real lead time before the schedule assumes stock.
- REFERENCE: Window lead times
    Label: Stock sizes | Value: 21 | Unit: Calendar days
    Label: Non-stock / custom sizes | Value: Verify with supplier before scheduling | Context: Silent lead-time trap — the schedule may assume stock lead for what is actually a custom unit
    Notes: Source: TCR supplier experience

## Sequencing & Schedule

- POLICY: Weathertight gate: Interior work begins only once roofing is complete, and insulation/drywall are never scheduled before rough inspections pass.
- DEFAULT: Retro-phase detection: Work belongs in its own Retro-phase item (pre-addition work on the existing home) when any signal fires: area mismatch with the addition objective, "existing" language in scope text, or unresolved spatial location for a new feature
    Condition: If Unless the PM explicitly folds it into the addition's new-construction scope
- DEFAULT: Front-loaded schedule pressure: Compression pressure belongs before interior finishes; from interior finishes onward the schedule keeps intentional slack and the back half is not panic-compressed
    Condition: If Unless the PM explicitly directs compressing closeout

## Closeout & Warranty

- DEFAULT: Completion milestone: The job-complete milestone is the PM's personal walkthrough with the customer, one working day after the last item (final inspection, landscaping, exterior finishes, deck) finishes
    Condition: If Unless customer scheduling forces it to be on a different day
- DEFAULT: Tie-in settling cracks: Hairline drywall cracks at new-to-existing tie-ins (above doors, windows, headers) are an expected year-one settling issue handled as a 1-year-warranty return visit, not a scheduled job task
    Condition: If Unless cracking is structural or beyond hairline

## Proposed (machine-derived, UNVETTED — canon above wins on any conflict)

- DEFAULT: Addition job cost breakdowns are built from a repurposed Basement-Remodel template: This was observed on one job's breakdown document, which self-declared 'Template Anchor: Basement_Remodel_Breakdown_Locked_Template_v1.xlsx' — treated as evidence of a company-wide practice, not confirmed across other Addition jobs. (Unvetted, Confidence 50%)
    Condition: If When reviewing or auditing an internal cost-breakdown spreadsheet for an Addition job against its scope-of-work.
    Notes: If a future Addition job's breakdown total looks unexplainably low relative to its scope, check first whether septic and roof-framing-method costs were folded into a generic bucket (e.g. 'General Conditions') or omitted entirely, before assuming the scope itself changed.
- DEFAULT: Treat job.notes dimensional/spec claims as unverified until cross-checked against scope and drawings: job.notes reflects a human's shorthand/paraphrase and may contain transcription errors (e.g. typos), not a superseding instruction (Unvetted, Confidence 50%)
    Condition: If If job.notes states a dimension, material choice, or scope detail that conflicts with the anchor scope-of-work or drawings on an Addition job
    Notes: Single-incident evidence so far; raise confidence if the same pattern (note vs. concurring documents) recurs on future Addition jobs.
