# Addition — Job Type Canon (Tri Cities)

<!-- GENERATED from canon.json — do not edit by hand. Edit the canon; this file is rebuilt on every change. -->

## Permits & Septic

- **Permit lead times** `policy`: Every permit application is filed 2 weeks before job start — except TDEC septic, which is filed 6 weeks before; demo never starts without the building permit in hand.
- **TDEC septic trigger** `policy`: TDEC septic permitting applies only when the job modifies or installs a septic system — added bedrooms or bathrooms alone do not trigger it; never break ground while TDEC is pending.

## Structure & Site

- **Framing method** `default` _(when: Unless scope explicitly specifies trusses, roof span exceeds ~24 ft, footprint exceeds ~800 sqft, or the PM confirms trusses)_: assume Stick-frame for small additions.
- **LVL-omitted risk** `default` _(when: Structural documents contain "LVL omitted, sized per IRC" language — unless final engineering is already complete)_: assume Carry it as a flagged change-order risk — value-engineered engineered lumber tends to come back as a change order after final engineering.
- **Below-grade package** `default` _(when: Sloped-lot or walkout addition — unless engineering specifies otherwise)_: assume A below-grade package runs between foundation and framing: waterproofing and drainage board on the below-grade wall, foundation drain with filter fabric sloped to daylight, gravel backfill.
- **Roof tie-in photos** `policy` _(when: The new roof ties into or over-frames the existing roof)_: Existing conditions are photo-documented on day one of roof framing.
- **Habitable space threshold** `reference`:
  - non-habitable clear height: under ~5 ft (no habitable-space code paths; access (e.g. exterior barn doors) rides in exterior finishes, not interior)
  - _source: IRC practice_

## Mechanical, Electrical & Plumbing

- **HVAC type** `default` _(when: Unless scope says "ducted", "duct work", or "air handler" (duct-extension path applies); if still ambiguous, ask rather than guess)_: assume Mini-split — short line-set rough, no separate rough-in phase.
- **Electrical service capacity** `policy`: Existing main-service capacity is verified before any subpanel or HVAC equipment order is placed; a subpanel rides the building permit, a main-service upgrade is its own permit.
- **Water heater plumbing delay** `reference` _(when: scope includes a new tank or tankless water heater)_:
  - added delay: 1 working day (tank is set before rough-in stubs into it; merely extending an existing heater's vent adds nothing)

## Procurement & Lead Times

- **Window ordering** `policy`: Windows and exterior doors are ordered at permit submittal; any non-stock size is verified for real lead time before the schedule assumes stock.
- **Window lead times** `reference`:
  - stock sizes: 21 calendar days
  - non-stock / custom sizes: verify with supplier before scheduling (silent lead-time trap — the schedule may assume stock lead for what is actually a custom unit)
  - _source: TCR supplier experience_

## Sequencing & Schedule

- **Weathertight gate** `policy`: Interior work begins only once roofing is complete, and insulation/drywall are never scheduled before rough inspections pass.
- **Retro-phase detection** `default` _(when: unless the PM explicitly folds it into the addition's new-construction scope)_: assume work belongs in its own Retro-phase item (pre-addition work on the existing home) when any signal fires: area mismatch with the addition objective, "existing" language in scope text, or unresolved spatial location for a new feature.
- **Front-loaded schedule pressure** `default` _(when: Unless the PM explicitly directs compressing closeout)_: assume Compression pressure belongs before interior finishes; from interior finishes onward the schedule keeps intentional slack and the back half is not panic-compressed.

## Closeout & Warranty

- **Completion milestone** `default` _(when: Unless customer scheduling forces a different day)_: assume The job-complete milestone is the PM's personal walkthrough with the customer, one working day after the last item (final inspection, landscaping, exterior finishes, deck) finishes.
- **Tie-in settling cracks** `default` _(when: unless cracking is structural or beyond hairline)_: assume hairline drywall cracks at new-to-existing tie-ins (above doors, windows, headers) are an expected year-one settling issue handled as a 1-year-warranty return visit, not a scheduled job task.
