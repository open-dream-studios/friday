---
generation_kind: intelligence_interview_v2
depends_on:
  - _projects/308-evergreen-street_APPPROJ-01KWD458DXBEREH8PWBJTFEADS/jobs/308-evergreen-street-addition_JOB-01KWD49ZCC89C3TCH1MZVJEV2P/manifest.json
  - _projects/308-evergreen-street_APPPROJ-01KWD458DXBEREH8PWBJTFEADS/jobs/308-evergreen-street-addition_JOB-01KWD49ZCC89C3TCH1MZVJEV2P/interview/round-1.md
---

# PM-confirmed facts

## Permits & pre-construction

- Home is on SEPTIC; TCR owns the TDEC permit process including soil-scientist coordination. Carry $500 TDEC fee + 6-week (42 calendar day) lead as a hard pre-construction line item. Emit `permit.tdec_septic` with `lead_time_days: 42` calendar and `pre_construction_offset_working_days: 30` per `job_types/addition/rules/tdec_septic_permit_offset.md` (rank 200). *(round 1, q.septic_tdec)*

## Customer early items

- No customer early items in scope. Do NOT split hall bath into a Rule-4V two-bucket pattern. The hall-bath acrylic shower swap stays INSIDE the single `hall_bath_mod` retrofit Component in `interior_finishes` — NOT a Day-1 `site_prep / customer_early_items` task. *(round 1, q.customer_early_items)*

## Retrofit components

- Hall-bath modification (window removal + infill framing, insulation, drywall patch, repaint, tub/shower → acrylic shower swap) is RETROFIT in existing space — NOT inside the addition footprint. The only physical dependency on new construction is shared drywall consolidation: a single Level-3 finish pass spans addition + hall-bath patch. The `hall_bath_mod` Component runs in parallel with main scope; the drywall portion folds into `drywall.consolidated`. *(round 1, q.retrofit_hall_bath_confirm)*
- The 4'×4' future elevator shaft sits INSIDE the new addition footprint — framing-only stub, no install. Aligns with shaft + dedicated 30A circuit shown on the drawings. Treat as part of normal addition framing; do NOT carve out a retrofit Component for it. *(round 1, q.retrofit_elevator_shaft)*

## Structural & roof framing

- Roof framing is STICK-FRAME on site (3/12 gable tying into existing 6/12) — chosen for tie-in flexibility against the existing 6/12. Do NOT emit `procurement.trusses`; the truss long-lead chain is OFF. Lumber arrives day-of with the framing crew. *(round 1, q.roof_framing)*
- The 3-ply 14" LVL beam is STANDARD STOCK SPF/LVL — NOT pressure-treated, NOT custom. Order through the normal lumber supplier. `wait.lvl` `lead_time_days: 14` calendar (no bump to 21). *(round 1, q.lvl_type)*
- The LVL beam BEARS LOAD — new floor + roof above transfer through the 15'-6" span; engineer-stamped sizing required. `framing.floor_system` (and any new roof load path resting on the LVL) MUST gate FS-after `structural.install_lvl`. The LVL sub-chain is NOT an independent parallel retrofit. *(round 1, q.lvl_load_bearing)*

## Procurement

- Windows: (3) 36"×60" DH are STOCK; (1) transom is SEMI-CUSTOM with a 4–6 week (28–42 calendar day) lead. All 4 units ordered in a SINGLE PO to avoid second-trip shipping. Pin `wait.windows` `lead_time_days: 42` calendar (upper bound — the transom dictates the bundle). `checkpoint.windows_arrived` gates on the slowest unit. *(round 1, q.window_order_type)*
