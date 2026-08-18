# Status

Last updated: 2026-08-18

**What this document is.** A plain answer to *what is true right now*. It is deliberately short.

- **History** lives in git (`git log -p STATUS.md`). Don't keep superseded entries here.
- **Why** things are built as they are lives in `DECISIONS.md`.
- **What to do next** lives in `todo.fungi4u` in Home Assistant — the actionable worklist, ordered by distance to income.
- If an entry here is only interesting because of how it was discovered, it belongs in `DECISIONS.md`, not here.

---

## Priority order — read this first

The objective is income for the family, via *committable* supply → new clients. Ranked by distance to that objective:

1. **Demand / new clients.** Demand is the binding constraint, not yield. **⛔ The Menlo Park Spar step — the only concrete route ever identified — is BLOCKED as of 2026-08-08 (see below). Priority #1 is now to find a replacement route, NOT to fall through to #2.**
2. **Cheap yield levers** — single-variable airflow/humidity experiments.
3. **Everything else** — microclimate build-out, monitoring, telemetry, dashboards, doc hygiene. Enabler or insurance, not the front of the queue.

*(The harvest scale was #1 until it was bought on 2026-07-22.)*

**Standing test for any task:** does it move committable supply or a client this month? If not, it waits.

**The trap:** microclimate and monitoring work is more tractable and more enjoyable than sales, so it will keep pulling attention. Treat that pull as the cue to re-read this list. As of 2026-07-26 the room is fully in band and has no live crop emergency — so there is nothing here justifying more room work ahead of demand.

**🔴 AND 2026-08-08 IS EXACTLY WHEN THAT TRAP SPRINGS.** Spar is blocked, so the only *actionable* work left on the board is room and yield work — which will feel like the queue reordering itself honestly. **It is not.** The ranking above is by distance to income, and losing the route to income does not move room work closer to it. **A yield gain with no new customer produces unsold mushrooms:** the 3 existing customers won't take more, so extra output is worth only the substrate saved (~R680/mo total), not the R40/punnet it looks like. **Finding a second demand route is still the whole game.**

### 🔴 THE OBJECTIVE OF ALL THE ROOM WORK IS NOT BEING MEASURED (named 2026-08-01)

**The operator states the objective plainly: every change to the fruiting and grow rooms was to lift yield to what can be expected — roughly *double* current output.**

**✏️ CORRECTED 2026-08-01, by the operator, and it changes the required action.** An earlier version of this entry said the pre-change number *"exists only in the operator's head"* and asked for it to be written down. **Wrong — it does not exist at all.** *"There is no baseline from measurements in this business. My expectation is because of industry results that I hope to also achieve."*

**So the target is ABSOLUTE, not relative — and that is better news, because an absolute target needs no baseline.** "Did we double?" was never the answerable question. **"Are we at industry yield?" is**, and it can be answered from the very next batch.

- **The metric is biological efficiency** — **kg fresh mushrooms per kg substrate**. It is self-normalising: it needs no history, no before-and-after, and it is directly comparable to published industry figures.
- **✅ The ledger already derives it.** `v_substrate_biological_kpi` computes it from `harvest_pickings`, per `stock-control/docs/LEDGER.md` Phase B. **Nothing needs building.**
- **✅ The instrument already exists.** The bench scale was priority #1 until it was bought on 2026-07-22; `LEDGER.md` calls it *"the yield instrument… required tooling for the objective, not overhead."*
- **⬜ What is missing is only the habit and the number to compare against.**

**The asymmetry is still worth stating baldly: this room's CO2 is measured to the ppm across five instrumented nights, and its *yield* — the thing all of it was for — has one week of data.**

**➡️ Two actions, both cheap, both this week:**
1. **Write down the industry figure being aimed at, and where it came from.** Grey oyster BE is commonly quoted around **75–125% of dry substrate weight**, or roughly **15–25% of *wet* block weight** across all flushes — but **the ranges are wide and definitions differ (dry vs wet basis, one flush vs total), so a number without its basis is not a target.** Record the operator's own source, on its own basis. **Without this the KPI has nothing to be measured against.**
2. **Weigh every flush separately, by batch, before combining** — per `LEDGER.md`. That is what turns *"bigger mushrooms"* into the measured claim a new client can be committed on.

**This outranks every remaining microclimate item**, because it is the difference between knowing the work succeeded and believing it did.

### 🔴 THE SECOND FLUSH IS MISSED BY ONE DAY, NOT BY WEEKS — and "4–6 weeks" is not our number (2026-08-13)

**W27 decomposed from `v_batch_residence` + the picking timestamps. It is the ONLY batch that has ever reached a second flush.**

```
day  3      first pick                    (lag from move-in: 3 days)
day  3–18   FLUSH 1 — 13,052 g
day 18–22   rest — 4.2 days
day 22      FLUSH 2 STARTS                (budget with 3 trolleys = 21 days)
```

- **⛔ THIS FILE'S "a second flush needs ~4–6 weeks" AND "incompatible by roughly a factor of two" ARE NOT SUPPORTED BY OUR OWN DATA.** Those are literature figures. **Measured here: flush-2 onset at day 22 against a 21-day budget — a miss of ONE DAY.** The trolley/wall case has been argued on the wrong magnitude.
- **🔑 THE LEVER IS SYNCHRONY, NOT SPEED. Flush 1 ran days 3–18 — a 15-day span for 23 bags.** That is not a flush, it is bags pinning individually across a fortnight. **76% of the grams landed days 10–14; the day-18 picking was a 624 g straggler (4.8%) — and it is what pushes the rest period, and therefore flush 2, out to day 22.** If the bags pinned together, flush 1 would close ~day 14, the same 4-day rest puts flush 2 at ~day 18, and **three days of it fall inside the existing budget with no extra trolley.**
- **➡️ SO MICROCLIMATE CAN PLAUSIBLY DELIVER THE SECOND FLUSH WITHOUT BUYING ANYTHING** — bags pin on local conditions, and this room currently runs **0.8 °C top-to-bottom with VPD swinging 0.19–0.42 across a day.** Uneven conditions produce uneven pinning almost by definition. **This is the first argument that makes microclimate work income-tier rather than enabler-tier.**
- **📐 And the right metric while slots are the constraint is `grams_per_bag_per_week`, not BE** — the view already computes it. **W25 106.0 · W26 173.6 · W27 176.6.** BE says what a batch can do; g/bag/week says what a *trolley earns*.

⚠️ **Hinges on n = 1.** W27 is the only batch to reach flush 2. **W25 and W26 were both removed ON THE DAY of their last picking**, so nobody knows whether they were about to flush again. **Size of the move if wrong: the entire trolley-and-wall yield case.**

**🔬 THE TEST THAT SETTLES IT IS NEARLY FREE, AND IT NOW OUTRANKS THE TROLLEY PURCHASE: hold ONE batch 4–5 days past normal removal and weigh flush 2.** Cost is a few days of cadence disruption, once. **If flush 2 lands at 30–50% of flush 1, the compression case is made and you know how many days to find. If it is tiny, the second flush is not worth its slot-time and BOTH the trolleys and the wall lose their yield argument.**

### ✅✅ BIOLOGICAL EFFICIENCY IS MEASURED — 2026-08-13, first time. And the flush-2 column is the finding.

**Computed exactly as `v_substrate_biological_kpi` defines it**, over all **33 pickings** in the ledger *(the anon-readable `v_recent_captures` is capped at `limit 20` by design — do not compute yield from it, it truncates at 08-01)*. Route: `supabase db dump --linked`, CLI already authenticated.

| Batch | Substrate | Flush 1 | Flush 2 | **BE** | Status |
|---|---:|---:|---:|---:|---|
| W25 | 109,000 g | 6,676 | **0** | **6.1%** | ✅ removed 08-04 — final |
| W26 | 121,200 g | 11,782 | **0** | **9.7%** | ✅ removed 08-11 — final |
| W27 | 119,600 g | 13,052 | 294 | 11.2% | in room |
| W28 | 134,700 g | 4,234 | 0 | 3.1% | 1 picking |
| W29 | 104,500 g | 2,584 | 0 | 2.5% | 2 pickings |
| **All** | **589,000 g** | | | **6.6%** | 33 pickings, 07-24 → 08-13 |

- **⛔ AGAINST THE 15–25% WET-BASIS BENCHMARK, THE TWO COMPLETED BATCHES ARE AT A THIRD TO A HALF OF THE LOW END.** The question this file has called *"the objective of all the room work is not being measured"* now has a number.
- **🔑 BUT FLUSH 2 IS ZERO ON BOTH COMPLETED BATCHES, AND THAT REFRAMES IT.** They were pulled having given **one flush**. This file already establishes why: **3 fruiting slots against a weekly pack cadence caps residence at ~21 days; a second flush needs 4–6 weeks.** **So the batches were removed mid-cycle by the room's geometry, not because they were spent.** A second flush typically adds 30–50% of the first — **double W26 and you get ~19%, inside the band.**
- **➡️ THE YIELD GAP IS THEREFORE A RESIDENCE PROBLEM, NOT (YET) A BIOLOGY PROBLEM.** *"The room harvests half of each batch and discards the rest"* is now the measured reading. **This is the strongest evidence yet for more fruiting slots — trolleys or the wall — and it outranks every microclimate item, because no amount of climate tuning recovers a flush that was never allowed to happen.**
- **⚠️ Trend 6.1 → 9.7 → 11.2% across W25/W26/W27 is the direction the room work predicts, but is NOT clean** — W27 had a 20-day picking window against 11–12 days. **Do not bank it.**

✅ **HINGE CLOSED SAME DAY (operator): 4 kg is the AIM, not the actual.** `total_substrate_grams` is the **measured total batch weight**, so BE divides by real substrate and **the figures above stand as computed.** *(`HANDBOOK.md`'s "~24 × 4 kg bags" is a target and should be read as one.)*

### ⚖️ AND THE BAGS MISS THAT AIM EVERY TIME, ALWAYS HEAVY — mean 4.64 kg, +16% (2026-08-13)

| | kg/bag | vs 4 kg | | kg/bag | vs 4 kg |
|---|---:|---:|---|---:|---:|
| W30 | **4.050** | **+1%** | W33 | 4.665 | +17% |
| W29 | 4.354 | +9% | W32 | 4.705 | +18% |
| W26 | 4.489 | +12% | W31 | 4.747 | +19% |
| W23 | 4.600 | +15% | W25 | 4.955 | +24% |
| W28 | 4.645 | +16% | W27 | **5.200** | **+30%** |

**Mean 4.641 kg · spread 28% · CV 6.4% · not one batch under target.** A one-directional miss is a systematic bias, not scatter.

- **🔑 THE UNEXPLAINED PART POINTS AT WATER: total batch weight runs 93–135 kg against what should be a FIXED input.** `HANDBOOK.md` — two bales → one 110 L drum → *"exactly one batch"*. **A fixed drum of dry straw cannot vary 45% in mass; hydration can.**
- **➡️ IF IT IS WATER IT IS A YIELD LEVER, AND FREE.** BE divides by **wet** weight, so excess water depresses it mechanically — dividing by mass that was never food. **And over-hydrated substrate goes anaerobic in pockets**, which costs colonisation and invites contamination. **If it is straw, it is instead a cost line: ~16% more substrate bought and processed than the plan assumes.**
- **✅ ANSWERED SAME DAY (operator): NO WATER IS ADDED AT ALL.** The drum is drained, then the liner and its soaked straw are **left to drain further**, and that wet straw is bagged. **So the 28% spread is RESIDUAL DRAINAGE WATER, set by how long it is left — same dry straw in, variable water out.** ➡️ **The control variable is drain time, and it is free.**
- **⛔⛔ THE CONTAMINATION LINK IS DEAD, AND THE ANALYSIS THAT SUGGESTED IT WAS MEASURING THE WRONG THING (operator, 2026-08-13).** ~~r = +0.44 across 10 batches, heaviest bags holding the highest cull rates.~~ **WITHDRAWN. Bags are also culled to be USED AS SPAWN when grain spawn runs short — a productive reuse, not a loss — and it is recorded only in the note field.**

  | The 12 culls | Bags | |
  |---|---:|---|
  | **Contamination** | **5** | W25 ×1, W26 ×1, W30 ×3 — **all GROW room** |
  | **Used as spawn** | **6** | W25 ×2, W27 ×4 — **all FRUITING** |
  | Unlabelled | 1 | W27 2026-07-27, no note |

  **➡️ TRUE CONTAMINATION IS 5 BAGS IN 233 PACKED ≈ 2.1%, AND THE PATTERN INVERTS: W30 — the LIGHTEST batch at 4.05 kg — is the worst at 10.7%, while W27, the heaviest at 5.20 kg, is 0–4.3%.** *(Corrected rates: W30 10.7%, W25 4.5%, W26 3.7%, W27 0–4.3%, rest 0%.)* **So if anything the data leans the other way, and the over-wet-is-risky idea has no support at all.**

- **🔴 AND IT IS A SCHEMA DEFECT, NOT JUST A MISREADING — `v_batch_contamination` COUNTS EVERY CULL AS CONTAMINATION.** It is `round(100.0 * culled_total / packed_bags, 1)` off `v_batch_bag_state`, so **it overstates W27 by 5× and W25 by 3×.** **There is ONE reason code, `CULLED`; the distinction between *a bag that died* and *a bag deliberately taken for spawn* exists nowhere in the schema** — only in free text, and **one of the six records has no note at all.**
  - **⚠️ This file already uses cull rate as the contamination signal** *(W30's 10.7%, W31 as the test)*. **That particular number survives — all three of W30's were genuine — but the metric it rests on does not.**
  - **⬜ Minimum fix: a distinct reason code for spawn harvest**, so the two are separable in the ledger rather than in prose. **Worth doing on its own merits too — a fruiting bag taken as spawn SUBSTITUTES FOR GRAIN SPAWN, so it is an input saving, not merely a non-loss, and nothing currently counts it.** ⛔ **Do not fix this by grepping the note text in a view** — rules belong in the schema (`SAFETY.md`).
- **🔑 THE SOLID CONSEQUENCE IS MEASUREMENT, NOT BIOLOGY: BE divides by WET weight, so a 28% moisture spread makes cross-batch comparison partly a drainage measurement.**

  | | kg/bag | BE (wet, as recorded) | BE normalised to 4 kg |
  |---|---:|---:|---:|
  | W25 | 4.955 | 6.1% | **7.6%** |
  | W26 | 4.489 | 9.7% | **10.9%** |
  | W27 | 5.200 | 11.2% | **14.5%** |

  **Same harvest, different denominator — W27 moves to within touching distance of the 15% industry floor purely by removing carried water.** Neither column is wrong: wet-basis is what happened, normalised is what the biology did. **⚠️ But you cannot detect a 10% yield gain through a 28% moisture wobble** — and proving a yield gain is what the whole room programme is for. **➡️ Standardising the drain (a timer, or "until it stops dripping" — and recording which) removes the largest noise source from the only yield instrument, for free.**
- **🔬 W30 IS THE NATURAL EXPERIMENT AND IT IS ALREADY RUNNING — nothing to set up.** At **4.050 kg it is the only on-target batch**, currently 25 bags in the grow room, not yet moved to fruiting. **When it fruits it gives a clean read on whether on-target bags outperform**, against nine batches that ran 9–30% heavy. ⚠️ **Do not lose track of which batch it is.**



### 🧭 ROOM PROGRAMME — where it stands, 2026-08-01 (a checkpoint, not the end)

_Operator, 2026-08-01: **"a very good checkpoint but definitely not the end of the work on the rooms."** Correct, and it corrects an overstatement made the same day — "nothing left worth building" was true of the **vent experiment series**, not of the room programme. **The tuning phase is closed. The design is not finished.** Phases below are `stock-control/docs/MICROCLIMATE.md`'s own._

**✅ What is genuinely done.** Phases 0–2 have substantially run. The room is in band on every KPI, the humidifier is off its pin, the bottom-shelf gradient is closed, and — as of today — **the crop independently confirms it: bigger mushrooms, evenly across the shelves.** That is a real checkpoint and it should be banked.

**⬜ What remains, in dependency order. Only the first is this week's work.**

| # | Work | Why it is where it is |
|---|---|---|
| **1** | **Capture yield per flush, per batch** *(Phase 3 / KPI #0)* | **The gate on everything.** Free, the scale exists, the view exists. Until flushes are in the ledger, **nothing above can be shown to have improved the crop** — and no client can be committed on supply that cannot be demonstrated |
| **2** | **Restore the circulation design** — the parked revert test: fan → LOW, then return end cap, then supply end cap, one at a time | Was blocked behind the vent experiment, **now unblocked.** The room runs on a workaround the docs call *"not the settled design"*. Settle it **before** scaling it |
| **3** | **Fan run-confirmation** — power-monitoring plug upstream of the variac | **Orphaned safety item.** It lost its host when the Fan 2 rework was cancelled. The blindness has bitten once: a dead fan showed "82%" in HA for ~24 h. **Do not let it lapse again** |
| **4** | **Aircon: can it be kept out of the humid air?** Relocate, duct, or run without condensing | **The actual gate on the wall** — not volume. See below |
| **5** | **Humidifier capacity for the combined room** — spare 12-disc unit + fresh discs, already on hand | Size it **after** #4. Adding capacity to out-run a dehumidifier is treating the symptom |
| **6** | **Remove the divider wall** | Dissolves the documented three-way tension (separation vs temperature vs grow-room ventilation) — **and, added 2026-08-05, it is the only structural fix for the second-flush constraint: 3 batches of fruiting capacity against a weekly pack cadence caps residence at ~21 days, while a second flush needs 4–6 weeks. The yield case is now the stronger one.** |
| **7** | **Re-validate in the new geometry, then Phase 4 automation** | ⚠️ **Automating before the wall comes down is wasted work** — every setpoint, duty baseline and gradient changes when the room does |

**The honest sequencing point: #1 is the only item that pays off regardless of whether the wall ever comes down.** Everything from #2 down is investment in a room that is about to change shape. **That is an argument for doing #1 now and the rest deliberately — not for doing none of it.**

### 🧱 REMOVING THE DIVIDER WALL — first-pass capacity answer (2026-08-01)

_Operator's concern, and it is the right one to raise: **"I am not sure the equipment will be able to maintain the microclimate in the bigger fruiting room."**_

**🔴 CORRECTED 2026-08-11 (operator) — THE ROOMS ARE 2720 mm WIDE, NOT 7000. FLOOR AND VOLUME WERE OVERSTATED ~2.6×.** The fruiting and grow rooms occupy the **old drive-through garage — a 2720 mm-wide internal strip on the LEFT of the outbuilding, against the fence.** The **7000 mm is the OUTBUILDING's width** and was wrongly applied to these rooms. ✅ **The 08-06 divider survey stands** — 1820 mm front / 2280 mm back / 75 mm partition = 4175 mm internal correctly identifies **4650 mm as the front-to-back axis**, and the drive-through runs that way. **It was only the width that was wrong.** Full working: `stock-control/docs/MICROCLIMATE.md` §1.

**📐 REFINED 2026-08-11 (operator) — the depths now close EXACTLY.** Front→divider **1820 mm**, divider **50 mm** *(not 75)*, divider→back **2280 mm**. **1820 + 50 + 2280 = 4150 = 4650 − 2 × 250.** *(The 08-06 survey's 25 mm discrepancy was the divider thickness.)* **Plus a recess:** the old garage-door opening is closed by drywall on the **outside** face, so along **2490 mm of the 2720 mm back wall the grow room is 250 mm deeper** — +0.62 m², +1.6 m³.

| | Depth | Width | Floor (total) | Floor (**usable**) | Volume |
|---|---:|---:|---:|---:|---:|
| **Fruiting** (front) | 1820 mm | 2720 mm | **4.95 m²** | **4.95 m²** | **13.3 m³** |
| **Grow** (rear) | 2280 mm *(+250 recess)* | 2720 mm | **6.82 m²** | **6.20 m²** | **17.7 m³** |
| **Combined** | 4150 mm | 2720 mm | **11.78 m²** | **11.15 m²** | **31.0 m³** |

- **⚠️ TOTAL floor for climate, USABLE floor for capacity — the recess is 250 mm deep and trolleys are 450 mm.** Nothing stands in it.

- **⛔ SUPERSEDED: 12.7 / 16.0 / 28.7 m² and ~34 / ~41 / ~76 m³.** ✅ **Width MEASURED at 2720 mm (operator, 2026-08-11) — no longer approximate.**
- **✅ THE FRUITING ROOM IS STILL THE SMALLER OF THE TWO**, and the wall is still a **~2.2× volume / ~2.3× floor** increase — **the RATIO is unaffected**, so arguments resting on the ratio survive. Any resting on **absolute** volume do not: the wall adds **~16 m³ to a ~13 m³ room**, not 40 to 34.
- **✅ BAG DENSITY STILL CORROBORATES — on USABLE floor.** Fruiting **76 / 4.95 = 15.4/m²**; grow **96 / 6.20 = 15.5/m²**. **Still within 1%**, because the two rooms were stocked independently. **The figure is ~15.5 bags/m², not ~6.** *(Include the recess and the grow room reads 14.2 and the agreement breaks — itself evidence that the recess is not stood on.)*
- **⚠️ AND ~6 BAGS/m² WAS THE TELL THAT SHOULD HAVE CAUGHT THIS.** It is implausibly sparse for an oyster fruiting room, where ~15/m² is ordinary. It was read repeatedly — including as "corroborated to within 1%" — without anyone asking whether the absolute value was *plausible*. **Internal consistency is not correctness: both rooms agreed because both used the same wrong width.**

**🎯 THE SECOND-FLUSH CAPACITY ANSWER SURVIVES — BY ARITHMETIC ACCIDENT, AND IT IS WORTH KNOWING WHY.** Old: 28.7 m² × 5.97 = **171 bags**. New: 11.3 m² × 15.5 = **175 bags**. **Area and density were wrong by the same factor, so their product was right.** The combined room still holds **~7 batches ≈ 7 weeks of residence** against the **4–6 weeks** two flushes require, so **the wall removal still clears the constraint with margin.**

**🔴🔴 AND THEN THE RACKING WAS MEASURED THE SAME DAY, WHICH CHANGES THE RECOMMENDATION: THE CONSTRAINT IS TROLLEYS, NOT FLOOR AREA — SO THE WALL IS NOT THE CHEAPEST ROUTE TO A SECOND FLUSH, OR EVEN A NEEDED ONE.**

**Trolleys are 1200 × 450 mm, four racks at 400 mm pitch. The fruiting room has 3 of them, 8 bags per shelf, ONE TROLLEY PER BATCH** (operator, 2026-08-06).

- **3 × 4 × 8 = 96 bag capacity, holding 76 — and one trolley per batch means exactly 3 batches, which is what `v_batch_residence` independently shows.** Two records agreeing.
- **⛔⛔ WITHDRAWN 2026-08-11 — THE HEADLINE CLAIM HERE IS PHYSICALLY IMPOSSIBLE.** *(It read: "That uses 1.62 m² of the fruiting room's 12.7 m² — 13% of the floor. **Five trolleys across the 7000 mm width**, two rows plus a 920 mm aisle, gives **10 trolleys / 320 bags on 43% of the floor: 3.3× current capacity inside the existing room**.")* **The room is 2720 mm wide. Five 1200 mm trolleys across need 6000 mm — they will not fit; even two side by side take 2400 mm and leave 320 mm, no aisle.** The 3 trolleys use **1.62 m² of 4.9 = 33% of the floor**, not 13%.
- **🎯 Trolley count IS residence in weeks, at one batch per week: 3 → 21 days (now), 4 → 28 days, 6 → 42 days. One extra trolley reaches the two-flush window; three clear it.**

**⛔ THE DEMOTION OF THE WALL'S YIELD CASE IS ITSELF WITHDRAWN, 2026-08-11 — IT RESTED ENTIRELY ON THE 7000 mm WIDTH.** *(It read: "the same outcome is available for the price of one to three trolleys… **do not spend on the wall for capacity reasons until the trolley route has been tried and found wanting**.")* **At 2720 mm the cheap in-room expansion route is far more limited than recorded, so the wall's capacity argument is BACK IN PLAY.** ⬜ **What in-room expansion remains has not been re-derived** — at 2720 mm the practical layout is a single trolley row with a working aisle, plus the **vertical** headroom below. **Do that arithmetic before any capacity decision.** ⚠️ **This does not make the wall cheap** — the aircon gate, the new grow room and the revert test all still stand in front of it. The wall's *climate* case — the documented three-way tension between separation, temperature and grow-room ventilation — is untouched and stands on its own.

**⚠️ Hinges on:** *that the environment carries the extra load, which is the real open question.* **CO2 has no active *control*** — the fresh-air fan is fixed-speed and unmodulated *(✏️ corrected 2026-08-13: this read "since the fresh-air fan was removed"; the fan was refitted 07-23)* — so more biomass raises CO2 and nothing corrects it. Humidifier duty could move either way — a fruiting crop transpires, so bags may be a net moisture *source* — but that is untested. **Establish both, plus the cost of a trolley, before buying.**

**➡️ Volume is NOT the binding constraint. The AIR CONDITIONER is.**

- **The fill transient is trivial.** Raising the added volume from ~50% to 92% RH at 17.5 °C is a step of **6.3 g/m³** (7.45 → 13.7). Over the **~16 m³** actually added *(✏️ corrected 2026-08-11 from ~40 m³)* that is **~100 g of water — a teacup.** A 12-disc ultrasonic does litres per hour. **Minutes, not a capacity problem.**
- **Steady-state load is set by outside-air exchange, not by volume** — and the leak paths do not move. The infiltration this room fights is the **front-wall floor openings**, which are already in the fruiting room (they are what five nights of vent experiments were about). **Removing the divider adds volume, not infiltration.**
- **A larger volume actually helps stability** — more moisture and thermal mass per unit of disturbance, so slower swings and a longer buffer when a door opens.

**🔴 But the aircon is a dehumidifier, and the wall is currently what buffers it.** It sits above the rear door, *inside* the space that would become one room held at **90–95% RH**. Air at 90%+ crossing a cold evaporator coil condenses, and that water leaves down the condensate drain. **Humidifier and aircon then work against each other continuously, by design, in the same room.**

- Today the divider partially separates them. **⛔ Corrected 2026-08-06: the coupling is NOT "via the doorway" — the divider door stays CLOSED unless access is required (operator).** The rooms still track within 0.2–0.5 °C, so the path is the **~18.6 m² of 75 mm insulated partition**, which cannot be opened or closed. **That kills the "three-way tension" framing carried through these files** — separation was never being traded against fruiting-room temperature, because the closed configuration is the one already running.
- **Remove the wall and that buffer goes.** The humidifier is at **63–85% duty** *now*, on the smaller room, with the coil one door away. **This is the number to worry about, and it is not a volume calculation.**
- **The spare 12-disc unit and the fresh discs stop being "margin" and become a prerequisite** — but adding humidifier capacity to out-run a dehumidifier is fighting the symptom. **The real question is whether the aircon can be relocated, ducted, or run in a mode that does not condense** — and that should be answered *before* the wall comes down, not after.

**🔴 CANDIDATE NAMED 2026-08-11 — THE BACK WALL IS ~92% DRYWALL, AND IT IS ON NO FAULT LIST.** The old garage-door opening is **2490 mm of a 2720 mm back wall**, closed by drywall from outside — so **~6 m² of panel, not 250 mm masonry, on a room with 6.2 m² of floor.**
- **➡️ It is a candidate for the grow room sitting 3.2–5.9 °C BELOW its 21 °C setpoint.** The recorded causes are stratification deceiving the thermostat, airflow obstruction, sensor position and capacity shortfall. **Envelope loss through a panelled door opening is not among them — and it is the only one that would explain a PERSISTENT shortfall rather than a sensing artefact.**
- **⚠️ Candidate, not conclusion.** The rear wall is recorded as *insulated* drywall + Isoboard, so the question is the **joints around a panel filling a door opening**, not the panel itself. **A smoke pencil settles it and answers the hinges-on below at the same time.**

**⚠️ Hinges on:** *that the rear half's envelope is no leakier than the front* — **now materially less safe, see directly above.** The rear wall is insulated drywall + Isoboard with its own external access door. **If that door or the drywall leaks materially, steady-state load rises with it** and the "infiltration does not change" argument weakens. One smoke-pencil pass would settle it.

**✅ And the ducts are in better shape than feared.** `MICROCLIMATE.md` §1: *"**Airflow ducts are already run for the full room**; unused duct openings are sealed for now."* **The duct runs were sized for the combined space from the start.** What is unvalidated is the **hole pattern** — and note that the room currently runs with **both end caps off**, which the same doc calls *"a live interim workaround, not the settled design."*

**➡️ So the operator's unease about the hole count and size is well founded, and it has a clear consequence: do not carry a fruiting-room-only workaround into the bigger room.** The parked revert test — fan to LOW, then return cap on, then supply cap — was blocked behind the vent experiment. **That experiment is now closed, so the revert test is unblocked.** It is a **prerequisite for the wall removal**, not work for this week: scaling a workaround is worse than scaling a design.

**🔴 ADDED 2026-08-05 — THE WALL HAS A YIELD CASE, NOT JUST A CLIMATE ONE, AND IT IS THE STRONGER ARGUMENT.** Everything above this line reasons about humidity, temperature and duct geometry. **None of it is the reason to remove the wall.** The residence findings below establish that:

- **The fruiting room holds 3 batches against a 1-batch-per-week pack cadence, so mean residence cannot exceed ~21 days** without the queue growing without bound. W25's actual residence was exactly 21 days.
- **The stated intention is to take a second flush, which needs ~4–6 weeks.** The room and the intention are **incompatible by roughly a factor of two**, so batches keep being pulled mid-cycle whatever rule selects them.
- **More fruiting slots is the only change that dissolves that trade instead of choosing a side of it.** Cutting the pack cadence would also balance the pipeline, but at the cost of throughput; the wall buys both.

**⚠️ This does NOT reorder the prerequisites — the aircon still gates the wall, and the revert test still gates the design.** What changes is *why the wall is worth doing at all*: it moves from a climate-and-comfort argument to the **only structural fix for the second-flush constraint**, which sits on priority #1. **⚠️ Hinges on:** *that a second flush is worth its slot-time* — unmeasured, and the cheap test (hold W26 through one) is recorded below. **If the second flush turns out to be small, the wall's yield case weakens and the climate case stands alone.**

### 🧩 THE NEW GROW ROOM — named 2026-08-05, and it is the undesigned half of the wall plan

**Operator, 2026-08-05: the wall removal is part of a future expansion that includes building a NEW grow room — and *"the new grow room has not been thought through"*.** Recording it because **every prerequisite list in this file treats the wall as a standalone step, and it is not one.** Absorbing the grow room into the fruiting room leaves ~96 bags of colonising substrate with nowhere to live. **The wall cannot come down before the new grow room exists.**

**➡️ AND TODAY'S DATA PROMOTES IT FROM A SHED TO THE MAIN EVENT: colonisation is the LONG POLE (21–30 days, mean 26) against fruiting's 13–21.** Bags spend **more than half their life** in the room nobody has designed. Anything that shortens colonisation compounds across every batch forever.

**🔬 THE STRONGEST DESIGN HYPOTHESIS, and it is testable before anything is built: the current grow room is COLD FOR COLONISATION.** Grey oyster colonises fastest around **24–27 °C**; this grow room runs **15–18 °C** — and lately **14.5** — because it shares the fruiting room's aircon and coupling. **It is being held at *fruiting* temperature, not colonising temperature.** Oyster on pasteurised straw at proper warmth typically colonises in 14–21 days; this operation measures 21–30. **If temperature is the limiter, a warm grow room could cut ~10 days off every batch's cycle** — which also *reduces* the number of colonising slots needed, compounding again.

**🎯 AND THIS MAY BE THE ANSWER TO THE AIRCON GATE, WHICH IS THE THING ACTUALLY BLOCKING THE WALL.** The recorded problem is that the aircon is a dehumidifier inside a space to be held at 90–95% RH. **But a grow room does not need high humidity.** So:

- **Move the aircon to the new grow room**, where warmth is wanted and condensation on the coil costs nothing.
- **The fruiting room is then free of it entirely** — no dehumidifier fighting the humidifier, which is precisely the condition item #4 above asks for.
- **One relocation resolves both the aircon gate and the colonisation-temperature problem.** It is the "relocate" option of "relocate, duct, or run without condensing", given a destination that did not previously exist in the plan.

**⬜ Requirements to settle before costing anything** — none of these are decided:
1. **Capacity — size for the FUTURE cadence, not today's.** At one batch/week and 26-day colonisation the steady state is ~4 batches / ~100 bags. **At two batches/week it is ~8 batches / ~200.** The expansion's pack rate is the input and it has not been chosen.
2. **Temperature control of its own**, warm and independent of the fruiting room — the point of the whole exercise.
3. **Ventilation, designed in.** The current grow room has essentially zero air exchange and has gone stuffy; that is a documented contamination and heat-build-up risk, not a nice-to-have.
4. **No humidification** — and confirm that, because it is what makes the aircon relocation work.

**⚠️ Hinges on:** *that colonisation here is temperature-limited rather than substrate- or spawn-limited.* **Unmeasured.** If the 26 days is really about spawn rate or substrate prep, a warm room buys nothing and the new grow room is only a capacity building. **This is cheap to probe before building anything — the natural range already in the data (21–30 days) plus W31/W32 colonising through the current cold spell is a free first look.**

**⛔ BUT THE RELOCATION AS WRITTEN ABOVE STRANDS THE FRUITING ROOM — operator, 2026-08-05: *"taking the aircon away to where the new grow room will be leaves the fruiting room with no temperature control."* Correct, and it is fatal to that proposal as stated.** The fruiting room's *only* temperature control today is indirect coupling to the grow-room aircon — **through the insulated partition, not through the door, which stays closed (corrected 2026-08-06).** Move the unit out and the combined room has **nothing** — no heating against the winter cold-draft through the front-wall floor openings, and no cooling at all in a Pretoria summer, for a cool-fruiting crop with a 15–18 °C band.

**⛔ "A SETPOINT, NOT A BUILD" — WITHDRAWN 2026-08-08. THE SETPOINT IS ALREADY 21 °C AND THE ROOM DELIVERS 17.8.** *(Original claim, kept so it is not re-derived: established 2026-08-06 that the grow room's temperature can be set on the aircon, so "run colonisation at 24–27 °C" is a dial, and the free test was to raise the setpoint one step to ~20 °C.)* **The operator confirms it has been set to 21 °C for a long time, unchanged.** So the dial was already past the proposed setting, the room misses it by 3.2–5.9 °C, and **there is no free test — there is a unit not meeting its target.** Full working in the Room state section. **➡️ Colonisation at 24–27 °C is therefore not reachable by adjustment, which puts the separate grow room back as the only route.** Fruiting rising ~1 °C per 4 °C of grow rise means ~25% coupling and room to push further; tracking near 1:1 means the rooms cannot be held apart and a separate colonisation space is needed after all. **In winter this helps both rooms — the fruiting room is currently below its 15 °C floor. In summer it inverts, and THAT is what still argues for the new grow room.** ⚠️ **Hinges on the aircon delivering it — recovery from the 08-01 fault is incomplete (16.3 against a pre-fault 17.25). Let it settle first or the setpoint change confounds the filter verdict.** Full working: `stock-control/docs/MICROCLIMATE.md`.

**➡️ The relocation does not CREATE that problem, it REVEALS one that already exists and is biting right now.** This file already records that the fruiting room has never had its own temperature control. **The current 14.2–15.5 °C excursion below the band floor is exactly that weakness failing** — the room is 0.2–0.5 °C above the grow room, entirely passively. **So "the fruiting room needs its own climate control that does not dehumidify" is a requirement of the expansion whether the aircon moves or not.**

**🔬 AND THE BLOCKING CONSTRAINT IS SEASONAL, NOT ABSOLUTE — this file has been overstating it.** Everywhere above, the aircon is described flatly as *"a dehumidifier sitting inside a space to be held at 90–95% RH."* **That is true in COOLING mode only.** In **heating** mode a reverse-cycle unit's indoor coil is the *condenser* — hot, not cold — so **moisture condenses on the OUTDOOR coil and nothing is stripped from the room.** Heating air at constant absolute humidity does lower RH, so the humidifier works harder, but **that is a load, not a loss of water, and the humidifier can answer it.**

- **Evidence this unit is reverse-cycle: it is being used for heating now** — the whole 08-04 filter diagnosis was about *reduced heat output*, and the grow room gains heat every afternoon.
- **➡️ So in WINTER the aircon could serve the combined fruiting room with no dehumidification conflict at all. The conflict is a SUMMER problem.** That is a materially smaller obstacle than "the aircon gates the wall" implies, and it means **the wall does not have to wait for a year-round answer — it needs a summer answer.**
- **✅✅ HINGE CLOSED 2026-08-12 — THE NAMEPLATE CONFIRMS REVERSE-CYCLE.** ~~*Hinges on: that the unit is genuinely reverse-cycle rather than cooling-only with a separate heat source.*~~ **`Alliance INAA18` carries a HEATING CAPACITY of 5790 W** *(range 1550–6740; heating input 1461 W)*, so it heats on the refrigeration cycle. **➡️ The seasonal argument above therefore STANDS: in winter this unit can serve the combined fruiting room with no dehumidification conflict, and the wall needs a SUMMER answer rather than a year-round one.** Full nameplate and its other two consequences — the capacity hypothesis killed, and the inverter throttling that explains the slow fan — are in the aircon RESULTS block under *"Room state"*.
- **⬜ The summer question is still open and is now the real one:** cooling a 90–95% RH room without condensing. Candidates not yet assessed — evaporative cooling (thermodynamically the right tool for a room that wants moisture, but limited by wet-bulb and only effective on dry make-up air), conditioning outside air and supplying it via the plenum, or a coil held above the room's ~15.8 °C dewpoint, which a conventional split cannot do. **Do not treat this as solved by the relocation idea.**

### ✏️ CUTTING THE TUB — MY ORDERING WAS WRONG, CORRECTED 2026-08-14 BY THE OPERATOR. **It moves up. The only real constraint left is sequencing, and it is one night.**

**Operator:** *"Why is the cutting of the sides of the tub not on the list? Because it can not be reversed? Reversing is not a big concern. If the cutting does not give the required improvement it can stay the way it is. Else I can replace the tub."* **✅ Both points are correct and they change the ranking.**

- **✅ CONCEDED — "IRREVERSIBLE" WAS CARRYING TOO MUCH WEIGHT.** A cut that does not help simply **stays**, and the worst case is **the price of a tub.** ➡️ **That is not irreversibility, it is a small bounded cost, and it should never have been ranked alongside a structural commitment.**
- **✏️ AND A SECOND ARGUMENT OF MINE WAS WEAKER THAN I STATED IT. I wrote that record-high AH proves transport is not the constraint. It does not.** **Record-high output shows the humidifier is not COLLAPSED. It says nothing about whether it is THROTTLED** — a tub that caps output at 15 g/m³ when it could pass 20 looks identical in that measurement. **The claim needed a ceiling to test against, and no ceiling has ever been measured.**
- **🔑 AND THE PRIOR EVIDENCE IS ON THE OPERATOR'S SIDE, NOT MINE.** **On 2026-07-25 cutting ONE hole in the tub side halved humidifier duty at the same RH** — *"the walls trapped the fog, it condensed and drained back, and the unit ran flat out feeding a sealed box."* ➡️ **That is the single largest measured humidifier improvement in this room's history, from precisely this intervention.** **My case rested on an inference; his rests on a measured 2×.**

**⛔ SO THE ONLY REMAINING CONSTRAINT IS ONE VARIABLE AT A TIME — AND THE WAIT IS ONE NIGHT, NOT A DEMOTION.** **The discs were changed today and their read is live tonight.** **Cut now and tonight's paired night is confounded and the disc test is void.** ⚠️ **This file has lost that bet repeatedly — the fan test to weather, two nights to the Inkbird freeze, the whole 100→83→72.4% duty series to the aircon step.** ➡️ **What one night buys is knowing WHETHER THE HUMIDIFIER NEEDS REPLACING BEFORE THE MIXING BOX — a several-thousand-rand decision. That is a good trade for 24 hours.**

**✏️ CORRECTED — IT IS NOT A SEPARATE STEP AND IT IS NOT FREE TONIGHT (operator: *"can not measure the tub hole now without disturbing everything"*).** **Reaching the hole means opening the plenum — the humidification hub — which dumps the moisture and voids the disc read, on top of the human-presence disturbance that already corrupted the 12:04 sample.** ➡️ **So MEASURE AND CUT IN THE SAME VISIT: one opening, not two.** **The measurement then costs nothing extra — it is the first two minutes of the cutting job.** **⬜ MEASURE THE EXISTING HOLE AGAINST THE TUB'S SIDE AREA BEFORE THE BLADE GOES IN.** **⛔ Nothing to do in the room tonight — leave it shut.** **It does not decide WHETHER to cut. It decides HOW MUCH, and it stops both failure modes:** cutting far too little to matter, or removing so much that the tub stops holding water. *(The same arithmetic that settled the return duct at 69 × 12 mm = 93% of duct area.)*

**✏️✏️ WITHDRAWN 2026-08-17 — "POSITION MATTERS AS MUCH AS AREA" IS WRONG, AND THE PLENUM'S ACTUAL GEOMETRY IS WHY.** *(It read: "cut WHERE THE PLENUM AIR ACTUALLY PASSES… an opening on a side with no airflow past it lets fog drift out and settle." That assumed a single exit from the lower chamber. There isn't one.)*

- **🔑 THE OPERATOR'S OBSERVATION THAT SETTLES IT: the baffle dividing the lower and upper chambers has a 10 mm GAP ALL AROUND ITS PERIMETER.** ➡️ **Air leaves the mixing chamber upward along EVERY edge, so every side of the tub faces an exit path and there is no dead side to get wrong.** **Side choice is free — cut whichever is easiest and safest to work on.**
- **📐 AND THE GAP IS NOT THE RESTRICTION.** A ~476 mm baffle gives roughly **1,900 mm of perimeter × 10 mm ≈ 190 cm²**, against the 110 mm supply duct's **~85 cm²**. **The exit passes about 2× what the duct downstream can take**, so liberating more fog does not just meet a new ceiling at the baffle.
- **🔑 ALSO RECORDED: THE TWO INLETS SIT BEHIND A BAFFLE** *(operator, 2026-08-17)*, so the incoming jets are deliberately broken up. **There is no fast stream anywhere near the tub by design** — which is why a tissue test there reads as almost nothing, and why "aim at the airflow" was never actionable advice.
- ⚠️ **WHAT DOES STILL BIND: cut ABOVE the working water line — the tub IS the reservoir and the float valve sets that level.** ⛔ **And after 2026-08-17 that line is higher than it looks:** the feed pipe was air-locked and the reservoir had been running starved for three nights. **Let the level settle after bleeding before marking the cut, or it will be marked to a false line and the tub will leak when the level returns.**
- ➡️ **So the remaining variables are HEIGHT and AREA only.** Wall height is the actual trap: ultrasonic fog is denser than air and pools in the tub, condenses and drains back.

**✅ DONE 2026-08-17 (~10:50) — AND THE OPERATOR DID NOT LOWER THE SIDES, FOR A BETTER REASON THAN THE ONE THIS FILE GAVE.**

**Operator:** *"I did not remove the sides of the tub because it has to support the float valve. I just cut horizontal holes of about 15 to 20 mm wide along the side about 40 mm above the water line, and I left some pieces in the corners and where the tub has strengthening curves in the plastic."*

- **🔑 THE TUB RIM IS STRUCTURAL — IT CARRIES THE FLOAT VALVE, WHICH IS WHAT SETS THE WATER LINE.** ➡️ **Lowering the walls would have traded the level-control mount for fog area.** **That constraint was not in this file and it outranks the "cut lower" advice given above.** Leaving material at the corners and at the moulded stiffening ribs keeps the tub from deforming — a deformed reservoir leaks, and it is the plenum floor.
- **📐 THE AREA TEST, AND IT IS THE ONE THAT MATTERS GOING FORWARD: at a ~17.5 mm slot height, ~485 mm of TOTAL slot length already equals the 110 mm supply duct's ~85 cm².** **Beyond ~500 mm the tub is no longer the restriction and the DUCT downstream is.** *(The plenum's own baffle gap is ~190 cm², so it was never the limit either.)*
- **🎯 WHICH ANSWERS "SHOULD I CUT MORE?" IN ADVANCE, AND THAT IS THE POINT OF MEASURING IT.** **If total slot length is past ~500 mm and the room does not improve, the constraint is downstream — and cutting more tub is wasted work on a solved problem.**
- **✅ ANSWERED — ~700 mm OF TOTAL SLOT (operator estimate, 2026-08-17). ⛔ THE TUB IS NO LONGER THE RESTRICTION.** **700 × ~17.5 mm ≈ 122 cm², against the supply duct's ~85 cm² — and even at the pessimistic 15 mm slot height it is 105 cm², still clear.** ➡️ **⛔ DO NOT CUT MORE TUB. Whatever happens tonight, this constraint is retired**, and the argument is **pre-registered rather than fitted afterwards**, which is what makes it worth anything.
  - ⚠️ **ESTIMATE, NOT MEASURED — from the operator's recollection the same morning, not a tape.** **Replace it at the next plenum opening that happens for another reason.** *(Deliberate: opening the plenum dumps the moisture, restarts the settling clock and voids tonight's read — the same "measuring is not free tonight" trap recorded on 08-14. The slot length keeps; tonight's read does not.)* **It clears the threshold by ~40%, so the conclusion survives a fairly wrong estimate.**
  - ➡️ **SO A FLAT RESULT TONIGHT POINTS DOWNSTREAM, NOT AT THE TUB** — the 110 mm supply duct at ~85 cm², which is also where `4b(d)`'s revert-test step 3 already points. **Two independent lines now converge on the supply duct as the next thing to touch.**
- **⚠️ 40 mm of freeboard means a 40 mm fog sump remains trapped** below the slots, where it can still condense and drain back. **Acceptable, and the safe choice while the reservoir was still refilling after the air-lock bleed.** ➡️ **If tonight is flat AND the slot length is already past 500 mm, do NOT cut more — the sump is the only remaining tub-side variable, and lowering the slot band is a separate, smaller experiment.**


### ⚠️ REOPENED 2026-08-17 — HUMIDIFIER DISCS REPLACED 08-14. **THE "DISCS DID NOTHING" VERDICT IS SUSPENDED: THE WATER FEED WAS AIR-LOCKED, AND THE CLEAN READ SITS INSIDE THE STARVED WINDOW. ⛔ The "do not buy a bigger humidifier" decision STANDS and is strengthened — see which parts survive, below.**

**🔴 NEW FAILURE MODE, FOUND BY THE OPERATOR 2026-08-17: AIR IN THE HUMIDIFIER'S FEED PIPE, BLED OUT BY HAND.** ➡️ **This is a SECOND silent path to the same symptom this file already records for the roof tank — *"if the tank is not filled, the humidifier reservoir stops refilling. Nothing alarms on it."* An air lock starves the reservoir with the tank full, and nothing alarms on that either.** **Both look identical from the data: steady temperature, AH sliding, relay pinned on.**

- **⛔ WHAT IS NOW UNSAFE TO CONCLUDE.** Overnight AH ran **13.72 (08-14 baseline) → 13.89 → 13.47 → 13.18**, i.e. **a three-night slide.** The 08-16 "clean read" that scored the discs at **−0.25 vs baseline is inside that slide.** **A starved humidifier depresses AH exactly as degraded discs would, and nothing in the data separates them.** ➡️ **The disc question is UNANSWERED, not answered in the negative.**
- **✅ WHAT STILL STANDS, AND IT IS THE LOAD-BEARING HALF.** The ten-night table below rests on **08-07 → 08-12**, which is **before the slide begins and before the 08-12 aircon change** — the humidifier held **90–92% RH and met the target outright on 08-09 at 17.1 °C**. **A unit that met spec on a clean supply is not undersized**, and the requirement-rose-with-temperature mechanism is unaffected. ➡️ **⛔ Still do not buy a bigger humidifier — there are now TWO independent reasons the recent numbers looked bad, and neither is capacity.**
- **🎯 THE REAL CLEAN READ IS THE FIRST FULL NIGHT AFTER THE BLEED.** Post-bleed baseline, 2026-08-17 08:40: **AH 13.1, RH 82.6%, 18.5 °C.** **Pre-registered now, before the outcome is known:** **AH returns to ≥13.8** *(the 08-15 level)* → **the feed was the constraint all along, and the disc test must be re-run from scratch.** **AH stays ≤13.5** → **the supply was a minor contributor, the slide has another cause, and the original disc verdict is restored.** **Between 13.5 and 13.8** → partial, and the disc question needs a properly instrumented re-run rather than another paired night.
- **⬜ AND IT ARGUES FOR THE ONE INSTRUMENT THIS ROOM STILL LACKS: NOTHING MEASURES WHETHER WATER IS ACTUALLY ARRIVING.** Two silent failure paths now share one symptom, and both were found by eye, late. **A reservoir float switch or a simple level sensor into HA would separate "humidifier weak" from "humidifier dry" instantly** — a distinction that has now cost two investigations. *(Cheap; scope it against the R653 RS485 sensor benchmark and the free Modbus address 3.)*

**🎯 THE FINDING, AND IT IS THE WHOLE POINT: THE HUMIDIFIER'S OUTPUT HAS NOT MOVED IN TEN NIGHTS. THE *REQUIREMENT* MOVED.** Overnight means, 00:00–08:00, with the absolute moisture each night actually needed for 92% RH **at its own temperature**:

| night | Temp | AH | RH | need@92% | gap | |
|---|---|---|---|---|---|---|
| 08-07 | 16.22 | 12.46 | 90.2 | 12.70 | −0.24 | |
| 08-08 | 16.99 | 13.15 | 90.9 | 13.29 | −0.15 | |
| 08-09 | 17.10 | 13.40 | **92.0** | 13.39 | **+0.01** | **target met** |
| 08-10 | 16.74 | 12.94 | 90.9 | 13.10 | −0.15 | |
| 08-11 | 16.65 | 12.85 | 90.7 | 13.03 | −0.18 | |
| 08-12 | 14.92 | 11.57 | 90.7 | 11.73 | −0.16 | |
| 08-13 | 18.16 | 13.54 | 87.3 | 14.26 | −0.72 | ⬅ **step** |
| 08-14 | 19.03 | 13.72 | 84.0 | 15.01 | −1.29 | |
| 08-15 | 18.74 | 13.89 | 86.5 | 14.75 | −0.87 | new discs |
| 08-16 | **18.39** | **13.47** | 85.7 | 14.45 | −0.98 | clean read |

- **⛔ THE DISCS ARE ACQUITTED OF DOING ANYTHING. The pre-registered threshold was fixed on 08-15, before this night existed: AH > +0.5 g/m³ over the 13.72 baseline = real. The clean read came back −0.25 — BELOW baseline.** Duty **100% with zero off-periods on all three nights**, and 13.47 sits inside the **12.5–13.9 g/m³ band the unit has held for ten nights straight.** ➡️ **Branch 2 of the original pre-registration fires: "duty still 100% AND AH no higher than 13.72".**
- **🔴 BUT ITS PRESCRIPTION — "a bigger humidifier comes before the mixing box" — IS WRONG, AND THE SAME TABLE IS WHY.** That branch was written while the room sat at 19 °C, treating the requirement as fixed. **It is not fixed: it is a function of temperature, and temperature is what changed.** **On 08-07 → 08-12 this same humidifier held 90–92% RH and hit the target outright on 08-09.** **A unit that met the spec five nights ago is not undersized.**
- **🎯 THE STEP IS 08-12 → 08-13, AND IT IS ALREADY IN THIS FILE: `FAN = MANUAL HIGH` set 08-12 ~09:30.** The grow room went from 5–6 °C below setpoint to holding 21.8 °C — **a real win on the 21–30 day colonisation long pole** — and the fruiting room warmed **~16.7 → ~18.4–19.0 °C** with it. **The requirement rose ~+1.4 g/m³; the humidifier delivered the same moisture into a room that now needed more.**
- **📐 THE NUMBER THAT MAKES THIS ACTIONABLE: AT ~13.5 g/m³ OF DELIVERED MOISTURE, THIS HUMIDIFIER HOLDS 92% RH ONLY AT OR BELOW ~17.2 °C.** ➡️ **The top of the 15–18 °C target band is unreachable on humidity with the equipment installed.** The room must sit in the band's **lower half**, or the humidity KPI cannot be met at any duty. **That is a design constraint, not a fault.**
- **⚠️ Hinges on:** *that the 08-12 aircon change is what warmed the fruiting room, and that moderating it returns the room to ~16–17 °C without giving back the grow-room gain.* **If wrong, the aircon comes down, colonisation is given back, AND the humidity does not recover — the worst of both.** ➡️ **This is exactly the fork this file already named** *("either the fruiting room gets moisture capacity to hold 90% RH at 18.3 °C, or the aircon setpoint comes back down and the colonisation gain is given back")* — **now with a price on one side: ~R0 and a setpoint change, versus a humidifier that the ten-night record says is not needed.**
- **✅ AND THE HARVEST CONFOUND IS NOW QUANTIFIED, AND IT POINTS THE SAME WAY.** `v_recent_captures` (queried 2026-08-16): **4,922 g picked 08-12 midday, 2,190 g on 08-13, 2,452 g on 08-14** — so **~7 kg of transpiring biomass came out immediately before the humidity failed**, which is exactly the alternative explanation. **⛔ It is ruled out by the direction of the numbers: across the 08-12 → 08-13 step, AH ROSE 11.57 → 13.54 g/m³ while RH FELL 90.7 → 87.3%.** **Removing transpiring biomass would LOWER absolute moisture. It rose.** ➡️ **More water went into the air and RH still fell, which only temperature can do. The harvest is not the cause.**
- **✅ WHAT THIS SAVES: the humidifier purchase, and the re-ordering of PLAN steps 6–8 it would have triggered.** **⛔ Do not re-propose a bigger humidifier without first showing the room held ≤17.2 °C and STILL missed 92% RH.** That is the only evidence that would overturn this.
- **◐ The daytime branch never resolved: the relay has not cut out once in 60+ h.** RH has not reached 92% since 08-09. **The OFF branch of that automation still has never run in production** — unchanged, still worth confirming the first time the room gets back under 17.2 °C.

<details><summary>Superseded detail from the 08-15 read (kept for the reasoning, not the conclusion)</summary>

**READ 2026-08-15 — no branch fired cleanly; the result landed in a gap the pre-registration left open.**

**The paired overnight window, 00:00–08:00, fan LOW both nights, windows clean of disturbances** *(the sharp CO2 moves in the last 60 h are all daytime — 08-13 15:20/15:49, 08-14 11:50/16:07 — none inside either window)*:

| | 08-14 baseline | 08-15 new discs | Δ |
|---|---|---|---|
| **Duty** | 100% | **100%** | **0** |
| **AH g/m³** | 13.72 | **13.89** | **+0.17 (+1.2%)** |
| RH % | 84.00 | 86.52 | +2.52 |
| Temp °C | 19.03 | 18.74 | −0.29 |
| VPD kPa | 0.35 | 0.29 | −0.06 |

- **✅ The baseline reproduces exactly** — 19.03 / 84.00% / 13.72 recomputed independently from the recorder, matching the table in "THE HUMIDIFIER IS AT ITS BEST-EVER OUTPUT AND LOSING" to the decimal. **The comparison is sound; the ambiguity is in the result, not the method.**
- **⛔ WHY NO BRANCH FIRES.** Branch 2 needed *"duty still 100% AND AH **no higher** than 13.72"* — but AH is **higher**, so it does not fire. Branch 3 needed AH **"clearly above"** 13.72 — **+1.2% is not clearly.** ➡️ **The pre-registration never defined the gap between "no higher" and "clearly above", and the answer landed in it.** *(Second time in three days: the 08-13 fan test also returned with none of its four branches firing. **The lesson is not "pre-register less" — it is that a branch on a continuous quantity needs a NUMBER for "clearly", set before the read.** Next time: state the threshold, e.g. ">+0.5 g/m³".)*
- **⚠️ AND HALF THE RH GAIN IS TEMPERATURE, NOT MOISTURE.** The room ran **0.29 °C cooler**, and cooler air needs less water for the same RH. Holding AH at 13.89 but temperature at the baseline 19.03 °C gives **85.2% RH** — so of the **+2.52 RH points, ~+1.2 is the moisture gain and ~+1.3 is simply the cooler night.** **Scoring this on RH alone would have doubled the apparent result.**
- **⚠️ THE PRE-REGISTERED CONFOUND DID NOT MATERIALISE — AND IT REVERSED.** The block predicted *"the room is 1.5 °C warmer than the 08-14 baseline night (19.3 vs 18.2 at 22:00)"*, arguing an unchanged duty at higher AH would therefore be a genuine improvement. **Over the actual window the room ran COOLER, not warmer.** That tailwind was never collected, so **the +0.17 stands on its own without that allowance.**
- **◐ THE DAYTIME READ ALSO CAME BACK INCONCLUSIVE, AS ITS SECOND BRANCH ALLOWED: the relay never cut out.** Duty is **100% across the entire 36.7 h of relay history** — RH never reached the 92% threshold. ➡️ **The OFF branch of that automation STILL has never been exercised in production** *(the watch item below remains open, not closed)*.
- **🎯 THE FILE ALREADY WROTE THE ANSWER FOR THIS CASE: *"If tonight comes back null or ambiguous, the clean read is the FOLLOWING night (08-16), once the room has settled at the new biomass."*** **Take it.** The harvest happened on 08-14, so 08-15's window is the first night at reduced transpiring biomass — **exactly the confound that makes a small positive unreadable.** One more night costs nothing and is already the recorded plan.
- **✏️ CORRECTED 2026-08-16 — THE HARVEST WAS LOGGED ALL ALONG, AND THIS BLOCK CLAIMED TWICE THAT IT WAS NOT.** The claim came from **this file's own unticked checkbox, not from the ledger**, which was never queried. `v_recent_captures` has it: **08-14 16:09 SAST, `SUB-2026-W28`, 2,452 g** — matching the 16:07 CO2 disturbance to the minute. **The capture habit is holding; the checkbox was stale.** ⚠️ **The general lesson is the one this file keeps relearning: an open checkbox records that nobody ticked it, NOT that the work is undone. Check the system of record before asserting a gap.**

---

**The original pre-registration, kept for scoring — written 2026-08-14 before the outcome was known:**

*(Branch 2 is the one that fired. Its verdict line — "a bigger humidifier comes before the mixing box" — is **overturned above**: it held the moisture requirement fixed, and the requirement is what moved.)*

**Operator replaced the discs — PLAN step 1, the free test that can invalidate the mixing-box build.** ⬜ **TIME OF CHANGE NOT YET RECORDED — get it, the read is a paired night and the window matters.**

**⛔ DUTY IS THE WRONG METRIC TO READ THIS EARLY, AND "STILL PINNED" IS NOT A FAILURE YET.** The firmware hysteresis is **ON below 88% RH, OFF above 92%** *(`fruiting-room-controller.yaml`)*. **RH is 86.6%, so the relay CANNOT cut out until the room is refilled to 92% — and it starts from a deficit.** ➡️ **A stronger humidifier must first RAISE ABSOLUTE MOISTURE; only then can it cycle. Reading duty today would score a working unit as a failure.** *(Relay confirms: 14 h, zero off-periods.)*

**✏️✏️ CORRECTED WITHIN THE HOUR — TIME OF CHANGE IS ~12:04 (operator), AND THAT VOIDS THE EVIDENCE THIS BLOCK FIRST CITED.** *(It read: "from the 07:00 trough, AH 13.08 → 15.08 and RH 81.2 → 86.6% while temperature ROSE — the signature that matters." **That entire rise is PRE-CHANGE. It is the normal morning warm-up and it has nothing to do with the discs.** Recorded rather than deleted because **it is this file's most-repeated failure — attributing a pre-existing trend to an intervention** — and it was committed here **twenty minutes after being written**, the same shape as the 08-13 duct/door-disturbance error.)*

**⛔ AND THE ONE STEP THAT DOES COINCIDE WITH THE CHANGE IS ALMOST CERTAINLY THE OPERATOR HIMSELF.** 11:54 → 12:04: **AH 14.70 → 15.10, RH 84.8 → 87.1** — an ~8× acceleration on the preceding rate, **in the single sample where a person was standing in the room with the plenum open.** ➡️ **`room_check.py` §6 exists precisely to stop human presence being read as a trend. Discard it.** *(The relay cannot help here: it reads the ESP32's command, so a humidifier unplugged at the multiplug still shows `ON`.)*

**✅ WHAT THE TIMESTAMP DOES BUY: A CLEAN BASELINE.** **Everything to 12:00 is settled pre-change data on the new fan setting**, so tonight's paired window is a genuine one-variable comparison. **Nothing is readable before this evening — the room must first refill, and the afternoon peak is still ahead.**

**⚠️ HARVEST IS ALSO HAPPENING TODAY (operator), AND IT IS NOT JUST A TRANSIENT — IT MOVES THE READ.**

- **✅ THE DAYTIME DISTURBANCE IS ALREADY HANDLED — that is WHY the window is 00:00–08:00.** An afternoon harvest sits **~8 h clear** of it, and the room settles. **Do not delay picking for an experiment: quality is time-sensitive, the crop is the business, and this test is instrumentation.**
- **⛔ BUT HARVESTING REMOVES TRANSPIRING BIOMASS, WHICH IS A LASTING STEP, NOT A BLIP.** `MICROCLIMATE.md`: *"a fruiting crop **transpires**, so bags can be a net moisture SOURCE rather than a load"* — **untested here.** ➡️ **So tonight carries TWO variables pulling OPPOSITE ways: new discs (better) and less transpiring biomass (worse).**
- **🎯 WHICH MAKES THE READ ASYMMETRIC, AND THAT IS STILL USABLE.** **An IMPROVEMENT survives the confound and is a STRONGER result — it was won against a headwind.** **A NULL does not: it cannot separate "discs did nothing" from "discs worked and the harvest ate it."** ➡️ **If tonight comes back null or ambiguous, the clean read is the FOLLOWING night (08-16), once the room has settled at the new biomass.**
- **⬜ AND THE CONFOUND CAN BE A NUMBER RATHER THAN A CAVEAT — LOG THE HARVEST WEIGHT AND TIME.** **The ledger already captures per-picking weights**, so the biomass removed is recorded rather than estimated. **Do it in the same session; it is the difference between a quantified confound and an excuse.**

**🎯 PRE-REGISTERED — TWO READS, written now:**

| when | outcome | verdict |
|---|---|---|
| **today, before the ~15:00–16:00 peak** | **RH reaches 92% and the relay CUTS OUT** | ✅ **Decisive. First off-period in this record. The discs WERE degraded and output is restored** |
| | RH stalls below 92% as temperature peaks | ◐ inconclusive — the afternoon rise fights it; wait for the night |
| **overnight 00:00–08:00, 08-15 vs 08-14** *(fan LOW both nights, one variable)* | **duty falls below 100%** | ✅ **Headroom exists. The mixing box is affordable in moisture terms** |
| | **duty still 100% AND AH no higher than 13.72** | ⛔ **The unit is at its ceiling. A BIGGER HUMIDIFIER COMES BEFORE THE MIXING BOX — PLAN steps 6–8 re-order** |
| | duty 100% but AH clearly above 13.72 | ◐ output rose, deficit still wins — the damper's water cost is the binding number *(PLAN step 3)* |

- **⚠️ CONFOUND, AND IT IS REAL: the room is 1.5 °C warmer than the 08-14 baseline night** *(19.3 vs 18.2 at 22:00)*. **A warmer room needs more absolute moisture for the same RH**, so **an unchanged duty at a HIGHER AH is a genuine improvement, not a null.** **Score AH and RH together, never duty alone.**
- **⬜ WATCH: if RH now overshoots toward 95%+ at 19–20 °C, VPD approaches the 0.1 band floor and free water on caps becomes a contamination risk.** The 92% cut-out should prevent it; **confirm it actually fires** — this room has never reached that threshold, so **the OFF branch of that automation has never been exercised in production.**

</details>


### ✅ READ 2026-08-18 — **THE RELAY CUT OUT FOR THE FIRST TIME. But the "record AH" was a midday value read against overnight ones, and the ceiling it moved was wrong.**

**Four changes went in on 2026-08-17:** feed pipe bled ~08:35 *(air-locked — new failure mode)* · reservoir refilled · tub slotted ~10:50 · **aircon 21 → 19 °C ~11:30** *(todo 6c)*. The first three were fault repairs; the aircon was the live variable. Overnight 00:00–07:00 read below, against the pre-registered branches.

| | 08-14 | 08-15 | 08-16 | 08-17 | **08-18** |
|---|---:|---:|---:|---:|---:|
| overnight AH g/m³ | 13.80 | 13.93 | 13.52 | 13.23 | **13.71** |
| overnight temp °C | 19.07 | 18.76 | 18.42 | 18.48 | **17.68** |
| overnight RH % | 84.4 | 86.6 | 85.8 | 83.7 | **90.8** |
| **overnight duty %** | 100.0 | 100.0 | 100.0 | 100.0 | **86.4** |

- **✅✅ THE DECISIVE BRANCH FIRED: THE HUMIDIFIER RELAY CUT OUT AT 2026-08-17 19:26:32**, after running **continuously since before 08-16 00:00**. It then cycled **13 times overnight** (~30–60 min on, 8–11 min off). ➡️ **The firmware's 92% OFF branch has now run in production for the first time** — it had never been exercised, and this file has carried that as an open question since 08-09. **It works. Close it.**
- **✅ AND THE SECOND PRE-REGISTERED BRANCH FIRED: DUTY CAME OFF THE PIN — 100/100/100/100 → 86.4%.** The disc block's table reads *"duty falls below 100% → **headroom exists. The mixing box is affordable in moisture terms**"*. ➡️ **The humidifier is NOT at its ceiling.** ⚠️ **Hinges on:** one night, and the room was 0.8 °C cooler — a cooler room needs less moisture for the same RH, so part of the headroom is the aircon's, not the unit's. **Size of the move if wrong: the PLAN 6–8 re-order, i.e. whether a bigger humidifier comes before the mixing box.**
- **⛔ "AH 14.3 IS HIGHER THAN ANYTHING IN THE TEN-NIGHT RECORD" IS WITHDRAWN — IT COMPARED A MIDDAY SPOT VALUE AGAINST OVERNIGHT MEANS.** Like-for-like, **daytime 12:00–16:00: 08-14 **14.86** · 08-15 **14.54** · 08-16 13.87 · 08-17 **14.21***(post-bleed)*. **The post-bleed figure is BELOW the two days before it.** Overnight, 13.71 is below 08-14's 13.80 and 08-15's 13.93. ➡️ **The bleed RECOVERED a three-night dip (13.52, 13.23) back to normal. It did not raise output, and there is no record.** *(This is the file's own §3 error — comparing humidity figures taken at different temperatures and times of day — committed in the entry that warns about it.)*
- **⛔ SO THE ~18.2 °C CEILING IS WRONG, AND IT IS THE NUMBER THE AIRCON DECISION RESTED ON.** It was computed from that same 14.3 spot value. **On sustained overnight delivery (13.71 g/m³) the limit for 92% RH is ~17.5 °C** — only **0.3 °C** above the original ~17.2, not 1.0. **The room ran 17.68 °C all night, i.e. just ABOVE its own ceiling** — which is exactly why RH sat at 90.8% and touched 92.1% only briefly. *(Arithmetic: AH = 216.7·es(T)·RH/T_K. The 18.2 figure is correct **for** AH 14.3; the input was the error, not the algebra.)*
- **➡️ THEREFORE: DO NOT RAISE THE AIRCON BACK TOWARD 20.** The over-cooling condition — *"comfortably ≥92% RH with the room well under 17.6 °C"* — **did not fire on either half**: RH 90.8 mean, temp 17.68 mean. **It was framed on a ceiling ~0.7 °C too optimistic.** ⚠️ **Hinges on:** the ceiling being a real equipment limit rather than a loss-rate one. **Size of the move if wrong: the 21–30 day colonisation long pole, which is why the question is worth re-asking, not dropping.**
- **⚠️ AND THE READ IS INCOMPLETE — THE PRE-REGISTERED CAVEAT FIRED EXACTLY AS WRITTEN. The grow room had NOT settled.** Overnight mean **19.96 °C**, still descending at dawn *(04:00–06:45 mean 19.68, min 19.00)* against its **19 °C** setpoint — it shed ~1.1 of the ~3 °C it owed. ➡️ **The fruiting-room figure is reading a room still in transit, so 08-19 is the truer read** — and it should run **cooler**, which could still carry RH past 92%. **The aircon verdict is deferred by one night, not decided.**
- **✅ AND THE DISC TEST IS NOW SETTLED CLEANLY — NO RE-RUN NEEDED. This night WAS the unconfounded re-run.** The 08-16 verdict *"the discs did nothing"* was **biased against the discs**: its test night (13.52) fell inside the starvation window and its 13.72 baseline did not, so a real disc gain could have been masked. ➡️ **Now compare like with like — new discs + unstarved feed = 13.71 against the pre-disc unstarved baseline 13.72. Delta −0.01.** **The discs did nothing, and it now rests on a fair comparison rather than a biased one.** *(This answers the todo item's own title question: the disc test does NOT need re-running.)*

### ✅ ITEM 7c DONE — **THE ROOM'S AIRFLOW IS MEASURED FOR THE FIRST TIME: 4.02 ACH = ~137 m³/h. Run 2026-08-16, fan off 18:13, fan on 18:32.**

**The decay fit is strong: λ = 4.02 /h, r = −0.9952 over 60 samples across 45 minutes.** ✅ **Independently validated by its own asymptote — the fit lands at 612 ppm against an observed overnight trough of 587.** ✅ **And it is offset-tolerant exactly as this file predicted: a decay RATE is a differential over one sensor, so the disputed ~350 ppm zero cancels.**

- **⛔ THE BUILDUP HALF OF THE RUN IS VOID, AND THE FAILURE IS INSTRUCTIVE.** Fitting the fan-off rise gave **λ = 7.03 /h — HIGHER than with the fan running**, i.e. a negative fan contribution, which is impossible. **Cause: the buildup began minutes after a harvest**, so the room was still re-mixing from an open door and a person in it rather than relaxing cleanly toward a fan-off steady state. ➡️ **Next time the room must sit undisturbed for ~30 min BEFORE the fan goes off.** *(The plateau itself is still usable — see below — because a steady state does not care how it was reached, only that it was reached.)*
- **🎯 THE TWO STEADY STATES RECOVER WHAT THE BAD FIT LOST, AND THEY BARELY DEPEND ON THE SENSOR'S ZERO.** CO2 generation is the same in both conditions, so `λ_off/λ_on = (612 − S)/(1008 − S)` for whatever the sensor reads on outside air, `S`:

| outside reads | passive | fan's own | fan's share |
|---|---|---|---|
| 400 ppm | 48 m³/h | 89 m³/h | 65% |
| 420 ppm | 45 m³/h | 92 m³/h | 67% |
| 450 ppm | 40 m³/h | 97 m³/h | 71% |

  ➡️ **Across every plausible value the answer is the same shape: passive infiltration is ~40–48 m³/h and the fresh-air fan supplies about two-thirds of total exchange.** **The permanently-open holes on the cold side are worth roughly a third of the room's air on their own.**
- **🔴 AND HERE IS THE NUMBER THAT MATTERS MOST, BECAUSE IT EXPLAINS THE HUMIDIFIER: AT 137 m³/h, EVERY 1 g/m³ OF INDOOR-OUTDOOR MOISTURE GAP COSTS 137 g/h OF WATER.** At a winter gap of ~6 g/m³ that is **~820 g/h — over 800 ml an hour, continuously.** ➡️ **The humidifier is not fighting the room. It is fighting the ventilation rate.** **This is why it sits pinned at 100% duty** *(see the CLOSED humidifier block above)*, and it is measured rather than inferred.
- **🎯 WHICH PROMOTES THE MIXING DAMPER FROM A TEMPERATURE FIX TO A HUMIDITY FIX AS WELL.** This file has argued the intake build on temperature grounds and on the cold-side-has-no-damper grounds. **Air exchange is now shown to be the humidifier's dominant load too, so modulating it buys BOTH KPIs from one build** — and **cutting exchange is the only humidity lever that costs nothing per litre**, unlike more humidifier capacity.
- **⚠️ Hinges on:** *the room being ~34 m³.* Every flow figure here is `λ × volume`, so a volume that is wrong by 20% moves 137 m³/h by 20%. **The volume has never been measured — it is carried from an earlier note.** ⬜ **Tape-measure it; it is five minutes and it underwrites every airflow number this file will ever quote.**
- **⛔ SIDE EFFECT — THE TEST RE-BASELINED THE INKBIRD, AND THE OFFSET SERIES IS BROKEN AT 2026-08-16 21:00.** The Inkbird stepped **+125 ppm** in one sample *(506 → 634)* and held there; **the primary walked smoothly down to its 588 trough with no discontinuity.** ➡️ **One sensor stepped while the other held — `MICROCLIMATE.md`'s own rule makes that a CALIBRATION shift, not the room.** **Mechanism: during the fan-off phase the bottom shelf was washed with genuine outside air and the Inkbird read 440–515 ppm, lower than it had ever seen. A cheap NDIR's automatic baseline correction takes its running minimum as ~400 ppm outdoor, so an unusually low exposure pushes every later reading UP.** ⚠️ **Consequence: `room_check.py` §5 will keep flagging a moved offset, and any comparison of Inkbird-vs-primary ACROSS 08-16 21:00 is meaningless.** *(Harmless to operations — the Inkbird is secondary and never a control input.)*
  - **🎯 AND IT IS EVIDENCE FOR THE OPEN QUESTION IN BACKLOG 4b(c): ABC re-baselining is now DEMONSTRATED in this room, on live hardware, with a known trigger.** That is the leading hypothesis for the **primary** sensor's unexplained ~+233 ppm zero move, and it has just gone from speculation to a mechanism observed here. ⬜ **It also means any future fan-off test will re-zero the Inkbird again — expect it, or disable its ABC first.**

### 📐 THE TWO ROOMS ARE THERMALLY COUPLED, AND THE COUPLING IS NOW A MEASURED NUMBER — 2026-08-16. **This prices the fork the humidifier finding leaves open.**

**Overnight means, 00:00–08:00, ten nights, grow room against fruiting room:**

**`fruiting = 9.15 + 0.433 × grow`, r = 0.961** — **the fruiting room follows the grow room at ~0.43 °C per °C.**

- **➡️ WHAT IT COSTS TO GET THE FRUITING ROOM BACK IN SPEC.** The humidifier holds 92% RH only at **≤17.2 °C**, and the room ran **18.39 °C** last night. Closing that **1.19 °C** needs the grow room down **2.75 °C — from ~21.4 to ~18.7 °C.** ⛔ **That is below the 21 °C setpoint and only ~1.2 °C above where the grow room sat BEFORE the 08-12 change. The colonisation gain would be almost entirely given back.**
- **🎯 BUT THE BAND HAS A BOTTOM, AND IT BUYS A MIDDLE OPTION.** The KPI is **90–95% RH**, not 92 flat. At the delivered ~13.5 g/m³, **90% RH allows ≤17.6 °C**, which needs the grow room only at **~19.6 °C**. ➡️ **That keeps roughly 2 °C of the colonisation gain AND puts the fruiting room at the bottom of the humidity band.** **Neither KPI is met handsomely; both are met.** ⚠️ **Sitting at the band edge means any warm night falls out of it** — this is a compromise, not a solution.
- **⛔ AND IT CONFIRMS THE FRESH-AIR FAN CANNOT DO THIS JOB.** This file already measured that actuator at **<0.3 °C**, against a **1.19 °C** correction needed. **Two nights were spent trimming it. It was never big enough.** ➡️ **The only route that gets BOTH KPIs without trading them is the direct outside→plenum intake (PLAN step 7)** — which is what this file has argued on other grounds, now with the trade it avoids priced.
- **⚠️ THE FIT'S REAL LIMITATION, STATED PLAINLY: it is two clusters, not a continuum.** Six nights at 14.5–17.5 °C and four at 21.4–22.4 °C, with the 08-12 step between them. **`r = 0.961` is therefore mostly the step, and `0.433` is the average across it — not a validated linear response.** **An intermediate aircon setting is what would test it**, and that test is also the middle option above, so **one action does both.**

### 🗺️ ROOM CLIMATE — WHERE BOTH SEASONS STAND, 2026-08-14. **Read this before the five blocks below it.**

**Operator asked: do we now have a plan for summer and winter? ➡️ We have TWO DIFFERENT THINGS, and calling them both "a plan" would flatter one of them.**

| | **WINTER** | **SUMMER** |
|---|---|---|
| what exists | **A DESIGN.** Settled architecture, parts identified, one price | **AN INVESTIGATION PLAN.** One candidate killed, three live, none chosen |
| temperature | ✅ solved on paper, authority ample | ⛔ **unsolved — no candidate selected** |
| humidity | ⚠️ a prediction; its hinge is unmeasured | ⛔ downstream of the above |
| built | **nothing** | nothing |
| measured | **nothing** | nothing |

**🔑 AND THE USEFUL FINDING IS THAT THERE ARE NOT TWO PROGRAMMES — THERE IS ONE MEASUREMENT PROGRAMME WITH TWO SEASONS DOWNSTREAM OF IT.** **Four of the five missing numbers serve BOTH seasons**, which is why nothing below should be sequenced as "winter work" and "summer work":

| # | the missing number | serves | cost | status |
|---|---|---|---|---|
| 1 | ~~Humidifier's real ceiling — fresh discs~~ | both | R0 | ✅ **DONE 2026-08-18 — discs did nothing, on a clean comparison** |
| 2 | ~~Fresh-air fan FLOW — CO2 decay~~ | both | R0 | ✅ **DONE 2026-08-16 — 4.02 ACH ≈ 137 m³/h** |
| 3 | **Outdoor temp + RH** | both | **R653.20** | ⬜ buy |
| 4 | **Aircon draw & capacity** — energy meter | both | **R720** | 🔓 **item 5(a) — UNBLOCKED 2026-08-18, part sourced** *(Shelly EM Gen3 + 50 A CT; the vent experiment that deferred it is resolved)* |
| 5 | Room load on a hot day | summer | R0 *(Oct–Nov)* | ⬜ |

- **✅ #1 AND #2 ARE NOW BOTH DONE, AND NEITHER INVALIDATED THE BUILD** *(updated 2026-08-18)* — the humidifier has headroom *(duty off its pin)* and the fan's flow is known. ➡️ **#4 is therefore the front of this queue, and it is no longer blocked.** ~~#1 AND #2 ARE FREE AND UNDONE, AND EITHER COULD INVALIDATE THE BUILD.~~ **If the humidifier has no headroom after re-disking, the mixing blade will out-run it and the room needs a bigger humidifier BEFORE it needs a box.** **Do them first.**
- **📅 THE CALENDAR DOES THE SEQUENCING, because the seasons gate the readings.** **Now–Aug:** the two free measurements. **Before Sept:** build, if going ahead — **Sept–Oct is the windiest period (39.4% of hours over 12 km/h), so it is when the uncontrolled path costs most AND the worst window in the year to READ a result.** **Build for protection, do not measure.** **Oct–Nov:** hot days give the summer load curve. **Nov:** a calm month — read the build's actual benefit. **Dec:** choose the summer candidate against real numbers. **Late Jan:** the 95-hour crunch.
- **⛔ WHAT IS STILL UNSCOPED, and it is not small: the FRONT-WALL half.** The mixing box is the **intake** only. The 07-23 design is **intake + defined exhaust + sealed grate**, and item 10 now needs a **MODULATING** front-wall damper *(shut at 03:00 in winter, open at 05:00 in summer)* **which nobody has designed.** **Until it exists, a controlled intake runs in parallel with an uncontrolled one and the weather still moves the room ~0.9 °C.**

**🔴 AND THE HONEST NOTE ON PRIORITY, BECAUSE THIS FILE'S OWN TRAP WARNING APPLIES TO TODAY.** **Everything in this section is ENABLER TIER.** **A perfectly banded room with no second customer earns nothing**, and **item 0 — Spar blocked, a second demand route unfound — has not moved.** ⚠️ **`CLAUDE.md`: *"room and ledger work is more tractable than sales, so it will crowd it out if allowed."* An entire session went into room engineering.** ➡️ **Of everything above, only the R0 measurements and the R653 sensor are defensible before there is somewhere to sell more mushrooms. The fabrication is not.**

### 🌬️ WIND IS SEASONAL, AND THAT CHANGES WHAT THE INTAKE HAS TO BE — measured 2026-08-14

**Operator, 2026-08-14:** *"We do not get much wind in Pretoria. Only in August and before a rain storm."* **✅ The archive confirms both halves — and adds one he did not name, which lands right after this month.** Open-Meteo archive, 3 years, this property's cell:

| | Dec–May *(quiet)* | Jun–Jul | **Aug** | **Sep** | **Oct** |
|---|---:|---:|---:|---:|---:|
| mean wind km/h | 7.6–8.2 | 8.3–8.5 | **9.7** | **11.7** ⛔ | **10.9** |
| % of hours over 12 km/h | 12.5–16.7% | 17.9–19.1% | **28.0%** | **39.4%** ⛔ | 36.7% |
| **night-to-night swing** *(the confound)* | **3.0–3.4** | 4.0–4.5 | **4.2** | **4.3** | 4.2 |

- **✅ HE IS RIGHT ON BOTH COUNTS.** August runs **28% of hours over 12 km/h against 12.5–16.7% in the quiet half of the year**, and **rain hours average 10.2 km/h against 8.8 dry** — *"before a rain storm"* is in the data.
- **⛔ BUT THE PEAK IS SEPTEMBER, NOT AUGUST — 11.7 km/h mean and 39.4% of hours over 12, the windiest month by a clear margin, with October second.** ➡️ **The windy season is August→October and it is about to get worse, not better.** **That is the single most decision-relevant line here**, because the intake is being designed now.
- **✏️ SO MY "3× DISTURBANCE SWING" FRAMING WAS OVERSTATED AS A YEAR-ROUND CLAIM.** It was fair for that night and it is fair for Aug–Oct. **It is not a permanent property of this room.** ⚠️ **Though it does not vanish either — even the calmest months carry a mean night-to-night change of ~3 km/h and consecutive-night ratios up to 3.6–4.3×, and the ratio that voided the fan test was 3.1×.** **That magnitude occurs in every month; August merely makes it frequent and larger.**
- **⚠️ AND THE MODEL IS 10 m WIND ON A ~1 km GRID CELL, NOT THE WIND AT THE WALL.** Local shelter — buildings, trees, the yard — plausibly cuts the absolute figure well below these numbers. **Trust the SEASONALITY, which is a regional signal; treat the MAGNITUDES as an upper bound.** The operator's direct experience of the site is the better guide to how hard it actually blows there.

**🔑 THE CONSEQUENCE THAT MATTERS, AND IT IS GOOD NEWS: FOR MOST OF THE YEAR THE DISTURBANCE IS STACK-DRIVEN, NOT WIND-DRIVEN — AND A STACK IS PREDICTABLE.** At ~8 km/h mean against a winter indoor/outdoor ΔT of **12–14 K**, buoyancy dominates for nine months. ➡️ **Stack flow is a slow, smooth function of a quantity the ESP ALREADY MEASURES on both sides.** **A controller can anticipate it. It cannot anticipate a gust.** **So the room is materially more controllable than the 08-14 night suggested** — that night was near the worst case, not the normal one.

**🎯 AND IT SETTLES A DESIGN QUESTION: THE INTAKE MUST BE A FAN *AND* A SHUTOFF, BECAUSE THE TWO SEASONS NEED OPPOSITE THINGS.**

- **❄️ WINTER — restrict a flow that is already too strong.** Stack ΔT is 12–14 K, so passive flow through the front-wall openings is vigorous and unwanted at 03:00. **The winter job is a DAMPER.**
- **☀️ SUMMER — create a flow where there is none.** In the 04:00–06:00 window outdoors sits at **16.6–17.0 °C against a 17 °C room, so stack ΔT is ≈ 0**, and summer wind is at its yearly low (8.1–8.3). ➡️ **Passive pre-dawn infiltration in summer is essentially nil. The only free cooling of the summer day cannot be captured without a powered fan.**
- ➡️ **One part does both: an inline fan with a backdraft/motorised damper.** **⛔ A passive damper alone fails summer entirely, and a fan alone cannot shut out a 14 K winter stack.** *(This is an argument for the operator's ESP-driven fan over the cheaper damper-only option, and it comes from the seasonal data rather than from preference.)*

**⬜ TIMING: BUILD EARLY, MEASURE LATE.** Sep–Oct is when the uncontrolled front-wall path does the most damage, so the intake earns most if it is in **before** September. **But it is the worst window in the year to READ a commissioning result** — 39.4% of hours over 12 km/h. ➡️ **Commission it for protection now; postpone any before/after measurement to November or later, or it will be voided the same way the fan test was.**

### ☀️ THE SUMMER PLAN — 2026-08-14. **Evaporative cooling is ruled OUT on measurement. The load has never been measured, and that is the gate.**

**⛔ CANDIDATE 1 — EVAPORATIVE COOLING: DEAD, AND ON TWO INDEPENDENT GROUNDS.** `STATUS.md` has carried it as *"thermodynamically the right tool for a room that wants moisture."* **Measured, it is not.**

| Pretoria summer, Dec–Feb, 3 seasons, n=6,504 h | dry bulb | **wet bulb** |
|---|---:|---:|
| 03:00–06:00 | 17.4–18.0 | 15.5–15.7 |
| **10:00–17:00** | **26.5–27.3** | **18.4 mean** ⛔ |
| all summer hours | 21.2 | 17.1 *(min 8.9, max 21.8)* |
| **% of summer hours with wet-bulb under 15 °C** | | **13.5%** |

- **⛔ WET-BULB IS THE FLOOR AN EVAPORATIVE COOLER CAN REACH, AND THE SUMMER DAYTIME FLOOR IS 18.4 °C — ABOVE THE 18 °C BAND CEILING.** **A theoretically perfect 100%-efficient cooler misses the band on an average summer afternoon, before any efficiency loss, any duct gain, or any envelope load.** Real units reach 70–85% of the wet-bulb depression, so the practical figure is worse still.
- **⛔ AND THE SECOND REASON IS MORE FUNDAMENTAL: THE EVAPORATIVE POTENTIAL IS ALREADY SPENT.** **The ultrasonic humidifier IS an evaporative cooler** — it takes its latent heat from the room. **The room already sits at 90–95% RH, which is air with almost no capacity to evaporate anything more.** ➡️ **There is no unexploited evaporative headroom to buy. A dedicated evaporative stage could only act on the make-up fraction, and even there it is floored at 18.4 °C.** **Strike it from the candidate list.**

**🔴 AND THE REAL GAP IS NOT A MISSING TECHNOLOGY — IT IS THAT NOBODY KNOWS WHAT THIS ROOM ACTUALLY DOES IN JANUARY.** **Instrumentation only starts around July 2026.** ➡️ **Every summer conclusion in this file is derived from OUTDOOR climate, not from the room.** **The 95-hour run proves the cold SOURCE is unavailable; it does NOT prove the ROOM goes out of band** — the ceiling is insulated, the walls are 250 mm, the front wall carries 100 mm Isoboard, and there is thermal mass and an aircon. **⛔ Do not size or buy a cooling solution against a load that has never been measured** — that is this file's own standing rule, and it has already been broken three times *(the 867 W aircon, the variac ΔT, the R707 fridge saving)*.

**➡️ SO THE PLAN IS SEQUENCED AROUND MEASUREMENT, AND SPRING IS THE WINDOW.**

**PHASE 0 — MEASURE, Sept–Nov. Nothing here is speculative and most is already queued.**
- **⬜ Buy the outdoor `SEN0438` NOW (R653.20).** ➡️ **It is not only the damper's feedforward — it is the instrument that makes a summer load reading INTERPRETABLE.** **Room temperature without outdoor temperature is the same unreadable pair that voided the fan test.**
- **⬜ Log the room through the hottest days of Oct–Nov.** **Late spring gives 30 °C+ days before the January crunch**, so **you enter December with a measured load curve instead of an estimate.** ➡️ **`room_check.py` already produces this; it just has to be run on the right days.**
- **⬜ Item 5(a) — CLAMP-METER THE AIRCON. This is the gate on every mechanical candidate below**, and it has been queued since July without being done. **Nameplate `Alliance INAA18` implies ~5.3 kW cooling; whether that holds ~34 m³ of fruiting room plus ~40 m³ of grow room on a 32 °C day is exactly the unanswered question.**
- **⬜ Item 7c — the CO2-decay flow measurement.** Same number is needed to size any make-up-air treatment.

**PHASE 1 — REDUCE THE LOAD BEFORE BUYING CAPACITY. Cheapest first, and the roof is already done.**
- **✅ The "insulate the roof" case is VOID and must not be resurrected — the ceiling is insulated** *(that calculation was built on it being bare and the premise was wrong)*. ➡️ **Remaining load levers are EXTERNAL: shading, and a reflective coating on the flat iron roof.** **⬜ Neither has been costed.**

**PHASE 2 — THE CROP-SIDE ANSWER, AND IT MAY DOMINATE THE ENGINEERING ONE.**
- **🎯 SUMMER IS HOSTILE TO FRUITING AND FAVOURABLE TO COLONISATION — the building's problem inverts with the season.** **Colonisation wants 24–27 °C and `STATUS.md` records it is *"beyond what this equipment delivers in this space at all"* in winter.** ➡️ ~~**In summer that comes free.**~~ **✏️ CORRECTED 2026-08-18 — LESS FREE THAN THIS READS.** Outdoor summer air is **below 24 °C for 74.2% of hours** and above 27 °C for only 10.5%, so the grow room may want trim *heating* at night, not cooling *(full working: the dewpoint block below)*. **The room does run warmer than ambient, by an unmeasured margin — so the direction of its summer duty is unknown.** **The seasonal-weighting idea survives** — weighting summer toward colonisation and winter toward fruiting still uses the building's natural swing instead of paying to fight it — **but it can no longer be argued on "free", only on "cheaper than the alternative".**
- **⬜ A WARM-FRUITING SPECIES FOR SUMMER — pink oyster (*Pleurotus djamor*) fruits at roughly 24–30 °C**, which turns the January problem into a non-problem for the cost of different spawn. ⚠️ **Its costs are commercial, not technical: a different product to sell, a notably shorter shelf life, and a market that has not been tested.** ⛔ **`CLAUDE.md` says cultivation technique is undocumented here — ask, do not assume.**
- ⚠️ **These are not defeatist options. They are the only ones on this page that cost near-zero capital**, against mechanical candidates that have never been costed at all.

**PHASE 3 — MECHANICAL COOLING, ONLY IF 1 AND 2 DO NOT CLOSE IT.**
- **✅ CANDIDATE 2 — CONDITION THE MAKE-UP AIR — is now the front-runner, and the winter build sets it up.** A cooling coil on the **outside-air branch only**: **it sits OUTSIDE the humid room, so its condensate drains away instead of fighting the humidifier in the growing space**, and the plenum re-humidifies downstream, which it already does. **✅ STRENGTHENED 2026-08-18 BY MEASUREMENT, NOT ARGUMENT: the summer dewpoint here averages 14.4 °C and exceeds 17 °C only 8.1% of hours, so an upstream coil barely condenses at all** *(dewpoint block below)*. ⛔ **This does NOT license a DX split — its coil surface sits at 5–10 °C whatever the air does.** ➡️ **🎯 SO SIZE THE MIXING BOX TO ACCEPT A COIL ON THAT BRANCH LATER. That costs nothing now and preserves the whole option** — build it cramped and Phase 3 needs the box rebuilt.
- **⬜ CANDIDATE 3 — chilled water held above the room's ~15.8 °C dewpoint.** **The technically correct answer and what commercial farms use**; a 1.2 K control window a conventional split cannot hold. **Almost certainly out of budget — price it only to know what "proper" costs.**
- **⬜ CANDIDATE 4 — a split in the fruiting room, fought with humidifier capacity.** **Cheapest capital, worst running cost**; the file's *"two appliances fighting and a large electricity bill"*. **Keep it on the list as the fallback it is.**

**⚠️ PRIORITY, UNCHANGED: this is enabler tier and demand is still the binding constraint.** **Phase 0 is the only part that should happen before there is a second customer** — it is cheap, it is mostly already queued, and **without it every later decision is a guess.**

### 📋 IS THE WINTER SOLUTION COMPLETE? — audit, 2026-08-14. **Temperature: yes on paper. Humidity: a prediction with one unmeasured term. Build: two-thirds designed.**

**Operator asked directly, and the answer is worth being precise about rather than encouraging.**

**✅ THE TEMPERATURE HALF IS SOLVED IN PRINCIPLE, AND THE AUTHORITY IS AMPLE.** The mixing box lets the fruiting room sit at 17 °C while the grow room keeps the 21.8 °C that bought the colonisation gain — the two-temperature problem this building has never been able to answer on one aircon. **Rough sizing: the fan currently supplies ~22 °C air into a 19 °C room; at full outside it would supply ~6 °C. That is a ~16 K swing across 100% of the fan's flow, against the ~10% flow change that moved 0.2–0.3 °C.** ➡️ **Authority is not the risk — OVER-cooling is**, which is exactly why the minimum-internal-fraction and the modulation matter. *(⚠️ Back-of-envelope off a confounded night, not a measurement.)*

**⛔ BUT THREE THINGS ARE NOT SOLVED, AND THE FIRST IS STRUCTURAL.**

1. **⛔ THE UNCONTROLLED PATH IS STILL OPEN — the design is 2 of its 3 parts.** `MICROCLIMATE.md`'s 07-23 design is **intake + front strip as defined exhaust + drain grate sealed.** **The mixing box is the intake only.** **The front-wall grate and 50 mm strip stay wide open, so a controlled intake runs in PARALLEL with an uncontrolled one and the weather still moves the room ~0.9 °C.** ➡️ **And the fix for that half is not merely unbuilt, it is UNSCOPED: item 10 now requires a MODULATING front-wall damper** *(shut at 03:00 in winter, wide open at 05:00 in summer)*, **and nobody has designed one.** **That is a second fabrication job of similar size to the first.**
2. **⚠️ THE HUMIDITY RECOVERY IS A PREDICTION, AND ITS HINGE IS STILL UNMEASURED.** Cooling to 17 °C drops the 92% RH requirement **14.99 → 13.30 g/m³** against a current delivered **13.72** — which is why it should cycle instead of pin. **✅ And the operating point is evidenced: 08-11 ran 16.65 °C / 90.65% RH / 72.4% duty.** ⛔ **But those nights were cool because the aircon was WEAK, not because outside air was being forced in. The damper ADDS a loss term that has never been in the record.**
   - **🔑 AND THE ENERGY BALANCE SAYS THE MOISTURE COST IS THE BIGGER HALF.** Per m³ of 6 °C outside air into a 17 °C room: **sensible cooling ≈ 13.3 kJ**, **latent cost of replacing the moisture ≈ 17.2 kJ** *(7.0 g × 2450 J/g)*. ➡️ **Ventilative cooling in a humidified room buys temperature with water, and the water is the larger term. It is not a free lunch and it must be modulated, not left open.**
3. **⛔ THE HUMIDIFIER'S CEILING IS UNKNOWN, AND SO IS THE FAN'S FLOW — SO THE TRADE CANNOT BE SIZED ON PAPER.** We know the unit delivers **13.72 g/m³ at 100% duty**; we do not know its maximum. **And `HARDWARE_REFERENCE.md` records that the manufacturer publishes NO airflow figure for this fan at all**, so the m³/h that would turn "7.0 g per m³" into a real gram-per-hour load **does not exist as a number anywhere.**

**🎯 THE ONE FREE MEASUREMENT THAT CLOSES THE BIGGEST GAP: A CO2 DECAY TEST.** **Let CO2 rise with the fan off, then run the fan and log the decay.** The air-change rate falls straight out of the decay constant against the room's known **~34 m³**, and **the flow is then a measured number for the first time.** ➡️ **✅ It works despite the sensor's ~350 ppm offset, because a DECAY RATE is a differential over one sensor and the zero cancels — the same argument this file already uses for the CO2 trend.** **Instrument already installed, nothing to buy, one evening.** ⚠️ **It also needs the fan genuinely off, which crashed the bottom shelf in ~4 h on 07-25 — so run it ATTENDED and short, not overnight.**

**➡️ AND THE CHEAPEST THING THAT WOULD DE-RISK THE WHOLE BUILD COSTS NOTHING AND IS ALREADY QUEUED:** **fresh discs** *(item 6b step 2 — on hand, reversible, and it establishes the humidifier's real ceiling)*. **Do that before spending on sensors, ducting or fabrication.** **If the unit has no headroom even after re-disking, the damper will out-run it and the design needs a bigger humidifier before it needs a mixing box.**

**⚠️ AND IT MANAGES THE CONFLICT RATHER THAN REMOVING IT.** Holding two rooms at two temperatures off one aircon means **heating air in the grow room and then deliberately cooling it on the way to the fruiting room.** **The structural fix is still a separate grow room / the divider wall** — this design makes the interim liveable, and should not be recorded as making the wall unnecessary. **⛔ Summer is untouched by all of it — the 95-hour January run stands (item 9b).**

### 🎛️ THE INTAKE BUILD — settled design, 2026-08-14. **Constant-speed fan + ESP-modulated mixing blade, feeding the plenum.**

**Operator's architecture, and it dissolves a problem this file has circled since 07-24.** `MICROCLIMATE.md` §142: the fresh-air fan *"simultaneously governs CO2 venting, temperature coupling, grow-room ventilation, positive pressure and the humidifier drying load — these pull against each other."* **Modulating temperature with FAN SPEED moves all five at once, which is why every fan experiment here has been unreadable.** ➡️ **A mixing element changes the TEMPERATURE of the supply without changing its VOLUME.** Total flow — and with it positive pressure, CO2 exchange, grow-room ventilation and moisture delivery — **stays put while temperature is controlled independently. Two actuators for two independent jobs, which is the right number.**

**🔑 AND THE GAIN IS *WHERE THE COLD AIR ARRIVES*, NOT MERELY THAT IT IS CONTROLLED.** Outside air currently reaches the room two ways and **neither delivers it usefully**: through the **15 mm hole → grow room → fan**, by which point it is tempered to ~22 °C and **is no longer cold**; or raw through the **front-wall grate**, dumped **at floor level onto the bottom shelf** — the documented cause of the overnight cold/dry layer. **A direct outside→plenum path is the only one that delivers cold air MIXED AND RE-HUMIDIFIED before it touches a bag.**

**🔧 THE BUILD — a two-port mixing box on the fan's inlet, one pivoting blade, one servo.**

- **⛔ IT IS FABRICATION, NOT A PURCHASE, AND THAT IS NOT OBVIOUS FROM THE ARCHITECTURE.** `MICROCLIMATE.md`: the fan is *"mounted against the ceiling, feeding into the plenum"* and **is not ducted to outside — its INLET IS AN OPEN MOUTH IN THE GROW ROOM.** **There is no bore for an inline damper to sit in.**
- **✅ AND ONE BLADE IN A TWO-PORT BOX BEATS A DAMPER: as it closes one port it opens the other, so total open area is constant BY GEOMETRY** — the architecture's core property delivered mechanically, with **one actuator instead of two linked ones.**
- **✅ FAIL-SAFE BECOMES MECHANICAL, WHICH BEATS A FIRMWARE RULE.** Park the blade **covering the OUTSIDE port at rest** *(spring, or gravity if geometry allows)*, so loss of power or signal lands at **full internal**. **Stuck full-outside floods the room with ~6 °C air and crashes it cold and dry within hours; stuck full-internal merely drifts warm, which is survivable.** **It cannot be forgotten in a reflash.**
- **⛔ NEVER 100% OUTSIDE — the grow room's ONLY ventilation is a side effect of this draw** *(it went stuffy over 07-18→07-23 when the fan was out)*. **A minimum internal fraction in firmware, alongside the minimum-flow floor. Two floors, two failure modes.**
- **⛔ KEEP THE 15 mm HOLE AS THE GROW ROOM'S OWN INLET; make a SEPARATE penetration for the outside duct.** Re-using it routes outside air **past** the grow room — the same failure.
- **⚠️ SERVO OUTSIDE THE BOX, shaft through the wall.** Two fans have already died in this building's humid airstreams. **Torque is trivial; 60–90° of travel is all that is used. Do not overspec.**
- **🎯 SIZE THE BOX TO ACCEPT A COOLING COIL ON THE OUTSIDE-AIR BRANCH LATER** — that is the summer plan's front-running candidate, and **building it cramped means rebuilding the box.**
- **⬜ MEASURE FIRST, none of it recorded:** the fan's **actual inlet spigot** *("100 mm inline" is a nominal duct size)*, the **ceiling clearance** for the box, and the **route and wall thickness** for the new penetration.

**🌡️ WHAT IT ACTS ON — three temperatures, three jobs. Only one is the setpoint variable.**

| role | sensor | status |
|---|---|---|
| **Controlled variable** | fruiting-room RS485 `SEN0438`, top shelf | ✅ installed |
| Feedforward, warm side | grow-room DHT22 (GPIO33) | ✅ installed |
| Feedforward, cold side | **outdoor temp + RH** | ⛔ **buy** |
| Verification — the blade's "tacho" | mixed-air, in the box, **before the humidifier** | ⛔ build-time |

- **🔑 FEEDFORWARD, NOT A PLAIN THERMOSTAT — the blade's authority changes by an order of magnitude across the year.** **`f = (T_grow − T_target) / (T_grow − T_out)`.** At 6 °C outside, 20% open is a large effect; at 17 °C on a summer pre-dawn, 100% open is nearly nothing. ➡️ **A fixed-gain room loop hunts in July and does nothing in January. The formula replaces tuning with arithmetic**, and a **slow** trim on the room sensor takes the residual — the room has hours of lag and must not be chased.
- **✅ THE MIXED-AIR PROBE IS THE BLADE'S TACHO.** A cheap servo has **no position feedback** — the same blindness that let a dead fan display **"82%"** for ~24 h. **Commanded position moves and mixed-air does not ⇒ the blade is stuck, and that is alarmable.**
- **⛔ NOT A TEMPERATURE-ONLY LOOP.** Opening toward outside costs **~7.7 g of water per m³**. **A humidity guard must be able to override temperature demand — computed ON-DEVICE from the RS485 sensor's own temp and RH**, because `SAFETY.md` puts control local and the existing `fruiting_room_vpd`/`absolute_humidity` are **Home Assistant templates that die with the Pi.** *(Judge on VPD/AH; raw RH is temperature-confounded and this blade changes temperature by design.)*
- **⚠️ Control on the TOP-SHELF primary. The shelf delta is an INTERLOCK, not an input, and it must FAIL SAFE ON STALENESS** — the Inkbird is *"verification only, never control"*, reads at 1 °C, and **on 08-09 it froze while the shelf-delta template kept producing plausible numbers, voiding two nights.** **Stale ⇒ blade to INTERNAL.**
- **➡️ Carry 07-29's preconditions:** plausibility clamp, fail-to-known-good, slew limit.
- **✅ AND IT DOES NOT REVERSE THE 07-29 "NO SENSOR AUTHORITY" DECISION — the sensor is different.** That refusal was about **CO2**, on the explicit grounds that it is untrusted *(both CO2 sensors under-read ~350 ppm AND agree, so their drift check is blind)*. **Temperature is cross-checked against two other instruments and has never taken a zero shift.** **Say this when building, or it will be read as the declined loop returning.**

**🧩 PARTS — and the enclosure was built for this.** **TB2 / MOSFET2 / GPIO27** is a **12 V PWM output, wired, fused (Fuse 4) and idle** since 07-18, wires **W36–W41** in place — **nothing inside the enclosure needs rewiring.** **GPIO21 free for a tacho if a fan is ever added.** **Sensors go on the RS485 bus** *(one bus, one protocol — the handover argument)*: **`SEN0438` at R653.20**, address **3** = mixed-air *(DIP 1+2)*, **4** = outdoor *(DIP 3)*. **Its start register `0x0000`, 2 registers, 4 data bytes are IDENTICAL to the installed sensor, so `query_device` needs no change and each addition is two lines.** **Fan and variac are R0 — already owned.**

**⛔ RULED OUT, so it is not re-proposed *(compressed 2026-08-14; full reasoning in `git log`)*:**

1. **A variable-speed fan as the temperature actuator** — it re-couples the five jobs the mixing blade separates. *(`DECISIONS.md` 07-29 already wanted the fan at **a fixed point, dialled in and left there**, which is what a variac gives at R0. Those two decisions were never in conflict — they are about different halves.)*
2. **`RS485-TH`** *(Micro Robotics' cheaper probe)* — **rated `0–80% RH`**, against a room at 90–95% and outdoor overnight RH that hit **94%** last night. **Also readdressed by BROADCAST to `00`, which on a live TB7 would readdress the CO2 and temp/RH sensors and blind the room**; its default address `01` collides with the CO2 sensor on contact. ⚠️ **Its byte order is also reversed vs the installed part — a blind copy-paste yields a plausible 27.3% RH / 62.6 °C.**
3. **1-Wire DS18B20 probes** — a second sensor standard for no gain, against an objective that is explicitly handover-readiness.
4. **An off-the-shelf butterfly damper** — nothing to fit it to *(no intake duct)*, and SA suppliers do not stock modulating dampers at this size *(Rotolok starts at 350 mm; Belimo-class actuators are commercial-HVAC scale)*.

### 💧 THE HUMIDIFIER IS AT ITS BEST-EVER OUTPUT AND LOSING — because the room got warm, not because the unit got weak. Measured 2026-08-14

**Operator, 2026-08-14:** *"To get more humidity capacity at the cheapest price i think the sides of tub must be cut and the disks replacement need to be tested."* **➡️ Both are on the record as candidates and both are re-openable — but the measurement says the cheapest capacity is not on the humidifier at all.**

| night | temp | RH | **AH delivered** | AH outdoor | deficit | duty |
|---|---:|---:|---:|---:|---:|---:|
| 08-09 | 17.12 | 91.74% | 13.37 | 5.42 | 7.95 | 100% |
| 08-10 | 16.74 | 90.85% | 12.94 | 4.65 | 8.30 | 83.1% |
| **08-11** | **16.65** | **90.65%** | 12.85 | 6.78 | 6.06 | **72.4%** |
| 08-12 | 14.92 | 90.70% | 11.57 | 6.28 | 5.30 | 76.6% |
| 08-13 | 18.16 | 87.28% | 13.54 | 5.93 | 7.61 | 100% |
| **08-14** | **19.03** | **84.00%** ⛔ | **13.72** ✅ | 6.06 | 7.66 | 100% |

- **🔑 THE TWO COLUMNS MOVE OPPOSITE WAYS, AND THAT IS THE WHOLE FINDING. AH delivered is the HIGHEST in this record (13.72) on the night RH is the LOWEST (84.00%).** A throttled humidifier — worn discs, a blocked tub — shows up as **low AH output**. **We have record-high AH output.** ➡️ **Neither disc wear nor a transport restriction is the current binding constraint, because both have the opposite signature to the one in the data.**
- **📐 WHAT ACTUALLY CHANGED IS THE REQUIREMENT.** To hold **92% RH** the room needs **12.53 g/m³ at 16 °C** and **14.99 at 19 °C — +20%** — while the deficit that drives the loss goes **6.23 → 8.69, +39%.** **The 08-12 aircon fix moved the room 3.3 °C and made the humidifier's job ~1.4× bigger overnight.** The unit answered with +7% output and lost the rest.
- **✅ AND THE ARITHMETIC RUNS BACKWARDS CLEANLY, WHICH IS THE CHEAP FIX.** Put **today's actual 13.72 g/m³ output** into a cooler room: **at 17 °C it gives 94.9% RH** — the top of the 90–95% band, with the humidifier **cycling instead of pinned**. At 16 °C it saturates. ➡️ **The room being ~2 °C too warm IS the humidity problem. Fix the temperature and the humidity fixes itself, with the equipment already installed and nothing cut.**
- **⛔ AND 19 °C IS INDEPENDENTLY WRONG.** `MICROCLIMATE.md` KPI 2 calls temperature the **highest control priority**, band **15–18 °C**, grey oyster a cool-fruiter. **So capacity spent holding RH at 19 °C is capacity spent sustaining a condition the crop does not want.** Fixing the temperature closes **both** faults; adding humidifier capacity closes one and leaves the crop too warm.

**⚠️ BUT THIS IS THE FORK THIS FILE ALREADY NAMED, AND IT IS EXPENSIVE BOTH WAYS.** *"Either the fruiting room gets moisture capacity to hold 90% RH at 18.3 °C, or the aircon setpoint comes back down and the colonisation gain is given back."* **The 08-12 change was a real win for the grow room** — overnight mean **14.48 → 21.84 °C, at setpoint for the first time in this record** — and colonisation is the long pole at 21–30 days. **Giving that back to cool the fruiting room is not free.**

- **🔑 WHICH IS EXACTLY THE BLENDING PROBLEM, AND IT NAMES THE CHEAP LEVER.** The two rooms need **different** temperatures — grow ~22 °C, fruiting ~17 °C — off **one** aircon. **The only actuator that can hold them apart is the cold side, and it has no valve** *(see the blender block below)*. ➡️ **A controlled cold-air intake lets the grow room keep its 21.8 °C AND the fruiting room come back to 17 °C — which then also fixes the humidity for free.** **One part, three problems.** *(`MICROCLIMATE.md`'s 07-23 tempered-intake decision.)*

**➡️ SO THE ORDER IS: TEMPERATURE, THEN DISCS, THEN CUTTING — cheapest and most reversible first, and each step may make the next unnecessary.**

1. **⬜ Get the room back toward 17 °C.** Free, reversible, fixes the band violation and the humidity together. **The lever with authority is the aircon** *(3.3 °C in one step)*, not the fan *(<0.3 °C)*.
2. **⬜ Fresh discs — free, on hand, reversible, and a diagnostic.** `MICROCLIMATE.md` already recommends this ordering: *"Try the new disks FIRST — likely the cheapest headroom fix… It's also a DIAGNOSTIC — a noticeable duty drop after re-disking confirms the old discs were degrading."* **✏️ AND THE "DISCS WERE NEVER WORN" FINDING OF 07-26 IS WEAKER THAN IT READS: it was INFERRED because the tub hole explained the symptom, never measured** — and `MICROCLIMATE.md` §5 records that **no instrument for disc wear exists** without the power-monitoring plug, which was never fitted. **Three weeks and a 3.3 °C step later, "optional" is worth ten minutes to retest.**
3. **⛔ CUTTING THE TUB IS LAST, AND NOT YET — it is the only irreversible one on the list.** ✅ **The operator is right that it is re-openable:** item 7's *"DO NOT CUT"* of 08-12 carries its own re-check condition — *"the room was below band on both test nights, and a colder room needs less absolute moisture for the same RH — re-check 04:00–07:00 once the aircon is settled"* — **and that condition has now fired.** ⚠️ **But the record-high AH says transport is not what binds today**, and **⬜ nobody has ever measured the existing hole's area against the tub's side area.** **Do that arithmetic first** — the same calculation that settled the return duct at *69 × 12 mm = 93% of duct area*. **If the existing opening is already a large fraction, more cutting buys little; if it is small, the case is strong.** **⚠️ And cut above the float's working level — the tub is the reservoir.**

### 🌡️ THE ROOM IS A BLENDER, AND IN SUMMER IT RUNS OUT OF ONE INGREDIENT — measured 2026-08-14

**Operator's framing, 2026-08-14, and it is the right one:** *"for the temp in winter the fruiting room will have a stable warm air source in the growing room. There is also cold air available from outside if we should choose to use it. In summer the cold air source will be gone in the day and even sometimes at night."* **➡️ The fruiting room has no refrigeration of its own — it reaches its 15–18 °C band by BLENDING a warm source against a cold one. Blending only works while the target sits BETWEEN the two sources.** This file has argued "summer inverts" in three places; **nobody had measured how far.** Open-Meteo archive, this property's grid cell, last summer and this winter:

| hours with outside air below… | **Summer** *(Dec 2025–Feb 2026, n=2160)* | **Winter** *(Jun–Aug 2026, n=1776)* |
|---|---:|---:|
| **18 °C** — the band ceiling | **24.6%** | **79.7%** |
| 17 °C | 13.6% | 74.7% |
| **15 °C** — cold enough to PULL a warm room down | **2.8%** ⛔ | 63.0% |
| longest unbroken run with **nothing** below 18 °C | **95 hours** *(from 2026-01-25 07:00)* ⛔ | 10 hours |

- **✅ WINTER IS A BLENDING PROBLEM AND IT IS SOLVED IN PRINCIPLE.** Air below 18 °C is available **100% of hours from 18:00 through 09:00** — every night, without exception, in this record. Warm side ~22 °C in the grow room, cold side 8–11 °C outside, target 15–18 sits squarely between. **No new refrigeration is needed to hold band in winter. What is needed is control** — see the actuator finding below.
- **⛔ SUMMER IS NOT A BLENDING PROBLEM AT ALL, AND "SOMETIMES AT NIGHT" IS PRECISE.** Hour-of-day, share of summer days offering air below 18 °C: **10:00–17:00 → 1–3%** *(essentially never)*; **midnight → 34%**; and it is only reliable in the **04:00–06:00 pre-dawn window at 72–88%**, where the mean is **16.6–17.0 °C — at the band's ceiling, not below it.** ➡️ **Both sources sit above target for most of a summer day, so there is no mixture that reaches 15–18 °C. This cannot be fanned, ducted, damped or vented away.**
- **🔑 THE 2.8% IS THE NUMBER THAT KILLS THE CHEAP OPTIONS.** To *pull down* a warm room you need a source meaningfully **below** target, not merely below its ceiling — and summer offers that **2.8% of hours**. ➡️ **Night-flushing into thermal mass is the first cheap idea anyone reaches for, and the 95-hour run in late January says it cannot carry the room: there is no night to flush with.** Assess it if you like, but assess it against 95 hours, not against one bad afternoon.
- **📅 SO THE SUMMER QUESTION ABOVE HAS A DATE AND A DURATION, WHICH IT DID NOT BEFORE.** The requirement is **hold 15–18 °C through ~95 continuous hours with no free cooling anywhere on the property**, and the crunch lands **late January**. ⚠️ **Hinges on:** *last summer being representative* — one season, one grid cell, modelled reanalysis rather than an on-site instrument. **Size of the move if wrong: the duration, not the conclusion. Even a mild summer leaves the 10:00–17:00 window at 1–3%, and the band is missed by the shape of the day, not by its extremes.**

### 🌡️ THE DEWPOINT WAS THE MISSING NUMBER, AND IT PARTLY REOPENS MECHANICAL COOLING — measured 2026-08-18

**Same Open-Meteo archive, same grid cell, same 2160 summer hours as the blender table above — with dewpoint pulled this time.** The blender analysis measured only *dry-bulb*, which answers "can I blend to 15–18 °C" but not "what does cooling cost me in water" — and the second question is the one that has blocked every mechanical candidate on this page.

| outdoor dewpoint, Dec 2025 – Feb 2026 *(n = 2160 h)* | |
|---|---:|
| mean | **14.4 °C** |
| hours above 15 °C | 47.3% |
| **hours above 17 °C** | **8.1%** |
| hours above 18 °C | 1.4% |

- **🎯 SO COOLING SOURCE AIR TO 17 °C STAYS ABOVE ITS DEWPOINT FOR ~92% OF SUMMER HOURS.** A coil there **condenses little or nothing.** ➡️ **The standing objection — *"the aircon is a dehumidifier sitting inside a space to be held at 90–95% RH"* — is a PLACEMENT problem, not a physics one.** Pretoria summer is warm but **dry in absolute terms**; at 1400 m that is what rescues the design. ✅ **This is the evidence Candidate 2 (condition the make-up air) was always missing, and it strengthens it: put the coil UPSTREAM of the humidifier, where the air is still dry.** ⛔ **A coil in recirculated fruiting-room air faces that room's own ~15.8 °C dewpoint and would condense continuously — that distinction is the whole design.**
- **⚠️ BUT EQUIPMENT STILL DECIDES IT, AND THIS DOES NOT MAKE A SPLIT ACCEPTABLE.** A conventional DX unit holds its **coil surface at 5–10 °C regardless of the air temperature**, which is below dewpoint whatever the bulk air is doing. **Candidate 3 — chilled water held above dewpoint — remains the technically correct version.** ✅ **What changed is the margin: the control window is wider than the 1.2 K this file assumed**, because it is set by the *source* dewpoint (14.4 °C mean) rather than the fruiting room's own.
- **⛔ AND IT CORRECTS "COLONISATION COMES FREE IN SUMMER" — that claim is weaker than it reads.** Against the 24–27 °C band, outdoor summer air sits **below 24 °C for 74.2% of hours** and **above 27 °C for only 10.5%** *(mean 21.2, max 32.6)*. ➡️ **So the grow room's summer duty may well be trim HEATING at night rather than cooling.** ⚠️ **The room runs warmer than ambient — solar gain, metabolic heat from the bags — but by an unmeasured margin, so the DIRECTION of its summer duty is unknown, not merely the magnitude.**
- **✅ AND THAT ONE IS FREE TO SETTLE — the grow-room DHT22 is already installed and logging.** It needs one summer of watching, not a purchase. **Folded into item 9b (Phase 0), not queued separately.**
- **🔑 THE ARCHITECTURE CLARIFICATION THIS FORCES, AND IT IMPROVES THE WINTER BUILD'S CASE: IN SUMMER THE TWO SOURCES SWAP ROLES.** Outside becomes the **hot** source and the grow room the **cold** one *(grow ~24–27 against an outdoor max of 32.6)*. ➡️ **So the mixing box is NOT idle in summer — it runs to the opposite end of its travel: minimum outside air, maximum grow-room air, with the coil trimming the last 7–10 K.** **The same part serves both seasons**, which is a materially better return on a fabrication job that was being justified on winter alone.
- ⚠️ **Hinges on:** *the grow room's dewpoint tracking outdoor rather than being lifted by the crop's own respiration in a closed room.* **Unmeasured — and measurable now**, since the grow-room DHT22 reports RH as well as temperature. **Size of the move if wrong: chilled water versus a split, i.e. the difference between "probably out of budget" and "cheapest capital".**
- **📋 REPRODUCIBLE.** `https://archive-api.open-meteo.com/v1/archive` · `latitude=-25.77&longitude=28.21` · `start_date=2025-12-01&end_date=2026-02-28` · `hourly=temperature_2m,dew_point_2m,relative_humidity_2m` · `timezone=Africa/Johannesburg`. *(`tools/outdoor_history.py` cannot do this — it uses the forecast endpoint, which reaches back only ~90 days and does not request dewpoint.)*

#### 📅 AND THE MONTHLY BREAKDOWN CHANGES THE ANSWER — added 2026-08-18, same archive, Sep 2025 – Mar 2026

**The Dec–Feb average hid both the shape of the season and the shape of the day. Neither is a detail.**

| | mean | night 00–06 | day 12–16 | <24 °C *(heat)* | 24–27 *(band)* | >27 *(cool)* | dewpt mean | dewpt >17 °C |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| **Sep 25** | 20.3 | 15.7 | 26.0 | 71.8% | 17.4% | 10.8% | **5.0** | **0.0%** |
| **Oct 25** | 19.6 | 15.1 | 24.9 | 75.9% | 14.1% | 9.9% | **9.1** | **0.0%** |
| **Nov 25** | 18.3 | 15.3 | **21.6** | **93.6%** | 5.3% | 1.1% | 13.8 | 0.7% |
| **Dec 25** | 20.1 | 16.7 | 23.9 | 81.5% | 14.9% | 3.6% | 14.8 | 5.4% |
| **Jan 26** | 21.5 | 17.7 | 25.9 | 72.6% | 16.7% | 10.8% | **15.0** | **13.4%** |
| **Feb 26** | **22.0** | **18.1** | **26.5** | 68.0% | 14.1% | **17.9%** | 13.4 | 5.2% |
| **Mar 26** | 19.8 | 16.8 | 23.5 | 86.0% | 10.9% | 3.1% | 14.6 | 12.5% |

- **✅ "DIRECTION OF DUTY UNKNOWN" IS NOW ANSWERED, AND IT WAS THE WRONG QUESTION — THE DIRECTION FLIPS EVERY DAY, NOT EVERY MONTH.** Peak-summer hourly means run **16.6 °C at 05:00 to 25.7 °C at 13:00**. ➡️ **Every night of the year sits 5–7 °C BELOW the 24 °C colonisation floor — midsummer included.** **So the grow room wants trim HEATING every night, all year**, and cooling is only ever an *afternoon* question — 11:00–17:00, and only in Sep, Jan and Feb. ⚠️ **What is still unmeasured is the room's OFFSET above ambient** *(solar gain + metabolic heat)*, which sets the magnitude. **The shape is now known; the size is not.**
- **⛔ FEBRUARY IS THE HOT MONTH, NOT JANUARY — this file has said "the crunch lands late January".** Feb leads on mean **22.0**, on afternoons **26.5**, and on hours above 27 °C at **17.9%** *(against January's 10.8%)*. **Both claims are true and they measure different things:** late January owns the **95-hour unbroken run with no cold air** *(a duration)*; February owns the **intensity**. **Do not let one stand in for the other when sizing anything.**
- **🎯 NOVEMBER IS THE SEASON'S ANOMALY AND IT IS FREE CAPACITY.** Afternoon mean **21.6 °C** — the coolest of the entire warm season, cooler than October — with **93.6%** of hours below 24 °C. The cloudy onset of the wet season. ➡️ **If a summer fruiting push is ever scheduled, November is the month that costs least.**
- **🔴🔴 AND IT EXPOSES A TRAP IN PHASE 0 AS WRITTEN — "MEASURE SEPT–NOV" CANNOT ANSWER THE HUMIDITY QUESTION, BECAUSE THE PROBLEM DOES NOT EXIST YET IN THAT WINDOW.** Hours above a 17 °C dewpoint: **Sep 0.0% · Oct 0.0% · Nov 0.7%**, against **Jan 13.4%** and **Mar 12.5%**. **September air is desert-dry here — a 5.0 °C mean dewpoint.** ➡️ **Measuring the coil's condensation behaviour Sept–Nov would sample a season in which it cannot condense, and conclude that it never does.**
  - **✅ THE HEAT HALF OF PHASE 0 IS STILL SOUND, AND THAT IS THE EXPENSIVE HALF.** **September afternoons average 26.0 °C against February's 26.5** — within 0.5 °C. **So the envelope's thermal response, the aircon's clamp-metered draw, and the room-versus-ambient offset are all properly samplable from September.** ⛔ **It is only the DEWPOINT/condensation question that must wait for Dec–Mar.** **Split the Phase 0 read in two and do not let the dry-month result close the wet-month question.**
- **✏️ AND IT PUTS A HONEST NUMBER ON THE COIL CLAIM ABOVE.** *"Above 17 °C only 8.1% of hours"* was the **Dec–Feb pooled** figure. **Per month it is Dec 5.4% · Jan 13.4% · Feb 5.2% · Mar 12.5%.** ➡️ **In the wettest month roughly one hour in seven would condense on a coil held at 17 °C.** **Still a minority, and the conclusion holds — but January and March are the test, not the average.**

**🔑 AND THE WINTER FINDING, WHICH FALLS OUT OF THE 08-13 FAN TEST: THE COLD SIDE HAS NO ACTUATOR, AND IT HAS ROUGHLY 3× THE AUTHORITY OF THE ONE WE HAVE BEEN ADJUSTING.**

**The warm side is controlled** — the fresh-air fan, and it is a ~7–13% flow switch worth **<0.3 °C**. **The cold side is not controlled at all**: the front-wall floor grate and the 50 mm strip are permanently open holes. **On 08-14 the wind fell 3× and the room moved ~0.9 °C** *(full read: the CLOSED fan-test block)*. ➡️ **We have spent two nights trimming a 0.3 °C actuator while a 0.9 °C input swings on the weather with no damper on it.** That is why the fan tests keep returning null, and **the missing part is a damper on the cold side, not a better fan.**

- **✅ THE DESIGN FOR THIS IS ALREADY DECIDED AND ON THE RECORD — this only raises its priority.** `MICROCLIMATE.md` (decision 2026-07-23): *a controlled tempered intake from the back, the front 50 mm strip kept as the defined exhaust, and the drain grate sealed.* **That is exactly "give the cold side a valve", and it is now the highest-authority thermal lever the room can have short of refrigeration.**
- **⛔ AND IT CORRECTS THE SHAPE OF TODO ITEM 10, WHICH WAS HEADING FOR AN IRREVERSIBLE CHANGE.** That item closes front-wall vents **permanently**. **The seasonal table says the correct opening is not a smaller fixed one — it is a MODULATING one**: summer wants those openings **wide open at 05:00** to catch the only cold air of the day, and winter wants them **shut at 03:00** against the draft. **A permanent seal optimises one season and breaks the other**, and it cannot be undone in the season it hurts. ➡️ **Do not cut. The blockers on that item already stand; this adds a third and it is structural rather than conditional.**
- **⚠️ PRIORITY, HONESTLY: this is enabler tier and it does not jump the queue.** Demand is still the binding constraint *(item 0 — Spar is blocked, and a second route is unfound)*. **A perfectly banded room with no second customer earns nothing.** ➡️ **What summer buys is not urgency, it is LEAD TIME:** the question is open, the candidates are unassessed, and December is the deadline. **Start assessing in spring, not in January.**

### 🧱 THE CEILING — construction recorded for the first time, 2026-08-05

**Operator: the roof has *insulation wool* and a *painted shade-cloth ceiling*.** Recording it because **no document described the ceiling at all** — `MICROCLIMATE.md` §1 lists insulation on the front wall, rear wall and divider, and mentions the roof only as *"flat corrugated iron"*. That silence is now filled.

**⛔ AND IT KILLS A RECOMMENDATION MADE EARLIER THE SAME DAY.** An "insulate the roof" case was built here — ~8 kW of summer solar gain, ~1.75 kW of winter loss, R6,500–11,000 of Isoboard, two-year payback. **It was explicitly conditioned on the roof being uninsulated, and it is not. The whole calculation is void. Do not resurrect those numbers.** *Recorded rather than deleted because the reasoning pattern was sound and the failure was one of premise: absence of documentation was treated as evidence of absence.* **This file did not describe the ceiling; that is not the same as there being no ceiling.**

**✅ RESOLVED 2026-08-11 — THE SHADE CLOTH IS NOT PERMEABLE (operator).** The 08-05 entry flagged this as its own load-bearing assumption — *"Hinges on: whether the shade cloth is genuinely permeable once painted. Paint may have sealed it into something much closer to an air barrier, which would answer question 2 on its own."* **It did.** Both questions below are answered or downgraded by it.

1. **⤵️ DOWNGRADED — is the wool still dry?** The original concern was a **continuous moisture drive upward from a 90–95% RH room through a permeable ceiling.** **That mechanism is closed.** ⚠️ **But an air barrier is not a vapour barrier** — vapour can still *diffuse* slowly through painted cloth and condense in the wool against cold iron, and the underside of a flat iron roof radiates to the night sky and can fall below ambient. **So this drops from a live concern to a slow one.** *Still worth a look — and **9.4 mm fell overnight 08-10→11, the first real rain in this record**, which is exactly when a leak or damp patch shows. Feel it; look for sagging, compression, staining or condensation marks on the underside of the iron.*
2. **✅ ANSWERED — humidified air is NOT continuously escaping into the roof void.** The standing, unmeasured ceiling moisture-loss path **does not exist.** No smoke-pencil test needed.

**➡️ TWO CONSEQUENCES, AND THE SECOND IS OPERATIONAL.**
- **✅ It makes the vent-experiment results cleaner.** With the ceiling ruled out, **the front-wall floor openings and the exhaust strip are the dominant controllable loss paths** — which removes a competing unmeasured explanation for the 08-10→11 humidifier-duty fall and **strengthens attributing it to the hole closure.**
- **🔴 It makes closing MORE holes riskier, for a reason independent of CO2.** A sealed ceiling means positive pressure now relieves **only** through the floor openings and the exhaust strip — **there is no diffuse ceiling bleed to take up slack.** `stock-control/docs/MICROCLIMATE.md`'s *"do not seal them all — the fan needs a relief path"* **binds harder than it did when the ceiling was assumed leaky.**

## Business snapshot

- **3 customers, ~31 punnets/week @ R40 → ~R5,370/mo.** Lynnpark 20 (cash on delivery), Vula 4 (monthly), Orchard 6–8 (prompt). About a quarter of the R20,000/mo objective.
- **Known costs ~R3,100/mo** (Jesca R1,430, **Sage R400** ✏️ *(corrected 2026-08-18 — recorded as a "Capitec fee" because that is how it appears on the statement; it is the Sage subscription)*, substrate R680, punnets R270, gas R320) **plus electricity ≈R1,470–1,680/mo** — fruiting room ~10.0 kWh/day plus chest freezer 0.784 kWh/day (measured 07-28) = **~10.8 kWh/day, ~328 kWh/mo, ~38% of the property**. Electricity is the single largest cost, bigger than Jesca. **The business electricity total is now fully measured — no unmeasured business load remains.**

### 💰 WHERE THE SAVINGS ACTUALLY ARE — ranked 2026-08-18. **And the first correction is to this file's own R5.12/kWh.**

**Electricity is the business's largest cost — ~328 kWh/mo, R1,470–1,680, bigger than Jesca's R1,430.** Breakdown of the fruiting room's measured 10.0 kWh/day:

| | kWh/day | ~R/mo @ R5.12 | basis |
|---|---:|---:|---|
| Humidifier | 2.76 | 424 | ✅ measured 2026-08-18 |
| Circulation fan (WF-150 on HIGH) | 1.32 | 203 | nameplate 55 W |
| **Aircon + fresh-air fan + lights + controller** | **~5.9** | **~900** | ⛔ **by subtraction — never itemised** |

- **🔴🔴 BUT R5.12/kWh IS THE WRONG MARGINAL RATE FOR THIS PROPERTY, AND IT INVALIDATES EVERY RAND FIGURE IN THE TABLE ABOVE.** `stock-control/docs/SOLAR.md`: **the whole property runs off the Sunsynk 5 kW inverter** *(stove plates excepted)*, and **"the meter sees only the shortfall left after solar and battery, so the same load costs nothing at midday and full price at 02:00."** ➡️ **A kWh has no single price here. Load REDUCTION and load TIMING are different levers and this file has only ever costed the first.**
- **🎯 WHICH PROMOTES A LEVER THAT IS NOT IN THE ROOM AT ALL, AND MAY BE THE LARGEST ON THE BOARD.** `SOLAR.md` records the inverter sitting in **"emergency-backup posture"** rather than **cost-saving self-consumption**. **If the 5.12 kWh battery is not being cycled daily, that is up to ~5 kWh/day of grid import not being displaced — of order R500–770/mo**, against every room-side lever here worth R37–250. ⚠️ **Hinges on:** *there being surplus PV to charge it beyond the house's daytime load, and on the "emergency-backup" description still being current.* **Both unmeasured — nothing solar is in HA; `SOLAR.md` confirms the Power Flow Card has no data integration behind it.** **Size of the move if wrong: the whole figure, which is exactly why it must be measured before it is believed.**
- **➡️ SO THE HONEST RANKING IS MEASUREMENT-FIRST, AND THE TWO INSTRUMENTS COST ABOUT THE SAME.**
  1. **⬜ Aircon circuit — Shelly EM Gen3 + 50 A CT, R720** *(SmartPad SA, priced 2026-08-18)*. Closes item 5(a), which gates **every** mechanical candidate for summer. **Cheaper than a decent handheld true-RMS clamp** *(UNI-T UT202A+ R950 at Communica; Fluke 305 R5,319)* **and it measures the RIGHT thing** — this file's own rule is *"read kWh over 24h, NOT instantaneous watts, everything here cycles"*, and a handheld cannot integrate. Logs to HA, permanent, and doubles as the Phase 0 summer-load instrument. **Takes 2 CTs, so one unit can meter the aircon AND the room's multiplug feed** — that splits the ~R900 unattributed block.
  2. **⬜ Sunsynk telemetry bridge, R750–1,100** — fully scoped in `SOLAR.md`, deferred on cost. **This is the one that prices everything else**, because without it no saving can be converted to rands at all.
- **🥇 THE ROOM-SIDE LEVER, ONCE THE ABOVE IS PRICED: THE FRONT-WALL DAMPER.** It is the only build that attacks both large lines at once, and **it is already required by the future view for summer** — so the saving is a by-product of a build that is happening anyway. **Air exchange is the humidifier's dominant load and the front-wall holes are 2.3× more expensive per m³ than the fan**; the cold side has **no actuator at all**, and an uncontrolled 0.9 °C weather swing is what the aircon is paying to fight. ✅ **Measured precedent: closing 20 of ~80 holes (−25% area, free) moved humidifier duty 100% → 83% → 72%.** ⛔ **That is an argument for a MODULATING damper, not more permanent closure — item 10's blockers stand.**
- **🥉 FREE AND AVAILABLE TODAY: circulation fan HIGH → LOW, ~R37/mo** *(55 → 45 W)*, and **its justification was superseded on 2026-07-25** when the tub, not airflow, proved to be the humidity cause. Also cuts cap-drying risk. **This is step 3 of the revert test.**
- **⚖️ AND THE COMPARISON THAT KEEPS THIS HONEST — ✏️ CORRECTED 2026-08-18, AND THE CORRECTION MAKES IT SHARPER, NOT WEAKER. The R400 is SAGE, not a Capitec bank fee** *(the operator; it was recorded as a bank charge because that is how it reads on the statement)*. ⛔ **The "switch to a cheaper business account" suggestion is therefore VOID — withdraw it.**
- **🔴 AND IT EXPOSES A DISTINCTION THIS FILE HAS BEEN BLURRING: ELECTRICITY IS NOT A CASH COST OF THIS BUSINESS.** `CASHFLOW.md`: the fruiting room's power **sits in the HOME bill, paid personally — it never touches Capitec.** ➡️ **So the entire electricity ranking above is a PROFITABILITY argument, not a CASH one.** **In cash terms the business pays Jesca R1,430 + Sage R400 = R1,830/mo out of Capitec against ~R1,650/mo in, and the balance drifts down.** **Sage is 22% of the cash outflow and the largest controllable line after wages.**
- ⬜ **UNRESOLVED, AND NOT TO BE THEORISED: whether the Sage R400 is reducible.** `HANDBOOK.md` records Sage as *"not well utilised yet"* and not connected to the stock ledger — R4,800/yr for a tool running below its capability, at a scale of one operator and three customers. **But VAT registration, SARS filing and whoever else touches the books all constrain it, and none of that is recorded here.** ➡️ **Ask before proposing anything.** ⚠️ **And Capitec's actual account fee is now an UNKNOWN separate line** — it was never a distinct entry, so it may be a further small cost hiding inside the same R400 assumption.
- ➡️ **And all of it together is worth less than one new customer.** Savings are the right work *while demand is blocked*, not instead of it.
- **The operation is near true break-even, not comfortably positive.** Most of any transfer to Wessel reimburses power he already pays personally.
- **Filling the room is what turns power from a burden into leverage** — the room costs much the same half-full as full. This strengthens the demand case.
- The Lynnpark cash (~R800/wk) is the real margin and is **untracked**. Banking it is the cash equivalent of ledger discipline.
- The ~R34k of personal money that built the operation was one-off *capital*, not running cost.
- Full numbers: `stock-control/finance/CASHFLOW.md`. Money of record stays in Sage/Capitec.

## Sales & growth gate

**The gate has moved from yield to demand.** With grey oyster as the only product, the 3 existing customers won't take more however much is grown. Growth needs new customers. *(Product diversification is the other untested demand lever — not explored.)*

### ⛔ SPAR IS BLOCKED — NOT REFUSED, AND NOT ON ANYTHING WE DID (operator, 2026-08-08)

**Menlo Park Spar is under HEAD OFFICE MANAGEMENT for a while and will not take on local suppliers until everything has settled.** So the shelf trial is **deferred by the store's own circumstances**, not lost on price, product, compliance or the barcode.

- **⛔ THE DEMAND EXPERIMENT IS OFF THE TABLE, AND THAT IS THE REAL COST — not the R202.40.** Every document in this repo rests on *"demand is the binding constraint"*, which is an **assumption that has never been tested**. The Spar trial was going to measure it directly, at the store's risk, for ~R280. **There is now no cheap instrument for the single load-bearing belief of the whole strategy.** That matters more than the lost shelf.
- **✅ NOTHING SPENT IS WASTED — the GTIN work is channel-agnostic and permanent.** GTIN `6001651378474` is a **once-off** licence, Active, published in Activate, and the printed label scans. It applies to **any** retail route — another Spar, a different chain, a farm stall, a deli, an online listing. **Do not re-buy or re-do any of it.** The one step that was outstanding (getting Spar to load the GTIN into their POS) simply moves to whichever retailer comes next.
- **⚠️ BUT ONE PREMISE OF THE COMPLIANCE READ HAS FLIPPED, AND IT IS NOT COSMETIC.** The light-touch position — *"Spar stores are individually owned, so the owner can shelf local produce on his own authority; formal central supplier onboarding may not bind here at all"* — **was true of an independently owned store.** Under head office management it is **exactly the opposite**: a central supplier process is likely to bind, which usually means a supplier code, a **Certificate of Acceptability**, food-safety paperwork and possibly an audit. **So if this store reopens as the route, it reopens as a HARDER one than the trial that was on offer.** Re-read `Regulatory & compliance` before assuming the old terms survive.
- **⬜ Re-approach trigger, so this does not simply fade:** the block is temporary by its own description. **Ask the owner what "settled" means and roughly when, and whether he wants to be approached again or will make contact.** A dated diary entry is the difference between a deferral and a dead lead. Until that date exists, this item cannot be planned around.
- **➡️ THE ACTIONABLE CONSEQUENCE: priority #1 is now to find a SECOND demand route, and none has ever been identified.** Spar was not the first of several candidates — it was the only one. **That gap is the most important open item in this file.** ⚠️ **Hinges on:** *that demand really is the binding constraint.* **If it is wrong, everything above is mis-prioritised** — but the experiment that would have settled it is precisely what was just lost, so the assumption now has to be carried unverified or tested some other way. **Size of the move if wrong: it inverts the entire priority order, putting yield and capacity first.**

**⬇️ EVERYTHING BELOW IS PARKED, NOT DELETED.** It is the fully-worked trial design — terms, pricing, margin arithmetic, capture mechanism — and it is **reusable as-is for whichever retailer comes next.** Read it as a template, not as live work.

- **Menlo Park Spar** will test grey oyster on shelf **if there's a barcode on the label**. First new-client approach. **⛔ SUPERSEDED 2026-08-08 — see the block above.**
- **Barcode: ✅ DONE 2026-07-27. GTIN `6001651378474`** — check digit verified valid. Paid R202.40 (R176 + R26.40 VAT); account `fungi4ushop@gmail.com` at `gs1zace.gs1za.org`, product record created in **GS1 Activate** (`activate.gs1.org`).
  - **Product record as finalised:** brand `Fungi4u`, functional name `Grey Oyster Mushrooms`, net content `250 Gram`, GPC `Oyster Mushrooms 10006031`, country of sale `South Africa`, product type **`Sold to consumers, fixed, single product`**.
  - **⚠️ The product-type field defaulted to "NOT sold to consumers" and had to be corrected before finalising.** That setting means a business-to-business trade item (case/carton/pallet), which takes a case-level GTIN-14/ITF-14 rather than a retail EAN-13 — it would have produced the wrong symbology and filed the punnet as a case in retailer data feeds. **Check this field on any future product.**
  - **⚠️ You own ONE number, not a range.** GS1 SA allocates single GTINs from a shared prefix (`6001651` also appears in GS1's own worked example), so there is no company prefix under your control. **Do not invent adjacent numbers for a 500 g pack** — they belong to other companies' products. Every new product or pack size is another R176 purchase.
  - **GPC note:** `10006031 Oyster Mushrooms` is the fresh-produce brick (it appears in the Produce Traceability Initiative commodity list). **Not** `10007718 Oyster Mushroom Funghi (Pleurotus Ostreatus)`, whose Latin-binomial naming follows GPC's horticultural convention and would suit spawn or grow kits. (GS1 SA is the only legitimate SA source — reseller-sold barcodes get rejected by the big retail chains). **One GTIN = one product *and* pack size**, so 250 g grey oyster is one number; a 500 g pack later is another R176.
  - **✅ ONCE-OFF CONFIRMED 2026-07-28 — no longer "on the balance of evidence".** The portal's own **Licences** page states it twice, in both *Product* and *Invoice Product*: **"1 Number Licence (Once-Off Fee)"**. Licence **Active**, **Integration Status: Successful**, account `Fungi4u`, GLN `6001651378474`, invoice `ORD-18016-S2S5Y6`. **R202.40 paid** — R176 + R26.40 VAT. The "Annual Renewal Fee" template field that caused the doubt was boilerplate, and the home page's *"annual subscription options"* refers to GS1 SA membership tiers, not to this licence.
    - **⚠️ One residual question, cheap to close:** confirm via *Catalogue → Invoices* that **no separate recurring GS1 SA membership line** exists. Nothing on the 07-27 order suggests one (entrance fee R0, single licence line), but a lapsed annual fee would fail **silently** — the GTIN would simply stop resolving months later, most likely when a chain listing depends on it. Same shape as the SIM-inactivity trap in `DECISIONS.md`.
  - **A GS1 account requires a completed company application, not just a user profile.** Registering an email gets you a login; the cart rejects it with "user not associated with an account" until the organisation application is done. Account opened 2026-07-27 under `fungi4ushop@gmail.com`.
  - **⚠️ HOW TO ACTUALLY GET INTO ACTIVATE — you do NOT log in at `activate.gs1.org`.** Established 2026-07-28 from GS1 SA's own *Activate User Guide* after a password reset returned *"no account with this email address is registered"*. Activate is reached by **SSO from the GS1 South Africa member portal**: `https://www.gs1za.org/` → **Member Login** → then either *Catalogue → Activate*, or scroll down to **"Access GS1 Activate & Verified by GS1"** → GS1 Dashboard → **"Activate Login"**. **A reset attempted at `activate.gs1.org` will report no account even when the account is perfectly healthy.**
    - **The SA portal signs in with a USERNAME, not an email** ("Sign in with a local account"). So an email-keyed reset can fail while the account exists. **Get the username from Bitwarden**; if the password is lost use *"Forgot your password?"* on the **gs1za.org** page, not the global Activate one.
    - **The account demonstrably exists:** the R202.40 purchase completed on 07-27, and per the note above the cart cannot check out without one. If login still fails it is a username mismatch, not a missing account — **contact GS1 SA support quoting the 07-27 order for R202.40**, which proves it.
    - **⚠️ The "Use this licence" toggle lives INSIDE Activate, not on the portal's Licences page.** Corrected 2026-07-28 — the portal page shows licence *status* (Active / Integration Successful) but has no toggle. Guide Step 8 comes **after** entering Activate and accepting its terms: *Licences* → **"Use this licence"** black → green → **Save**, for each single-number GTIN-13. Until that is done the licence is not applied for GTIN issuance, which would explain a number that looks bought and active yet does not resolve.
    - The GS1 Dashboard also carries a **"Verified by GS1"** link, so the publication check can be done without leaving the portal.
- **✅ Label designed and printed 2026-07-28.** Artwork is in the `stock-control` repo.
- **✅ GTIN WORK COMPLETE 2026-07-28 — verified in Activate, not inferred. ONE step remains, and it is not ours.**
  1. **✅ SCAN-TESTED 2026-07-28 — the printed label scans correctly.** Print quality, quiet zone and scaling are all fine, so the print run stands and the reprint risk is closed. *(Worth having confirmed the scanner showed `6001651378474` specifically, not merely that it read: artwork generated from a mistyped number scans perfectly, because the generator computes a valid check digit for whatever body it is given — a typo yields a legitimate-looking EAN-13 belonging to another company.)*
  2. **⏸️ PARKED 2026-08-08 — carry this step to whichever retailer comes next.** The "scans as unknown" risk is **the retailer's system, not GS1's database**. Whoever shelves it must create the item against `6001651378474` with a description, 250 g and the shelf price. Until they do, the barcode fails at the till however good the label is. **An independently owned store does this itself; a head-office-managed one will not** — which is part of why the Spar route got harder, not just later.
  3. **✅ PUBLISHED — CONFIRMED IN ACTIVATE 2026-07-28.** The product summary (`activate.gs1.org/#/product/summary/1993610`) reads **`● Active`** with **no Finalise button outstanding**, carrying the GS1 registration badge. Every attribute matches what was recorded: GTIN `6001651378474`, GPC `Oyster Mushrooms (10006031)`, Countries of sale `South Africa`, and **Product Type `Sold to consumers, fixed, single product`** — the field that had defaulted wrong and is confirmed correct. **The `STATUS` vs `todo` conflict is resolved in `STATUS`'s favour: the record was real all along and the todo was stale.**
     - **The whole "no account" scare was a wrong-door problem, nothing more.** Login works, the licence is Active with Integration Successful, and the product is Active. Route recorded above; nothing was broken at any point.
     - **Optional, free, and worth doing once:** the summary shows **`-no image-`**. A product photo enriches the Verified by GS1 record that retailers and marketplaces read. Not blocking, not urgent.
     - **Residual belt-and-braces check, no longer blocking:** search the GTIN at **Verified by GS1** (`gs1.org/services/verified-by-gs1`, free, 30/day) to see what the outside world sees. Expect it to resolve. **Traps if you do:** GEPIR no longer exists (`gepir.gs1.org` 301-redirects there, though GS1 SA still links to it); allow for propagation, so a "not found" immediately after publishing proves nothing; and ignore third-party barcode apps (Open Food Facts, barcodelookup) — they are not the GS1 registry.
- **⏸️ Was the next action, now unavailable: get Spar's full supplier requirement list.** The barcode is unlikely to be the only blocker, and an onboarding checklist tells you exactly which regulations bind — so you comply with what's required rather than everything imaginable. **The principle survives the store: ask ANY prospective retailer for their supplier requirements before doing compliance work speculatively.** It is the cheapest way to avoid gold-plating.
- **⚠️ THE RISK HAS FLIPPED — supply → sell-through (2026-07-27).** The owner said directly: **give him the barcode and he will put it on the shelf to monitor demand.** That is a *trial*, not a supply agreement — small volumes, no committed quantity — so the old worry ("Spar onboarded on an expectation, committable volume unproven, failing to supply a Spar is worse than never approaching one") is largely defused. **The new failure mode is that it doesn't sell.** Presentation on shelf and shelf life now matter more than production volume: mushrooms that sit and degrade unsold report weak demand for reasons that are not demand.
- **This is the demand experiment, and it is nearly free.** That demand is the binding constraint is an *assumption* everywhere in these docs. A shelf trial measures it directly, at the store's risk. Treat the result as the most valuable data the business can currently obtain.
- **Terms as at 2026-07-27: mushrooms supplied FREE for the trial; Spar considering R59 shelf price.**
- **Free is cheap here, and the reason matters: demand is the constraint, not production.** Trial punnets do not displace sales to Lynnpark/Vula/Orchard — those three won't take more. So the real cost is **marginal, ~R7/punnet**, not the R40 otherwise booked. ~10/week for 4 weeks ≈ **R280 total** for the most valuable information the business can buy.
- **Three conditions on the free supply — the second is the one that gets skipped:** (1) **a defined end date** (4 weeks is a normal produce trial); (2) **agree the post-trial price NOW, in writing** — even WhatsApp: *"free for 4 weeks from [date], thereafter R40/punnet"*, because free arrangements without an agreed conversion date tend to continue, and the conversation only gets harder; (3) **weekly sell-through numbers, in units** — without this agreed up front you have funded an experiment and received an anecdote.
- **The downside of free: no skin in the game.** A retailer who paid for stock chases the sale. Free stock can sit in a poor spot and quietly underperform, so ask about placement and restock cadence explicitly.
- **R59 supports the existing price — the economics already work.** R59 shelf against R40 wholesale is R19, **32% of retail**, squarely in the normal fresh-produce band (30–40%). If he pushes for a full 40% margin he'd want ~R35, which still contributes ~R28 marginal — but **R40 is defensible at R59 and should be held.**
- **⚠️ Reading the result: the trial tests the product AND R59 together.** Weak sales at R59 is not the same finding as weak demand — it may be a price signal. If it underperforms, have the promotional-price conversation before concluding grey oyster doesn't sell in Menlo Park.
- **✅ Free-stock capture built and deployed 2026-07-27.** Free punnets still leave stock, so they post to the ledger under a new **`PROMO_SAMPLE`** reason code (direction OUT) via the panel's **Give Free Stock** card — *not* Record Sale, which would invent revenue and corrupt the very number the trial exists to produce. `v_operational_snapshot` gained `packed_units_promo_this_week`, shown as *Free this week (trial)*: that is the figure to reconcile against Spar's reported sell-through. Migration `20260727180000` applied to production; panel live on the Pi (previous version kept as `mushroom-control.html.bak-20260727`). Full rationale in `stock-control/docs/LEDGER.md`.
- **Cold storage is at its limit** — a capacity constraint on growth. The current unit is the **chest freezer** (business load).
  - **✅ MEASURED 2026-07-28: 0.784 kWh/day** over the 24h window 07-27 07:30 → 07-28 07:30. That is **32.7 W average** and **≈R107–122/mo** (R4.48–5.12/kWh). It is the last unmeasured business load; the business electricity total is now closed at ~10.8 kWh/day.
  - **⛔ THE ~R707/mo "FRIDGE SAVING" IS DEAD — it is arithmetically impossible, not merely prospective.** The *entire* cold-storage bill is **R122/mo**. R707 is **5.8× everything currently spent on cold storage**, so no change to cold storage can save it. The figure was never a saving on this business at all — it was the internal gap between running a *different, larger, glass-doored* unit gutted vs ungutted. **Remove it from any tempo or payback reasoning.**
  - **⛔ The glass-door buy would ADD power, substantially. Do not treat it as an efficiency move.** The gutting table's own best case is **5.4 kWh/day — 6.9× the chest freezer's 0.784**. So an R8,000 second-hand glass-door unit costs **~+R700/mo gutted, ~+R1,400/mo ungutted**, against a business clearing ~R2,000/mo cash. Gutting it would recover part of a cost that buying it created.
  - **✅ The chest-freezer form factor is now validated by measurement, not preference.** 0.784 kWh/day is exceptional — the lid geometry (cold air doesn't spill out when opened) plus, presumably, running at fridge rather than freezer temperature. **If capacity must grow, another chest freezer on an external thermostat is the measured-best option.** A solid-door commercial unit is the fallback. Glass-door is now only defensible if it buys capacity available no other way, and the energy penalty must be booked against it explicitly.
  - **Timing: not urgent, and buying ahead of the Spar answer is backwards.** The trial is small volumes supplied free — it will not strain cold storage. Spending R8,000 at near break-even, before the trial says whether demand justifies more capacity, is the wrong order. **The purchase is now a pure capacity decision with a known energy penalty — there is no cost argument in favour of it.**
  - **⚠️ Two caveats on the 0.784 figure.** (1) **It is a winter reading.** Pretoria late-July ambient means minimal compressor duty; summer will be materially higher, so treat R122/mo as a floor and re-measure in January before annualising. (2) **Usable capacity in litres is not recorded**, so the kWh/day-per-litre benchmark — the figure that actually lets a replacement quote be judged — is still incomplete. Measure the internal dimensions.

## Regulatory & compliance — to verify, not confirmed

A landscape to check with each authority, **not legal advice**. It mostly gates the formal-retail (Spar) path; the existing informal customers presumably don't trigger most of it, so this rises in priority in proportion to the bet on Spar. Don't gold-plate.

- **Legal metrology (NRCS)** — selling *by weight* needs a trade-approved/verified scale. **But** pre-packed punnets at a fixed price may not trigger it; what bites then is accurate net-weight declaration. **Confirm which model applies before buying a verified scale.** The bench scale already bought is fine for internal yield measurement either way.
- **Food-handling premises** — a Certificate of Acceptability from municipal environmental health. Supermarkets often require it of suppliers.
- **Food labelling** — name, net weight, producer, batch/date, origin, barcode. Overlaps the Spar label work.
- **Business/tax registration** — CIPC / SARS / VAT threshold. May already be sorted.

## Room state (verified 2026-08-13 off a 48h `room_check.py` run plus a 240h recorder pull)

### ✅✅ THE FAN FIX WORKED, COMPLETELY — the grow room is AT SETPOINT for the first time in this record. And it has moved the problem, not removed it (2026-08-13)

**`FAN = MANUAL HIGH` was set on 08-12 at ~09:30** *(the step is in the recorder between 09:00 and 10:00)*. **The grow room went from 5–6 °C below its 21 °C setpoint to holding 21.8 °C overnight, in one step, with nothing else changed.**

| overnight mean 00:00–08:00 | 08-12 *(before)* | 08-13 *(after)* | change |
|---|---:|---:|---:|
| **Grow room** | 14.48 | **21.84** | **+7.36** |
| **Fruiting room** | 14.92 | **18.17** | **+3.25** |
| Grow room min | 14.10 | **20.80** | +6.70 |
| Fruiting RH | 90.4 | **87.0** | −3.4 |
| Humidifier duty 00–08 | 76.6% | **~100% (pinned)** | — |

- **⛔ "THE GROW ROOM IS 3.2–5.9 °C BELOW SETPOINT" IS CLOSED.** It ran **21.7–22.0 °C all night** and 20.8 at its coldest. **The recirculation diagnosis is confirmed by intervention, not just by inference** — the unit was always able to deliver this, and the fan setting was the whole of it.
- **⛔ SO ARE THE COMPETING CANDIDATES, and they should not be re-opened.** The **back-wall drywall** (named 08-11 as the leading envelope candidate), the **grow-room door leaks**, and the residual **capacity** worry all predicted a persistent shortfall that a fan speed could not fix. **A fan speed fixed it.** Envelope work on the back wall has **no temperature case left** — if it is done, it must be justified on something else.
- **⚠️ AND IT REVERTS SILENTLY. Nothing alarms on it.** See `HANDBOOK.md` — this is now a **load-bearing setting**, and today's data is the first hard evidence of what it is worth: **7.4 °C.**

**🔑 THE COUPLING IS ~45%, NOT ~25% — MEASURED, AND IT SETTLES THE OPEN QUESTION IN THIS FILE.** The 08-08 entry left it hanging: *"Fruiting rising ~1 °C per 4 °C of grow rise means ~25% coupling and room to push further; tracking near 1:1 means the rooms cannot be held apart and a separate colonisation space is needed after all."* **+3.25 on +7.36 is 44%.** There is **no room to push further.**

- **➡️ COLONISATION TEMPERATURE IS UNREACHABLE IN THIS GEOMETRY. This is now measured, not hypothesised.** At 44% coupling, running the grow room at the **24–27 °C** grey oyster wants would drag the fruiting room to **19.2–20.5 °C** — **1.2 to 2.5 °C above its 18 °C ceiling**, on a cool-fruiting crop. The rooms cannot be held apart across a 50 mm partition.
- **➡️ SO THE SEPARATE GROW ROOM IS CONFIRMED NECESSARY, not preferred.** It was the *"undesigned half of the wall plan"* resting on an unmeasured hinge. **The hinge is now closed in the direction that requires the build.** The ~10 days/batch colonisation prize stands and is only reachable that way.
- **✅ One hinge from 08-05 is also closed in passing:** *"that colonisation here is temperature-limited"* is still **unmeasured** — but the grow room is now warm, so **W32/W33 colonising at 21.8 °C against the recorded 21–30 day range is a free, running experiment.** Do not disturb it; just read the dates.

**🔴 BUT THE FRUITING ROOM IS NOW OUT OF BAND AT THE TOP, AND THE HUMIDIFIER IS PINNED AND LOSING GROUND.** This is the cost side and it is live right now.

- **Temperature 18.1–18.8 °C continuously since 08-12 13:00, against a 15–18 °C band.** `room_check.py`'s 47.9% in-band is flattered by the cold pre-fix half of its window; **since the fix it is essentially 0%.** *(48h scorecard: mean 16.82, min 14.70, max 18.90.)*
- **🔴 The humidifier has not cycled since 08-12 15:08 — ~18 hours continuously ON.** `humidifier_duty_24h` reads **98%**. **This is the first time it has been genuinely out-run rather than merely working hard.**
- **🔑 AND IT IS A REAL MOISTURE DEFICIT, NOT THE RH/TEMPERATURE ARTEFACT THIS FILE KEEPS WARNING ABOUT.** Across 08-13 00:00–08:00 the **temperature was flat (18.22 → 18.30)** while **AH fell 13.74 → 13.26 g/m³** and RH fell **88.3 → 84.8** — a steady **−0.44 RH points/hour**. **Absolute moisture is leaving with the humidifier at 100%**, so this passes the doctrine's own test and cannot be dismissed as temperature confounding.
- **⚠️ VPD IS STILL IN BAND BUT CLOSING ON THE CEILING: 0.246 → 0.320 kPa overnight, ~+0.009/h against a 0.40 limit.** At 18.3 °C, **VPD leaves band at ~81% RH — 3.8 points below where it now sits.** **On a straight-line read that is this afternoon.** *(Projection, not a measurement — the rate may flatten. But the direction has been monotonic for 8 hours.)*
- **⛔ THE EXHAUST-HOLE DUTY TREND IS VOID FROM HERE.** The 100 → 83 → 72.4% series was the strongest evidence for closing more holes. **A 3.3 °C step change in room temperature has invalidated the baseline** — 72.4% and 98% are not comparable numbers. **Do not read the pinning as the hole closure failing, and do not close more holes to fix it.** *(The standing condition — a mild, still night — is unchanged and still unsampled.)*

**➡️ THE DECISION THIS FORCES, and it is the operator's:** the fruiting room's 15–18 °C band and the grow room's 21 °C setpoint are **now in direct conflict at 44% coupling**, and 21 °C is the *low* end of what colonisation wants. **Either the fruiting room gets moisture capacity to hold 90% RH at 18.3 °C, or the aircon setpoint comes back down and the colonisation gain is given back.** The **spare 12-disc humidifier and fresh discs are already on hand** — item #5 on the room programme, which said *"size it after #4 (the aircon)"*. **#4 is now answered, so #5 is live.** ⚠️ **Hinges on:** *that the deficit is a humidifier-capacity shortfall rather than the aircon condensing.* **In HEAT mode the indoor coil is the condenser and strips nothing** *(nameplate-confirmed reverse-cycle, 08-12)*, so capacity is the likelier read — **but a warmer room also drives more vapour out through the front-wall openings, and that is a loss no amount of disc capacity fixes cheaply.** **Size of the move if wrong: adding discs treats a symptom and the room stays out of band.** ⬜ **Cheapest discriminator: run the spare unit for one night and see whether AH stops falling.** If it holds, it was capacity.

**⬜ Two smaller reads, neither urgent.**
- **The 08-11 11:33 recorder gap (57.5 min) hit all four entities *including the Inkbird*** — different device, different transport. **Points at the Pi/HA or the network, not the controller.** Second occurrence noted; still no action.
- **`room_check.py` flags an offset step at 08-13 05:00 (−17 → −100 ppm, score 2.6).** **Low score, and it sits inside the largest thermal transient in this record** — a 3.3 °C warmer room plausibly changes the vertical gradient between a top-mounted primary and a bottom-shelf Inkbird. **Not actionable as drift.**

### ✅ CLOSED 2026-08-14 — FRESH-AIR FAN HIGH → LOW. **VOID AS A COUPLING TEST: the disturbance moved 3× while the actuator moves ~10%.**

**Run 2026-08-13 17:21, read over the pre-registered window 00:00–08:00 on 08-14. ⛔ NONE OF THE FOUR PRE-REGISTERED BRANCHES FIRES.** The fruiting room got **warmer** on LOW — **+0.87 °C** — which is the opposite of what the mechanism predicts, and the pre-registration did not anticipate a warming.

| overnight mean 00:00–08:00, time-weighted | 08-13 *(HIGH)* | 08-14 *(LOW)* | change |
|---|---:|---:|---:|
| **Fruiting temp** | 18.16 | **19.03** | **+0.87** ⛔ |
| Grow temp | 21.84 | 22.41 | +0.57 |
| **Room-to-room gap** | **3.67** | **3.37** | **−0.30 — narrowed** ⛔ |
| VPD | 0.26 | 0.35 *(max 0.42)* | +0.09 |
| RH | 87.28 | 84.00 | −3.28 |
| Absolute humidity | 13.54 | 13.72 | +0.18 |
| **Humidifier duty** | **100.0%** | **100.0%** | **0** ⛔ |
| `temp_shelf_delta` | −0.17 | −0.03 | +0.13 ✅ |
| CO2 primary, displayed | 593 | 651 | +58 |

**⛔ WHY IT IS VOID, AND IT IS NOT THE SAME OBJECTION AS LAST TIME.** The 08-13 correction voided the *temperature branch* because the two-speed switch is only a ~7–13% flow actuator *(`HARDWARE_REFERENCE.md` §"Fan failure mode"; Arm C measured 0.20 °C for the same swing)*. **That still stands — but this night adds a second, independent invalidator: the dominant disturbance changed by 3× underneath the test.** Open-Meteo for the two windows: **outdoors 5.90 → 5.28 °C (test night was COLDER, so ambient cannot explain a warming) but wind 14.3 → 4.6 km/h, and cloud 20% → 0%.**

- **🔑 THE WIND IS THE FRUITING ROOM'S DOMINANT THERMAL TERM, AND THIS FILE ALREADY SAID SO.** `MICROCLIMATE.md`: *"the aircon is at the back and the fruiting room is chilled from the front by cold outside air through the floor openings"* — the front-wall grate and the 50 mm strip. **A calm night removes that draft, and the room floats up toward the grow room.** That single mechanism explains **both** anomalies — the warming **and** the narrowing gap — and it predicts them in the right direction, which the fan hypothesis does not.
- **⛔ THE MECHANISM'S OWN PREDICTION IS CONTRADICTED, WHICH IS THE CLEANEST READING HERE.** `MICROCLIMATE.md` §"Fresh air": the fan **is not ducted to outside** — outside air enters a 15 mm hole in the grow room's rear wall, crosses the grow room, and is drawn into the plenum already tempered to grow-room temperature. **So its intake is ~22 °C air, warmer than the fruiting room: less fan must mean less heat imported, and a WIDER gap.** Both went the other way.
- **📐 THE MOST THE FAN COULD OWN IS ~0.30 °C.** The grow room warmed +0.57 on the same night with its aircon idle *(above setpoint, HEAT mode, so free-running)*. Treat that as the common-mode calm-night term and the fruiting room's excess is **+0.30 °C** — the same order as Arm C's 0.20 °C, i.e. the actuator's weakness again. **⚠️ Hinges on:** *that the calm-night effect is common-mode across the two rooms.* **It is not: the fruiting room owns the floor openings and the exhaust strip, so it is the leakier of the two and gains MORE from a still night.** **So 0.30 °C is a ceiling, and the honest estimate is nearer zero. Size of the move if wrong: the entire 0.87 °C is weather, and there is no fan signal in this night at all.** *(Wind is Open-Meteo's modelled 10 m value on a ~1 km grid cell, not measured on site — there is no anemometer here.)*

**✅ THREE RESULTS DO SURVIVE, because none of them depends on attributing the temperature.**

1. **✅ LOW DOES NOT TRIP THE PRESSURE FLOOR — the abort branch did not fire, and it was the thing genuinely at risk.** `temp_shelf_delta` **improved** through the night, −0.23 at 00:00 → **+0.18 by 07:00**, i.e. the bottom shelf ended *warmer* than the top. The 07-25 failure mode did not recur. ➡️ **`HARDWARE_REFERENCE.md`'s "never leave this fan off overnight" was written about OFF; LOW is now measured and is safe for a night.** *(It had entered the window at −0.80 on 08-13 evening, which is why this was the watched risk.)*
2. **✅ CO2 DID NOT RUN AWAY, AND THE MONOTONIC CLIMB IS BROKEN.** The pre-registration priced ~135 ppm of headroom at ~150 ppm/day — about one night. **Actual: it peaked at 699 (08-13 21:00) and then FELL monotonically to 646 by 04:00–06:00, 637 by 09:00.** Night-over-night the *level* is still up (+58 displayed), but **+197 ppm/24h has become +58, and the within-night direction has reversed.** ➡️ **The block below predicted a plateau needing 48–72 h; this is it arriving.**
3. **⛔ THE HUMIDIFIER GOT ZERO RELIEF — 100.0% both nights, off relay transitions.** The evening 2-hour read's AH reversal at 17:20 was real but **did not convert into any duty headroom at all.** ➡️ **This is branch 2's second clause and it stands on its own: the moisture deficit is independent of the fan.** **The spare 12-disc unit is the next single variable**, and it no longer has to wait behind the fan question.

**🔴 AND THE COST SIDE GOT WORSE: the room was out of band ALL NIGHT — 18.70–19.40 °C against a 15–18 band, 0% in band**, against 17.90–18.40 on 08-13. **VPD peaked at 0.42, over the 0.40 limit.** The conflict recorded above is not diurnal any more; it is now overnight too.

**➡️ WHAT IS STILL OPEN, and it is narrower than before.** The **coupling question is untestable on this fan** — for two reasons, and **✏️ CORRECTED 2026-08-14: THEY ARE NOT BOTH PERMANENT.** *(1)* a **~10% actuator** — permanent, and it is the binding one; *(2)* a disturbance that moved 3× between nights — **SEASONAL, and this test ran in the wrong month.** Operator: *"We do not get much wind in Pretoria. Only in August and before a rain storm."* **The archive agrees and extends it — see the wind-seasonality block.** ➡️ **So "normalise against wind" is a December–May concern only in the small; in August–October it is the whole story.** **But a calmer month does NOT rescue this test** — a 0.2–0.3 °C signal is still about 1:1 with the noise. ⬜ **The cheap route is repetition, not a better actuator: ~10 alternating HIGH/LOW nights in a calm month, paired, drives the standard error to ~0.13 °C. Free, and it needs only that nothing else changes.** Until one or the other is done, neither the trolley/wall case nor "a separate room is forced" can be settled here. **⛔ No disturbance in the window** (no sharp CO2 moves; the door entity is not physically installed and reads floating — ignore it), so the night itself was clean; it is the weather that voids it.

**✅ OPERATOR CONFIRMED 2026-08-14: the fan is STILL ON LOW and nothing else changed.** So the night had exactly two moving parts — the fan and the weather — and the confound analysis above stands as written. **`HARDWARE_REFERENCE.md` now records LOW as the confirmed setting** *(a setting, not a decision)*.

**⛔ AND THAT KILLS "JUST PUT IT BACK TO ARM C's HIGH" — WHICH THIS SESSION RECOMMENDED BEFORE CHECKING IT.** `MICROCLIMATE.md` §Phase-2 already says it plainly: **Arm C chose HIGH on 07-30 with the grow room at ~17–18 °C, and it now runs 21.8–22.4 °C.** The premise is gone. **And the direction is now actively wrong: the fan's intake is grow-room air** *(§"Fresh air" — outside air enters a 15 mm hole in the grow room's rear wall, crosses that room, and reaches the plenum already tempered)*, **so HIGH imports ~22 °C air into a room that ran 18.7–19.4 °C against a 15–18 band.** ➡️ **Neither speed is a restore-to-known-good. Decide the fan on CO2 and grow-room ventilation — the jobs where it measurably does work — and NOT on temperature, where it moves <0.3 °C in either direction.**

**🔑 THE BAND PROBLEM IS THE AIRCON'S, NOT THE FAN'S, AND THE TWO LEVERS ARE AN ORDER OF MAGNITUDE APART.** The 08-12 aircon change moved this room **3.3 °C in one step**. The fan moves it **<0.3 °C**. **Every night spent on the fan is a night not spent on the lever that actually has authority.**

**⬜ NO WEATHER-MATCHED REPLICATION IS AVAILABLE THIS WEEK — CHECKED 2026-08-14, DO NOT WAIT FOR ONE.** A LOW night under 08-13's windy conditions would separate fan from wind for free. **The forecast does not offer it:** overnight means for 08-15 / 08-16 / 08-17 are **6.8 / 7.2 / 8.9 km/h**, against the 14.3 that voided the comparison — all nearer last night's calm 4.6 than to 08-13. ➡️ **Holding the room on LOW to wait for a matched night is a plan with no end date. The one free thing a second LOW night does buy is whether ~19 °C is now the room's resting state**, which is worth knowing regardless of attribution — *(⚠️ and only weakly a wind test: 4.6 → 6.8 km/h is 1.5×, not the 3× that did the damage, and outdoors warms 5.3 → 6.4 °C at the same time, which pushes the room the other way)*.

**➡️ SEQUENCE FOR THE INKBIRD, UNCHANGED AND STILL NOT INTERCHANGEABLE:** ① settle the fan and give the room a day → ② co-locate for 24 h with nothing else changing → ③ read the offset → ④ return it to the bottom shelf **and log that you did**. **⛔ `temp_shelf_delta` IS the Inkbird** (bottom minus top), so moving it up collapses the delta toward zero **because both sensors are then in the same place** — the tripwire would read healthy through an actual crash. This file has already been burned by that exact mechanism: the shelf deltas are **template sensors that recompute when the OTHER input changes**, and they produced plausible numbers right through the 08-09 Inkbird freeze, voiding two nights. **While co-located there is no bottom-shelf instrument at all, so it must not span any airflow change.**

### 🔴 CO2 IS CLIMBING — the warming raised production far more than it raised ventilation (2026-08-13)

**✏️ CORRECTS AN ENTRY MADE THE SAME DAY.** The block above first read *"CO2 itself is healthy: overnight trough 402 displayed, unchanged, well under target."* **That was read off the 48h `room_check.py` window, which straddles the fan change and averages the cold half in.** The 24h trend says the opposite.

| night trough, displayed | 08-10 | 08-11 | **08-12** |
|---|---:|---:|---:|
| Primary | 482 | 393 | **570** |

**Hour by hour since the fan change it is monotonic: 412 ppm at 08-12 09:00 → 609 at 08-13 09:00. +197 ppm in 24 hours, still rising, no plateau.**

- **🔑 THE TREND IS OFFSET-INDEPENDENT, WHICH IS WHY IT CAN BE TRUSTED.** It is a *differential* over one sensor, so the unmeasured zero error cancels. **Whatever the absolute value is, the direction is unambiguous and it is the wrong way.**
- **➡️ THE MECHANISM IS BIOLOGICAL — PRODUCTION ROSE, VENTILATION DID NOT.** Respiration scales with temperature: at Q10 ≈ 2 the fruiting room's **+3.3 °C is ~+26% CO2 production**, and the grow room's **+7.3 °C is ~+66%** — from **96 colonising bags**, the most metabolically active thing on the property, **in a room with essentially zero air exchange of its own.** Meanwhile the fresh-air fan is a **fixed-speed 2-speed unit sitting on HIGH**, so its flow did **not** rise to meet it, and the passive paths gained only ~7% (stack ΔT 8.0 → 9.1 K, the outdoors having warmed 6.9 → 9.1 °C the same night and cancelled most of the room's gain). **Production up tens of percent against a ventilation rate that is essentially constant is the whole story.**
  - **✏️ CORRECTED 2026-08-13, SAME DAY — an earlier version of this bullet described the room as passively ventilated and computed the flow change on a stack-effect square-root law alone.** That was **wrong: the fresh-air fan is installed and running** (operator). See the correction block below — the error also invalidated a recommendation, so it is recorded rather than silently edited out.
- **⚠️ IT HAS NOT PLATEAUED, so the ceiling is not yet known.** 24 h is less than one settling time for a passively-vented room that just took a step change. **Do not price the final level off today's number** — read it again after a full 48–72 h at the new temperature.

### ✏️ CORRECTION 2026-08-13 — THE FRESH-AIR FAN IS INSTALLED AND RUNNING. An analysis published earlier today treated the room as passively ventilated, and it was wrong.

**Operator, 2026-08-13. And this file already said so** — line ~1089 under *"Hardware — current configuration"*: **`Fresh-air fan: 100mm 2-speed AC inline (ACDC), mains, on HIGH`**, corrected 08-11 and settled by the **07-30 Arm C** decision. `MICROCLIMATE.md` records the **2-speed mains fan installed 2026-07-23**. **The SEAFLO was removed 07-18 and replaced five days later.**

- **⚠️ HOW THE ERROR HAPPENED, because the trap is re-walkable.** The 07-18 removal is written up in **three places, at length, with reasoning** (`DECISIONS.md`, `HARDWARE_REFERENCE.md` §"Fan failure mode", `MICROCLIMATE.md`). The **replacement** is a clause in a config table. **The dramatic entry outranked the current one in attention, and the HA entity names — `PHANTOM … drives nothing` — read as confirmation.** They are not: *"off-controller"* means **the ESP32 cannot drive it**, not that it is absent. **The WF-150 carries the identical label and plainly exists.**
- **✅ ALL STALE REFERENCES CORRECTED 2026-08-13** (operator confirmed the fan is unchanged since 07-23). Fixed in **`STATUS.md`** (2 places), **`HARDWARE_REFERENCE.md`** ("Fan 2 (fresh air)", now the authoritative entry, plus the post-reflash rule which implied only one fan to check), **`MICROCLIMATE.md`** (7 places, including the Phase-2 experiment list where *"fresh-air fan speed vs CO2"* was struck through as superseded and is now **reinstated and runnable for R0**), and **`DECISIONS.md`** (the 07-18 entry, which stays as written because it was true on its date, now carries a pointer forward). **The correct phrasing everywhere is "since active CO2 *control* was abandoned", not "since the fan was removed".**

**🔑 AND THE CORRECTED PHYSICS INVERTS THE OBVIOUS HUMIDITY MOVE. THE FAN IS NOT WHAT IS DRYING THE ROOM — IT IS THE CHEAP PATH, AND IT GOT CHEAPER.**

The fan draws from the **grow room**, not outdoors. The grow room warmed 7.3 °C, so **its air now carries far more absolute moisture** — while the outdoor air coming through the floor openings and exhaust strip did not change.

| moisture gradient the humidifier must replace | before (08-12) | after (08-13) | change |
|---|---:|---:|---:|
| **Fan path** (fruiting − grow room) | 11.55 − 8.26 = **3.29** | 13.5 − 10.54 = **2.96** | **−10%** |
| **Passive path** (fruiting − outdoor) | 11.55 − 6.1 = **5.45** | 13.5 − 6.6 = **6.9** | **+27%** |

- **➡️ THE ENTIRE INCREASE IN MOISTURE DEMAND SITS ON THE PASSIVE PATH.** Per m³ the holes are now **2.3× more expensive than the fan** *(6.9 vs 2.96)*. **So slowing the fresh-air fan is a WEAK humidity lever** — it would throttle the *least* drying air in the room while surrendering CO2 dilution, temperature coupling and positive pressure. **This confirms, on new numbers, the standing strategy at line ~1386: seal the expensive path, buy the flush back through the cheap one.**
- **✅ BUT SLOWING IT IS A STRONG *TEMPERATURE* LEVER, AND THAT IS NOW A REAL PROBLEM.** The fan is the mechanism that *"buffers the fruiting room against the grow room"* (line ~906). **The fruiting room is above its ceiling precisely because that buffer is now importing 21.8 °C air.**

**🔴 WHICH QUALIFIES THE 45% COUPLING CONCLUSION ABOVE — AND IT WAS POINTING AT AN EXPENSIVE BUILD.** That entry read the coupling as conduction through the 50 mm partition and concluded colonisation temperature is unreachable, so **the separate grow room is "confirmed necessary, not preferred."** **If the coupling is carried substantially by the fresh-air fan, it is partly a FAN SETTING, not a wall property** — and a fan setting can be changed for R0. **⬜ The 44% figure stands as a measurement; its INTERPRETATION does not.** Re-measure it at fan LOW before treating the new grow room as forced.

**🔬 AND ARM C'S "HIGH BEATS LOW ON EVERY AXIS" WAS DECIDED UNDER CONDITIONS THAT NO LONGER HOLD.** It was settled **2026-07-30**, when the grow room ran **~17–18 °C** — a *cool* source. **It is now 21.8 °C, and the fruiting room is above its band.** The axis that made HIGH win (importing the grow room's conditioning) has **reversed sign**. ➡️ **Switching the fan to LOW for one night is free, instant, reversible, and now tests a genuinely different question than Arm C did.** ⚠️ **Watch the bottom shelf** — the fan's load-bearing job is **positive pressure**, and switching it *off* on 07-25 crashed the bottom shelf within hours. **LOW is not off, but that is the failure mode to watch for.**

**⛔ SO THE HUMIDITY-BY-SEALING ROUTE IS BLOCKED, AND NOW FOR TWO INDEPENDENT REASONS.** Closing more of the 50 mm exhaust strip is the natural answer to the moisture deficit above — it cuts the loss directly, without touching moisture delivery. **But the standing gate (a mild, still night, never sampled) is now joined by a second: the CO2 KPI is moving the wrong way at ~200 ppm/day.** Cutting the only passive exhaust while production is rising is the one change guaranteed to compound it.

**✏️✏️ CORRECTED 2026-08-14 — THE ABSOLUTE LEVEL IS PROBABLY FINE, AND THIS ENTRY GOT IT WRONG BY QUOTING A DEAD NUMBER.**

*(This block first argued that the room was at **~960 ppm true and already failing**, on a "+350 ppm" offset, and presented +90 vs +350 as the live uncertainty.)* **Both figures were already falsified — the working was in the sensor block below, unread, because it was 32 KB long.**

- **⛔ +350 died on 2026-08-08** (the Inkbird recalibration settled at ≈+200, not the predicted +326). **+210 died on 08-11.**
- **✅ THE MOST RECENT MEASUREMENT, 2026-08-11: the primary read `+7` against the Inkbird's outdoor-validated zero — essentially ACCURATE.** **So displayed ≈ true, current CO2 is ~610 ppm, and the room is comfortably inside the <800 target.**
- **⚠️ BUT THAT IS A SNAPSHOT OF A MOVING QUANTITY.** The primary's zero has shifted twice, once by ~+233 in three days, cause unknown. **A two-day-old "accurate" is not a calibration.**

**🔑 WHAT SURVIVES THE CORRECTION, AND IT IS THE PART THAT MATTERS: THE TREND.** **412 → 609 ppm in 24 h, monotonic, no plateau.** That is a *differential over one sensor*, so the zero cancels — **it holds regardless of which offset is right, and it is the reason not to seal.** ➡️ **The revised read: there is more absolute headroom than this entry claimed (~190 ppm to target, not −160), but it is being consumed at ~200 ppm/day and the ceiling is unknown because the room has not settled.**

**➡️ Still the right next action, now for a sharper reason: co-locate the Inkbird beside the primary for 24 h.** Not to discover a *stored* offset — the finding below is that no stored offset is valid — but to **confirm the primary is still near-accurate** before any sealing decision rests on it. Free, no reflash. `room_check.py --inkbird colocated --since '<time>'`, read after 24 h.

⚠️ **Hinges on:** *the primary not having moved again since 08-11.* **Unchecked for two days, on a sensor whose defining behaviour is that it moves.** **Size of the move if wrong: the whole sealing decision — at +233 the room would be at ~840 and over target instead of comfortably under.**

### ✅ THE AIRCON INVESTIGATION, 2026-08-01 → 08-13 — CLOSED. Compressed 2026-08-13; full narrative in git.

**Cause: a recirculation feedback loop, not a fault.** The indoor unit's intake sits 100 mm below the ceiling, so its ~40 °C output rose straight back into it, the thermostat read ~8 °C hotter than the room, the unit throttled, and on `AUTO` it dropped the fan — removing the jet's throw, worsening the recirculation. Self-reinforcing.

**Fix: `HEAT` · fan `MANUAL HIGH` · setpoint 21 °C, louvres steeply down.** **Proven 2026-08-13: grow-room overnight mean 14.48 → 21.84 °C, at setpoint for the first time in this record.** ➡️ **Operating rule and its silent-revert risk: `HANDBOOK.md`.** The permanent repair is geometric — deflect or duct the supply away from the intake — and that is what would make `AUTO` safe again.

**⛔ RULED OUT — do not re-litigate these. Each was a live theory that cost time:**

| Candidate | How it died |
|---|---|
| **Dirty filter** | The 08-01 event's diagnosis. Filter attended to; the shortfall persisted |
| **Capacity / undersizing** | **Measured 16 °C supply-to-return rise.** Nameplate `Alliance INAA18`, 5790 W heating — **3–5× oversized** for 17.7 m³ |
| **Defrost cycling** | **No ice, no condensate** on the outdoor unit |
| **Low refrigerant** | Same 16 °C rise — a healthy unit cannot be short of gas |
| **Back-wall drywall / envelope loss** | Leading candidate on 08-11. **A fan speed fixed the room; an envelope leak cannot be cured by a fan speed** |
| **Grow-room door leaks** | Same test, same disposal |
| **Grow-room sensor reading low** | A probe said 21 °C where the DHT22 said 15.5. **An ice-water bath put the +7 °C error on the MULTIMETER.** The DHT22 was right |

**🔧 THE FOUR-READING DIAGNOSTIC, kept because it is reusable and it is what actually cracked this.** Take all four **at the same moment, while the compressor is running:** ① supply air at the outlet louvres, ② return air at the intake grille, ③ bag level mid-room out of the blast, ④ ceiling height. **① − ② is the rise: 15–25 °C is healthy, under ~8 °C is a plant problem.** **② vs ③ is the load-bearing pair** — return warmer by 2–4 °C means the unit is cutting out on air the crop never sees. Use a cheap instant-read probe; **verify it against ice water first.**

**⛔ THE EXTRAPOLATED COUPLING TABLE (20 °C → fruiting 17.1, 25 °C → 19.6) IS SUPERSEDED.** It was inferred from four nights of weather-driven drift. **Coupling was measured directly on 2026-08-13 at ~44%** — see the fan-fix block at the top of this section, including the open question of how much of it the fresh-air fan carries.

### 🔬 THE FRONT-WALL VENT SERIES — CLOSED 2026-08-01. Compressed 2026-08-13; five arms' data in git.

**20 of ~80 holes in the 50 mm exhaust strip were closed on 2026-08-09** (open area ~63 → ~47 cm², −25%).

- **⛔ THE STATED TARGET WAS ALREADY MET BEFORE IT RAN.** The bottom-shelf gradient it aimed at was already flat — temp −0.1 to −0.2 °C, RH +1.1 to +1.8 — closed by the earlier fan work. **The experiment measured its side effects, not its purpose.**
- **✅ THE REAL PAYOFF WAS HUMIDIFIER DUTY: 100 → 83.1 → 72.4% overnight**, and it was won on the week's *hardest* night — stack drive doubled, wind tripled, moisture deficit unchanged. **First time the <70% KPI came within reach.** *(⚠️ That series is now void as a baseline: the 08-12 fan fix stepped room temperature 3.3 °C. 72.4% and today's ~100% are not comparable numbers.)*
- **✅ The rain objection was tested and STRENGTHENS the result.** 9.4 mm fell inside the window, but saturated air at 6.1 °C holds only 7.3 g/m³ — in absolute terms that night was *drier*. **"It rained so the air was humid" is an RH intuition; the humidifier replaces absolute moisture.**

**🔴 THE STANDING CONDITION, STILL LIVE AND STILL UNSAMPLED: DO NOT CLOSE MORE HOLES UNTIL A MILD, STILL NIGHT (~13 °C, light wind) HAS BEEN READ.** Every CO2 result so far came from cold or windy nights, when stack effect ventilates hardest — **the easiest possible test, not a reassuring one.** The sealing risk lives in weak-drive conditions that have never been measured. **⚠️ Reinforced by the sealed ceiling** (painted shade cloth is not permeable) — the exhaust strip and floor openings are now the *only* relief path, so `MICROCLIMATE.md`'s *"do not seal them all"* binds harder than when written.
### ⛔ AND ONE THING GOT WORSE — humidifier duty is PINNED at 99.2% overnight, 98.0% overall, R433/mo

**Exactly as predicted: a warmer room needs more absolute moisture at the same RH, so recovery raised duty rather than lowering it.** It is now **the only failing KPI**. **➡️ Arm D is unblocked and is the next move** — free, ~13 duty points, and the aircon verdict it waited on is in.

---

### 🗄️ The 2026-08-01 → 08-04 aircon fault report — RESOLVED, compressed 2026-08-13

**The failure signature lives in `HANDBOOK.md`** §"Grow-room air conditioner — filter cleaning", which is the right home for it: it is a maintenance-recognition pattern, not current state. **The cause was NOT the filter** — see the closed investigation directly above.

**The one durable process point:** it was found by the **weekly `room_check.py`, run one day late**, and nothing else was watching. The aircon still has no telemetry, no `climate.*` entity and no alarm. **That scorecard remains the only instrument that sees this unit.**

*(Full original report: `git show 18f3846:STATUS.md`.)*
### 🔴 LIVE — THE FRUITING ROOM HOLDS THREE BATCHES AGAINST A WEEKLY PACK CADENCE (found in the ledger 2026-08-05)

**This was found while chasing the aircon, and it outranks it — it lands on priority #1, committable supply.**

**⚠️ An earlier version of this section called the grow room a 95-bag backlog. That was wrong and is corrected here.** With packing every Tuesday and roughly four weeks of colonisation, a steady-state grow room *should* hold about four batches at the 1/2/3/4-week marks — which is exactly what is there. **The grow room is the normal buffer, not a pile-up.** Read off `v_batch_bag_state`:

| Batch | Packed | Bags | → fruiting | In grow | In fruiting |
|---|---|---:|---:|---:|---:|
| W26 | 06-23 | 27 | 25 | 1 | **25** |
| W27 | 06-30 | 23 | 23 | 0 | **22** |
| W28 | 07-07 | 29 | 29 | 0 | **29** |
| W29 | 07-14 | 24 | **0** | **24** | 0 |
| W30 | 07-21 | 28 | **0** | **25** | 0 |
| W31 | 07-28 | 25 | **0** | **25** | 0 |
| W32 | 08-04 | 21 | **0** | **21** | 0 |
| | | | | **96** | **76** |

- **The fruiting room holds three batches — W26, W27 and W28 — totalling 76 bags. W28 moved in on 04/08**, four weeks after being packed.
- **The grow room holds four batches (96 bags) at roughly the 1, 2, 3 and 4-week colonisation marks.** Normal, given the cadence.
- **🎯 THE BINDING ARITHMETIC IS IN THE FRUITING ROOM, AND IT IS SIMPLE.** Capacity is **three batches**; input is **one batch per week**. **So the pipeline only balances if a batch's fruiting-room residence is about three weeks.** Longer than that and the queue must grow — there is nowhere else for it to go. **The operator's own read — *"they are all staying longer than what I think they should"* — is exactly this constraint being felt rather than measured.**
- **⚠️ Whether the queue is ACTUALLY growing yet is not established.** W28 moved in at four weeks post-pack; if W29 moves at the same point it is due ~11/8 and nothing is late. **The test is whether successive batches move in at a widening gap — which needs the `bag_movements` dates, not the bag counts.**
- **✅ CONFIRMED BY THE OPERATOR 2026-08-05 — THIS IS REAL, NOT A CAPTURE GAP.** *"23/6; 30/6; and 7/7 is in the fruiting room. 14/7; 21/7; 28/7; and 4/8 is in the grow room."* **The ledger is accurate and the physical room matches it.** The alternative reading — that `fn_move_bags_to_fruiting` simply was not being called since `bag_movements` was created on 07-28 — is ruled out. *Worth banking separately: the bag-movement capture is trustworthy, which is not something that could be assumed of a two-week-old table.*
- **➡️ SO THIS IS A SUPPLY STORY, NOT A MICROCLIMATE ONE.** The environment has been tuned to the ppm while the throughput constraint — how fast batches clear the fruiting room — has never been measured at all.
- **✅ W29 IS READY AND SPACE-GATED — operator, 2026-08-05: *"w29 looks good. if i remove an old batch from the fruiting room it can be moved in."*** So the backlog is not a colonisation delay. **The fruiting room is full, and the queue is waiting on an eviction, not on biology.** W30 (21/7) is a week behind it; W31 and W32 are within normal colonisation time and are exactly where they should be.
- **The move is arithmetically clean:** fruiting holds 76 (W26 25 + W27 22 + W28 29). **Removing W26 — the oldest at 6 weeks — frees 25 slots for W29's 24 bags**, landing the room at 75.

### 🔴 THE REAL CONSTRAINT IS RESIDENCE TIME, AND IT IS THE ONE THING NEVER MEASURED (named 2026-08-05)

**Operator, 2026-08-05, and this reframes the entire room programme:** *"They are all staying longer than what i think they should but that then was the reason the micro climate improvement was initiated."*

**➡️ THE MICROCLIMATE WORK WAS STARTED TO FIX RESIDENCE TIME, AND SUCCESS WAS THEN MEASURED ENTIRELY IN ENVIRONMENTAL KPIs — VPD, temperature, RH, CO2, uniformity. None of those measure residence time. So the programme has never been able to tell whether it achieved its own stated purpose.** This is sharper than the yield-measurement gap already named above: it is not merely that yield is uncaptured, it is that **the specific quantity the work exists to improve has no instrument at all.**

**⚠️ And the committed KPI is blind to it by construction.** Biological efficiency — kg fresh per kg substrate — is a **ratio with no time in it**. A batch yielding 15 kg over 8 weeks and one yielding 15 kg over 4 weeks score **identically on BE**, while the second doubles what the room delivers per week. **Committable supply is `bags × yield-per-bag ÷ residence weeks`.** Residence time is a direct multiplier on weekly supply and it is absent from the scorecard.

**🔬 MEASURED 2026-08-05 off `v_batch_residence`, first read against production. Two guesses made earlier today are corrected by it — in opposite directions.**

| Batch | Packed | Moved in | Days colonising | Days fruiting | Picks | Grams | g/bag | **BE %** | **g/bag/wk** |
|---|---|---|---:|---:|---:|---:|---:|---:|---:|
| W25 | 18/6 | 14/7 | 26 | **21** *(complete)* | 8 | 6,676 | 317.9 | **6.1** | **106.0** |
| W26 | 23/6 | 23/7 | 30 | 13 *(open)* | 6 | 9,214 | 368.6 | **7.6** | **198.5** |
| W27 | 30/6 | 21/7 | 21 | 15 *(open)* | 9 | 12,428 | 540.3 | **10.4** | **252.2** |
| W28 | 7/7 | 4/8 | 28 | 1 *(open)* | — | — | — | — | — |

- **⛔ CORRECTION 1 — fruiting-room residence is ~2–3 WEEKS, not the 5–7 implied this morning.** W25 completed its whole fruiting life in **21 days**; W26 and W27 are 13 and 15 days in. The earlier figure came from treating batch age as residence and was wrong by roughly a factor of three.
- **⛔ CORRECTION 2 — the room is NOT structurally oversubscribed.** The balance point for 3 batches of capacity at one batch per week is ~21 days, and **W25 came in at exactly 21.** The pipeline is running close to balance, not 2× over it. **Delete the "oversubscribed by 2×" reading; it was arithmetic on a wrong residence figure.**
- **🎯 SO THE LONG POLE IS COLONISATION, NOT FRUITING — and that is the opposite of where the room programme has been looking.** Colonising takes **21–30 days (mean 26)**; fruiting takes **13–21**. Bags spend **more than half their life in the grow room**, which is the room with no ventilation, no supply duct, and no KPI of its own. **W29 at 22 days is inside the normal colonisation range — it is not late, and "the fruiting room is full" and "W29 is ready" are both true without anything being broken.**
- **⚠️ HYPOTHESIS, NOT ESTABLISHED — the cold grow room and the throughput constraint may be the same problem.** The grow room has been running **~14.5 °C instead of ~17.7 °C** since 08-01 (see the aircon issue above), and cold slows colonisation. **If that is real, the aircon fault is not merely a comfort issue — it is lengthening the long pole of the whole production cycle.** **The test is free and already instrumented:** W29 (packed 14/7) colonised mostly before the cold; **W31 (28/7) and W32 (4/8) are colonising through it.** If their `days_colonising` comes in above ~30 when they move, that is the evidence. **Do not act on this until those two batches move.**
- **🔬 AN ACCIDENTAL NATURAL EXPERIMENT — W27 JUMPED THE QUEUE AHEAD OF W26, AND IT IS THE CLEANEST TEST OF COLONISATION TIME THIS BUSINESS IS LIKELY TO GET.** The operator recalled a batch going in out of order but not which; the move dates identify it. **W26 was packed a week EARLIER (23/6 vs 30/6) but moved in two days LATER (23/7 vs 21/7)** — so W26 sat **30 days** in the grow room, the longest on record, while the younger W27 went ahead of it on **21 days**, the shortest.
  - **Near-ideal controls:** packed a week apart, moved in two days apart, same room, same conditions since. The one material difference is **9 extra days of colonisation.**

    | | W26 (30 days) | W27 (21 days) |
    |---|---:|---:|
    | BE % | 7.6 | **10.4** |
    | g/bag | 368.6 | **540.3** |
    | g/bag/week | 198.5 | **252.2** |
    | BE per day in fruiting | 0.58% | **0.69%** |

    The last row normalises for W27's two extra days in the room. **W27 still leads by ~19% on that basis and ~27% on g/bag/week.**
  - **⚠️ Hinges on:** *the direction of causation, and it genuinely runs both ways.* Either **(a)** the extra 9 days cost W26 yield — blocks over-ran and consumed substrate they would otherwise have fruited with — in which case **moving bags in sooner is a free yield lever**; or **(b)** W26 took 30 days *because it was already the weaker batch*, slow colonisation being a symptom rather than a cause, in which case the move date changed nothing. **One pair cannot separate these. Do not shorten the colonisation window on the strength of this.**
  - **✅ But it will answer itself, at no cost.** `days_colonising` already varies naturally from **21 to 30** across recorded batches, and **W31 and W32 are colonising through the cold spell**, which will widen that range further. **A few more completed batches make this a correlation, not an anecdote** — and `v_batch_residence` now captures both sides automatically.
  - **➡️ If (a) proves right, it compounds with the long-pole finding above: the grow room — no ventilation, no supply duct, no KPI, and 3 °C cold since 08-01 — is where the yield is, not the fruiting room the entire programme has been tuning.**
- **✅ W28's apparent zero-production anomaly is RESOLVED and was never an anomaly** — one day in the fruiting room when the captures were read. Nothing wrong with the batch or the capture habit.
- **⚠️ The g/bag/wk column is NOT yet a like-for-like comparison.** W25 is complete, so its 106.0 is a lifetime average including its declining tail. W26 and W27 are **mid-life and still producing**, so their 198.5 and 252.2 will fall as they age. **W26 is not "underperforming W27" and neither is beating W25 — the comparison only becomes fair between completed batches.** First honest read: when W26 and W27 are removed.

#### 🔴 AND THE HEADLINE THE VIEW WAS BUILT TO SURFACE: BIOLOGICAL EFFICIENCY IS 6–10%, AGAINST THE 15–25% THIS FILE ITSELF NAMES AS THE TARGET

**This is the first time the question at the top of this document — *"are we at industry yield?"* — has had a number attached.** The answer on current data is **no, by a factor of roughly two to three.** W25, the only *completed* batch, came in at **6.1%**.

**✅ BASIS CONFIRMED WET — operator, 2026-08-05: *"the bags are filled with the soaked straw. The straw is wet."*** So `total_substrate_grams` is soaked-straw weight and **the comparison against the 15–25% wet-basis range is like-for-like.** The dry-basis reading is ruled out. **This was the cheapest of the open questions and it is now closed.**

**✅ And the data is internally coherent, which is worth banking on its own.** Back-solving substrate weight from BE gives **~109 / 121 / 120 kg** for W25 / W26 / W27 across 21 / 25 / 23 bags — **~4.9–5.2 kg of wet straw per bag on all three.** Independent batches agreeing to within 6% means the substrate figures are being entered consistently, not estimated.

**So in per-bag terms:** 15–25% of ~5.2 kg is **780–1,300 g per bag**. W25 finished at **318 g — under half the bottom of that range.** W27 is at 540 g and still producing.

**⚠️ Hinges on** what remains: *harvest-capture completeness, and whether these are single-flush figures.* Both point the same way — **the number is understated, not overstated:**
- **Capture completeness is the bigger doubt, and it points the same way — the number is more likely understated than overstated.** Every batch's first recorded picking is **on or after 24/7**, which is about when harvest capture became a habit. W27 moved in 21/7 and was first picked 24/7 — a plausible 3 days. But **W25 moved in on 14/7 and shows nothing until 24/7 — a 10-day gap that probably means its early flush was harvested and never recorded.**
- **🔴 `flush_count` reads 1 for ALL THREE, AND W25 WAS PICKED ON 04/08 AND REMOVED ON 04/08 — THE SAME DAY.** It was **still producing when it was pulled**, and it never entered a second flush: no rest gap appears across its 8 pickings from 24/7 to 4/8. **The 15–25% benchmark is quoted *across all flushes*, so comparing it to a single-flush figure is not like-for-like — and a first flush is typically only half to two-thirds of a batch's total.** That alone could account for much of the shortfall.

**➡️ SO THE OPEN QUESTION IS NOW A SHARP ONE, AND IT IS THE BIGGEST YIELD LEVER VISIBLE ANYWHERE IN THESE DOCS: is a second flush normally taken, or are bags cleared after the first?** Ask before concluding — 19 of W25's bags were explicitly marked `SPENT`, so the operator judged them finished, and that judgement may well be right.

**⚠️ If bags ARE being cleared before a second flush, it is not a mistake — it is the fruiting room's capacity constraint expressing itself, and the two sides of that trade are now both measurable for the first time.** Three batches of capacity against one batch a week forces a choice: **hold a batch for its second flush, or free the slot for the queue.** `grams_per_bag_per_week` prices the throughput side; a completed second flush would price the yield side. **Until both are measured the trade is being made implicitly, every Tuesday.**

**🔴 AND THE OPERATOR HAS NAMED THE LIKELY MECHANISM (2026-08-05): *"if the batch was removed because it was the oldest in the fruiting room even though it was not there long, it might not have had a chance for a second flush."*** **If removal is decided on PACK DATE, the rule is measuring the wrong thing — and it penalises exactly the batches that colonised longest.**

- **The penalty compounds, and it is arithmetic, not opinion.** W25 was removed at **47 days total age** having had **21 days** of fruiting. Apply that same age threshold to the two now in the room, given when they actually went in:

  | Batch | Packed | Moved in | Age-47 falls on | **Fruiting days it would get** |
  |---|---|---|---|---:|
  | W26 | 23/6 | 23/7 | ~09/8 | **17** |
  | W27 | 30/6 | 21/7 | ~16/8 | **26** |

  **A 53% difference in productive time, from nothing but a 9-day difference in colonisation.** W26 already sat longest in the grow room; an age-based removal rule then charges it for that a second time. **Double-penalised for being slow to colonise.**
- **⚠️ THE W25 REMOVAL CANNOT TELL US WHICH RULE IS IN USE — it was oldest on BOTH measures.** On 04/08 W25 was both the oldest by pack date *and* the longest-resident in the fruiting room (21 days, against W26's 12 and W27's 14). **The two candidate rules agree on that case, so it is not evidence either way.**
- **✅ BUT THE NEXT REMOVAL DISCRIMINATES, AND IT IS IMMINENT.** W26 and W27 disagree: **by pack date you pull W26; by time-in-fruiting you pull W27**, which has been in the room two days longer despite being the younger batch. **Whichever one goes next identifies the rule actually in force — for free, with no experiment.** Note it when it happens.
- **➡️ WHAT THE RULE SHOULD PROBABLY BE, once there is data to support it: remove on PRODUCTIVITY, not on age.** `v_batch_residence` now carries `last_picked_on` and `grams_per_bag_per_week` — a batch that has stopped producing has earned its eviction; a batch still picking on the day it is pulled, as W25 was, has not. **Pack date was a reasonable proxy while nothing better existed. Something better now exists.**

#### 🔴🔴 THE INTENTION IS TWO FLUSHES, AND THE ROOM CANNOT PHYSICALLY DELIVER THEM (named 2026-08-05)

**Operator, 2026-08-05: *"I intention is to take a second flush."*** So W25 being pulled mid-first-flush was **not** the plan. **It is not a discipline problem — it is arithmetic, and the two numbers have never been put side by side before:**

- **Two flushes need roughly 4–6 weeks of fruiting residence** — first flush, a 1–2 week rest, second flush.
- **The room allows ~3 weeks.** Capacity is **3 batches**; input is **1 batch/week**; so mean residence cannot exceed 3 batches ÷ 1 per week = **21 days** without the queue growing without bound. **W25's actual residence was exactly 21 days.**

**➡️ THE STATED INTENTION AND THE ROOM ARE INCOMPATIBLE BY ROUGHLY A FACTOR OF TWO. Every batch will keep being pulled mid-cycle, whatever rule is used to choose it, until either capacity rises or the pack cadence falls.** This is the single cleanest explanation yet offered for the low BE, and it was invisible while residence went unmeasured.

**⚠️ AND THE OBVIOUS FIX MAY BE BACKWARDS — this needs measuring before it is acted on.** If **slots** are the binding constraint, what matters is yield per slot per *week*, not per batch. Illustratively, using the only figures that exist:

| | Residence | Yield/bag | **Per bag per week** |
|---|---:|---:|---:|
| One flush, fast turn *(W25 actual)* | 21 d | 318 g | **106 g** |
| Two flushes, slow turn *(assumed +60%)* | ~42 d | ~510 g | **~85 g** |

**On those numbers a second flush LOWERS weekly output**, because the rest period is unproductive occupancy of a scarce slot. **That is counterintuitive and it may well be wrong — but it is the calculation that decides the question, and nobody has run it.**

**⚠️ Hinges on:** *the size of the second flush and the length of the rest* — the one input nobody has measured, because no batch on record has been held for one. **A second flush at 60% of the first loses; at 100% it wins.** Substrate cost does not settle it either way (R680/mo against ~R5,370 revenue, so halving substrate per kg is a small effect); **slot-throughput dominates.**

**➡️ THIS GIVES THE DIVIDER-WALL REMOVAL A BUSINESS CASE IT DID NOT HAVE.** It has been framed as a microclimate and capacity question gated on the aircon. **It is actually the thing that would let both flushes be taken without surrendering throughput** — more slots dissolve the trade instead of choosing a side of it. **That belongs in the wall decision above, which currently reasons only about humidity and temperature.**

**➡️ Cheapest way to get the missing number: hold ONE batch to a full second flush and measure it.** It costs one slot for ~3 extra weeks and produces the figure the whole decision turns on. **W26 is the natural candidate** — it is the one an age-based rule would evict next, and it has already been penalised twice (longest colonisation, earliest eviction).

**➡️ Next honest read: W26 and W27 on removal** — capture has been continuous for their whole fruiting life, so they will be **the first trustworthy BE figures this business has ever had.**
- **⛔ THE ANALYSIS CANNOT BE TAKEN FURTHER FROM HERE, AND THAT IS BY DESIGN.** `v_recent_captures` is hard-limited to **20 rows**, and the 2026-08-04 migration header explicitly says *"Do not widen it to full history without revisiting 20260728140000's reasoning."* `v_harvest_pickings`, `v_current_biomass` and `v_substrate_biological_kpi` are all correctly closed to anon. **The numbers above are one week, three batches, and no substrate-weight denominator — treat them as a signal, not a result.**
- **✅ BUILT, VERIFIED AND LIVE — `v_batch_residence`, migration `20260805100000_batch_residence_view.sql`. ✏️ CORRECTED 2026-08-08: this entry said "⬜ NOT YET PUSHED" and that is STALE. It IS applied to production** — `supabase migration list --linked` shows `20260805100000` in **both** the Local and Remote columns, and the file is committed and on origin (`f62eced`). **Nothing is outstanding on it.** *(Worth noting how the stale line survived: "not yet pushed" is a claim about a remote system that no one re-checked, and it was carried forward and repeated as an open item three days running. **Verify a deployment claim against the deployment, not against the note that recorded it.**)* One read view over existing tables — no schema change, nothing new to capture. It reports per batch: **days colonising**, **days in fruiting room**, first/last picking, flush count, harvested grams net of corrections and voids, biological efficiency, and **`grams_per_bag_per_week`** — yield per bag per week of fruiting-room occupancy, the throughput figure BE cannot express.
  - Verified on a local stack against a seeded scenario: the colonising/residence split, the SAST timezone boundary (a 01:00 SAST move is 23:00 UTC the previous day and would otherwise understate every duration by a day), NULL-not-zero for unmoved batches, no division error for a batch moved today, correction and void arithmetic, and the anon boundary — per-picking and per-movement detail stays blocked.
  - **`supabase migration list --linked` shows no drift, and as of 2026-08-08 there is no local-ahead migration at all** — local and remote agree through `20260805100000`.
- **⚠️ Hinges on:** *that yield does not simply shift later when batches are pulled earlier.* If the final weeks contribute meaningfully once a batch's own flush rhythm is accounted for, pulling early trades yield for throughput and could be net-neutral. **The three-batch table above cannot distinguish "old batches are spent" from "these particular batches were between flushes that week."** That distinction is worth roughly the difference between a ~50% supply increase and none — and it is exactly what the residence view would settle. **Do not restructure the rotation on one week of data.**
- **🔬 It also gives the aircon investigation a candidate that costs nothing to check: 96 bags stacked in the grow room is a large physical change in that room, and if any of it obstructs the aircon's air path or return it would reduce delivered heat progressively — which looks identical in the recorder to a dirty filter.** W31 went in 07-28; the decline began 07-31/08-01. **Look at where the bags are stacked relative to the unit before spending money on refrigerant or a technician.**

**Humidifier duty is now PINNED — 93.7% overall, 95.4% overnight, 96.1% midday**, worse than any measured vent arm. Two compounding causes, neither of them a humidifier fault:

1. **The room is still in arm E's configuration.** The 08-01 recommendation to revert to **arm D (every fourth hole sealed, fan HIGH)** was never actioned. Arm D was worth ~13 duty points.
2. **The cheap air path got expensive.** Outdoor absolute humidity has halved (**4.7 → 2.8 g/m³**), and the grow-room air the fan supplies is now **~9.0 g/m³** (14.9 °C / 70.2%) against the **12.2** the vent reasoning was built on. Every m³ entering costs more moisture than it did a week ago.

**✅ Humidity control itself is NOT broken — verified, not assumed.** RH held at **90.4–91.2%** every day through the fall. The absolute-humidity drop (13.38 → 11.53 g/m³) is **fully explained by the temperature drop at constant RH**: predicted from T and RH alone it comes out 13.36 / 12.78 / 12.18 / 11.96 / 11.49 — matching measurement to **within 0.05 g/m³ on all five days**. The humidifier is pinned because it is chasing a colder, leakier room, not because it has failed. *(This is the "use absolute humidity, not RH" method from `DECISIONS.md` 2026-07-17, run in the other direction to exonerate a component.)*

### 🗄️ Scorecard, 48h to 2026-08-05 — SUPERSEDED, compressed 2026-08-13

**Every figure in it is superseded** by the 08-13 readings at the top of this section. Two things from it are durable and are kept:

- **The CO2 row was an ARTEFACT, and it is the trap to remember.** It read *"displayed trough 450 ≈ 800 true — on target"* and looked like the best result of the whole vent series. **It was cold-night stack ventilation flattering the number, not the seal working.** Judge CO2 on a mild, still night or not at all.
- **Humidifier duty went the wrong way** (93.7 → 97.7%) **while the arm-D revert stayed un-actioned.** The pattern — a recommendation recorded, not run, and the metric drifting meanwhile — is the one to watch for.

*(Full scorecard: `git show 18f3846:STATUS.md`, §Room state.)*
### ⚠️ LIVE — the primary CO2 sensor's zero MOVES. Compressed 2026-08-13; four weeks of working in git.

**🔑 THE FINDING, and it is not a number — it is that there is no stable number to write.** The primary SEN0659's zero has shifted **twice with no established cause**, most recently by **~+233 ppm between 2026-08-08 and 08-11**. **A stored correction only helps a sensor with a *constant* error.** Everything below follows from that.

**⛔ DO NOT WRITE ANY VALUE TO `0x006B`. Three have been proposed and all three are dead:**

| Value | Derived | Killed by |
|---|---|---|
| **+90** | the 07-25 zero shift | 07-27 co-location: settled delta was **+346** |
| **+350** | that co-location | 08-08 Inkbird recalibration: delta settled **≈+200**, not the predicted +326 |
| **+210** | the 08-08 discriminator | **08-11 outdoor check: the primary had moved and read +7 — accurate.** Writing +210 would have *created* a 210 ppm error |

**⚠️ AND `STATUS.md` WENT ON QUOTING "+350" AFTER IT WAS FALSIFIED TWICE** — it was still being used on 2026-08-13 to argue the room was over target. **Its stated derivation only ever established that the offset exceeds ~23 ppm; the jump to 350 assumed the conclusion.** Treat any bare offset figure in these files as suspect unless it names the check that produced it and its date.

**🎯 THE TRUST HIERARCHY IS INVERTED FROM WHAT THESE FILES SAY.** The primary is described throughout as *"nominally authoritative"* and the Inkbird as *"verification-only"*. **On the evidence the Inkbird is the STABLE one** — its outdoor zero is reproducible across weeks (401, 404, 457–460 in daylight) and it survived being carried indoors and back. **The primary is the one that wanders.** Do not give it actuator authority *(operator decision, 2026-07-29 — and this is why)*.

**✅ LAST MEASURED STATE, 2026-08-11 08:45: the primary read `+7` against the Inkbird's outdoor-validated zero — i.e. ACCURATE.** ⚠️ **This is a snapshot of a moving quantity, not a settled offset**, and it is now two days old.

**⬜ THE OPEN QUESTION IS *WHY* IT MOVES, AND THE OBVIOUS CANDIDATE CANNOT BE TESTED: the controller exposes no uptime or last-boot sensor**, so *"did it reboot and re-baseline its ABC?"* is unanswerable from Home Assistant — entities go `unavailable` identically for a reboot and a network dropout. **Two lines of ESPHome fixes it; it is on the next-reflash list** (`HARDWARE_REFERENCE.md`).

**📋 METHOD — the outdoor check, which is the only calibration instrument here:**
- **Take the Inkbird outside, wait for it to settle, expect ~400–430 in fresh air.** Four-plus consecutive stable reads, not one.
- **⚠️ DAYLIGHT ONLY, AND TIME-OF-DAY MATCHED.** Ground-level outdoor CO2 pools overnight and falls through the day, so a dawn reading and an afternoon reading are not comparable and the difference is the *atmosphere*, not the sensor.
- **⚠️ Calibrate in FRESH AIR, never room air** — recalibrating at ~800 ppm sets the zero ~375 high, wrong in a new direction.
- **↩️ Return it to the bottom shelf afterwards and log that you did** — while it is out, the shelf gradient has no instrument.

**➡️ THE ACTION THAT IS ACTUALLY OUTSTANDING, and it now gates a live decision: CO-LOCATE THE INKBIRD BESIDE THE PRIMARY FOR 24 h.** `MICROCLIMATE.md` records this **has never been done for CO2** — the 07-21 baseline used the temp/RH sensor 3.85 m away. It is free, needs no reflash, and it is what tells you whether the room is near target or over it. **Run it with `room_check.py --inkbird colocated --since '<time>'`; allow 24 h before reading, because a freshly moved NDIR reads low until it settles.**

**📌 THE STANDING LESSON, earned three times now:** *an argument that rests on an uncalibrated sensor is not an argument.* It killed the 07-27 variac energy case, it nearly wrote +210 into a sensor that was already correct, and it produced a wrong CO2 verdict on 08-13.

*(Full four-week working — the 07-27 co-location, the 08-08 recalibration and pre-registered read, the 08-08 discriminator, the 08-10 and 08-11 outdoor checks: `git show b4af191:STATUS.md`.)*

## Hardware, network & firmware — MOVED 2026-08-13

**➡️ All of it now lives in `stock-control/docs/HARDWARE_REFERENCE.md`** — the current-configuration tables (fans, sensors, controller access), the network settings table, and the next-reflash payload.

**Why it moved.** It was the authoritative answer to *"what is actually installed and running"*, and it sat at **line ~1106 of a 1,603-line file**, below ~845 lines of investigation narrative. **On 2026-08-13 that cost real work: a session declared the room passively ventilated and built two recommendations on it, because it read the fresh-air fan's *removal* — written up at length in three narrative places — and never reached the one-line record of its *replacement* down here.** The same move also caught `HARDWARE_REFERENCE.md` still saying the circulation fan runs on LOW, eight days after this file recorded it on HIGH.

**The rule this establishes, and `CLAUDE.md` now states it:** **`HARDWARE_REFERENCE.md` is authoritative for what physically exists.** `STATUS.md` and `DECISIONS.md` narrate how things got that way and **describe past states as well as present ones** — they are not to be read as an inventory. **Do not copy configuration facts back into this file.** One place, or it drifts again.

## Ledger

**In use since 2026-07-24** (Phase C). Supabase, captured via `stock-control/index.html`, hosted on the HA Pi at `/config/www/mushroom-control.html` → `http://homeassistant.local:8123/local/mushroom-control.html`, with a home-screen icon added via **Samsung Internet** (Chrome won't offer it for plain-HTTP LAN pages). Updating it = copy the repo's `index.html` over that file.

**Current data:** batches `SUB-2026-W23` and `SUB-2026-W25`–`W30`, reconciled against a physical bag count on 2026-07-26. Raw stock 2,366 g.

- **The packing date is recorded (`packed_at`) and the batch ID is derived from it**, enforced in the database against the ISO week. The panel asks for the packing date, shows the derived ID and the weekday live (batches are packed Tuesdays), warns on back-captures over 10 days old and on future dates. The free-text ID field is gone.
- **⚠️ Hard limit: one batch per ISO week.** The ID *is* the week, in both panel and database. Lifting it needs a suffix scheme both would have to learn.
- **Pickings before 2026-07-22 are not recoverable** — there was no scale. **Do not back-fill them**; `SAFETY.md` says measured values only, and partial data also breaks gap-based flush inference.
- **The 9 Jun batch is deliberately not in the ledger** (being physically discarded). Recording a batch purely to remove it would create a phantom zero-yield row dragging down every yield statistic. *The bags still need taking out — tracked on `todo.fungi4u`.*

### ✅ CAPTURE CORRECTIONS BUILT AND THE 4 AUG SESSION REPAIRED — and the blind spot behind it is closed

**Three pickings went in within 2m41s on 2026-08-04, and two of them were wrong.** W25 1010 g ✅, W26 2752 g ✅, then **the same W26 2752 g submitted again 2m22s later** — and the entry that was actually intended, **2324 g against W27, was never recorded at all.** The previous entry was resubmitted instead of a new one being captured, which produced a phantom *and* lost a real harvest.

- **⚠️ The fault was reported as "a W27 picking of 2752 that should have been 2324" — and that matched nothing in the database.** There has never been a 2752 g picking on W27. **The guard caught it, not the diagnosis:** migration `20260804150100` refused to act on a weight it could not identify uniquely and printed W27's real pickings instead, which is how the true fault surfaced. **A naive `update … where grams = 2752` would have hit the wrong batch, or both rows.**
- **✅ Repaired on production. Raw 22,686 → 22,258 g**, verified against `v_operational_snapshot` before and after.
- **The mechanism, now permanent** (`20260804150000`, `20260804160000`): a `PICKING_CORRECTION` reason code, an **append-only `picking_corrections` table** mirroring `bag_movements`, `fn_correct_picking` (give it the weight the picking *should* read; it derives the delta) and `fn_void_picking` for a capture that never happened.
  - **Corrections deliberately do NOT touch `harvest_pickings`.** Editing `grams` would erase the evidence an error was made, in an operation whose rule is measured-values-only; appending a negative *picking* row would corrupt gap-based flush inference. Voided rows are dropped **before** the gap arithmetic for the same reason.
  - **`v_substrate_biological_kpi` needed no change** — it sums `grams` from `v_harvest_pickings`, so corrections reach the yield KPI automatically.
  - Verified end to end on a local stack: guards fire, corrections compose, re-runs change nothing, and anon stays denied the base table.
- **⚠️ This is the third instance of the wrong-batch dropdown fault** (24 and 26 Jul were the first two). The hard guard added on 07-28 only blocks batches with *no fruiting bags* — W25, W26 and W27 are all pickable, so **it structurally cannot catch choosing the wrong *pickable* batch.**

#### 🔴 The blind spot was the root cause, and it was self-inflicted

**Operator, 2026-08-04: *"i find that it is a blind spot not to be able to see what was captured."*** Correct — and the reason is uncomfortable. **The 2026-07-28 anon-grant revoke correctly closed a leak that exposed every picking ever recorded, and in doing so it removed the panel's ability to show the operator their own work. Nothing replaced it.** The only remaining feedback is a client-side "recorded this session" log that does not survive a refresh. That is why today's error had to be described from memory, and was described wrongly.

- **✅ `v_recent_captures` built and live** (`20260804170000`) — the last 20 pickings with **captured vs effective weight** and a `VOIDED` / `CORRECTED` / `OK` status, so a repair is visible rather than silent. **A deliberate, bounded re-grant to anon, not a regression:** the leak was unbounded history readable *by accident*; this is a 20-row window granted *on purpose*, carrying no more than `v_operational_snapshot` already does. Verified that `v_harvest_pickings` and `picking_corrections` remain denied.
- **✅ PANEL CARD BUILT AND DEPLOYED 2026-08-04.** `index.html` gained a **"Recent captures"** card above the session list — the last 20 pickings as the database has them, **VOIDED struck through** and **CORRECTED showing the original weight**, so a repair is visible rather than silent. Refreshes on load and after every picking. Deployed to the Pi (previous version kept as `mushroom-control.html.bak-20260804-1457`; the live file was confirmed **byte-identical to repo HEAD** before overwriting, so no drift was lost). Serving HTTP 200.
  - **➕ It also flags likely duplicates** — same batch, same weight, inside 15 minutes, ignoring already-voided rows. **Replaying the pre-fix 4 Aug state confirms it flags both 2752 g W26 rows and leaves the 1010 g W25 alone**, so it would have caught today's fault at the moment it happened. **Soft warning, never a block**, per the panel's standing rule: two identical lots are genuinely possible, and a hard block on a guess is worse than the mistake.

### ✅ Processing capture corrected 2026-07-28 — weigh the off-cuts, derive the packed weight

Raised by the operator **before the first processing session was ever run**, so this is a correction rather than a repair. Migration `stock-control/supabase/migrations/20260728220000_processing_capture_waste_not_packed.sql`, applied to production; panel deployed.

- **The panel asked for a packed weight nobody measures.** Punnets are filled by eye to a bit over 250 g and counted, so the only way to fill the field was **units × 250 — an assumption wearing the costume of a measurement.** It would have corrupted three stored columns at once: `average_pack_weight` becomes exactly 250.0 every time (a tautology, in the one column whose job is to reveal overfill), `waste_weight` absorbs all the overfill, and `processing_yield` is understated by the same amount.
- **Now the measurement and the derivation swap places.** Off-cuts are **weighed**; `packed = raw − off-cuts`. Every stored number is measured or derived from measured values, per `SAFETY.md`.
- **The size of the error, measured on a local replica** (8.00 kg raw, 800 g off-cuts, 27 punnets):

  | | Corrected | What units × 250 would have stored |
  |---|---:|---:|
  | Waste | 800 g | **1,250 g — 56% too high** |
  | Packed | 7,200 g | 6,750 g |
  | Processing yield | 0.900 | 0.844 |
  | Avg per punnet | **266.7 g** | 250.0 g *(by construction)* |

- **`average_pack_weight` is now a real number, and it is worth watching.** At 266.7 g into a 250 g punnet that is **~6.7% given away** — on a 27-punnet session, roughly 450 g, about 1.8 punnets. Invisible until now, and controllable once seen.
- **⚠️ What the derivation assumes:** `packed = raw − waste` holds only if nothing *else* vanished between picking and packing. Raw is weighed at picking and cold-stored for days, so **any shrinkage is silently absorbed into packed weight — the direction that flatters.** The detector is `average_pack_weight` itself: if it reads far above what is actually being packed by eye, the excess is shrinkage hiding in the packed figure, not generosity.
- **The parameter was renamed to `p_waste_weight` deliberately**, so a stale panel fails loudly (`PGRST202`) rather than silently reading a packed weight as waste — plausible-looking and badly wrong. Verified: the old call signature no longer resolves on production.

### ✅ CLOSED 2026-07-28 — the ledger now models bag movement, and the backfill is in

**Bag state as recorded (this is now a query, not a walk to the room):**

| Batch | Packed | Packed bags | Culled | Grow | Fruiting | Productive |
|---|---|---:|---:|---:|---:|---:|
| W25 | 18 Jun | 22 | 1 | 0 | **21** | 21 |
| W26 | 23 Jun | 27 | 1 | 25 | **1** | 26 |
| W27 | 30 Jun | 23 | 0 | 0 | **23** | 23 |
| W28 | 7 Jul | 29 | 0 | 29 | 0 | 29 |
| W29 | 14 Jul | 24 | 0 | 24 | 0 | 24 |
| W30 | 21 Jul | 28 | 3 | 25 | 0 | 25 |
| *(W23, 2 Jun)* | | 9 | 0 | — | — | — | *removed spent 07-28* |
| **Live total** | | | **5** | **103** | **45** | **148** |

- **✅ It reconciles independently against the 2026-07-26 physical count on all three batches that had one** — W25 21, W26 25 grow + 1 fruiting, W30 25. The count and the ledger were built from different sources and agree exactly.
- **First spawn-run figures the business has ever had: 21, 26 and 30 days** packed→first move (W27, W25, W26). Every future move adds one for free.
- **⚠️ W26 is lagging and it may be worth a look.** Packed 23 Jun, and 25 of its 26 bags were still in the grow room at 35 days, while W27 — packed a *week later* — moved across in full on 21 Jul. The single bag moved 23 Jul. That may be deliberate (one bag pulled early because it was pinning; a 30 Jul move was previously mooted), but if W26 is genuinely slow that is 25 bags of committable supply running late, right as the Spar trial tests demand.
- **⚠️ W30's contamination is the outlier twice over: highest rate AND earliest onset.** 3 bags at **10.7%** against 3.7–4.5% on W25/W26 and **0% on W28 and W29** — so it is a spike, not a trend. Timing is the part worth acting on: **W30 lost 3 bags just 3 days after packing**, against 5 days (W25) and 15 days (W26) for one bag each. Contamination that early and that clustered points at **sterilising, spawn, or inoculation hygiene** rather than later ingress. **W31 is the test** — if it repeats, something in that process moved and it is worth money to find.
- **Two artefacts, both known and harmless.** W23 shows 9 bags in the grow room while flagged removed — `fn_remove_batch` posts no SPENT movement (follow-up 3), and W23 predates this table so there is no honest history to record. The room views filter on `removed_at`, so nothing downstream sees it.
- **✅ `v_current_biomass` FIXED 2026-07-28** — `stock-control/supabase/migrations/20260728160000_biomass_fruiting_room_only.sql`. It had summed every non-removed batch regardless of room, reporting **153 bags** as fruiting-room biomass when **45** were there — a **3.4× overstatement** in the one view whose only job is respiration context for CO2. *(153 not 148: `number_of_bags` is fixed at packing, so it counted the five culled bags too — wrong on both axes, where the bags are and whether they still exist.)* Now reports **45 fruiting / 103 grow**, with grow-room figures added rather than hidden. Substrate grams are apportioned per bag from packing weight, so treat them as a **proxy for respiring biomass, not a mass** — it assumes equal bags and ignores water loss.
- **✅ `fn_record_picking` GUARD ADDED 2026-07-28** — `stock-control/supabase/migrations/20260728180000_picking_requires_fruiting_bags.sql`. **This is the fix for a failure that already happened:** on 07-24/26 four pickings were logged against batches still in the grow room, because the dropdown is newest-first and one position too far down was selected, twice. Mis-attributed pickings corrupt yield per batch *silently* — the number meant to prove committable supply.
  - **Two layers:** `v_pickable_batches` stops the dropdown offering impossible choices (currently W25, W26, W27), and the RPC refuses them whatever calls it.
  - **⚠️ It is a HARD block, departing from the panel's soft-guard rule, and that is deliberate.** The failure modes are not symmetric: a mis-attributed picking corrupts data silently and is near-impossible to find later; a blocked picking fails loudly with a message naming the remedy. **It only became safe once the backfill was in and the panel had a Move-to-Fruiting card** — a hard guard is acceptable only when the fix is reachable by whoever hits it. The same change on 07-26 would have stopped capture entirely.
  - **Known trade-off:** bags marked SPENT before a late picking is captured will block that picking. Capture pickings *before* marking bags spent.
  - `v_open_substrate_batches` is deliberately **not** tightened — Remove Batch still uses it, so a batch with no recorded movements (as W23 had) stays removable.
- **✅ `fn_remove_batch` NOW CLOSES OUT BAGS 2026-07-28** — `stock-control/supabase/migrations/20260728200000_remove_batch_posts_spent.sql`. **All three follow-ups are now done; the bag-movement work is complete.** Removal posts SPENT rows for whatever bags remain, per room, so removal and bag state cannot disagree. W23 backfilled at its own recorded removal date and now reads 0/0.
  - **SPENT may now leave either room** (the constraint allowed fruiting only). A batch can be written off with bags still recorded in the grow room — genuinely abandoned during spawn run, or, as with W23, because its moves predate the table. **SPENT stays distinct from CULLED**, so contamination rate and `bags_productive` are untouched: a write-off is not evidence of contamination.
  - **⚠️ Relaxing that constraint exposed a real bug, caught in local testing before it reached production.** `v_batch_bag_state` subtracted the *entire* spent total from the fruiting room — correct only while SPENT could not come from anywhere else. Removing a batch with bags in both rooms drove the fruiting count **negative** (20 fruiting/2 grow → −2 fruiting/2 grow). Spent is now split by room exactly as culls already were. **The lesson generalises: loosening a constraint changes what the derived views must handle — check every consumer of the thing you relaxed.**
  - The panel now states the consequence before removal (how many bags in which room become spent) and flags grow-room bags, which usually mean a move was never captured.

**The gap this closed, kept for the reasoning:**

- **Batches split across rooms.** 23 Jun has 25 bags growing + 1 fruiting. A batch is not in one place.
- **Bags get culled for contamination. ✅ Operator-confirmed 2026-07-28**, and it matches the 26 Jul physical count exactly — two independent sources agreeing, so treat these as measured:

  | Batch | Packed | Ledger bags | Culled | **Actual** | Cull rate |
  |---|---|---:|---:|---:|---:|
  | SUB-2026-W25 | 18 Jun | 22 | 1 | **21** | 4.5% |
  | SUB-2026-W26 | 23 Jun | 27 | 1 | **26** | 3.7% |
  | SUB-2026-W30 | 21 Jul | 28 | 3 | **25** | 10.7% |
  | *(W23, W27, W28, W29)* | | 85 | 0 | 85 | 0% |
  | **Total** | | **162** | **5** | **157** | **3.1%** |

  **⚠️ W30 is the outlier and it is the NEWEST batch — 3 bags at 7 days old, against 1 apiece on batches four to six weeks older.** Contamination shows up early, so this is not W30 catching up; it is a worse batch. **One batch is not a trend** — but it is the first cull-rate signal the business has ever been able to see, and if W31 does the same, something changed in the substrate or sterilising process and it is worth money to find. **The ledger cannot store any of this**, which is the point of this section. *(Cull dates were not recorded and are not recoverable — capture them going forward.)*
- **Consequences:** yield per bag is wrong (the denominator counts culled bags — W30 is understated by exactly the 10.7% above, and that is the number meant to prove committable supply to Spar); contamination rate is invisible; biomass for CO2 interpretation is overstated.
- **✅ FIX BUILT, VERIFIED AND APPLIED TO PRODUCTION 2026-07-28 — `stock-control/supabase/migrations/20260728120000_bag_movements.sql`.** Append-only `bag_movements` table (TO_FRUITING / CULLED / SPENT), **per bag count, not per batch**, with `v_batch_bag_state`, `v_fruiting_room_bags` and `v_batch_contamination` deriving counts, and three narrow RPCs that refuse any movement driving a room negative. Separate table per `SAFETY.md`; mirrors the `stock_ledger` append-only trigger pattern without sharing its logic. Verified end-to-end on a local stack: arithmetic, every guard, immutability, and the anon surface (views readable, base table denied, RPCs enforcing through REST).
  - **It is deliberately INERT — it changes no existing view, table or function**, so applying it breaks nothing and nothing improves until movements are recorded. **That is the lesson from the falsified draft**, which tightened the picking dropdown and `fn_record_picking` on day one and would have stopped data capture entirely until backfilled.
  - **⚠️ The backfill is the blocker, and it needs facts nobody has yet:** the cull *dates* (never recorded, not recoverable) and *which room* each cull happened in, plus the current grow/fruiting split per batch. Cull **counts** are known (W25 1, W26 1, W30 3). Until then every batch reports as wholly grow-room — honest about the data, wrong about the world. Template is at the bottom of the migration, commented out.
  - **✅ Panel cards live 2026-07-28 — "Move Bags to Fruiting" and "Cull Contaminated Bags"**, deployed to the Pi (previous version kept as `mushroom-control.html.bak-20260728`). Both were added, not just the cull: **a cull from the fruiting room cannot be recorded until a move exists**, because every batch reads as wholly grow-room until then. Each card shows a live "N in grow · N in fruiting · N culled so far" hint, catches an impossible count client-side, and **asks for the date the thing physically happened** rather than defaulting to now — the five existing culls are unrecoverable precisely because nobody wrote the date down.
  - **Follow-ups still deferred to after the backfill** (listed in the migration): point `v_current_biomass` at real fruiting-room bags; guard `fn_record_picking`; have `fn_remove_batch` post a SPENT movement.
- **⛔ The draft at `stock-control/supabase/drafts/20260726150000_batch_location_fruiting.sql` assumes whole-batch moves and is FALSIFIED by the split-batch finding. Do not apply it** — it is superseded by the migration above. *(Its backfill note also names batch IDs from before the 07-26 week renumbering; do not lift dates or IDs out of it.)*
### Anon grant leak — ✅ FIXED AND APPLIED 2026-07-28

Found while testing the bag-movement migration. **`stock-control/supabase/migrations/20260728140000_revoke_default_anon_grants.sql`** — verified on a local stack, then applied to production and re-verified against the live database: the four objects now return "permission denied", the panel's read views and RPCs still work, and the trigger functions are no longer reachable.

- **What leaked.** The Phase B security migration closed the anon surface by revoking **explicitly, by name**, from the seven tables that existed then. A `revoke` is a point-in-time statement, not a standing rule, and Supabase's default privileges grant anon full rights on every new relation. So **everything created in a later migration silently inherited them.** Confirmed readable on production with the publishable key: **`v_harvest_pickings` (every picking — batch, grams, timestamp, flush), `v_current_biomass`, `v_substrate_biological_kpi`.**
- **⚠️ An earlier note here said "not currently exploitable, RLS default-denies". That was true of the *table* and wrong about the *views*, which is where the data is.** `harvest_pickings` the table did hold — RLS enabled, no policies. But these views are **owner-run** (`alter view … owner to postgres`), which the Phase B migration itself documents as being *"so it can read the RLS-protected base table"* — that is how `v_operational_snapshot` works for anon at all. **An owner-run view bypasses RLS by design, so for a view the grant is the only gate and RLS was never a backstop.**
- **Severity: low, read-only, and it is the operation's own data** — picking weights, bag counts, yield KPIs. Not credentials, money, or personal data. Writes stayed blocked. Reach is anyone holding the publishable key, which is public by design (it sits in `index.html`, served unauthenticated over plain HTTP on the LAN). **It is not in the public `fungi4u-governance` repo — checked. No key rotation is needed or useful; the grants are the fix.** A revoke closes the door going forward and does not undo any read that already happened.
- **The real bug is the default privileges, not the four objects** — otherwise this recurs every time the schema grows, and it already did once. The migration revokes them for role `postgres` (the role migrations run as). Proven: a table and a view created afterwards came out with no anon grants. The `supabase_admin` equivalent is wrapped in an exception handler — `postgres` cannot alter another role's defaults even locally, and unwrapped it would abort the migration.
- **⛔ Functions cannot be fixed this way, and this was tested rather than assumed.** `alter default privileges … revoke execute on functions from public` is accepted and recorded, **and new functions still come out with PUBLIC EXECUTE anyway** (reproduced twice). So for functions the control is a **convention**: every new internal function must be revoked explicitly *from PUBLIC*, not just anon. The migration carries a one-line audit query for it. **Audited 2026-07-28 — the current state is correct**: the nine panel wrappers are callable, `fn_post_stock_event` is not.
- **`keep_alive()` is deliberately left callable** — not in the panel, not SECURITY DEFINER, so it looks like an external pinger holding the project open. A paused project is worse than a harmless callable no-op. Find out what calls it before touching it.

## Not built / not installed

- **GSM cellular alarm** — battery-backed 4G dialler on the controller's breaker, thresholds moved local into the ESP32. **The single biggest risk-reducer:** the room has *no* monitoring at all when its power or internet fails, which is exactly when it has failed. Must be 4G/LTE — SA completes 2G/3G shutdown by end-2027. Candidate: Interlynx S150; confirm the 4G module, the MTN/Vodacom bands, **and a SIM plan that can't lapse for inactivity** before ordering — **the actual blocked step is getting a price from Interlynx, which has never been requested.** ⛔ SIM800/SIM800L are 2G-only and are ruled out (2026-07-27). The HA phone push (`fruiting_room_alarm.yaml`) stays a best-effort extra only.
- **Variac tuning — ⛔ DROPPED 2026-07-27, not deferred. Do not restart it without new evidence.** *(⚠️ Clarified 2026-07-29: "the existing variac" means one is **owned**, not that it is **fitted** — it still has to be wired in.)* The plan was to dial the variac down to the lowest fresh-air fan speed that still held CO2. Three independent findings killed the savings case (reasoning in `DECISIONS.md`): (1) **no CO2 headroom** — the room runs at ~765 ppm true against an 800 target, ~35 ppm of slack, so it is not over-ventilating; (2) **no thermal driving force** — the fresh air comes from the *grow room*, measured over 72h at mean 17.97 °C against the fruiting room's 17.26 °C, a mean ΔT of just **+0.71 °C**, and *colder* for 20 of those 72 hours — order-25 W of sensible load against a room averaging ~417 W; (3) **the binding constraint is positive pressure, not CO2** — turning the fan off crashed the bottom shelf within hours (07-25), so the speed floor is set by pressure and may already bind. **Best case ~R20–60/mo against a real risk of re-crashing the bottom shelf.** *(The fridge gutting was cited here as a ~15× larger alternative — note it is avoided cost on an R8,000 purchase not yet made, not a saving available today. The comparison still holds directionally, but neither is money on the table right now.)* **Reopen only if CO2 is ever measured genuinely low with the fan at its pressure floor.**
- **🌀 FRESH-AIR FAN — nothing to buy: the variac is ON HAND, but ⚠️ NOT YET FITTED (clarified 2026-07-29).** An earlier version of this entry said it was already installed and the change was "a knob, not a purchase". **Half right: it is not a purchase — the variac is owned — but it is not a knob either, because it still has to be wired in.** So the cash cost stands at **R0**; what is outstanding is an **installation job**, not money. The 12V DC fans stay decided-against. **Until it is fitted the fresh-air fan has no continuous control and no software control at all** — both HA fan entities are phantoms, named in HA itself *"drives nothing — off-controller"* — so speed today is a **physical 2-speed switch**. **See the vent-seal experiment below: switching to high is free and immediate, and it tells you which way the optimum lies before you fit anything.** Two decisions had become entangled in one unflashed firmware draft, and separating them dissolves the *DC-fan* purchase (reasoning in `DECISIONS.md`). ⛔ **The operator declines to give the CO2 sensor authority over this fan** — and the evidence backs it: both CO2 sensors currently under-read by ~350 ppm *and agree with each other*, so the drift detector is blind. Flashing the proportional firmware today would **pin the fan at `fresh_min`** while the room sits above target, with a `co2_high` alarm needing a true ~1846 ppm to fire — bad sensor, actuator authority, unarmed alarm. **Once closed-loop control is off the table, the only requirement left is "settable to an arbitrary fixed speed" — which a variac on the installed inline fan satisfies.** Electronic modulation was only ever needed so the *controller* could vary it. ➡️ **This restores the position already recorded below under "Decided against": the 12V DC fans (ebm-papst 4312/2, REF100-11/12) were rejected because they cost more and mounted worse than reusing the installed fan on a variac.** The firmware draft had drifted back to the rejected part; `MICROCLIMATE.md`'s "the proper part is a 12V brushless or EC fan" is superseded by that entry and is now amended. **Action: fit the variac, set the operating point, leave it — but see the experiment below first, which may show the fan's existing high position is enough.** ⚠️ The uncommitted draft in `stock-control/esphome/fruiting-room-controller.yaml` (+71/−40) is written for **decided-against hardware** and a **declined control law** — obsolete, not merely premature. **Do not flash it.**
  - **⚠️ Consequence to re-home: the RPM/tacho blindness fix has lost its host.** `DECISIONS.md` (2026-07-17) parked it as *"fold it into the Fan 2 rework, since that position is being redesigned anyway."* **There is now no Fan 2 rework.** The blindness is real and has bitten once — a fan died while HA cheerfully displayed "82%" commanded PWM, RH fell ~90%→~80%, the humidifier pinned, and the alarm fired ~20 h later pointing at humidity, a *symptom*. **Cheapest fix that needs no new fan and no firmware: a power-monitoring smart plug upstream of the variac** — real run-confirmation from actual watts, exactly the trick already proposed for the humidifier in `stock-control/docs/MICROCLIMATE.md`. **Do not let this quietly lapse just because the rework it was attached to is cancelled.**
  - **Two things to watch on the variac, neither blocking:** (1) a mains induction motor held at low voltage loses torque *and* self-cooling, so a very low continuous setting can run the motor hot — a variac's clean sine output is far kinder than a triac speed controller, but on a 24/7 duty it is worth a hand on the casing occasionally; (2) confirm the variac itself is enclosed and rated for continuous unattended duty.
- **Supabase environmental telemetry** — sensors go to HA only. Load-bearing for *proving* consistency to Spar, but a build.
- **Door sensor (TB10) and IR transmitter (TB11)** — wiring and terminals exist, devices not mounted.
- **Grow-room supply duct** — the plenum feeds two ceiling ducts, only the fruiting-room side exists. Also confirm whether the new fan actually re-ventilates the grow room.
- **Solar monitoring** — fully scoped in `stock-control/docs/SOLAR.md` (Sunsynk SG01LP1 5kW, Waveshare RS485-TO-ETH → kellerza add-on → MQTT → HA, ~R750–1,100). **Deferred on cost, not bought.** Water remains intent-only.
- **⚠️ WATER SUPPLY IS A HANDOVER DEPENDENCY, and it is unmetered (logged 2026-07-29).** The fruiting room's water — humidifier reservoir, substrate hydration, cleaning — does **not** come from the municipality. The property runs on a **private borehole owned by the property owner, not by the business**: the Tshwane bill read 2026-07-16 shows every consumption line at R0.00, with the municipal connection retained only as an emergency backup. **The fruiting room is plumbed off the property's pressure pump** (confirmed 2026-07-29), so it is a **continuous draw**, not hand-filled — the float valve on the humidifier reservoir in `stock-control/docs/MICROCLIMATE.md` is fed from the house supply. Supply chain: borehole → 1000 L roof tank (filled **manually, once a day**, 18 min) → variable-speed pressure pump → fruiting room. Three consequences a successor must be told: (1) **the business does not own or control its water source**, and any future arrangement is a matter between the operator and the property owner; (2) **water consumption is entirely unmeasured** — there is no flow meter anywhere, so the true cost of a flush is unknown and the ~R2,000/mo surplus in `stock-control/finance/CASHFLOW.md` is stated before both electricity *and* water; (3) **⚠️ a single manual daily action stands between this business and no water** — if the tank is not filled, the humidifier reservoir stops refilling. Nothing alarms on it. **No borehole, plumbing or property detail belongs in this repo** — that is the owner's private admin. Only the dependency and its cost consequence are business facts.
- **🌡️ GRAIN-SPAWN WARM INCUBATOR — built 2026-08-10. The cheapest available probe of the colonisation-temperature hypothesis, and the first record in these files of any part of the grain-spawn stage.**

  **The build, as it actually stands (operator, 2026-08-10):** a **polystyrene tub with a matching polystyrene lid**; a **10 mm foam plastic mat with a hole per bottle** suspending **11 bottles** so they **do not touch the tub floor**, submerged to the neck; **~28 L** of water to that level; a **Dophin AH-1008-4, 150 W** aquarium heater. **No pump. ✅ THE CONTROLLER NOW EXISTS AND IS FLASHED — 2026-08-14, and it is NOT the Inkbird this entry planned to buy. See "The controller, as built" below.**

  - **Why it matters beyond the tub.** This file records colonisation as the **long pole — 21–30 days, mean 26, more than half a batch's life** — and the 08-08 finding that 24–27 °C is *"beyond what this equipment delivers in this space at all"*, which put a separately heated colonisation space back as the only route. **A tub and an aquarium heater test the temperature-limited hypothesis for a fraction of a building.**
  - **⚠️ But it tests the GRAIN SPAWN stage, not the bulk-substrate residence the 21–30 day figure measures.** Both are colonisation; different vessels, different rooms, different timescales. **A good result here does not by itself justify the new grow room** — it makes the hypothesis more credible, which is not the same thing.

  **📐 SIZING — the heater is 12–19× oversized, and that is the headline.** *(Estimated from an assumed ~45 × 32 × 20 cm water body in ~25 mm polystyrene — **assumption, not measurement**; re-derive if the tub differs.)*
  - Holding **24 °C in a 16 °C room costs ~8–12 W** with the mat and lid on. Heat-up from cold ~2 h. **The heater will run at ~5% duty — roughly 3 minutes per hour.**
  - **Heater spec, confirmed:** 300 mm long, **±2 °C accuracy**, fully submersible, **water-line mark on the tube the level must never drop below**. ~R308 SA retail. Brand Dophin, manufacturer **KW Zone** (Penang); the series suffix encodes wattage (AH-1008-6 is the 300 W). **300 mm against a ~200 mm deep tub is why it cannot stand upright** — the suspended-bottle mat leaves the floor clear, so **it lies flat with full clearance and nothing contacts the element.**
  - **⬜ Horizontal mounting is NOT confirmed.** KW Zone publish no spec table and no retailer listing states orientation — **the packaging leaflet is the authority.** General mechanism, context only: the bimetal strip shares an air-filled tube with the element, so lying it flat alters their coupling — typically a **calibration shift (reads high, undershoots), not a safety failure.** **The external controller below makes this moot**, since the heater's own dial becomes a backstop rather than the regulator.

  **📐 SPAWN RATIO — recorded for the first time (operator): ONE BOTTLE INOCULATES TWO BAGS.** A batch is ~24 bags, so **a batch is exactly 12 bottles.**
  - **🎯 Which makes the tub one bottle short of a batch — 11 bottles = 22 bags = 92%.** ➡️ **Size it to 12.** 12 is the natural unit: **one tub = one batch**, and every downstream figure stays whole. At 11 the rig is **two bags short on every run, permanently.**
  - **⚠️ ONE TUB IS NOT A PRODUCTION INCUBATOR AT THE CURRENT CADENCE — do not let it be mistaken for one.** At 12 bottles/week and a colonisation time of **N weeks**, steady state needs **12 × N bottles in flight**, i.e. **roughly N tubs.** **As built this is an EXPERIMENTAL unit**, and should be treated as one until N is measured.

  **🔴 THE DOMINANT RISK IS A STUCK-ON HEATER, NOT A COLD TUB — and the oversizing is what makes it fast.** Aquarium thermostats fail **closed**. At 150 W into 28 L the tub goes **24 °C → 30 °C in ~75 minutes** — where bacteria and Trichoderma take the jars — and an insulated, lidded tub has **no safe equilibrium above that.**
  - **Risk sized: a stuck-on heater destroys ONE BATCH'S WORTH OF SPAWN.** The substrate is minor (~R170 of straw); **the real cost is a missed production slot, surfacing as a hole in supply a growing cycle later** — the **same failure shape already recorded for the straw chopper** — and with 3 customers on standing weekly supply that is a **service failure, not merely lost revenue.**
  - **✅ THE FIX IS TWO THERMOSTATS IN SERIES, NOT A SMALLER HEATER.** A **plug-in thermostat controller** (Inkbird **ITC-306** heat-only, or **ITC-308** dual-stage — ~R400–600, rated 2200 W at 220 V) sits between wall socket and heater: **probe in the tub, set 24 °C**; the **heater's own dial set to ~28 °C** as a backstop. **Two independent failures are then required to lose the run.**

    **✅ THE CONTROLLER, AS BUILT (2026-08-14) — THE PRINCIPLE STANDS, THE PURCHASE DOES NOT. IT IS AN ESP32 THE BUSINESS ALREADY OWNS, AND THE INKBIRD IS NOT BEING BOUGHT: ~R400–600 SAVED.**
    - **The device predates this entry** — built **2026-02-05** for exactly this job, then shelved when the fruiting room took priority, and forgotten until **2026-08-14**. It is `grain-spawn-temp`, an **esp32dev** with a **DS18B20 on GPIO14** and a **relay on GPIO23**. Config now lives in git at **`stock-control/esphome/grain-spawn-temp.yaml`** *(it was on a loose path in `~/grain_spawn/`, in neither repo nor the HA Pi — which is why the first look concluded it had no source at all)*.
    - **The two layers this entry requires are intact:** the **ESP32 holds 24 °C** (23.75 on / 24.25 off, the 0.5 °C hysteresis specified above) with a **hard cutout and latching lockout at 26 °C** — the high alarm this entry already set — and the **heater's own dial at 28 °C** is the second, independent layer. ⛔ **The dial goes to 28, NOT maximum**; that setting is the whole backstop.
    - **⛔ THE CONTROL LOOP RUNS ON THE DEVICE, NOT IN HOME ASSISTANT** (`SAFETY.md`: device-level logic is authoritative for physical safety). HA displays and logs; the bath holds temperature with HA, the network, or the Pi down. **Do not "improve" this into an HA automation.**
    - **🎯 AND IT ADDS A LAYER THE INKBIRD CANNOT: a dry-fire / no-progress watchdog.** 30 minutes of continuous heating with under 0.5 °C gain opens the relay and latches. **That covers the worst failure walked above — "probe falls out of the water → reads room air ~16 °C → the controller heats continuously"** — because a probe reading cold while the bath fails to warm is itself the signal. Same catch for a tub run dry, which this entry flags as **an ignition risk in a straw-dust building**.
    - **It also fixed a real defect in the original firmware:** the old loop compared temperature against `NAN`, and **every** NaN comparison is false — so a probe that died mid-cycle could be turned neither on nor off, and **left the heater energised indefinitely.** Probe loss now forces the relay open.
    - **Master enable switch, defaulting OFF**, because the tub sits empty between batches and an energised heater in an empty tub is the failure that starts a fire. It *is* remembered across reboots, so a power cut mid-run resumes heating unattended — which is what the thermal-mass upside above assumes.
    - **✅ THE RELAY IS CONFIRMED AND THE SAVING IS REAL (photographed 2026-08-14): a `SRD-05VDC-SL-C` Songle module, marked `10A 250VAC / 10A 30VDC`, CQC-marked.** The heater is **150 W at 230 V = 0.65 A**, so the contacts carry **~15× the load** — and at ~5% duty the switching is a few minutes an hour, not a cycling load. **This was the one hinge under the R400–600 saving, and it holds.** Build is mains-fed via an AC-DC module in a gasketed plastic enclosure, earth wire present, ESP32 dev board and relay on the same plate.
    - **✅ WIRED TO `NO` (NORMALLY OPEN) — operator-confirmed 2026-08-14.** This is the assumption the whole safety design rests on: **an ESP32 that is unpowered, crashed or mid-reflash leaves the heater OFF.** `restore_mode: ALWAYS_OFF`, the default-off enable switch, the 26 °C cutout and the dry-fire watchdog all reduce to "open the relay", so **on `NC` every one of them would have inverted** and a dead controller would have become the stuck-on heater this entry calls the dominant risk. **⛔ If this relay or its wiring is ever replaced, re-confirm the contact before energising anything.**
    - **🔴 NOT YET PROVEN IN PLACE — THE WIFI LINK IS THE OPEN RISK.** It reported **−83 dBm on first contact and −85 dBm after flashing**, and before it was moved it was **flapping: up ~40 s, down ~20 s**, rebooting on its 5-minute timeout. **A controller that cannot be seen is not the risk — the loop runs locally regardless — but a controller that cannot be WATCHED gives up the logging that is the entire point of choosing it over the Inkbird.** Measure RSSI at the cupboard before trusting it with a run.
    - **The three failure modes, walked:** (1) **heater thermostat welds closed** → it becomes a dumb element, **controller still cuts at 24 °C**; (2) **controller relay welds closed** → **the heater's own dial regulates at 28 °C** — too warm, but not the 40 °C+ runaway; (3) **⚠️ probe falls out of the water** → it reads room air ~16 °C, the controller heats continuously, and **the heater's 28 °C setting is the ONLY protection left. This is why the heater dial is set to 28 and NOT to maximum, and why the probe must be clipped or taped so it cannot float free.**
    - **Probe placement: mid-depth, opposite end from the heater** — it must read what the bottles sit in, not the element's plume.
    - **Settings: hysteresis ~0.5 °C** (≈ **90 min off / 6 min on** at 8–12 W loss against a 150 W heater — a slow cycle, no meaningful relay wear); **high alarm at 26 °C**; **calibrate the probe** against a trusted thermometer at setup.
    - **✏️ CORRECTED: an earlier version of this line claimed ±0.3 °C. The published figure is ±2 °F ≈ ±1.1 °C** — better than the heater's ±2 °C but not by the margin claimed. **The precision case was overstated; the safety case is unaffected and was always the main one.** The real advantages are that the **probe sits in the tub rather than beside the element**, **hysteresis is adjustable in 0.1 °C steps**, it is **calibratable**, it **alarms**, and it is an **independent second layer**.
    - **⛔ Bare STC-1000 modules (~R150–250) need wiring into an enclosure yourself. Pay the extra for a pre-wired unit** — a successor can simply replace it, the same handover-readiness reasoning `DECISIONS.md` used against the DIY alarm build.
  - **⚠️ Cost honesty: the controller costs MORE than the heater it protects (~R308)**, against a business near break-even. **Still the right buy** — it protects a whole batch.
  - **⚠️ Set the water to 24 °C, not 27.** Actively colonising grain generates metabolic heat, so **bottle cores sit above water temperature.** Let the bottles find their own level above the setpoint.

  **🌀 THE PUMP — DO NOT BUY IT YET. MEASURE FIRST.** *(This supersedes an earlier same-day note recommending a pump against hot-spotting. The suspended-bottle geometry dissolved that argument.)*
  - **The geometry is close to ideal for natural mixing:** heat source lying on the **floor**, free convection paths rising around suspended bottles, **nothing in contact with the element.** Stratification is a problem when a heater sits *high*.
  - ➡️ **Test: two thermometers, top and bottom, bottles loaded, overnight. Expect under 1 °C — in which case the pump is money saved.**

  **⚠️ Secondary risks and things to watch**
  - **Water level over a 3–4 week run.** The lid and mat make evaporation small, but **the level must stay above the heater's water-line mark** — a dry-fire is both a heater failure and an ignition risk in a straw-dust building. **Check it weekly.**
  - **⬜ Does the 10 mm foam mat SAG?** A grain-filled jar is net heavier than the water it displaces, so the mat carries real load. **Sag in the middle lowers the bottles, and far enough brings water to the closures.** Check a few days into the first run.
  - **Keep water clear of the closures.** A wet filter is a contamination highway. *(The lid-condensation path is **CLOSED** — the lid is polystyrene, so its inner face runs near headspace temperature and will not act as a cold condensing surface.)*
  - **Electrical:** mains in water in a straw-dust room needs an **earth-leakage protected circuit and drip loops** on every cord.
  - **Structural:** 28 L is **28 kg** plus bottles — polystyrene shears at the corners and needs continuous flat support.
  - **⛔ ARGUED AGAINST, and now moot: the two-vessel pumped loop.** Recorded because it was the operator's original plan for the depth problem, which the suspended mat solved instead. **The heater's thermostat regulates its own local water, not the tub** — so if the pump stops, the remote vessel reaches setpoint, the heater switches off, and **the tub cools with nothing indicating a fault.** That is the same silent-failure shape as the dead fan Home Assistant displayed at "82%" (`DECISIONS.md` 2026-07-17). It also doubles heat-loss surface. **Only revisit if the heater genuinely cannot lie flat — and then put the controller probe in the tub.**

  **✅ TWO FREE UPSIDES, WORTH BANKING**
  1. **The thermal mass rides out power cuts unaided** — lidded, the tub drops only ~3 °C in **8–10 hours**. No battery or alarm involvement needed for a normal outage.
  2. **The heater's indicator light is a free colonisation instrument.** 11 bottles of actively colonising grain plausibly generate the same order as the tub's 8–12 W loss, so **if the light stops cycling mid-run, that is the metabolic peak announcing itself.**

  **⛔ THERE IS NO COLONISATION BASELINE FOR GRAIN SPAWN** — confirmed by the operator: *"I do not have stats on how long the bottles currently take to colonise."* **This figure decides whether warm incubation scales to one tub, three tubs, or a heated cabinet, and it is what the entire experiment is scored against.** *(Same shape as the yield-baseline finding of 2026-08-01: the number does not exist rather than merely being unwritten.)*

  **🎯 BUT THE CONTROL CONDITION EXISTS AND IS ALREADY RUNNING — the bottles currently colonise IN THE GROW ROOM (operator, 2026-08-10). This upgrades the tub from a side experiment to the probe this file has been asking for since 08-05.**
  - **The grow room is recorded above at 15.1–17.8 °C against a 21 °C setpoint it has never reached**, with essentially zero air exchange. **So the bottles colonise at ~16–18 °C against a 24–27 °C optimum — in the same cold room as the 96 bulk bags.**
  - **➡️ The tub therefore has a real control: current practice.** Same spawn, same grain, same week, **one variable changed, with a 7–8 °C separation** — a large, clean signal if temperature is genuinely the limiter.
  - **➡️ AND IT IS EXACTLY THE TEST `THE NEW GROW ROOM` CALLS FOR:** *"colonisation here is temperature-limited rather than substrate- or spawn-limited… **Unmeasured.** This is cheap to probe **before building anything**."* **A ~R300 heater and a foam tub are that probe.**
  - **⚠️ It does NOT settle the bulk-substrate half** — bags do not fit in 28 L, and testing those needs a different, larger warm enclosure. **But markedly faster spawn at 24 °C is strong evidence that the room's temperature limits colonisation generally**, obtained for a fraction of a building.
  - **⚠️ RECORD CONTAMINATION COUNT FOR BOTH CONDITIONS, not just dates.** The move changes **location as well as temperature**, and the grow room is documented as stuffy with a contamination risk. **If the cull rate moves, the two changes are confounded unless both are counted.**

  **🗄️ THE OPERATOR PROPOSES TRACKING THE BOTTLES IN THE DATABASE. Right destination, wrong sequence — capture the first run on paper FIRST.**
  - **⛔ The reason is this repo's own recorded failure.** `stock-control/docs/LEDGER.md`: *"the workflow, not the schema, is what makes or breaks adoption (the system was built once and went unused)."* **The entire ledger was built correctly and then held zero production data for months.** Phase C capture only began **2026-07-24** — a three-week-old, still-fragile habit. **Adding a table before a single spawn run has been measured risks repeating exactly that.**
  - **➡️ The baseline needs TWO DATES, not a schema:** inoculation date and full-colonisation date, on a phone note. **Zero build, and the number exists in 2–4 weeks.** Build afterwards, once it is known whether **per-bottle** detail matters or a **per-run count** suffices — which cannot be known before running it once.
  - **➡️ When built, the CHEAP version is probably correct: two nullable columns on `substrate_batches`** — inoculation date and incubation method. One migration, no new table. **It works because 12 bottles = exactly one batch, so a run maps to a batch ~1:1.** Promote to a **`spawn_runs`** table (following the `harvest_pickings` precedent) only when that ceases to be true or per-bottle contamination becomes interesting. ⚠️ **Either way it goes through a committed git migration — never the dashboard or MCP** (`DECISIONS.md` 2026-07-11).
  - **🎯 The bit worth getting right either way is the LINK FORWARD.** Recording incubation *method* against the batch lets **`v_substrate_biological_kpi`** eventually answer ***"did warm-incubated spawn yield better"*, not merely *"did it colonise faster"*** — which is what feeds **KPI #0**, this file's gate on everything. **Colonisation speed alone adds no output today**, because the binding constraints are demand and fruiting-room residence, not spawn throughput.

  - **✏️ CORRECTED 2026-08-10 — the 28 L is TUB VOLUME to the fill line; the bottles displace part of it, so the WATER is ~18–20 L (operator). But an earlier note here warned this "shortens the runaway timeline by about a third", and THAT WAS WRONG — it counted only the water.** **The bottles that displaced it are thermal mass too:** ~19 L water ≈ 80 kJ/K, plus ~11 bottles of wet grain and glass ≈ 30 kJ/K, giving a **system total ~111 kJ/K against the ~117 assumed for 28 L of water — within ~5%.** ➡️ **The runaway timeline stands at roughly an hour**, not 50 minutes; coupling through the glass is not instant, so the *water* runs ahead of the bottles on a fast transient — call it **55–75 min** to 30 °C. **Steady-state loss and duty cycle are unaffected** (set by surface area and insulation, not volume). **Outage ride-through drops slightly, to ~6–8 h for a 3 °C fall.** *(Lesson: when a vessel is packed with product, the product is part of the thermal mass — do not compute the transient from the fluid alone.)*
  - **⚠️ Hinges on:** *that colonisation here is temperature-limited rather than spawn- or substrate-limited.* **Unmeasured**, exactly as recorded under `THE NEW GROW ROOM`. **Size of the move if wrong: a warm colonisation room buys nothing and the new grow room reverts to a pure capacity building.**
- **Liquid culture and grain spawn stages are otherwise undocumented anywhere.** Ask rather than assume. **The incubator entry above is the first record in these files of any part of the grain-spawn stage.**
- **🌾 THE STRAW CHOPPER IS UNDOCUMENTED, AND IT IS A SINGLE POINT OF FAILURE (logged 2026-07-29).** Straw is cut **every Monday** on a **converted lawnmower**, the day before Tuesday's batch. **Two bales → one 110 L drum → one batch** — which confirms the `stock-control/finance/CASHFLOW.md` assumption of 2 bales × R55 = R110/week; the ratio is now operator-confirmed, not inferred. Three gaps: **(1) the machine itself is recorded nowhere** — make, what was modified, how it is set up and operated. It is **bespoke**, so a successor cannot simply buy a replacement, and no off-the-shelf equivalent is identified. **(2) No backup and no spare.** If it fails on a Monday there is no batch on Tuesday, and the gap shows up as a hole in production roughly a growing cycle later — the same shape of risk as the manual daily water fill above. **(3) `SAFETY.md` says nothing about it** — modified machinery with a blade, plus straw dust, operated weekly. For a handover-ready business that is a required entry, not an optional one. **None of this is urgent while it keeps working; all of it is cheap to write down and expensive to reconstruct.**
- **Straw-chopper electricity — unmeasured, but bounded and almost certainly immaterial.** Not in `CASHFLOW.md`. It does not need a plug meter: **a typical electric mower motor is ~1–1.8 kW and this runs once a week**, so even a pessimistic full hour is **~7.8 kWh/mo ≈ R40** at the R5.12 marginal rate — against ~340 kWh/mo (~R1,740) for the fruiting room. **What would close it costs nothing: time the cut next Monday and read the motor's plate.** Spend the plug meter on `stock-control/docs/SOLAR.md`'s ranked list instead.

## Smaller open items

- **🧾 BUSINESS SLIP RETENTION — not built, and it is the business's own obligation (opened 2026-08-04).** The cable-tie purchase (R99.96, business card, Groenkloof Hardware) is the first paper slip this business has needed to keep. **SARS retention is five years and the duty sits on the business**, so this cannot be left to habit.
  - **⛔ The business does NOT use the household document store, and must not.** A Paperless-ngx instance exists on the workstation, but it is **personal infrastructure holding personal records**, and putting Fungi4u slips into it would both breach the repo separation and **break handover — a successor cannot be given an archive containing the operator's private data.** Same boundary already set for water: the infrastructure is personal, the business's own consumption and obligations are Fungi4u's. Detail stays on the personal board; only the dependency belongs here.
  - **➡️ Working copy: attach the slip to its transaction in Sage**, which `HANDBOOK.md` already names as the money of record and describes as under-utilised. **⚠️ Confirm attachments are free on the current plan before designing around it.** **⛔ Sage's AutoEntry add-on is credit-based pay-as-you-go — do not buy it** for roughly four slips a month; keying them is cheaper.
  - **⚠️ A Sage attachment is not a durable archive.** Cloud accounting attachments generally become unreachable if the subscription lapses — **the same silent-failure shape as the GS1 lapsed-fee trap in `DECISIONS.md`**, and the retention obligation would survive the subscription. So the business needs **its own copy, under its own control, backed up independently.**
  - **The backup is a shared METHOD, not a shared archive** — the same tooling and constraints as the household one, but a **separate archive with its own passphrase**, so the business's records can be handed over (or lost) without anyone else's. Marginal cost is the same script pointed at another path.
  - **⬜ Open until: attachment cost confirmed in Sage, a business archive path chosen, and the backup actually runs.** Until then every business slip is single-copy on paper or on a phone. **Photograph slips at the time** — a faded thermal slip is not a record.
- **Inkbird housekeeping** — it's live but on **no dashboard**; add an entities card. Delete the 3 dead orphans (`sensor.co2`, `sensor.inkbird_temp`, `sensor.inkbird_humid`) and the dead "Inkbird CO2" device, which is why the companion app shows "unavailable" — the working sensors have `device_id = null` and aren't on that page. Optionally add a shared `device:` block in `configuration.yaml` to group them.
- **Plug-meter sweep — ✅ business side COMPLETE 2026-07-28.** The chest freezer (the *business* cold-storage unit; the house freezer is the **stand-up** one — don't confuse them and double-count) read **0.784 kWh/24h**. See the cold-storage block above for what it settles. Read kWh over 24h, not instantaneous watts; set cost to R5.12/kWh.
  - **🔬 RUNNING: the STAND-UP freezer went on the meter 2026-07-28 13:50 — read it 2026-07-29 13:50.** This is a **HOUSE** load and belongs in the house column; the business total stays at ~10.8 kWh/day regardless of what it reads.
  - **The chest freezer's 0.784 kWh/day is now the yardstick.** Same job, business side, measured. If the stand-up comes in at 2–3× that for comparable capacity the gap is the finding, not the number — and it points at where the ~1.1 kW house base load actually sits. **Note the capacity of both** or the comparison stays qualitative.
  - **Then: house fridge, then heaters**, 24h each. ⚠️ **The geyser and any hard-wired heater cannot be plug-metered at all** — if winter heating dominates the base load, this method hits its limit and a clamp meter at the DB becomes the only route.
  - **⏳ Aircon deliberately NOT next, despite being the larger load.** (1) Metering it while the floor-vent experiment runs samples a room in a deliberately altered configuration — a transient, not a baseline. (2) It is likely hard-wired, so it needs a **clamp meter at the DB** that we do not have. (3) Its follow-up test (can the aircon work less?) is already barred from running concurrently with the vent experiment. **Revisit once the vents are resolved and the room has settled.**
  - **Worth one sanity check on the freezer reading**, since 32.7 W average is low for the form factor: watch the meter's instantaneous watts until the compressor cycles on, and confirm it shows ~80–120 W. If it never does, the meter isn't seeing the compressor and the 24h figure is wrong. Cheap to do, and everything above rests on this one number.
- **`weather.forecast_home` is not reporting Pretoria** (found 2026-07-27). It forecast lows of 15.9–21.3 °C and highs of 26.8–29.6 °C for the week of 27 July; Pretoria late-July norms are ~5 °C min / ~19.6 °C max, and a 29.6 °C July day would be near-record. The HA home location or the weather integration is misconfigured. **Cosmetic today — nothing depends on it — but do not use it as an outdoor reference** (it was nearly used as one when sizing the floor-vent infiltration question).
- **RS485 poll timing** — seen once at 341 ms against a 340 ms budget (two back-to-back 150 ms blocking delays in one tick). No functional failure yet; if it worsens, split the two sensor queries across alternating ticks.
- **Watch the WF-150 and fresh-air fan bearings** in the ~90% RH airstream. Better than the SEAFLO, not immortal.
- **Lower-shelf crop observation** — verdict due ~2026-07-29. Largely mooted now the bottom shelf matches the top.
- **Drain-grate seal** — likely unneeded now positive pressure fixed the bottom shelf. Revisit only if the gradient returns.
- **Partially closing the front-wall floor vents — WORTH DOING, as a measured experiment. Confirmed 2026-07-27 that they open directly OUTDOORS.** *(An earlier note the same day said "no energy value" on the assumption they were purely the fan's relief path. That was wrong for this geometry — corrected below.)*
  - **Two exchange mechanisms the fan does not control.** **Stack effect:** room 17.25 °C against Pretoria winter nights of ~3–8 °C is a 10–14 °C difference across a *floor-level* opening, driving dense cold air inward continuously — **15–20× the 0.71 °C driving force in the grow-room loop**, and why the 07-25 fan-off test crashed the bottom shelf within hours rather than drifting. **Wind:** a front wall means gusts can locally reverse flow through the aperture regardless of fan pressure.
  - **The humidity cost is the concrete one.** Room 13.4 g/m³ absolute; the grow-room air the fan supplies is ~12.2 g/m³ (17.7 °C / 81%), a deficit of only ~1.2 g/m³. Pretoria winter outdoor air is realistically 5–8 g/m³. **Air entering through the holes instead of through the fan costs the humidifier 4–7× more per m³.**
  - **⛔ Do not seal them all** — the fan needs a relief path. **The limiting constraint is that CO2 headroom is only ~35 ppm** (room ~765 true vs 800 target), so choking the relief path pushes CO2 over target fast.
  - **🎯 Prediction recorded in advance.** *Good case (cutting uncontrolled infiltration):* humidifier duty drops, bottom-shelf gradient stays flat, CO2 rises <50 ppm. *Too far (choking the relief path):* CO2 climbs >100 ppm and keeps climbing. **CO2 is the discriminator — temperature and humidity look better in BOTH cases, which is the trap.** Watch `sensor.humidifier_duty_24h`, `co2_shelf_delta` and displayed CO2 against ~450 (= 800 true), over 24h, not a spot check. The Inkbird returned to the bottom shelf 2026-07-27 ~12:00, so gradient monitoring is live.
  - **🔬 EXPERIMENT RUNNING — every second hole sealed with duct tape 2026-07-28 ~13:15.** On schedule against the plan (baseline 07-27 ~13:00 → seal 07-28 ~13:00 → read 07-29 ~13:00). **Read the 22:00–06:00 window, before vs after — not the 24h mean**, because stack effect scales with ΔT and peaks pre-dawn.
  - **📋 BASELINE, captured from the recorder before the seal — 22:00–06:00, 07-27→07-28, vents fully open:**

    | Metric | min | **mean** | max |
    |---|---:|---:|---:|
    | `humidifier_duty_1h` | 55.8 | **76.3** | 87.5 |
    | CO2 primary (displayed) | 459 | **485** | 519 |
    | RH (controller) | 87.4 | **90.5** | 92.1 |
    | Temp (controller) | 16.4 | **16.8** | 17.2 |
    | `co2_shelf_delta` | −42 | **−7** | 128 |
    | `temp_shelf_delta` | −0.2 | **+0.2** | +0.6 |

  - **✅ RESULT READ 2026-07-29 ~14:00 — the trade is real, and it lands in the ambiguous middle. Abort line held; do NOT seal any more holes.** Same 22:00–06:00 window, 07-28→07-29. *(The baseline above was re-read from the recorder and reproduced to the decimal — 76.3 / 484.9 / 90.5 / 16.8 / −7.1 / +0.2 — so the windows are comparable.)*

    | Metric | Baseline | **After** | Δ | Read |
    |---|---:|---:|---:|---|
    | `humidifier_duty_1h` | 76.3 | **66.5** | **−9.9** | ✅ the win |
    | CO2 primary (displayed) | 484.9 | **568.5** | **+83.5** | ⚠️ over the <50 good case, under the >100 abort case |
    | RH (controller) | 90.5 | **90.4** | −0.0 | ✅ **same RH for ~10 points less work** |
    | Temp (controller) | 16.8 | **17.3** | +0.5 | ✅ less cold infiltration |
    | `co2_shelf_delta` | −7.1 | **−42.9** | −35.7 | ⚠️ a gradient appeared where there was none |
    | `temp_shelf_delta` | +0.2 | **−0.3** | −0.5 | ⚠️ bottom shelf now slightly the cooler one |

  - **🔑 THE FINDING THAT MATTERS — the overnight CO2 *shape* inverted, which is the mechanism made visible.** Baseline: CO2 **peaked in the evening (~524 at 20:00) and fell all night** to ~455 by 07:00 — the stack effect was *flushing* the room hardest pre-dawn, exactly when ΔT is greatest. After sealing: CO2 **rose through the night (555 → ~575) and then plateaued** at 573–576 from 02:00 to 07:00. **The pre-dawn flush is gone.** That is the same mechanism as the humidity win, seen from the other side: the stack effect was simultaneously importing dry cold air *and* exporting CO2. Halving the aperture bought back the moisture and gave up the flush. **This is a genuine trade, not a free lunch.**
  - **Scored against the pre-registered prediction: neither branch cleanly.** Good case required duty down ✅, gradient flat ❌, and CO2 <50 ppm ❌ (+83.5). "Too far" required **>100 ppm *and* still climbing** — it reached +83.5 and **plateaued**, so that branch is not met either. **Abort line (displayed >600 sustained 3h) NOT breached:** the only excursion was 612 at 08:00 and 598 at 09:00 — two hours, during morning activity, with the sharp shape of a door opening rather than a steady state. Daytime has since settled at ~526–529.
  - **⚠️ In TRUE terms this is the uncomfortable part.** With the +350 offset: baseline overnight ≈ **835 true** (already 35 over the 800 target); now ≈ **918 true**, plateauing near **925**. The room is running **~120 ppm over target overnight**. Not yet in the range where oyster morphology visibly suffers, but the target exists for a reason and the margin is gone.
  - **The gradient looks REAL, not another calibration step.** `co2_shelf_delta` moved −7 → −43 **and `temp_shelf_delta` moved in the same event** (+0.2 → −0.3). The standing discriminator says one sensor stepping while the other holds = calibration; a delta that moves *with conditions*, alongside an independent variable, = physics. And it is physically coherent: the *remaining* holes still admit cold outdoor air at floor level, which is both colder and **lower** in CO2 (~425 outdoor), so it pools low — bottom shelf cooler and CO2-leaner. **Watch the bottom shelf**, but −0.3 °C is nothing like the 07-25 crash.
  - **➡️ RECOMMENDED NEXT MOVE — don't revert, don't seal more: SWITCH THE FRESH-AIR FAN TO ITS HIGH POSITION for 24h and re-read the same window.** The premise of this experiment was that *"air entering through the holes instead of through the fan costs the humidifier 4–7× more per m³"* — outdoor at 5–8 g/m³ against grow-room air at ~12.2. **The seal did its job: it cut the expensive path. The follow-up is to buy the flush back through the cheap path, which is the fan.** ⚠️ **The variac is NOT installed**, and both HA fan entities are phantoms (*"drives nothing — off-controller"*), so the only control that exists today is the fan's **physical 2-speed switch**.
    - **Why high is affordable NOW when it was not before: the seal freed ~10 points of humidifier duty.** Previously duty was pinned with no headroom, so more fan meant more drying and a worse room. At 66.5% there is real slack — and that slack is exactly the budget a higher fan speed spends, only it spends it on *moist* grow-room air instead of dry outdoor air.
    - **The test brackets the range before any wiring is done.** The variac is **owned but not fitted**, so fitting it is an installation job that can wait a day. If **high holds CO2 near target without re-pinning the humidifier**, the fan's existing switch may be enough and the variac becomes optional rather than needed. If **high over-ventilates** (duty pins, temp drops, CO2 crashes under target), then low is too little and high is too much, **the in-between optimum is demonstrated rather than argued**, and fitting the variac is clearly worth the afternoon. Either way the test costs nothing and makes the subsequent dial-in faster, because it will already be known which direction the optimum lies.
    - Target if high is right: CO2 back under ~500 displayed with duty still near 66. *(This does **not** conflict with the 2026-07-27 variac drop — that killed turning airflow **down** to save energy. This is turning it **up** for CO2, and more airflow can only help positive pressure and the bottom shelf.)*
  - **🔬 ARM C RUNNING — fresh-air fan switched to HIGH at 2026-07-29 ~17:50.** Vents stay half-sealed. **Read the same window: 2026-07-29 22:00 → 07-30 06:00.** *(Settling time is 4h10m vs 8h45m on the seal arm, and the room was disturbed at the switch — CO2 638 / duty 98.3% at 17:54 is a person in the room with the door open, **not** a reading. If the result comes out marginal, run a second night rather than deciding on this one.)*

    | Arm | Configuration | `humidifier_duty_1h` | CO2 displayed |
    |---|---|---:|---:|
    | **A** | vents open, fan low | 76.3 | 484.9 |
    | **B** | half-sealed, fan low | **66.5** | **568.5** |
    | **C** | half-sealed, **fan HIGH** | *tonight* | *tonight* |

  - **🎯 PREDICTION, RECORDED IN ADVANCE — and note the discriminator has FLIPPED.** On the seal arm, CO2 was the discriminator because temperature and humidity improved under both outcomes. **Here it is the opposite: CO2 falling is the *goal* and cannot really overshoot harmfully on its own — the cost of too much airflow shows up in HUMIDIFIER DUTY and TEMPERATURE.** So watch duty and temp, not CO2.
    - **✅ Success — high is the answer and nothing needs fitting:** CO2 falls to **~450–520 displayed** (800–870 true) **and duty stays ≤ ~70**. The fan buys the flush back using moist grow-room air (~12.2 g/m³) instead of dry outdoor air (5–8), which was the entire premise of sealing the holes.
    - **⚖️ Mixed — the variac is justified by measurement:** CO2 falls **but duty climbs back toward or past 76.3**. That means low is too little and high is too much, so **the optimum lies between them and cannot be expressed by a 2-position switch.** This is precisely the evidence that would warrant wiring in the variac (owned, not yet fitted).
    - **❌ Too far:** duty **pinned near 100% sustained**, temp below ~16.5 °C, or VPD leaving the 0.1–0.4 band. Revert to low and fit the variac.
    - **Also watch, both of which should IMPROVE if the mechanism is understood correctly:** `temp_shelf_delta` back toward 0 or positive (more fan → more positive pressure → better bottom shelf, currently −0.3) and `co2_shelf_delta` back toward 0 (currently −43) if that gradient really was a flushing artefact rather than a sensor step.
  - **✅ ARM C READ 2026-07-30 — keep the fan on HIGH, and the variac is NOT justified. CO2 must come from the vents.**

    | Metric | A open/low | B seal/low | **C seal/HIGH** | C−B |
    |---|---:|---:|---:|---:|
    | `humidifier_duty_1h` | 76.3 | 66.5 | **63.8** | −2.7 |
    | CO2 displayed — **mean** | 484.9 | 568.5 | **570.7** | +2.3 |
    | CO2 displayed — **at 06:00** | 461.9 | 571.8 | **547.7** | **−24.1** |
    | RH | 90.5 | 90.4 | 90.4 | −0.1 |
    | Temp | 16.8 | 17.3 | **17.5** | +0.2 |
    | `co2_shelf_delta` | −7.1 | −42.9 | −50.4 | −7.5 |
    | `temp_shelf_delta` | +0.2 | −0.3 | **−0.1** | +0.2 |
    | VPD | 0.19 | 0.2 | 0.2 | in band |

  - **⚠️ THE MEAN IS THE WRONG STATISTIC FOR THIS ARM — the shape is the signal.** On the mean, CO2 "did not move" (+2.3 ppm). But the window means are not comparable, because **the intervention itself disturbed the start of arm C**: switching the fan at 17:50 put a person in the room with the door open, and CO2 peaked at 596 by 18:00. Arm C therefore *opened* high, at 590. **The trajectories are opposite:**
    - **Arm B rose all night** — 555 → 576, accumulating, then plateauing.
    - **Arm C fell all night** — 590 → 548, and held ~548–551 through 08:00.

    **The fan on high restored overnight *clearing*** — the same shape arm A had with the vents fully open, and the thing the seal had removed. By the 06:00 mark arm C sits **24 ppm below** arm B and still falling.
  - **But it only recovers about a fifth of what sealing cost.** Sealing cost **+110 ppm** at the 06:00 point (461.9 → 571.8); the fan gives back **−24 ppm** (→ 547.7). In true terms: A ≈ 812, B ≈ 922, **C ≈ 898** against an **800 target — still ~98 ppm over.** The fan is a minor actuator on this axis; the vents are the major one.
  - **✅ Decision: LEAVE IT ON HIGH.** Every measure moved the right way or stayed flat — duty *fell* 2.7 points (so the extra air cost nothing in humidity, consistent with grow-room air being moist at ~12.2 g/m³), temperature rose 0.2 °C, and **`temp_shelf_delta` recovered from −0.3 to −0.1**, which is the positive-pressure benefit predicted in advance. It is free. *(Caveat: −2.7 pp and +0.2 °C are small enough to be night-to-night variation. The clean, defensible claims are the CO2 **shape change** and that high costs nothing.)*
  - **⛔ THE VARIAC IS NOT JUSTIFIED — and for a reason not previously considered.** The pre-registered "mixed" outcome that would have warranted it (CO2 falls **but duty climbs**) **did not occur** — CO2 improved *and* duty improved. **High beats low on every axis, so there is no evidence of an optimum in between.** And decisively: **a variac can only reduce voltage below mains.** If the best setting is full-speed high, a variac has nothing to offer here. **This is the second time today the variac question has resolved to "do not fit it."** Keep it for a future need; it is not this one.
  - **➡️ NEXT MOVE — the vents are the real variable actuator: partially REOPEN.** Halving the aperture moved CO2 +110 ppm; the fan claws back only 24. So the aperture is the control, and **duct tape is infinitely adjustable one hole at a time** — the continuously-variable actuator this position has been wanting was never the fan. **Unseal half of what was sealed (from every second hole to every fourth) and read the same 22:00–06:00 window.** Expect CO2 between 548 and 462 displayed, and duty between 63.8 and 76.3 — the aim is the point where CO2 approaches ~500 displayed (~850 true) while duty stays under ~70.
  - **❓ And the question the instruments cannot settle: is ~898 ppm true acceptable to the crop?** The humidity win is real and worth having — duty **76.3 → 63.8** across the whole exercise, which is meaningful insurance given pinned duty is the documented leading indicator of failure. The cost is ~98 ppm over target. **Elevated CO2 shows up in oyster morphology as longer stems and smaller caps, so the next flush is the judge, not the sensors.** Tie this to the lower-shelf crop observation already on the list.
  - **🔬 ARM D — half the sealed holes reopened 2026-07-30 ~09:00**, so **every fourth hole sealed** (was every second), fan stays **HIGH**. 13 hours of settling. **✅ READ 2026-07-31 — results and verdict below the prediction.**
  - **🎯 QUANTITATIVE PREDICTION, recorded in advance.** Using the 06:00 points, sealing 50% of the aperture cost **+109.9 ppm** (461.9 → 571.8) and the fan gives back **−24.1**. If flow is roughly proportional to open area, 25% closure should cost about half of 110:

    | | Predicted at 06:00 | Predicted duty |
    |---|---:|---:|
    | **Arm D (¼ sealed, fan high)** | **~493 displayed** (~843 true) | **~69** |

    **That would hit the target almost exactly** (CO2 ≤ ~500 displayed with duty < 70) — so this arm is a real test of the linear-aperture model, not just a data point. **If CO2 comes in much above ~520 or duty much above ~72, the aperture does not behave linearly** and the remaining holes are doing more than their share.

  - **✅ ARM D READ 2026-07-31 — tape confirmed still down by the operator, so this is a valid result, not a void one.**

    | Metric | A open/low | B ½seal/low | C ½seal/HIGH | **D ¼seal/HIGH** |
    |---|---:|---:|---:|---:|
    | `humidifier_duty_1h` | 76.3 | 66.5 | 63.8 | **68.5** |
    | CO2 displayed — mean | 484.9 | 568.5 | 570.7 | **531.5** |
    | CO2 displayed — **at 06:00** | 464 | 575 | 545 | **512** |
    | RH | 90.5 | 90.4 | 90.4 | **90.4** |
    | Temp | 16.8 | 17.3 | 17.5 | **17.5** |
    | `co2_shelf_delta` | −7.1 | −42.9 | −50.4 | **−51.6** |
    | `temp_shelf_delta` | +0.2 | −0.3 | −0.1 | **−0.0** |
    | VPD | 0.19 | 0.2 | 0.2 | **0.2** |
    | **stack ΔT — MEASURED** | **5.7** | **7.3** | **5.4** | **7.9** |

    **CO2 fell all night** — 536 → 545 → 539 → 536 → 532 → 526 → 522 → 512. The clearing shape held.

  - **⚠️ THE PREDICTION WAS RIGHT FOR THE WRONG REASON — and Arm D is CONFOUNDED.** The forecast-based revision assumed *"the warmest night of the four, ΔT ~4.8, the weakest stack yet"* and moved the prediction up to 505–520. **Measured via Open-Meteo, this was the COLDEST night: outdoor mean 9.6 °C, ΔT 7.9 — the strongest stack of all four arms.** The forecast was wrong by 3.1 °C of driving force, in the opposite direction. 512 landed inside the band by luck.
    - **Corrected reading:** on a night with **21% more buoyancy than arm C** (√7.9 vs √5.4) *and* double the aperture, CO2 came back only **35.7 ppm** against the ~55 that linear aperture scaling predicts. **Aperture and driving force rose together, both pushing CO2 down and duty up. One night cannot separate them.**
    - **⚠️ The uncontrolled variable is now larger than the treatment.** ΔT ranged **5.4–7.9** across four arms; the fan's entire measured effect was 24 ppm. **Single-night arms cannot resolve effects this size** while ΔT moves freely.
    - **The only ΔT-matched pair in the series is A vs C (5.7 vs 5.4)**, and it carries the one solid result: **half-sealing costs ~86 ppm even with the fan on high.**
    - **Duty climbed through the night** — 62.6 at 23:00 → 74.7 by 05:00, peaking **82.5** — as the stack strengthened and pulled in dry outdoor air. On a colder night that pins, and **pinned duty is the documented leading indicator of failure.**

  - **⛔ THE LOAD-BEARING ASSUMPTION, named 2026-07-31 — and it does not hold up.**
    **⚠️ Hinges on:** *that the room's CO2 headroom is worth spending to cut humidifier duty from 76.3%.* **If wrong:** the tape comes off entirely and four nights bought a worse room.
    - **This entry set the constraint before the first hole was taped:** *"the limiting constraint is that **CO2 headroom is only ~35 ppm**"* — and the pre-registered failure condition: *"**Too far:** CO2 climbs >100 ppm and keeps climbing."*
    - **Arm B came in at +110 ppm. That is the pre-registered "too far" outcome, breached on the very first arm, against 35 ppm of headroom.** By the rule written in advance, the correct move at arm B was to revert. Arms C and D have instead been clawing back toward the baseline, and have not reached it: **against arm A, CO2 is 48 ppm worse and duty 7.8 points better.**
    - **76.3% duty was never pinned.** The documented failure indicator is duty *pinned near 100%*. 76.3 leaves ~24 points of headroom, while the CO2 headroom being spent was ~35 ppm of a ~35 ppm budget.

  - **🎯 THE MISSING ARM — never run, and it may dominate everything tested.** Arm A was vents open with the fan on **LOW**. Arm C proved the fan on **HIGH** is worth **−24 ppm CO2 and −2.7 duty, for free**. **Nobody has ever run vents-open + fan-HIGH.** Extrapolating C's fan effect onto A:

    | Configuration | CO2 displayed | duty |
    |---|---:|---:|
    | A — open, fan low *(measured)* | 464 | 76.3 |
    | D — ¼ sealed, fan high *(measured)* | 512 | 68.5 |
    | **open, fan HIGH — NEVER RUN** | **~440** | **~73.6** |

    If that holds it **beats arm D on CO2 by ~72 ppm** for ~5 points of duty, with duty still nowhere near pinned. **The fan change was free and reversible; the tape spends headroom the room did not have. The two were never separated at full aperture.**
  - **🔬 ARM E RUNNING — ALL TAPE REMOVED 2026-07-31 ~13:30 by the operator.** Vents fully open, fan stays **HIGH**. **8h25m of settling** before the window — better than arm C's 4h10m and comparable to the seal arm's 8h45m. **Read 2026-07-31 22:00 → 2026-08-01 06:00.**

    **🎯 PREDICTION, RECORDED IN ADVANCE (written 13:34, before any data exists).** Built from arm A (open, fan LOW: 464 displayed / duty 76.3) plus arm C's measured fan effect (**−24 ppm, −2.7 duty**):

    | | CO2 @06:00 | duty |
    |---|---:|---:|
    | **Arm E (open, fan HIGH)** | **~440 displayed** (~790 true) | **~73.6** |

    **⚠️ CONDITIONAL ON ΔT — and the forecast is not to be trusted.** Open-Meteo currently forecasts tonight at outdoor ~11.9 °C, **ΔT ~5.6**, which would be near-ideal (arm A 5.7, arm C 5.4). **But last night's forecast said 4.8 and delivered 7.9** — wrong by 3.1 °C, which is larger than the entire spread between arms. So:
    - **If ΔT lands 5.0–6.0:** the figures above stand as a clean, comparable read against A and C.
    - **If ΔT lands ≥ 7:** buoyancy flow scales ~√ΔT, so expect **~420 displayed and duty ~78** instead — and the arm is **confounded again**, exactly as D was. Read trajectory, not the mean.
    - **Confirm what it actually was** with `stock-control/tools/outdoor_history.py --nights 2 --room 17.5` before drawing any conclusion.

    **📋 THE DECISION RULE, pre-registered — and this time it gets honoured.** *(Arm B breached its pre-registered "too far" threshold at +110 ppm and the series continued anyway. That is the mistake this rule exists to prevent.)*
    - **✅ Tape stays off permanently, vent question CLOSES:** CO2 **≤ ~460 displayed** and duty **≤ ~76.3** (arm A's level). The fan alone did the work, the tape was spending headroom the room did not have, and nothing needs buying or fitting.
    - **⚖️ The tape was doing real work after all:** duty climbs **materially past 76.3** while CO2 improves only marginally on arm D. Then the humidity cost of the open vents is genuine, arm D's configuration is defensible, and the tape goes back to every fourth hole.
    - **❌ Something is wrong with the model:** CO2 comes in **above ~500** with the vents fully open. That would mean arm C's fan effect does not transfer to full aperture, and the whole linear picture needs rethinking rather than another arm.

  - **✅✅ THE CROP HAS ANSWERED — operator observation 2026-08-01: BIGGER mushrooms, and more EVEN production across all the shelves.** This was the pending question and it resolves favourably.
    - **The CO2 worry is parked.** `MICROCLIMATE.md` §"Optimization" names the failure signature precisely: *"Only revisit… if cap quality shows CO2 stress — **long stems / small caps**."* **Bigger caps is the opposite of that signature.** So ~862–900 ppm true has not visibly cost morphology, and the load-bearing assumption behind recommending arm D — *that ~862 true is tolerable to the crop* — **holds on the evidence available.**
    - **⚠️ But the operator is right that CO2 itself cannot be judged: too many things changed at once.** What is claimable is the *absence of the damage signature*, not a causal read on CO2. **Do not upgrade this into "CO2 doesn't matter."**
    - **✅ The evenness is independent corroboration of the positive-pressure work.** `temp_shelf_delta` recovered −0.3 → −0.0 across arms C/D, and the bottom-shelf gradient was the thing that work targeted. **The instrument and the crop now agree**, which is a stronger result than either alone.
  - **✅ ARM E READ 2026-08-01. The pre-registered "close it" branch is NOT met — duty went the wrong way, hard. ➡️ Recommend reverting to arm D (every fourth hole).**

    | Metric | A open/low | B ½/low | C ½/HIGH | D ¼/HIGH | **E OPEN/HIGH** |
    |---|---:|---:|---:|---:|---:|
    | **stack ΔT — MEASURED** | 5.7 | 7.3 | 5.4 | 7.9 | **9.2** ⚠️ |
    | `humidifier_duty_1h` | 76.3 | 66.5 | 63.8 | 68.5 | **81.1** |
    | duty **from relay** *(cross-check)* | 76.2 | 68.7 | 63.2 | 68.0 | **85.2** |
    | CO2 displayed — mean | 484.9 | 568.5 | 570.7 | 531.5 | **475.8** |
    | CO2 displayed — **at 06:00** | 464 | 575 | 545 | 512 | **450** |
    | RH | 90.5 | 90.4 | 90.4 | 90.4 | **90.8** |
    | Temp | 16.8 | 17.3 | 17.5 | 17.5 | **16.6** |
    | `co2_shelf_delta` | −7.1 | −42.9 | −50.4 | −51.6 | **−42.2** |
    | `temp_shelf_delta` | +0.2 | −0.3 | −0.1 | −0.0 | **+0.1** |

    **CO2 fell all night** — 493 → 488 → 483 → 478 → 475 → 473 → 461 → 452. Clearing shape, as arm C had.

  - **🔑 CO2 IS THE BEST OF THE SERIES AND IT DOES NOT MATTER, BECAUSE DUTY IS THE WORST BY 9 POINTS.** 450 at 06:00 (~800 true — **on target**) is the best number this room has produced. But duty ran **81.1 by sensor, 85.2 by relay**, peaked **92.5**, and stood at **90.0 at 06:00**. The relay recorded only **20 transitions against 35–41 on every other arm** — fewer, longer on-periods, which is what approaching pinned looks like. **`room_check.py` documents that the duty *sensor* under-reads when pinned; the relay is the reliable measure, and it is the higher of the two here.**
    - **Arm D's warning came true in one night:** *"Duty climbed through the night… peaking 82.5. **On a colder night that pins**, and pinned duty is the documented leading indicator of failure."* This was that colder night.
  - **⚠️ CONFOUNDED AGAIN, and worse than arm D — as the pre-registered conditional anticipated.** ΔT was **9.2**: the coldest night of the five, against a spread of 5.4–7.9 for everything before it. The rule said *"if ΔT lands ≥ 7 … the arm is confounded again"*. It did. **A colder night raises duty and lowers CO2 regardless of the vents, which is exactly the pattern observed — so arm E cannot separate the treatment from the weather.**
    - **The forecast missed again, and by more:** predicted outdoor ~11.9 °C / ΔT ~5.6; **measured 8.2 °C / ΔT 9.2 — wrong by 3.6 °C**, having been wrong by 3.1 °C the night before. *"The forecast is not to be trusted"* is now measured twice.
    - **Even against the cold-night conditional it underperformed:** that predicted ~420 displayed / duty ~78. Actual **450 / 81–85**. **Opening the vents bought back less CO2 than the linear-aperture model expects, and cost more duty.**
  - **📋 Scored against the pre-registered rule — and this time it IS honoured.**
    - **✅ "Tape stays off permanently"** required CO2 ≤ ~460 **and** duty ≤ 76.3. CO2 ✅ 450; **duty ❌ 81.1 / 85.2.** **Branch NOT met — so the vent question does not close, and the tape does not stay off.**
    - **⚖️ "The tape was doing real work"** required duty materially past 76.3 ✅ **and** CO2 improving only marginally on arm D ❌ — it improved 62 ppm, which is not marginal. **Not cleanly met either.**
    - **❌ "Model is wrong"** required CO2 above ~500 with vents open. Not met (450).
  - **➡️ RECOMMENDATION — revert to arm D: every fourth hole sealed, fan stays HIGH.** D is the best-measured compromise in the series: **CO2 512 at 06:00 (~862 true) for duty 68.** E buys 62 ppm of CO2 for **17 points of duty** and a 92.5% peak. **The CO2 gain is worth having; it is not worth buying at a near-pinned humidifier**, because pinned duty is the documented leading indicator of failure and ~862 true is below the level at which oyster morphology visibly suffers.
    - **⚠️ Hinges on:** *that ~862 ppm true is tolerable to the crop.* **If wrong**, the whole trade inverts — the tape comes off, and the room runs at 85% duty accepting the pinning risk as the price of on-target CO2. **The next flush is the judge, not the sensors** — longer stems and smaller caps are the signature. Tie to the lower-shelf crop observation already on this list.
    - **⚠️ Right now the room is in arm E's configuration and running hot on duty: `humidifier_duty_24h` read 86.9% on 2026-08-01, higher than any arm window.** That is not a spot artefact; it is the state the room has been left in.
  - **✅ The two ΔT-matched comparisons are the only clean numbers in the whole series** — everything else mixes treatment with weather:
    - **A (5.7) vs C (5.4):** half-sealing with the fan high buys **13 duty points** for **+81 ppm**.
    - **B (7.3) vs D (7.9):** going half → quarter sealed buys back **−63 ppm** for **~0.7 duty points** — nearly free, and the reason D is the recommended configuration.

    **This is the last planned arm.** ΔT moves more between nights (**now 5.4–9.2**) than any treatment measured (24–110 ppm), so further single-night arms cannot resolve anything. **After this, the crop is the judge** — elevated CO2 shows in oyster morphology as longer stems and smaller caps, which ties to the lower-shelf crop observation already on the list.

  - **🔧 TOOLING, built 2026-08-01 because this read needed it — `stock-control/tools/arm_read.py`.** Reads any 22:00–06:00 window from the recorder with explicit SAST handling, and `--validate` re-reads arms A–D and checks it reproduces the published figures. **It does, to the decimal (76.3 / 66.5 / 63.8 / 68.5 and 484.9 / 568.5 / 570.7 / 531.5)** — so arm E is comparable, not a fresh method. *(It also settled that the published series used a **simple** mean of recorded points, not a time-weighted one; both are now reported, and the difference is ≤1.5 points.)*
  - **🐛 AND A BUG THAT NEARLY VOIDED THIS ARM — `tools/outdoor_history.py` fixed 2026-08-01.** Night windows were keyed by decrementing the day number by hand (`d - 1 if d > 1 else date`), which **breaks on the first of a month.** Arm E's window is 31 July → 1 August, so the six small-hours readings were filed under a night that had not happened yet, leaving the arm showing **n=2 of 8 hours and ΔT 6.6** — which reads as a near-ideal, comparable night. **The true figure is n=8, ΔT 9.2 — the most confounded arm of the five.** Fixed with real date arithmetic; arms A–D re-read unchanged (5.7 / 7.3 / 5.4 / 7.9), confirming the bug only ever fired at a month boundary. **Had this not been caught, arm E would have been scored as a clean read and the vent question closed on it.**

  - **✅ Method note — the arm A–C figures were re-verified 2026-07-31 and are sound.** Recomputed from the recorder with explicit SAST windows: duty **76.3 / 66.5 / 63.8** and CO2 mean **484.9 / 568.5 / 570.7**, matching the published values to the decimal. *(The HA history API returns UTC timestamps; reading them as local shifts the window two hours and gives 79.2 / 471.4 for arm A — nothing like the published figures, which confirms the original reads were done correctly. The `@06:00` points differ by 2–3 ppm on endpoint convention, which changes no conclusion.)*
  - **⚠️ CONFOUNDER, and it should have been raised at Arm A: outdoor temperature is UNCONTROLLED and currently UNMEASURABLE.** Stack effect scales with ΔT, and this entry's own reasoning puts that driving force at **15–20× the grow-room loop's 0.71 °C** — so **outdoor temperature is the dominant driver of the very mechanism being tested**, and it is different every night. Checked 2026-07-30 against `weather.forecast_home`: the recorder holds **n=1, n=1 and n=5 temperature points** for the three windows, at 23.1 / 22.7 / 20.3 °C — implausible for a Pretoria winter night (this entry assumes ~3–8 °C) and almost certainly stale forecast values carried between state changes. **The data cannot answer the question.**
    - **Consequence for how these results are read:** prefer **within-night trajectory** (does CO2 rise or fall across the night?) over **cross-night means**, because trajectory is far less sensitive to the absolute ΔT. That is exactly why Arm C's verdict rests on the shape inversion rather than the mean.
    - **✅ Free fix for the FUTURE:** `weather.forecast_home` exposes temperature as an *attribute*, which the recorder only logs when the entity's **state** changes. **Add a template sensor** exposing it as its own numeric sensor — mirrored in `stock-control/home-assistant/outdoor_conditions_sensors.yaml`, which also derives outdoor absolute humidity and a `stack_delta_t` (room − outdoors). Monitoring only; hot-reloads, no restart.
    - ~~**⬜ STILL NOT DEPLOYED as of 2026-07-31** … **the single highest-value free action left on the vent work**~~ **⛔ WITHDRAWN 2026-08-01 — DO NOT DEPLOY IT. The source is wrong, and the file's own unverified warning is now verified.** Checked at 21:00 SAST against Open-Meteo for the same hour: **`weather.forecast_home` reads 20.9 °C against 12.4 °C measured**, with today's daily **max** at 19.5 — so it reports the **daily maximum, not current conditions**, and its state had not changed in over three hours.
      - **The failure is not noise, it is a sign inversion.** Room 17.5 − 20.9 = **ΔT −3.4**, i.e. *"warm air flowing out"*, on a night measured at **+9.2** with cold air pouring in. **And it would look authoritative on a dashboard.** `outdoor_absolute_humidity` and `stack_delta_t` both derive from the same bad temperature, so all three inherit it.
      - **➡️ `stock-control/tools/outdoor_history.py` already solves this, and better** — hourly *analysed* Open-Meteo history, free, no API key, ~90 days back, nothing to deploy, and it works **retrospectively**, which a sensor never can. It produced the ΔT figures for all five arms.
      - **The templates keep a purpose only for something LIVE** — a frost alert, a dashboard tile — **and only once the weather integration is fixed or swapped.** Annotated in place at `stock-control/home-assistant/outdoor_conditions_sensors.yaml`. *(Task moved here 2026-07-31 from `personal/STATUS.md`, where it had been mis-filed under House — it is fruiting-room work and belongs on this board.)*
    - **⛔ AND IT MAKES AN OUTDOOR TEMPERATURE SENSOR NOT WORTH BUYING.** Asked directly 2026-07-31. A physical sensor's only advantage over Open-Meteo is measuring air at the actual front wall rather than a gridded 1394 m analysis — but **that difference is a systematic offset, and a systematic offset cancels in cross-arm comparison.** Every arm is compared against every other; if the grid reads 1.5 °C cool at the wall, it reads 1.5 °C cool on all four nights. What matters is night-to-night *variation*, which reanalysis tracks well and which is the entire confounder. **It would buy accuracy on the axis that is not used.** It would earn its keep only for closed-loop ΔT compensation (declined — no actuator authority), frost alerts, or wind (which a temperature sensor does not measure and Open-Meteo already provides). **Deploy the template sensor; buy nothing.**
    - **✅✅ AND THE PAST IS RECOVERABLE — confounder now RESOLVED for arms A–C.** Open-Meteo's forecast endpoint serves **hourly analysed history** via `past_days`, free and with no API key, for ~90 days. Script: `stock-control/tools/outdoor_history.py`. Measured for the actual windows:

      | Arm | Vents / fan | Outdoor mean | Room | **Stack ΔT** | Outdoor AH |
      |---|---|---:|---:|---:|---:|
      | **A** | open / low | 11.8 | 16.8 | **5.0** | 4.7 |
      | **B** | ½ sealed / low | **10.2** | 17.3 | **7.1** | 5.8 |
      | **C** | ½ sealed / HIGH | 12.1 | 17.5 | **5.4** | 6.4 |
      | **D** | ¼ sealed / HIGH | *12.7 fcst* | ~17.5 | **~4.8** | — |

    - **🔑 THE CORRECTION STRENGTHENS BOTH EARLIER VERDICTS — it does not overturn them.** ΔT varied **5.0 → 7.1 °C**, a 42% spread, and it ran *against* the measured effects:
      - **Arm B had the STRONGEST driving force (7.1 °C, the coldest night) and still recorded the worst CO2.** More stack = more flushing through the remaining holes, so B had the *best* natural conditions of the three and CO2 still rose +110 ppm. **The cost of sealing is therefore understated, not overstated.**
      - **Arm C had a 24% WEAKER driving force than B (5.4 vs 7.1) and still improved CO2 by 24 ppm with the trajectory inverting to clearing.** So the fan achieved that against a weaker natural flush. **The fan's contribution is understated too.**
    - **⚠️ REVISE THE ARM D PREDICTION UPWARD — tonight is the WARMEST night of the four** (outdoor ~12.7, ΔT ~4.8, the weakest stack yet). The naive linear-aperture forecast of ~493 displayed assumed A/B conditions (ΔT 5.0–7.1). Buoyancy flow scales roughly with √ΔT, so on tonight's weaker driving force **expect ~505–520 displayed** rather than 493. **If it still lands at or below ~493, the aperture effect is stronger than the ΔT correction implies** — which would be the cleaner result.
    - **✅ AN ASSUMPTION IN THE VENT ARGUMENT IS NOW MEASURED AND CONFIRMED.** This entry's reasoning rests on outdoor air being **~5–8 g/m³** against the grow room's ~12.2, which is why air through the holes costs the humidifier *"4–7× more per m³"* than air through the fan. **Measured: 4.7–6.4 g/m³ — confirmed, at the lower end.** Against a room at ~13.4 g/m³, outdoor air at 4.7 needs **8.7 g/m³** added versus **1.2** for grow-room air: a ratio of **7.25×**, at or just above the claimed upper bound. **The premise of the whole experiment holds, on measured numbers rather than an estimate.**
  - **⚠️ THE BASELINE IS WORSE FOR CO2 THAN THE PLAN ASSUMED — margins are thin.** The prediction above was written against "room ~765 true vs 800 target, ~35 ppm headroom". **Overnight actually runs 485 displayed ≈ 835 true — already ~35 ppm OVER target, not under.** The abort line (displayed >600 sustained 3h) is therefore only ~115 ppm away, and the "too far" signature (>100 ppm rise) lands almost exactly on it. **CO2 is the discriminator and it starts with very little room.**
  - **⚠️ RH starts ~3 points from its abort**, at 90.5 mean / 92.1 max against ">95% sustained 1h" — and sealing is *expected* to push RH up. The todo already calls this the likeliest abort to bite; the baseline confirms it.
  - **✅ Circulation setup is a CONSTANT across this experiment, not a variable — confirmed by the operator 2026-07-28.** The WF-150 has been on high and both duct end caps open since 07-21, unchanged through both the baseline and the sealed period. **The vent read is therefore valid as taken.** It does mean the result describes the room *in its current over-ventilated configuration* — so if the fan is later reverted to LOW, the vent conclusion may need re-testing under the quieter airflow.
  - **⚠️ DUCT TAPE CAN PRODUCE A FALSE NULL.** Adhesion in ~90% RH is unreliable. If the tape peels overnight the vents silently reopen and the "after" data looks like a null result — which would be read as "the holes don't matter" when in fact the seal failed. **Physically check the tape is still down when reading the result**, before drawing any conclusion. That check is the difference between a null and a void experiment.
  - **⛔ DO NOT RECALIBRATE THE INKBIRD WHILE THIS RUNS (asked and answered 2026-07-28).** Counterintuitive but load-bearing: **both sensors are currently low by roughly the same ~350, so their *difference* is a clean gradient signal** — `co2_shelf_delta` ran mean **−7** overnight, i.e. a usable "gradient ≈ 0". Recalibrating the Inkbird alone pushes that delta to ~**+350** and buries the gradient under calibration offset again, **during the exact window the bottom-shelf abort criterion has to work**. It also changes a monitored quantity mid-run, which is why the reflash is already excluded. It buys nothing for the primary's +350 correction, which rests on the co-location and the physical-impossibility argument, not on the Inkbird. **Do it after the 07-29 read**, recalibrating in outdoor air, validating outdoors (expect 400–430) before returning it, and logging the delta on return so any step is visible. Treat it as provisional either way — its zero has moved twice and does not survive handling.
  - **Still worth doing regardless: a power-monitoring smart plug on the fresh-air fan.** Sealing softens the consequence of a fan death; the plug makes it *detectable*. The fan is an unmonitored single point of failure — no tacho, two predecessors dead in that position.

## Decided against (so it isn't re-litigated)

- **A third CO2 sensor — don't buy.** Detection already works free: `co2_shelf_delta` caught this drift. What co-location buys is *quantification*. The real problem is that the Inkbird has two conflicting jobs (continuous bottom-shelf monitoring vs cross-check reference) and can't do both at once — a third sensor resolves only that. **Trigger that would justify it: CO2 going back to *controlling* something.** Today a wrong reading misleads a human but cannot mis-actuate anything. **If it ever happens, the spec is: RS485/Modbus (not I2C — the sensors hang on ~1100mm drops off a Cat5e field run in ~90% RH; cable length is the whole reason this room is on RS485), address 3 on the existing bus, and it must expose a calibration/ABC-control register — treat that as a purchase criterion, not something to discover afterwards.**
- **Humidifier power-monitoring smart plug** — was justified mainly as disc-degradation early warning and to disambiguate capacity vs internal cutoff. The tub-hole finding answered both; mostly moot now.
- **Smart plug to power-cycle the Inkbird** — it has a rechargeable battery, so cutting mains doesn't reboot it. Its flakiness (brief self-recovering blips) is acceptable for a sensor that never controls anything.
- **12V DC fans for the fresh-air position** (ebm-papst 4312/2 axial, REF100-11/12 centrifugal) — all cost more and mounted worse than reusing the installed inline fan on a variac. *(⚠️ 2026-07-29: reads as though the variac is fitted — it is **owned but not yet wired in**. The comparison still holds, and stands stronger for the variac already being paid for.)* If full ESP32 closed-loop is ever wanted, the easiest route is a **mains EC inline duct fan with 0–10V input**, not a DC blower.

## Worth investigating (not decided)

- **Ledger ↔ Sage reconciliation.** The ledger records operational *units*; money lives in Sage. Nothing connects them. Revisit once Phase C is carrying real numbers on both sides.

## Standing lessons

- **Look at the physical thing first.** The humidifier's cure was a hole in a plastic box, and it sat undiscovered behind three sessions of fan theory, sourcing sweeps and a rejected overnight experiment.
- **Reconcile against the physical thing before rewriting records.** The batch-ID session was about to repoint correct pickings; the operator's "the week numbers are all one off" is what caught it.
- **Use the HA recorder for anything about trends or reliability** — the add-on log retains only ~1–2h and structurally cannot show a diurnal cycle. **Never settle a diurnal question with a spot check.**
- **Never trust an HA fan percentage** — both fans are 2-wire with no tacho, and a commanded PWM says nothing about airflow. This is exactly what hid both fan deaths.
- **A repo edit does not reach the running HA automation.** The alarm's CO2 leg sat silently unarmed for days because the repo copy was fixed and the live automation wasn't.
- **HA numeric triggers are edge-triggered** — they fire on crossing a threshold, not on sitting beyond one, so they won't fire for a condition already in progress when they load.
