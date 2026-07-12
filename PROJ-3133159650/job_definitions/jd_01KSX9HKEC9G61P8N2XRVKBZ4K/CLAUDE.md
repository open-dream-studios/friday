# Addition rules — TCR job-type knowledge for room and structure additions

This document is the addition-specific layer on top of the company-level
editor rules. It captures what an addition needs that other job types do
not: the permitting realities, the long-lead structural items, the
retrofit patterns that almost always show up, and the change-order risks
unique to tying new construction into existing structure.

Use this document when the project scope describes adding new square
footage to an existing home (bedroom addition, bathroom addition, master
suite addition, second-story addition, garage conversion to living space).
For pure interior remodels of existing space, use the company editor
rules baseline without this layer.

---

## Septic — the silent long-lead item

For additions that add a bedroom, a bathroom, or any other fixture that
the TDEC (Tennessee Department of Environment and Conservation) counts
against septic capacity, the septic permit process is the longest single
lead time in the project and often determines the realistic start date.

Septic work is only needed if it's specifically called out in the scope
of work.

**The TDEC process (~6 weeks total):**

1. Initial contact with TDEC.
2. Soil scientist site test ($500 permit fee + scientist's time).
3. Soil report completed by TDEC.
4. TDEC review and permit issuance.

End-to-end this is typically 4–8 calendar weeks from first contact to
permit-in-hand. Treat it as a `lead_time` task in `pre_construction` with
`lead_time_days: 70` minimum.

---

## Structural long-lead items

Two structural items consistently drive the addition critical path:

**Roof trusses (custom).** 4–6 weeks lead time from order to delivery.
Order at structural sign-off, well before framing starts. Trusses can
land weeks before they're installed without issue. Use
`lead_time_days: 35` as the default.

**LVL beams.** Although nominal lead time is 7–14 days, default to 21
days for safety when an LVL is on the critical path. LVL availability
fluctuates with lumber market conditions and "next week" can quietly
become "three weeks" without notice. Better to early-order and have the
beam waiting than to halt framing.

Both belong in `pre_construction` as procurement tasks gating the
relevant framing tasks via FS.

---

## Windows — order at permit submittal

Windows are ordered a minimum of 21 calendar days prior to demo / first
phase of project, not at framing start. Custom windows (28–42 days)
usually arrive just-in-time. Verify with the customer whether windows are
custom or standard order — the answer changes the lead-time task.

---

## Retrofit detection — almost always present in additions

It is rare for an addition project to be ONLY new construction. The
addition almost always disturbs existing space (the wall where the new
addition ties in is usually load-bearing; new bedrooms often trigger
existing-bath modifications for code or layout reasons; new master suites
often involve closing off or repurposing an existing hallway or closet).

When a breakdown section describes work on an area that is NOT the
addition objective, treat it as retrofit:

1. Put it in its own Component, not commingled with the new-construction
   Components.
2. Do NOT gate retrofit work on new-construction dependencies that don't
   physically apply (a hall bath modification is not waiting on the new
   exterior framing of a bedroom addition).
3. Retrofit work runs in parallel with new construction wherever the
   trade and crew constraints allow.
4. Emit a `warnings[]` entry naming the retrofit section and what tipped
   you off (e.g. "section X mentions hallway bath; addition objective is
   bedroom — flagging as retrofit").

Also, suggest to the user a list of retrofit items on the project. After
user confirms them, ask them to list any other work not specifically
listed before finalizing the retrofit items — including when each should
be completed during the project.

**Common retrofit patterns to watch for in additions:**

- New bedroom addition → existing hall bath modified for layout or code.
- New master suite → existing master closet repurposed or hallway
  reframed.
- Second-story addition → existing first-floor electrical panel upgraded
  for new load.
- Garage-to-living conversion → existing HVAC or panel modified to feed
  the new conditioned space.

---

## Customer-requested early items

It's common for the client to request a small piece of work be done
BEFORE the main addition starts (a shower swap, a leaky fixture, a quick
demo) so they can live with it during the months of construction. These
appear as small sections in the breakdown; verify whether they are a
critical-path task or portion.

Treat them as standalone tasks scheduled in `pre_construction` or very
early in the on-site timeline. Verify whether they gate on permitting,
framing, or any addition-specific predecessor. Surface in `assumptions[]`
if you're not sure whether a small section is a customer-requested early
item versus part of the addition scope.

---

## Concealed roof tie-in — change order risk

When the addition's new roof ties into the existing roof, the structural
conditions ABOVE the existing ceiling are concealed until demo opens them
up. The existing rafters or trusses may not be sized to accept the new
load, or may have hidden damage, or may be framed in a way that doesn't
permit a clean tie-in.

Emit a `warnings[]` entry whenever a section describes roof tie-in to
existing structure, naming concealed-condition risk and recommending a
2–3 day schedule buffer immediately after the concealed area is opened
up. The buffer absorbs the discovery-and-redesign cycle that may follow.

---

## Existing electrical service — amperage check before subpanel

If the addition's electrical scope includes a subpanel feeding the new
space, the existing main service amperage MUST be checked or verified.
Typically homes have a 200A service, but may not have space to accept the
subpanel without a service upgrade. The amperage check is a 0.5-day task
in `pre_construction` (general trade), and its result drives whether the
project needs an added service-upgrade scope.

If the breakdown includes a subpanel but no service-upgrade section, emit
a `warnings[]` entry: *"subpanel scope present, no existing-service
amperage verification — flag for PM to confirm main service capacity
before signed contract."*

---

## LVL temporary shoring — independent retrofit

When the project requires an LVL beam to replace an existing load-bearing
wall (very common in additions that open up the existing floor plan to
the new space), the temporary shoring + LVL install + permanent shoring
removal is its OWN sub-chain. It is gated by demo (the wall has to be
exposed) but it is NOT gated by new-construction framing.

**Sequence:**

1. `demo.expose_bearing_wall` (1d, demo)
2. `structural.temporary_shoring` (0.5d, framing)
3. `structural.install_lvl` (1–2d, framing, FS after `procurement.lvl`)
4. `structural.remove_shoring` (0.5d, framing)
5. `inspect.framing` covers this work along with the rest of new framing

This sub-chain can run in parallel with new exterior framing. Don't gate
new framing on it unless the new floor or roof load actually bears on
the LVL location.

---

## Material ordering for additions — interior finishes wait

The general "order tied to use date" rule from the company editor rules
is especially important for additions because there is a substantial gap
(often 4–6 weeks) between project start and the interior finish phase,
taken up by foundation, framing, and roof dry-in. Interior finish
materials (tile, cabinets, fixtures, flooring) are ordered AFTER the
structural shell is underway, not at project start.

**Exceptions:**

- Long-lead cabinets (42–56 days) may need to be ordered at structural
  sign-off to hit the cabinet install date.
- Long-lead tile (custom, 14–21 days) ordered ~3 weeks before tile
  install starts.

Everything else (paint, flooring, trim, standard fixtures) needs to be
on site 2 weeks ahead of use date. Typical delivery for these standard
items is ~1 week. Net: order ~3 weeks prior to starting the work.

---

## Addition-specific phase additions

For additions, insert these on top of the company editor rules spine
where the scope calls for them:

- `pre_construction.tdec_septic` — if septic-impacting fixture is added.
- `pre_construction.amperage_check` — if subpanel is in scope.
- `structural_and_shell.roof_tie_in` — its own Component, with the
  concealed-condition buffer attached.

---

## Mandatory addition warnings

In addition to the base mandatory warnings in the company editor rules,
emit these when the conditions apply:

1. Roof tie-in to existing structure is in scope, but no schedule buffer
   is reserved after the concealed area is opened up.
2. Subpanel is in scope, but no existing-service amperage verification
   task is present.
3. New-construction sections and probable retrofit sections are mixed
   into the same Component.
4. Truss or LVL procurement is missing from `pre_construction` even
   though the breakdown includes framing that requires them.

---

## Will's Walkthrough — closing every addition

For home addition jobs, add a final checkpoint at the end of the job —
the very last thing — called **"Will's Walkthrough"**, scheduled one day
after the final item. Will goes to the home, visits the customer, and
closes the job with a personal final walkthrough. This is the customer's
last touchpoint with TCR and non-negotiable for additions.
