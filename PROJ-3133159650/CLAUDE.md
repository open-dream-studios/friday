 # About Tri Cities Remodeling (TCR)

  TCR is a residential remodeling company based in Johnson City, Tennessee, serving the broader Tri Cities region (Johnson City, Bristol, Kingsport, and surrounding Washington/Sullivan/Carter counties). Core work: bathroom remodels, kitchen remodels, and home additions (single- or multi-story — both are within scope). More broadly, TCR takes on most residential remodeling and renovation work; there are few residential job types they turn down outright. The main hard "no" is ground-up new-construction builds. Commercial work and exterior-only projects are generally avoided but not categorically refused — evaluate case-by-case rather than declining automatically. Do NOT raise "is this within TCR's scope?" as a question unless the scope clearly falls outside residential remodel/renovation territory (e.g. a request to build a new house from foundation up).

  Owner + primary decision-maker: the company owner. Everything material — pricing, scope, subs, timelines — routes through the owner. Assume PM-level decisions default to the owner until the intelligence layer explicitly says otherwise. Only cite a specific person by name when they are named on the current entity's data.json (e.g. `lead_employee`, `customer`).

  Design ethic: mid-to-upper mid-market. We compete on execution quality and speed, not lowest price. Most customers came via referral or Google (site: tricitiesremodelingco.com).

  ---

  ## Team model

  We run a hybrid: small in-house crew + trusted subs. This split is the single most important thing to understand about how we operate.

  **In-house crew (~6 people, ballpark):**
  - Framing, drywall, tile, carpentry, punch-list, finish work
  - Anything that touches the customer's living space and needs quality control on our name
  - Anything that has to happen fast, cleanly, on a scheduled day (customers get frustrated when we don't show)

  **Trusted subs (long-standing relationships, not one-offs):**
  - Demo (fast, cheap, dirty — no reason we should burn crew hours)
  - Rough electrical + rough plumbing (licensed, insured, permits)
  - HVAC changes when we open ceilings
  - Cabinet installers on kitchens (specialists move faster than general crew)
  - Countertop templating + install
  - Custom glass (shower doors, mirrors)
  - Painting on larger jobs — smaller jobs stay in-house

  **Rules of thumb for sub vs in-house:**
  1. Skilled trade with licensing/permit implications → sub, always.
  2. Repetitive commodity work (demo, drywall hang) where speed wins → sub.
  3. Anything the customer will look at every day for 20 years → in-house.
  4. If the sub is 2x faster AND the quality bar is standard → sub.
  5. Never split framing between sub and in-house. One team owns the shell.

  Margins matter. In-house is more expensive per hour but zero coordination overhead. Subs are cheaper per hour but need scheduling + payment terms + fallback plans. Rule of thumb: if in-house can do it in 1 day, use them; if it'd take them
  3+, sub it.

  ---

  ## Job types + typical shape

  - **Bathroom remodel** — 4-8 weeks depending on scope. Typical: demo (1-2 days), rough MEP (2-3 days), tile + waterproofing (5-8 days), fixtures + finish (1 week). Permit pull always. Customer picks tile + fixtures BEFORE demo starts, no
  exceptions (this rule cost us 3 miserable jobs before I locked it in).
  - **Kitchen remodel** — 6-10 weeks. Cabinet lead time is the pacing constraint. Order cabinets FIRST, schedule the demo to land when cabinets ship. Countertops are templated after cabinets in — never before, never based on drawings.
  - **Home addition** — 10-16 weeks. Permit review can eat 3-6 weeks alone in Johnson City. Foundation + framing weather-dependent (avoid mid-Dec through mid-Feb).

  We do not take on jobs under $15k. Not worth the overhead. If a lead comes in for something smaller (small tile fix, single vanity swap), refer out.

  ---

  ## Scheduling philosophy

  - **We honor start dates.** If we said Monday, we start Monday. If we can't, we tell the customer at least 3 business days ahead. This is a hard cultural rule and drives 90% of our positive reviews.
  - **We do not run two active jobs of the same trade in the same week** if it stretches the crew. Better to sequence than to half-do both.
  - **Weather buffer** — every outdoor-touching phase gets a 20% timeline buffer built into estimates. It's real and customers accept it.
  - **Fridays are punch-list / walk-through days** on wrapping jobs. Not new demo starts.
  - **Never demo without materials on site** for the next phase. Empty rooms with no next step erode trust fast.

  Priority order when conflicts arise:
  1. Customer safety / active leak / no-heat situation → stop everything, respond same day
  2. Scheduled start date on a signed contract
  3. Punch-list on a job we're 90% done with
  4. New sales / estimates
  5. Everything else

  ---

  ## The TCR phase spine

  Every TCR job moves through the same general spine. Skip a phase that doesn't apply rather than inventing a new one — phases are constraints, not categories, and fewer is better than more.

  | order | phase id                 | name                                            | pre-construction |
  |------:|--------------------------|-------------------------------------------------|------------------|
  | 0     | `pre_construction`       | Permits, ordering, planning                     | yes              |
  | 1     | `site_prep`              | Dumpster, equipment delivery, site protection   | no               |
  | 2     | `demo_and_protection`    | Demolition, abatement if needed, haul-out       | no               |
  | 3     | `structural_and_shell`   | Excavation, foundation, framing, roof dry-in    | no               |
  | 4     | `rough_trades`           | Rough plumbing, electrical, HVAC                | no               |
  | 5     | `rough_inspections`      | Bundled rough MEP + framing inspections         | no               |
  | 6     | `insulation_and_drywall` | Insulation, drywall, prime                      | no               |
  | 7     | `interior_finishes`      | Tile, flooring, trim, cabinets, paint coat 2    | no               |
  | 8     | `finish_trades`          | Plumbing finish, electrical finish, HVAC finish | no               |
  | 9     | `closeout`               | Punch list, final clean, final inspection       | no               |

  `pre_construction` always includes: permitting (~14 calendar day default lead time), procurement for anything with >7 calendar days of lead time, and short 1–2 day selection tasks for tile, fixture, paint choices.

  ---

  ## Default crew sizes + productivity

  Starting numbers used to translate `labor_hours` into duration. Override per section if the breakdown clearly implies different staffing.

  | Trade           | Default crew | Productivity                                                                   |
  |-----------------|--------------|--------------------------------------------------------------------------------|
  | general         | 2            | Permitting / site PM                                                           |
  | demo            | 3            | ~150 sqft/day for selective interior demo                                      |
  | abatement       | 2 (cert.)    | Asbestos/lead — gates demo; subbed to certified contractor                     |
  | excavation      | 2 + machine  | ~30 cy/day with mini-ex                                                        |
  | concrete        | 4            | Footings ~40 lf/day; flatwork ~200 sqft/day                                    |
  | masonry         | 2            | Brick ~150 brick/day; chimneys ~1 day each                                     |
  | framing         | 3            | Walls ~250 sqft/day; floor systems ~300 sqft/day                               |
  | roofing         | 3            | Shingle ~10 sq/day                                                             |
  | siding          | 3            | ~250 sqft/day for lap siding                                                   |
  | windows_doors   | 2            | ~3 windows/day install incl. flashing                                          |
  | glazing         | 2            | Shower glass ~0.5 day install; templating + fab adds 1–2 weeks                 |
  | electrical      | 2            | ~6 rough boxes/hour; finish slower                                             |
  | plumbing        | 2            | ~4 hr/fixture incl. supply + DWV                                               |
  | hvac            | 2            | Mini-split day-of-install; ducted varies                                       |
  | insulation      | 2            | ~400 sqft/day batts                                                            |
  | drywall         | 3            | Hang 1000 sqft/day; finish 3-day cycle                                         |
  | paint           | 2            | Prime + 2 coats: ~400 sqft/day finished                                        |
  | flooring        | 2            | LVP ~250 sqft/day; tile slower                                                 |
  | tile            | 2            | Wall tile ~30 sqft/day; floor tile ~50 sqft/day                                |
  | trim_carpentry  | 2            | Base/case ~150 lf/day                                                          |
  | cabinets        | 2            | Kitchen install ~1.5 days; vanities 0.5 day                                    |
  | countertops     | 2            | Templating + install, 2 visits                                                 |
  | appliances      | 1–2          | Delivery + install; coordinate with cabinets, plumbing finish, electrical      |
  | landscaping     | 2            | Site restoration / final grading; sod ~1000 sqft/day                           |
  | cleanup         | 2            | Final clean — ~0.5–1 day bathroom; 1–2 days whole-house                        |
  | inspector       | 1            | 0.5-day blocks, requires scheduling lead time                                  |

  ---

  ## Lead-time items (procurement)

  Each becomes a `procurement` task with `lead_time_days` in calendar days, `crew_size = 0`, `duration_days = 0`. Purpose: gate the downstream install task via FS.

  | Item                       | Typical lead time         | Order trigger                    |
  |----------------------------|---------------------------|----------------------------------|
  | Permits                    | 14 calendar days          | At signed contract               |
  | Windows (stock)            | 14–21 days                | At permit submittal              |
  | Windows (custom)           | 28–42 days                | At permit submittal              |
  | Exterior doors (custom)    | 21–28 days                | At permit submittal              |
  | LVL beams                  | 21 days                   | At structural sign-off           |
  | Roof trusses (custom)      | 28–42 days                | At structural sign-off           |
  | Mini-split unit            | 7–14 days                 | Before rough HVAC                |
  | Tankless water heater      | 7–14 days                 | Before rough plumbing finish     |
  | Custom cabinets            | 42–56 days                | Once cabinet layout final        |
  | Countertops (slab)         | 14 days from template     | After cabinets installed         |
  | Tile (custom)              | 14–21 days                | Before tile install start        |
  | Electrical panel           | 7–14 days                 | Before rough electrical          |
  | Glass shower enclosure     | 7–14 days from template   | After tile shower complete       |

  **Will's rule on ordering:** materials are tied to use date, not project start. Short jobs (bathroom ~2–3 weeks on-site) — order nearly everything up front because the use date is close. Longer jobs with a roof phase between project start and interior finish — order interior finish materials closer to that phase so they don't sit on site. Job-type docs may override with item-specific timing.

  ---

  ## TN residential inspection sequence

  Inspections are gates — the downstream trade cannot start until the inspection passes. Each is a 0.5-day `inspection` task with a 1-day scheduling lead (`FS lag_days: 1` on the edge before the inspection).

  1. Footing — before pour. Predecessor: footing forms set.
  2. Foundation / slab — after slab pour, before backfill.
  3. Rough electrical — after rough-in, before insulation.
  4. Rough plumbing — after rough-in, before insulation.
  5. Rough HVAC — after rough-in, before insulation.
  6. Framing — AFTER rough MEPs (MEPs drill the framing).
  7. Insulation — after insulation, before drywall.
  8. Final E/P/M — after finish trades, before CO.
  9. Final building — the last gate before close-out.

  Inspections 3–6 are bundled into the same day with the same inspector whenever possible. Inspections 7 onward are typically separate visits.

  ---

  ## Trade dependency cheat-sheet

  | Trade                          | Must finish before this trade starts        | This trade gates                       |
  |--------------------------------|---------------------------------------------|----------------------------------------|
  | Demolition                     | Project start, after permits                | All structural work                    |
  | Excavation                     | Demo + site prep                            | Foundation                             |
  | Foundation                     | Excavation; footing inspection              | Framing                                |
  | Structural mods (LVL/shoring)  | Existing structure exposed                  | Floor/roof loading above               |
  | Framing                        | Foundation cured; structural mods if any    | Roofing, exterior, rough trades        |
  | Roofing                        | Roof framing + sheathing                    | Interior protection (dried-in)         |
  | Windows/exterior doors         | Framing                                     | Insulation, weather barrier            |
  | Exterior siding                | Windows installed, weatherproofing          | None for interior critical path        |
  | Rough electrical               | Framing complete                            | Insulation                             |
  | Rough plumbing                 | Framing complete                            | Insulation                             |
  | Rough HVAC                     | Framing complete                            | Insulation                             |
  | Insulation                     | All rough trades inspected                  | Drywall                                |
  | Drywall                        | Insulation inspected                        | Interior finish                        |
  | Interior trim/paint/flooring   | Drywall                                     | Cabinets, final fixtures               |
  | Tile (wet areas)               | Substrate complete, plumbing rough done     | Plumbing finish                        |
  | Cabinets                       | Floor + drywall + paint complete            | Countertops                            |
  | Countertops                    | Cabinets installed                          | Plumbing finish (sink hookup)          |
  | Final inspections              | All trades complete                         | CO / closeout                          |

  ---

  ## Overlap + crew concurrency rules

  - Rough electrical, rough plumbing, rough HVAC can run in parallel using SS.
  - Roofing can start once roof sheathing is done; overlap with remaining exterior framing at `FS lag_days: -2` is common.
  - Exterior siding can start once dried-in, in parallel with rough trades.
  - Paint touch-ups can start before drywall finish completes — `FS lag_days: -1`.

  **Interior crew concurrency — Will's rule.** No more than TWO trades work concurrently inside the building. Space gets cramped and crews trip over each other. Outside there is no such limit (siding, landscaping, exterior paint all run alongside interior work). When a plan wants to overlap 3+ interior trades, emit a `warnings[]` entry and pick the two most schedule-critical.

  **Same-crew exterior pattern.** TCR's siding crew also does trim and gutters. Run those three as a single continuous block from the same crew. No lead time between them; no separate gutter procurement gate unless gutters are explicitly custom.

  ---

  ## Per-trade operational rules

  **Paint — two phases, not one.** Phase 1: prime + first coat, before trim and cabinets so painters aren't cutting around finish work. Phase 2: finish coat, after trim and cabinet install so painters can spot, caulk, and finish clean. Substantial completion ties to phase 2 finishing, not phase 1.

  **Drywall — consolidate zones.** Hang / tape / sand cycle with cure waits between. Model cure waits as FS `lag_days`, not duration. Multi-zone jobs (addition + retrofit bath) — consolidate drywall into a single hang block and a single finish block where possible rather than sending the crew back twice.

  **HVAC — mini-split vs ducted.** Mini-splits are day-of-install once equipment is on site: one task, one day, one crew, NO separate rough-in phase. Ducted systems have a rough-in (duct runs) and a finish (registers + equipment connect). Never model a mini-split job as if it had a rough-in phase.

  **Plumbing — tank set first.** If a water heater is in scope (tank or tankless), set the tank BEFORE plumbing rough-in begins. Rough-in stubs into the already-set tank. Order: `procurement.tank` → `plumbing.tank_set` → `plumbing.rough_in`.

  **Foundation — monolithic by default.** Prefer a monolithic pour (footing + slab in one pour) over separate footing and stem-wall pours. Collapses the footing inspection + cure + foundation-wall sequence into one inspection and one cure. Split only when the breakdown explicitly calls for stem walls or a basement.

  **Equipment delivery — day before, not day-of.** Dumpsters, porta-johns, scaffolding, lifts arrive the day BEFORE the phase that needs them, not on day 1. A dumpster lands the day before demo begins; a second dumpster (or swap) lands the day before drywall hangs; scaffolding lands the day before roof or siding starts. Equipment tasks are `general` trade, `duration_days = 0.5`, and gate the consumer phase via FS.

  ---

  ## Closeout — the punch-list workflow

  Closeout is not just final clean. It contains:

  1. PM walkthrough with the client — produces the punch list.
  2. Punch-list work (1–3 days, multiple trades coming back briefly).
  3. Final clean.
  4. Final building inspection (FS lag 2).
  5. CO + handoff.

  Each punch-list trade return is its own short task in `finish_trades` or `closeout`, NOT bundled into one "punch list" monolith.

  **Substantial completion** = paint phase 2 finishing. That is the milestone the client sees as "done"; closeout activities happen after but the project is functionally complete at that point.

  ---

  ## Pricing philosophy

  - **Gross margin floor: 30%.** Anything below that, we walk. We've held this line since 2024 and it's what keeps the business alive.
  - **Fixed-price contracts, always.** No T&M for residential work — customers can't budget it, we can't defend it in disputes.
  - **Change orders are written, signed, and paid before the change starts.** No exceptions, no "we'll square up at the end." Verbal changes have burned us every single time.
  - **Materials at cost + 15% markup**, itemized in the estimate. Labor is not itemized (opens debate).
  - **Deposit 25% at contract, 25% at demo start, 25% at rough-in inspection, 25% at completion.** Adjust for scope size but never let the customer get ahead of the work.

  Discounts: rare. We'd rather sharpen the scope than drop the price. If a customer pushes hard on price, offer scope-reduction (e.g. keep existing tub instead of replacing) — this is a real, valuable exercise anyway.

  ---

  ## Customer communication norms

  - **First response to a new lead: same business day.** Ideally within 2 hours.
  - **Weekly update on every active job**, even if nothing changed. "Here's where we are, here's this week's plan, here's what we need from you." Sent Monday morning.
  - **Never surprise the customer with a delay.** If we know Wednesday the tile won't arrive until Friday, they hear it Wednesday.
  - **Photos of anything we're closing up** (behind drywall, under tile) — for our records AND for the customer's warranty file.
  - **We do NOT provide competitive line-item pricing.** If the customer wants to compare us to another quote, they can compare the total. We're not itemizing labor to arm the shopper.

  Red flags to watch on customers:
  - Wants extensive changes after contract signed → tighten change-order discipline
  - Delays material selections beyond 2 requests → schedule slides, communicate hard
  - Multiple decision-makers with different opinions → get all of them in one meeting or the project will thrash
  - Suggests paying "off the books" → walk. Not worth it, ever.

  ---

  ## Quality bar

  - **Every job gets a walk-through with the customer at end-of-week during finish phase.** Punch-list items get logged same day.
  - **We warranty labor for 1 year**, materials per manufacturer. We honor it without argument — one grumpy repost on Facebook costs more than one $300 warranty visit.
  - **Photos in every job's inputs folder before-during-after.** For future reference, dispute defense, and marketing.
  - **We do not compromise waterproofing.** Ever. Kerdi or Wedi behind every tiled shower. Skimping here burns us 2-3 years later and we've had to rip out 2 showers in the past 3 years because a previous crew (before we tightened the
  standard) cheaped out.

  ---

  ## Edge cases + hard-learned rules

  - **Older homes (pre-1970): assume galvanized plumbing** somewhere and price accordingly. Every old-home bath remodel gets a "plumbing budget contingency" line item.
  - **Any home with a septic system**: check age. Overloading old drain fields with a new bath addition is a real risk we've hit once.
  - **HOA neighborhoods**: check HOA rules BEFORE the estimate. Some Bristol subdivisions require ARB approval for any external change; we've been surprised twice.
  - **Customer wants "just paint" as part of a bigger remodel**: fine, but scoped separately and priced separately. Painting always expands.
  - **Cabinet supplier lead times swing wildly** in Nov/Dec (holiday shipping). Any kitchen with a late-fall demo start needs the cabinet order placed by mid-September.
  - **Never open walls in the kitchen unless the customer has a working kitchen alternative** for the whole duration. Ideally staged: microwave + hot plate + fridge in the garage. Set expectations day one.

  ---

  ## What NOT to do

  - Do not schedule a job when the customer has not made final material selections.
  - Do not begin demo without the signed contract in hand AND the 25% deposit received.
  - Do not accept a job under $15k, no matter how "quick" it looks.
  - Do not run more than 2 simultaneous kitchen remodels unless the crew is genuinely bench-strength ready — cabinet-install week collisions destroy schedules.
  - Do not skip permits to save time. Ever.
  - Do not talk down the customer's designer / architect / neighbor's contractor. Even when they're wrong. Costs us referrals.
  - Do not tell a customer "we'll figure it out" when they ask about scope or price. Say "let me get you a written answer by end of day." Then do it.

  ---

  ## About the owner

  - Prefers structured, written communication (Slack, email, docs). Verbal decisions get lost.
  - Values clean data + clean systems. If you're making a decision that will affect future scheduling or intelligence, err on the side of writing it down.
  - Time-obsessed. Every hour saved is real money. Optimize for speed AT the quality bar, not below it.
  - Wants the AI to be direct. If something looks off, say so. Do not soften.

  If you're the AI reading this, the meta-lesson is: TCR wins by executing well on tight timelines with hybrid staffing. Every decision you help make should feel that value system. Speed + quality + margins, in that priority order after
  safety and honoring commitments.