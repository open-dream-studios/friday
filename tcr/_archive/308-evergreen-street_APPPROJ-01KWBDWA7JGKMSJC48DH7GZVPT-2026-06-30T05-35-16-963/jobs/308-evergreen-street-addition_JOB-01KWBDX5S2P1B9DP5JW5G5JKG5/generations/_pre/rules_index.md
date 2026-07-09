---
generation_kind: intel_gather_v1
artifact: rules_index
last_verified_at: 2026-06-30T05:00:00Z
---

## Company Rules

- **dev_rules.md §4A — Permits = 1-day work task** — this job requires permits per IRC 2018/NEC; model as `general.permitting` kind:work 1d not a lead_time wait
- **dev_rules.md §4B — Monolithic foundation is the DEFAULT** — scope explicitly says 12"×12" continuous footings + 4" slab, no CMU/stem walls → monolithic pour applies; one footing inspection covers both
- **dev_rules.md §4C — Rough inspections MUST be bundled** — job has full MEP rough (electrical, plumbing, mini-split line set) + framing → all four bundle into one inspector visit
- **dev_rules.md §4D — 2–4 day punch-list buffer after rough inspections** — standard addition; default 2 working days lag after rough_bundled before insulation
- **dev_rules.md §4E — Paint is ALWAYS two phases (mandatory)** — job has drywall throughout new addition + bedroom remodel + hall bath retrofit; paint.phase_1 and paint.phase_2 both required
- **dev_rules.md §4F — Paint phase_2 = LAST work task; gates ALL finish trades** — must include trim.install, flooring.install, cabinets.install (vanity), tile.grout_seal, plumbing.finish, electrical.finish, hvac.minisplit_install
- **dev_rules.md §4G — HVAC type drives MEP order** — scope confirms mini-split ("ductless mini-split system") → MEP rough order: plumbing → electrical → mini-split line set
- **dev_rules.md §4H — Tank set FIRST (conditional)** — base scope says "extend existing gas WH vent through new roof" (vent-only, no new tank); existing WH stays → DO NOT emit procurement.tank or plumbing.tank_set in base scope. If tankless optional package is added, this rule activates.
- **dev_rules.md §4I — MEPs depend on underlayment + windows, NOT dried-in milestone** — addition project; all rough MEP tasks gate on roofing.underlayment AND windows.install
- **dev_rules.md §4J — Windows install IMMEDIATELY after roof framed** — windows.install FS after framing.roof (parallel with roofing.underlayment); NOT after dried-in milestone
- **dev_rules.md §4K — Heat pump relocation BEFORE demo** — scope explicitly calls out "relocate existing heat pump and electrical disconnect" → prep.heat_pump_relocate in site_prep phase, minimum 3 days before demo
- **dev_rules.md §4L — Interior finish dependencies strict** — flooring after paint.phase_1 + shower pan; trim after flooring; electrical.finish after paint.phase_1 (NOT paint.phase_2); plumbing.finish after cabinets + flooring + tile.grout_seal
- **dev_rules.md §4M — Final inspections = ONE day, ONE inspector** — bundled final electrical + plumbing + HVAC + building inspection
- **dev_rules.md §4N — 2-trades-max interior HARD constraint** — standard 3-finish-trade overlap (electrical.finish + plumbing.finish + hvac.minisplit_install) → apply default HVAC-after-electrical stagger
- **dev_rules.md §4O — Equipment day-before-phase + 2-week checkpoint** — demo phase needs dumpster + concrete saw/mini-ex; roof/siding phase needs scaffolding; excavation needs mini-ex
- **dev_rules.md §4P — Selections-finalized checkpoint (mandatory)** — checkpoint.selections_finalized in pre_construction, 3 weeks before on-site start; gates finish material procurement (tile, LVT, vanity, fixtures, paint)
- **dev_rules.md §4Q — Trusses procurement CONDITIONAL** — scope says "truss or rafter framed, determined during design phase" = ambiguous, NOT explicit trusses; footprint 590 sqft addition, span ~10' → stick-frame default; DO NOT emit procurement.trusses
- **dev_rules.md §4R — Procurement uses 3-task pattern** — windows (21-day lead), LVL beam (7-14 day lead), mini-split unit (7-14 day lead), electrical panel (7-14 day lead), tile/vanity/fixtures must all use order/wait/checkpoint pattern
- **dev_rules.md §4S — Free-floating PC tasks need pre_construction_offset_working_days** — permit (offset 15), selections checkpoint (offset 15), equipment checkpoints (offset 10) must all have this field set
- **dev_rules.md §4T — Lead-up windows on PM prep tasks** — selections_finalized (lead_up 5), permitting (lead_up 2), equipment checkpoints (lead_up 2), order.* tasks (lead_up 2) must have lead_up_working_days set
- **dev_rules.md §4U — No-op checkpoints FORBIDDEN** — every checkpoint.* must have a downstream consumer
- **dev_rules.md §4V — Customer early items and retrofit in same area = SEPARATE components** — hall bath has both an acrylic shower swap (customer early item?) AND retrofit window/drywall work → verify with PM whether shower swap is a Day-1 early item or concurrent retrofit
- **dev_rules.md §9 — Retrofit detection** — hall bath modification (Signal A: area outside addition objective; Signal B: "existing" hall bathroom; Signal C: new features in existing space) → separate component; primary bedroom remodel also retrofit (Signal A + B)
- **dev_rules.md §11 warning #27 — Spatial ambiguity** — elevator shaft location(s), basement storage lighting, relocated windows are in/near existing structure; confirm which are new addition vs. retrofit
- **editor_rules.md — Plumbing rough-in duration** — job has master bath (2 lavs + toilet + custom shower), W/D relocation, vent stacks through roof → 4 working days × 2 crew minimum per Will's nominal
- **editor_rules.md — Drywall consolidation** — consolidate new addition + primary bedroom remodel + basement storage + hall bath patch into ONE drywall hang/tape/sand block (9-11 days typical)
- **editor_rules.md — Same-crew exterior pattern** — siding + trim/fascia/soffit + gutters run as one continuous crew block
- **editor_rules.md — Concealed roof tie-in** — 3/12 new into existing 6/12 with valleys/transitions; no explicit scope for structural mods at tie-in; flag as schedule risk in assumptions
- **plumbing_rough_min_duration.md** — job includes master bath with multi-fixture layout + W/D relocation → 4 working days × 2 crew hard floor (this is a company rule, not just editor guidance)

## Company Beliefs

- **stick_frame_default_for_small_additions.md** — roof span ~10' (<24'), addition footprint 590 sqft (<800 sqft), scope says "truss or rafter TBD during design" = ambiguous → stick-frame default applies; no procurement.trusses task needed unless PM Interview confirms otherwise

## Job-Type Rules

- *(No job_types/addition/ rules folder detected in context — addition-specific rules are embedded in dev_rules.md sections 4I, 4J, 4K and editor_rules.md)*
