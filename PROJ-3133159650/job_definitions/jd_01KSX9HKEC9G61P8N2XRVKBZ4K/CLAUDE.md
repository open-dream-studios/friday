# Addition — Job Type Canon (Tri Cities)

<!-- GENERATED from canon.json — do not edit by hand. Edit the canon; this file is rebuilt on every change. -->

## Policies

- **Electrical service capacity** `policy`: Existing main-service capacity is verified before any subpanel or HVAC equipment order is placed; a subpanel rides the building permit, a main-service upgrade is its own permit.
- **Permit lead times** `policy`: Every permit application is filed 2 weeks before job start — except TDEC septic, which is filed 6 weeks before; demo never starts without the building permit in hand.
- **Roof tie-in photos** `policy` _(when: the new roof ties into or over-frames the existing roof)_: Existing conditions are photo-documented on day one of roof framing.
- **TDEC septic trigger** `policy`: TDEC septic permitting applies only when the job modifies or installs a septic system — added bedrooms or bathrooms alone do not trigger it; never break ground while TDEC is pending.
- **Weathertight gate** `policy`: Interior work begins only once roofing is complete, and insulation/drywall are never scheduled before rough inspections pass.
- **Window ordering** `policy`: Windows and exterior doors are ordered at permit submittal; any non-stock size is verified for real lead time before the schedule assumes stock.

## Defaults

- **Below-grade package** `default` _(when: sloped-lot or walkout addition)_: assume a below-grade package runs between foundation and framing: waterproofing and drainage board on the below-grade wall, foundation drain with filter fabric sloped to daylight, gravel backfill — unless engineering specifies otherwise.
- **Completion milestone** `default`: assume the job-complete milestone is the PM's personal walkthrough with the customer, one working day after the last item (final inspection, landscaping, exterior finishes, deck) finishes — unless customer scheduling forces a different day.
- **Framing method** `default`: assume stick-frame for small additions — unless scope explicitly specifies trusses, roof span exceeds ~24 ft, footprint exceeds ~800 sqft, or the PM confirms trusses.
- **Front-loaded schedule pressure** `default`: assume compression pressure belongs before interior finishes; from interior finishes onward the schedule keeps intentional slack and the back half is not panic-compressed — unless the PM explicitly directs compressing closeout.
- **HVAC type** `default`: assume mini-split — short line-set rough, no separate rough-in phase — unless scope says "ducted", "duct work", or "air handler" (duct-extension path applies); if still ambiguous, ask rather than guess.
- **LVL-omitted risk** `default` _(when: structural documents contain "LVL omitted, sized per IRC" language)_: assume carry it as a flagged change-order risk — value-engineered engineered lumber tends to come back as a change order after final engineering — unless final engineering is already complete.
- **Retro-phase detection** `default`: assume work belongs in its own Retro-phase item (pre-addition work on the existing home) when any signal fires: area mismatch with the addition objective, "existing" language in scope text, or unresolved spatial location for a new feature — unless the PM explicitly folds it into the addition's new-construction scope.
- **Tie-in settling cracks** `default`: assume hairline drywall cracks at new-to-existing tie-ins (above doors, windows, headers) are an expected year-one settling issue handled as a 1-year-warranty return visit, not a scheduled job task — unless cracking is structural or beyond hairline.

## Calibration

- **Water heater plumbing delay** `calibration` _(when: scope includes a new tank or tankless water heater)_ — rough plumbing start delay:
  - added delay: 1 working day (tank is set before rough-in stubs into it; merely extending an existing heater's vent adds nothing)

## Reference

- **Habitable space threshold** `reference` — storage/crawl level classification _(source: IRC practice)_:
  - non-habitable clear height: under ~5 ft (no habitable-space code paths; access (e.g. exterior barn doors) rides in exterior finishes, not interior)
- **Window lead times** `reference` — window and exterior door lead times _(source: TCR supplier experience)_:
  - stock sizes: 21 calendar days
  - non-stock / custom sizes: verify with supplier before scheduling (silent lead-time trap — the schedule may assume stock lead for what is actually a custom unit)
