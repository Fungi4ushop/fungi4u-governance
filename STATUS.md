# Status

Last updated: 2026-08-11

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

**📐 MEASURED 2026-08-06 — the divider position was captured and it revises the numbers this section was built on.** It sits **1820 mm from the front wall, 2280 mm from the back**; with the 75 mm partition that is 4175 mm internal, which identifies **4650 mm as the front-to-back axis and 7000 mm as the width** (the 7000 axis cannot fit 1820 + 2280). Full working: `stock-control/docs/MICROCLIMATE.md` §1.

| | Depth | Floor | Volume |
|---|---:|---:|---:|
| **Fruiting** (front) | 1820 mm | **12.7 m²** | **~34 m³** |
| **Grow** (rear) | 2280 mm | **16.0 m²** | **~41 m³** |
| **Combined** | 4175 mm | **28.7 m²** | **~76 m³** |

- **⛔ THE FRUITING ROOM IS THE SMALLER OF THE TWO.** Nothing in these files said so, and the wall discussion has read throughout as though the fruiting room were the larger space being modestly extended. **It is not.**
- **⛔ "~86 m³ for the whole building" is an EXTERNAL-dimension figure** and overstates the usable interior by ~13%. **Internal is ~76 m³.** *(The ~40 m³ added by removing the divider was right; the base it is added to was not.)*
- **➡️ So the wall is a 2.2× VOLUME and 2.25× FLOOR increase to the fruiting room, not an extension.** Every argument below that turns on "how much bigger" should be read at that scale.
- **✅ And bag density is now a MEASURED figure, corroborated across two independently stocked rooms:** fruiting 76 bags / 12.7 m² = **5.97/m²**; grow 96 bags / 16.0 m² = **6.02/m²**. **Agreement to within 1%.**

**🎯 WHICH SETTLES THE SECOND-FLUSH CAPACITY QUESTION — it is now arithmetic, not assertion.** At ~6 bags/m² the combined room holds **~171 bags ≈ 7 batches**. At one batch per week that is **~7 weeks of fruiting residence**, against the **4–6 weeks** two flushes require. **The wall removal clears the constraint with margin** — where this morning the same claim rested on "roughly half the building".

**🔴🔴 AND THEN THE RACKING WAS MEASURED THE SAME DAY, WHICH CHANGES THE RECOMMENDATION: THE CONSTRAINT IS TROLLEYS, NOT FLOOR AREA — SO THE WALL IS NOT THE CHEAPEST ROUTE TO A SECOND FLUSH, OR EVEN A NEEDED ONE.**

**Trolleys are 1200 × 450 mm, four racks at 400 mm pitch. The fruiting room has 3 of them, 8 bags per shelf, ONE TROLLEY PER BATCH** (operator, 2026-08-06).

- **3 × 4 × 8 = 96 bag capacity, holding 76 — and one trolley per batch means exactly 3 batches, which is what `v_batch_residence` independently shows.** Two records agreeing.
- **⛔ That uses 1.62 m² of the fruiting room's 12.7 m² — 13% of the floor.** Five trolleys across the 7000 mm width, two rows plus a 920 mm aisle, gives **10 trolleys / 320 bags on 43% of the floor: 3.3× current capacity inside the existing room.**
- **🎯 Trolley count IS residence in weeks, at one batch per week: 3 → 21 days (now), 4 → 28 days, 6 → 42 days. One extra trolley reaches the two-flush window; three clear it.**

**➡️ SO THE WALL'S YIELD CASE, MADE ABOVE, IS DEMOTED — NOT WITHDRAWN.** It remains true that the wall would deliver ~7 batches of capacity. **But the same outcome is available for the price of one to three trolleys, with no aircon question, no new grow room and no construction.** ⚠️ **Do not spend on the wall for capacity reasons until the trolley route has been tried and found wanting.** The wall's *climate* case — the documented three-way tension between separation, temperature and grow-room ventilation — is untouched and stands on its own.

**⚠️ Hinges on:** *that the environment carries the extra load, which is the real open question.* **CO2 has no active control** since the fresh-air fan was removed, so more biomass raises it with nothing to correct it. Humidifier duty could move either way — a fruiting crop transpires, so bags may be a net moisture *source* — but that is untested. **Establish both, plus the cost of a trolley, before buying.**

**➡️ Volume is NOT the binding constraint. The AIR CONDITIONER is.**

- **The fill transient is trivial.** Raising the added volume from ~50% to 92% RH at 17.5 °C is a step of **6.3 g/m³** (7.45 → 13.7). Over ~40 m³ that is **~250 g of water — a quarter of a litre.** A 12-disc ultrasonic does litres per hour. **Minutes, not a capacity problem.**
- **Steady-state load is set by outside-air exchange, not by volume** — and the leak paths do not move. The infiltration this room fights is the **front-wall floor openings**, which are already in the fruiting room (they are what five nights of vent experiments were about). **Removing the divider adds volume, not infiltration.**
- **A larger volume actually helps stability** — more moisture and thermal mass per unit of disturbance, so slower swings and a longer buffer when a door opens.

**🔴 But the aircon is a dehumidifier, and the wall is currently what buffers it.** It sits above the rear door, *inside* the space that would become one room held at **90–95% RH**. Air at 90%+ crossing a cold evaporator coil condenses, and that water leaves down the condensate drain. **Humidifier and aircon then work against each other continuously, by design, in the same room.**

- Today the divider partially separates them. **⛔ Corrected 2026-08-06: the coupling is NOT "via the doorway" — the divider door stays CLOSED unless access is required (operator).** The rooms still track within 0.2–0.5 °C, so the path is the **~18.6 m² of 75 mm insulated partition**, which cannot be opened or closed. **That kills the "three-way tension" framing carried through these files** — separation was never being traded against fruiting-room temperature, because the closed configuration is the one already running.
- **Remove the wall and that buffer goes.** The humidifier is at **63–85% duty** *now*, on the smaller room, with the coil one door away. **This is the number to worry about, and it is not a volume calculation.**
- **The spare 12-disc unit and the fresh discs stop being "margin" and become a prerequisite** — but adding humidifier capacity to out-run a dehumidifier is fighting the symptom. **The real question is whether the aircon can be relocated, ducted, or run in a mode that does not condense** — and that should be answered *before* the wall comes down, not after.

**⚠️ Hinges on:** *that the rear half's envelope is no leakier than the front.* The rear wall is insulated drywall + Isoboard with its own external access door. **If that door or the drywall leaks materially, steady-state load rises with it** and the "infiltration does not change" argument weakens. One smoke-pencil pass would settle it.

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
- **⚠️ Hinges on:** *that the unit is genuinely reverse-cycle rather than cooling-only with a separate heat source.* Cheap to confirm by looking at the nameplate, and it changes the whole seasonal argument.
- **⬜ The summer question is still open and is now the real one:** cooling a 90–95% RH room without condensing. Candidates not yet assessed — evaporative cooling (thermodynamically the right tool for a room that wants moisture, but limited by wet-bulb and only effective on dry make-up air), conditioning outside air and supplying it via the plenum, or a coil held above the room's ~15.8 °C dewpoint, which a conventional split cannot do. **Do not treat this as solved by the relocation idea.**

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
- **Known costs ~R3,100/mo** (Jesca R1,430, Capitec fee R400, substrate R680, punnets R270, gas R320) **plus electricity ≈R1,470–1,680/mo** — fruiting room ~10.0 kWh/day plus chest freezer 0.784 kWh/day (measured 07-28) = **~10.8 kWh/day, ~328 kWh/mo, ~38% of the property**. Electricity is the single largest cost, bigger than Jesca. **The business electricity total is now fully measured — no unmeasured business load remains.**
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

## Room state (verified 2026-08-05 off a 48h `room_check.py` run)

### 🔬 LIVE EXPERIMENT — 20 of ~80 exhaust holes closed 2026-08-09; the clean night is READ (08-11): the gradient was already flat, the win is humidifier duty

**The operator closed every 4th hole in the front-wall 50 mm exhaust strip on Sunday morning 2026-08-09** — 20 holes, open area ~63 → ~47 cm², a **25% cut in the room's only passive exhaust.** This is option (3) from `MICROCLIMATE.md`'s own fix list, run partially: block the openings, watch the bottom gradient and CO2, *before* committing to the permanent 45° Isoboard cover.

- **✅ The documented risk did not appear.** `MICROCLIMATE.md` warns that sealing trades easier humidity for less CO2 venting, with a tripwire at an overnight trough that stops falling to ~680 and holds >1000. **The first night after measured a trough of 503 ppm — the lowest of six nights.** Large headroom remains. *(⚠️ Qualified 08-11: that night — 08-09→10, stack 5.2 K, wind 5.7 — is a **mid-range** ventilation night and remains the better of the two CO2 datapoints. **The 08-10→11 trough of 482 is NOT** — see the CO2 inversion below. **Neither is the weak-drive night the risk actually lives in.**)*
- **✅ Humidifier duty fell ~9 points** overnight (89.2 → 79.7 against 08-08, the closest match on temperature), RH held in band, and the room carried nearly the same absolute humidity while working less for it.
- **⛔ The bottom-shelf gradient — the thing this change is FOR — has not been read at all.** All three shelf deltas derive from the Inkbird, which froze on 08-09 morning and returned only at 07:42 on 08-10. **The experiment has so far measured its side effects and not its purpose.**

#### ✅ THE CLEAN NIGHT WAS READ, 2026-08-11 — AND THE TARGET METRIC TURNS OUT TO HAVE BEEN ALREADY FLAT. THE PAYOFF IS ELSEWHERE.

**⛔ FIRST, A DATA TRAP THAT MUST NOT BE RE-WALKED: THE SHELF DELTAS KEPT REPORTING NUMBERS THROUGH THE INKBIRD FREEZE, AND THEY WERE ARITHMETIC ON A DEAD SENSOR.** The deltas are **template sensors that recompute whenever the *other* input changes**, so a frozen Inkbird still yields a moving delta. Proof: 08-09→10 shows `inkbird_co2` **n=1 at 646** while `co2_shelf_delta` reports **mean +116.6** — and **646 − 529.4 (primary mean) = 116.6 exactly.** ➡️ **08-08→09 and 08-09→10 shelf deltas are VOID.** *(This also explains the "offset moved" step `room_check.py` flagged at 08-10 10:00 — that is the freeze **ending**, not a calibration shift.)*

| night | outdoor | stack ΔT | AH deficit | wind | duty 00–08 | temp Δ | rh Δ | co2 Δ |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 08-06→07 *(open)* | 13.1 | 2.9 K | 8.9 | 7.9 | **100.0%** | −0.2 | +1.1 | −69.5 |
| 08-07→08 *(open)* | 11.4 | 5.4 K | 6.4 | 5.1 | 85.2% | −0.1 | +1.8 | −20.9 |
| 08-09→10 *(closed)* | 11.6 | 5.2 K | 8.3 | 5.7 | 83.1% | — VOID — |
| **08-10→11 *(clean)*** | **6.1** | **10.3 K** | 6.6 | **15.3** | **72.4%** | **+0.3** | **+0.6** | **−20.9** |

*Deltas are bottom minus top. Outdoor from Open-Meteo 22:00–06:00; duty from the relay history.*

- **⛔ THE STATED TARGET WAS ALREADY MET BEFORE THE EXPERIMENT RAN.** Pre-closure nights show temp **−0.1 to −0.2 °C** and RH **+1.1 to +1.8** — which is precisely what `MICROCLIMATE.md`'s 07-21 scorecard already called *"flat"* and passing. **The hole closure was aimed at a gradient the fan work had largely closed.** Post-closure the bottom sits **0.3 °C warmer** than the top and RH is flatter at **+0.6** — real, right direction, small.
- **✅ THE ACTUAL PAYOFF IS HUMIDIFIER DUTY, AND IT WAS WON ON THE HARDEST NIGHT OF THE WEEK.** Duty is trending **100.0 → 83.1 → 72.4%** across the closure. Against **08-07, which had an almost identical moisture deficit (6.4 vs 6.6) but half the stack drive**, duty fell **85.2 → 72.4**. **First time the KPI's <70% target has been within reach.**
- **✅ THE RAIN OBJECTION WAS TESTED AND STRENGTHENS THE RESULT (operator raised it, 2026-08-11).** **9.4 mm fell inside the night window** and outdoor RH hit **85%** against 32–66% on other nights. **But in ABSOLUTE terms the rainy night was marginally DRIER: outdoor AH 6.3 vs 6.8 on 08-07**, because saturated air at 6.1 °C holds only **7.3 g/m³**. **The temperature drop cancelled the humidity rise, so the humidifier saw no relief from the rain.** *(Textbook `MICROCLIMATE.md` §3 — "it rained so the air was humid" is an RH intuition; what the humidifier replaces is absolute moisture.)*
- **✅ AND THE WIND MAKES IT HARDER STILL — 15.3 km/h against 2.4–7.9, roughly triple.** `MICROCLIMATE.md` records that on a front wall, gusts can locally reverse flow through the apertures regardless of fan pressure. **So stack effect was at double, wind at triple, and the moisture deficit unchanged — every infiltration driver at its weekly maximum — and duty still hit its weekly low.**
- **🔴 WHICH INVERTS THE CO2 READING: LAST NIGHT WAS THE EASIEST POSSIBLE CO2 TEST, NOT A REASSURING ONE.** Cold plus wind means the room ventilated harder than on any other night this week, and **stack effect IS this room's ventilation now the fresh-air fan is gone.** The **482 ppm trough therefore says almost nothing about whether sealing is safe.**
- **➡️ THE CONDITION ON CLOSING MORE HOLES IS NOW A MILD, STILL NIGHT — ~13 °C outdoors and light wind, like 08-06 — when stack drive is weakest.** That is the state the sealing risk actually lives in, and it has not been sampled. **⚠️ Reinforced independently by the ceiling finding above: with the shade cloth confirmed non-permeable, the exhaust strip and floor openings are the ONLY relief path.**

**🛠️ ONE TOOLING DEFECT FOUND WHILE READING THIS — ✅ FIXED 2026-08-11.**
- **`room_check.py` reported a failing KPI as a pass.** It printed `Cycling — has headroom (KPI: not pinned, under ~70%)` for **any** overnight duty ≤95%, so **76.9% read as "has headroom" while failing the 70% target stated on the same line.** Now three-state against the KPI itself — `OK` / `FAILS KPI` / `PINNED`, thresholds as named constants. Verified live and at the 70/95 boundaries.
- **✏️ A second "defect" was reported and was WRONG — recorded so it is not re-raised.** `--since` **does** exist and does what `MICROCLIMATE.md` §6 documents. **It marks the co-location start for the offset calculation; it is not a window selector** — the window is always `--hours`. Passing it alone appears to be ignored, which is what caused the misreading.

**🌐 ✅ THE 08-09 INSTRUMENT FAILURE WAS THE NETWORK, NOT THE DEVICES — established 2026-08-11, and it reattributes the Inkbird freeze.**

`room_check.py`'s sensor-health section flagged a **simultaneous ~6 h gap across every controller entity — temp, CO2 AND the humidifier relay — on 08-09 13:11 → 19:14**, plus 47 min and 64 min dropouts earlier the same day. The Inkbird stopped at **12:00**, within the hour, and did not return until **07:42 on 08-10**.

- **⛔ NOT a power cut, and the fans are confirmed turning (operator, 2026-08-11).** Cause was **the house network problems** that ended in the **08-10 router factory reset** (see §network). The mandated post-power-event fan check of `DECISIONS.md` 2026-07-17 is therefore satisfied.
- **✅ CONTROL WAS NEVER LOST — this is a REPORTING gap, not a control gap.** With mains present the ESP32 kept running and kept driving its relays. **✏️ An inference made earlier on 08-11 — that the relays de-energised and the room went ~6 h without humidification — is WRONG and withdrawn.** It would have made the 08-09→10 night look harder than it was. *(That night's duty figure is unaffected regardless: the outage ended 19:14 and the window starts 22:00.)*
- **✅ IT IS THE 2026-01-26 LOCAL-CONTROL DECISION WORKING AS SPECIFIED** — *"if the network, Supabase, or Home Assistant goes down, the climate control hardware must keep enforcing its own safety limits regardless."* **Six hours blind, room in band throughout. The cost fell entirely on the record, not the crop.**
- **⚠️ But duty figures spanning 08-09 13:11–19:14 are computed across a hole in the relay history** and should not be quoted. The per-night numbers in the table above all sit outside it.
- **🎯 AND IT REATTRIBUTES THE INKBIRD FREEZE, which this file has been blaming on the device.** The standing explanation is its *"known WiFi-drop history"*. **It stopped within an hour of the controller, during a house-wide network fault — so the network is the better explanation than a flaky sensor.** ✅ **Supporting evidence: on 08-10→11 it ran clean for the first time in this experiment — 737 points, no gaps — immediately after the network rebuild.** ⬜ **Two or three more clean nights would settle it.** The device may be materially more reliable than recorded.

**⚠️ Hinges on:** *the Inkbird staying up overnight* — still the sole instrument for the shelf deltas, but see directly above: **the reliability estimate is now in question in the device's favour.** **⛔ Note the smart-plug fix is WITHDRAWN — the device has an internal battery (`DECISIONS.md` 2026-07-19).** Full working and the per-night table: `stock-control/docs/MICROCLIMATE.md`.

**⚠️ And this is n=1.** One clean post-closure night with a live Inkbird, and **batch day 08-11 disturbs the room**. The duty trend is convincing directionally; the shelf-delta result is a single observation.

### ✅ CLOSED 2026-08-07 — THE ROOMS COOLED, THE FILTER WAS THE CAUSE, AND BOTH HAVE RECOVERED

**Full recovery confirmed. Temperature is 100% in band** — 15.20–17.50 °C, mean 16.28, against **78.4% when the fault was found**. VPD and absolute humidity both 100%. **The grow room is at 17.78 °C overnight, slightly above its pre-fault 17.25.**

| night | grow | fruiting | outdoor | fruiting − grow |
|---|---:|---:|---:|---:|
| 08-03 | 15.07 | 15.07 | 10.1 | 0.00 |
| 08-04 *(filters cleaned)* | 15.96 | 15.62 | 11.8 | −0.34 |
| 08-05 *(the clean test)* | 16.28 | 15.79 | 11.7 | −0.49 |
| 08-06 | **17.78** | **16.32** | 13.4 | **−1.46** |

**⚠️ One honest qualification, kept because it would otherwise be re-argued: the 08-06 rise was largely weather-assisted** — outdoor +1.7 and grow +1.50, near 1:1 — and **grow-minus-outdoor held flat at 4.2–5.0 K throughout the recovery, which is passive-envelope behaviour rather than thermostatic control** (the healthy period's slope was 0.02, i.e. decoupled). **The verdict rests on 08-05, where outdoor was flat and the room rose anyway. The regulation test is the next cold night: does it hold ~17.5 as outdoor falls?**

### 🎯 AND THE PARTITION COUPLING MEASURED ITSELF — the setpoint experiment, run by the weather

**The fruiting−grow gap widened 0.00 → −1.46 °C over four nights while the aircon recovered.** Grow rose **+2.71**, fruiting **+1.25** — so **coupling is 46% over the recovery, 35% on the last night alone.** This is the number `MICROCLIMATE.md` set up a deliberate experiment to obtain; it arrived free.

| Grow setpoint | Fruiting lands at | |
|---|---|---|
| 20 °C | 17.1–17.3 | ✅ in band |
| **21 °C** | **17.4–17.8** | ✅ **in band — available now, for nothing** |
| 22 °C | 17.8–18.3 | ⛔ out of band |
| 25 °C | 18.8–19.6 | ⛔ out of band |

**➡️ So the grow room can run ~3 °C warmer without pushing fruiting out of band — but 24–27 °C is unreachable while the rooms share a wall.** That splits the colonisation question in two: **21 °C is free and testable on W31/W32 now; the 24–27 °C optimum needs the separate grow room.** It is a partial win, and it prices the new grow room against a real alternative for the first time.

**⚠️ Hinges on:** *this being conduction rather than both rooms responding independently to outdoor.* **Probably conservative** — the fruiting room has the front-wall floor openings, so it is *more* outdoor-exposed and should have risen *more*, not less.

#### 🔴🔴 THE SETPOINT IS ALREADY 21 °C AND HAS BEEN "FOR A LONG TIME" (operator, 2026-08-08) — WHICH VOIDS THE TABLE ABOVE AND THE 08-06 RECOMMENDATION

**The grow room is asked for 21 °C. It has delivered 15.07, 15.96, 16.28 and 17.78 on the last four nights. That is a standing shortfall of 3.2–5.9 °C against its own setpoint, and it is not new.**

- **⛔ THE "FREE SETPOINT DIAL" IS GONE. There is nothing to turn up.** The 08-06 entry recommended *"raise the grow setpoint one step to ~20 °C"* and called 21 °C *"available now, for nothing"*. **It was already there the whole time.** The proposal was to move a control that is already past where it was going to be moved to.
- **⛔ AND THE COUPLING TABLE IS NOT A MENU OF OPTIONS.** Its rows (20 → 17.1–17.3, 21 → 17.4–17.8, 22 → 17.8–18.3, 25 → 18.8–19.6) were extrapolated from four nights of recovery **on the assumption that a setpoint is reached.** The room does not reach 21, so **22 and 25 are not choices that were rejected for pushing fruiting out of band — they are states this equipment cannot produce.** The measured 35–46% coupling figure still stands; **what it was used to predict does not.**
- **✅ AND IT EXPLAINS AN ANOMALY THIS FILE ALREADY RECORDED BUT COULD NOT ACCOUNT FOR.** The 08-07 entry notes *"grow-minus-outdoor held flat at 4.2–5.0 K throughout the recovery, which is passive-envelope behaviour rather than thermostatic control"*, and that the 08-06 rise tracked outdoor near 1:1. **A room that never reaches setpoint has no thermostatic behaviour to show.** The observation was right and the explanation was missing; this is it.
- **🔴 SO THE 08-07 "FULL RECOVERY" VERDICT IS PARTIAL, NOT WRONG.** *"Temperature is 100% in band"* was scored against the **fruiting room's** 15–18 °C band. **The grow room's own target was never checked, because nobody in these files knew what it was.** A unit sitting 3.2 °C below setpoint on its best night has not demonstrably recovered — the filter clean helped, and that is all that was shown.

**➡️ THE STRATEGIC CONSEQUENCE, AND IT RUNS THE OTHER WAY FROM 08-06: THIS STRENGTHENS THE NEW GROW ROOM RATHER THAN DEFERRING IT.** The 08-06 finding was read as *"a setpoint, not a build"* — that colonisation temperature was a dial, which *"prices the new grow room against a real alternative for the first time."* **That alternative does not exist.** The dial is already at 21 and the room delivers 17.8, so **24–27 °C is not merely blocked by the shared wall — it is beyond what this equipment delivers in this space at all.** A separate, independently heated colonisation space is back to being the only route.

**⬜ WHY IT MISSES SETPOINT IS UNKNOWN, AND THE CHEAP CAUSES MUST BE ELIMINATED FIRST — do not book a technician or price refrigerant on this.** In rough order of cost to check:

1. ~~**MODE** — a unit set to COOL at 21 °C in a room at 17.8 °C is satisfied and never runs.~~ **⛔ ELIMINATED 2026-08-08: it is on AUTO.** AUTO at 21 in a room at 17.8 calls for heat.
2. ~~**Is it actually running** — idle, fan-only, or on a timer.~~ **⛔ ELIMINATED 2026-08-08: operator confirms it runs 24 × 7.**
3. **⭐ STRATIFICATION OR RECIRCULATION DECEIVING THE THERMOSTAT — the leading candidate.** The unit is mounted high, above the rear door, and regulates on **its own return-air temperature**. If the ceiling zone reaches 21 °C while the bags sit at 17.8, the unit is "at setpoint" exactly where its sensor is looking and nowhere else. **The grow room has no circulation of any kind**, which is precisely the condition that lets a room stratify. *Check: a thermometer at bag level vs up at the unit.* **Same fault class as the fruiting room's bottom-shelf gradient, which circulation fixed.**
4. **Airflow obstruction — still live, still free to check, and it feeds candidate 3.** 96 bags are stacked in that room, and the 08-05 entry notes *"if any of it obstructs the aircon's air path or return it would reduce delivered heat progressively."* **Obstruction can also short-circuit supply straight back into the return**, so the unit reads its own warm output and cuts out early.
5. **Where is the grow-room sensor?** If it sits low, near the external door, or in a draught, it may be reading a genuine cold spot rather than the room. **Cheapest of all to check and it has never been asked.**
6. **Output or capacity shortfall.** Only after 3–5.

#### ⛔ CORRECTION, 2026-08-08 20:30 — "24 × 7" MEANS POWERED, NOT RUNNING CONTINUOUSLY. **THE COMPRESSOR CYCLES.**

**Operator: *"The aircon is switched on 24 × 7 but it starts and stops all the time. It is not stuck at on."*** **An earlier version of this section took "runs 24 × 7" to mean the compressor never stops, eliminated stratification on that basis, and concluded the unit was running flat out and losing. All of that is withdrawn.** *(It was flagged at the time as the load-bearing assumption — *"'runs 24×7' meaning the compressor genuinely never cycles off, rather than the unit merely being left switched on… the distinction decides everything above."* It did.)*

**🔑 AND CYCLING IS THE MORE INFORMATIVE FACT, BECAUSE IT MEANS SOMETHING IS STOPPING THE UNIT WHILE THE ROOM IS 3 °C BELOW ITS SETPOINT.** A unit that is genuinely undersized would run and run. **This one stops.** So either it believes it has arrived, or it is stopping for its own reasons. **Two families, and they need different fixes:**

- **A — IT THINKS IT IS SATISFIED (a sensing problem).** Candidates 3, 4 and 5 above. **The unit is fine; the air it measures is not the air the bags are in.** ➡️ Fix is circulation or sensor placement, and it is cheap.
- **B — IT IS STOPPING FOR ITS OWN REASONS (a plant problem).** ⭐ **DEFROST CYCLING is the strongest new candidate and it fits every symptom.** In heating mode at Pretoria winter temperatures the **outdoor coil frosts**, and the unit periodically reverses to melt it — delivering **no heat, or briefly cold air**, while it does. Frequent defrost is a large net loss of heat output, it presents exactly as *"starts and stops all the time"*, and **it is invisible from indoors.** It would also explain the room tracking outdoor rather than holding setpoint.

**➡️ ONE HOUR OF WATCHING SEPARATES THEM, AND IT COSTS NOTHING.**

| Observation | Reads as |
|---|---|
| Cycle interval **regular** (~30–60 min) regardless of room temperature; outdoor unit **steams, drips or is iced**; indoor air goes **cool** during a stop | **B — defrost** |
| Cycle interval **varies with load**; indoor air stays **warm** right up to each stop; outdoor coil **clean and dry** | **A — sensing** |

**⭐ AND TAKE THE SUPPLY-AIR TEMPERATURE WHILE IT IS RUNNING — still the single best diagnostic and still never taken.** A healthy reverse-cycle split in heating delivers **35–50 °C** at the outlet. **20–25 °C means it is barely heating even when it is on.** One thermometer in the outlet stream, one minute.

**⬜ Then, cheapest first:** look at the **outdoor unit for ice** (settles B outright); **thermometer at bag level vs at the unit** (settles A); **check the bag stacking** against supply and return; and the **smoke-pencil pass on the rear wall and its external door**, which the wall-removal section already wants for its own reasons — **run it once, use it twice.**

**⚠️ Hinges on:** *the grow-room temperature sensor being representative of the room.* Everything above treats 17.8 °C as what the room is. **If that sensor is in a cold spot, the room may be nearer setpoint than these files think and the whole shortfall shrinks.** **Establish where it physically sits before spending anything.**

##### 🌡️ THE TEMPERATURE READINGS TO TAKE — procedure, written 2026-08-08. Four readings, one visit, ~5 minutes.

**⚠️ Take all four AT THE SAME MOMENT and WHILE THE COMPRESSOR IS RUNNING, and write down which it was.** Mixing readings from a running and a stopped cycle produces a rise figure that means nothing. **If the unit stops partway through, wait for it to restart and take the whole set again.**

| # | Reading | Where exactly |
|---|---|---|
| **①** | **Supply air** | **In** the airstream leaving the indoor unit, a few cm in front of the outlet louvres, mid-flow. Wait 20–30 s for the reading to stop climbing |
| **②** | **Return air** | At the unit's **intake grille** (top or front face of a high wall split), a few cm off it. **This is the air the thermostat senses and it is what decides when the unit stops** |
| **③** | **Bag level** | Mid-room, at the height the bags actually sit, **out of the direct blast** from the unit |
| **④** | **Unit height / ceiling** | Near the ceiling, away from the outlet. If only one extra reading is possible, make it this one |

**Also record: where the grow-room HA sensor physically sits** (height, distance from the external door or a wall) **and its reading at the same moment.**

**📋 HOW TO READ THE RESULT**

| Comparison | Outcome | Verdict |
|---|---|---|
| **① − ②** *(the rise)* | **15–25 °C** | ✅ Unit is heating properly |
| | **under ~8 °C** | ⛔ Barely heating even when on — **family B, a plant problem** |
| **② vs ③** | within ~1 °C | No stratification — the thermostat is not being fooled |
| | **② warmer by 2–4 °C** | ⭐ **STRATIFICATION CONFIRMED — family A.** It cuts out on air the bags never see |
| **④ vs ③** | large gap | Same finding, seen directly as a vertical gradient |
| **③ vs the HA sensor** | disagree | The sensor is in a cold spot — **part of the shortfall is measurement, not heat** |

- **🔑 THE LOAD-BEARING PAIR IS ② AGAINST ③.** If the return reads ~21 while the bags read ~17.8, **the mystery is solved and the fix is circulation — cheap — not a new aircon.**
- **⚠️ Use the RISE (① − ②), not the absolute supply figure.** A heat pump's outlet temperature depends on how warm the air entering it is, so 35 °C means something quite different in a 17 °C room than in a 21 °C one. **Judging output off ① alone will mislead.**
- **Instrument: a cheap instant-read probe thermometer.** ⚠️ **The Inkbird will do at a pinch but reports at 1 °C resolution**, which is coarse for a 3 °C question — the same limitation that already killed the horizontal-uniformity read on 07-27.

**⬜ RESULTS — not yet taken.** *(Record ①②③④, running/stopped, the HA sensor's value and position, and the time. Then score against the table above.)*

**✅ HINGE CLOSED 2026-08-08 — operator: *"it is in the grow room so it can only directly control the grow room."*** The 21 °C is unambiguously the **grow room's** setpoint. **The shortfall reading stands as written: the room is asked for 21 and delivers 17.8.** *(The alternative — that it was set for the fruiting room's benefit, which would have inverted the whole reading — is ruled out.)*

**➡️ AND STATING IT PLAINLY, BECAUSE NO SINGLE LINE IN THIS FILE HAS: NEITHER ROOM IS UNDER EFFECTIVE TEMPERATURE CONTROL.** The grow room has a setpoint and misses it by 3.2–5.9 °C. **The fruiting room has no setpoint at all** — this file already records that its only temperature control is passive conduction through the 75 mm partition, with the divider door kept closed. **So the fruiting room's temperature is a by-product of a by-product**, and the 15.2–17.5 °C it currently holds is the envelope's doing as much as the equipment's.

- **This is the honest frame for the "100% in band" result of 08-07.** In-band it is, and that is worth having — **but it is not evidence of control, and it will not survive a season change.** A Pretoria summer applies heat this arrangement has no way to reject in the fruiting room, and the aircon's cooling mode is the one that dehumidifies.
- **➡️ It also re-prices item #4 of the room programme** (*"Aircon: can it be kept out of the humid air?"*). That item assumed a working unit whose placement was the problem. **The prior question is whether it meets its target at all** — relocating a unit that misses setpoint by 3–6 °C moves the shortfall, it does not fix it.

### ⛔ AND ONE THING GOT WORSE — humidifier duty is PINNED at 99.2% overnight, 98.0% overall, R433/mo

**Exactly as predicted: a warmer room needs more absolute moisture at the same RH, so recovery raised duty rather than lowering it.** It is now **the only failing KPI**. **➡️ Arm D is unblocked and is the next move** — free, ~13 duty points, and the aircon verdict it waited on is in.

---

### 🗄️ RESOLVED — the original fault report, kept for the signature

**This is the first thing to action. It was found by the weekly `room_check.py` on 2026-08-04 (the run was one day overdue).** The fruiting room has fallen **17.29 → 14.73 °C** in daily mean over four days and is **still falling**; today's minimum is **14.20 °C — below the 15 °C band floor and at the ESP32's own `temp_floor` of 14 °C.**

| Daily mean | 07-31 | 08-01 | 08-02 | 08-03 | 08-04 |
|---|---:|---:|---:|---:|---:|
| **Fruiting room** | 17.29 | 16.54 | 15.76 | 15.50 | **14.73** |
| **Grow room** | 17.73 | 16.84 | 15.95 | 15.79 | **14.52** |
| **Outdoor, 22:00–06:00** | 8.2 | 9.2 | 10.1 | 10.1 | **12.8** |

- **⛔ The outdoors got 4.6 °C WARMER while both rooms fell ~3 °C.** That inverse correlation rules out weather as the cause. Measured with `tools/outdoor_history.py`.
- **The grow room is the driver, not the fruiting room.** It fell further (−3.2 vs −2.6 °C) and the fruiting room tracks it **0.2–0.5 °C above, throughout** — which is the documented coupling working exactly as designed.
- **✅ This RULES OUT a fan death, cheaply and without a physical check.** Tight tracking between the two rooms means the fresh-air fan is moving air. The expensive theory is disposed of first, not last.
- **➡️ So the question is what stopped heating the GROW room, and the aircon is the only candidate with no telemetry.** It is still not linked to HA (no `climate.*` entity exists), so a mode change, a setpoint change, a tripped breaker or a failure would be **invisible to every dashboard**.
- **🔧 OPERATOR DIAGNOSIS 2026-08-04: the aircon filter needs cleaning — and the data is consistent with it.** Two details support *weak* output rather than *absent* output: the decline **decelerates** toward a new equilibrium near ~14.5 °C (−0.85, −0.92, −0.34, −0.38 °C/day on a like-for-like 00:00–09:00 window) instead of falling toward the envelope's no-heat balance point, and **the grow room still gains heat every afternoon** (16.6 → 18.35 °C between 11:00 and 16:00 on 08-01, with daily peaks 19.2 → 18.6 → 18.0 → 18.0). The unit is running and delivering progressively less.
- **⚠️ UNCONFIRMED — the recorder can only say "reduced heat output".** Low refrigerant, a fouled coil or a changed setpoint would look identical from the data. **The filter is the right first move because it is free, not because it is proven.** **Confirmation test: clean it, change nothing else (leave the vents alone — changing two things at once is how the vent series lost four nights), and expect the grow room to recover first with the fruiting room following toward ~17.3 °C within a day.** Re-run `room_check.py` ~24h after. If it does not recover, the filter was not the cause and the remaining candidates cost money or a technician.
- **🔬 FILTERS CLEANED 2026-08-04 ~09:30 SAST (plural — there was more than one). ⚖️ READ OUT 2026-08-05: THE DECLINE STOPPED AND REVERSED, BUT THE TEST WAS CONFOUNDED AND THE VERDICT IS NOT PROVEN.** Nothing else was changed: the vents stay in arm E and the fan stays HIGH, so this was intended as a single-variable test.
  - **The four-day slide broke.** Overnight 22:00–06:00 means, grow room: 15.61 → 15.32 → 15.07 → **15.96** for the nights of 08-01 → 08-04. The trend had been −0.25 to −0.29 °C/night; this night came in **+0.89**, about **+1.15 °C against the extrapolated trend**. Fruiting room followed at **15.6** (from 15.1), **0.2–0.5 °C above the grow room throughout** — the predicted signature, grow room leading.
  - **✅ The room stopped breaching the band floor.** Overnight minimum **15.2 °C**, back above the 15 °C floor and off the ESP32's 14 °C `temp_floor`; the 48h in-band figure rose 78.4% → **84.9%**.
  - **⛔ BUT THE NIGHT WAS 1.7 °C WARMER OUTDOORS, AND THE FORECAST WAS WRONG AGAIN — BY 1.3 °C, FOR THE THIRD TIME.** The test was designed on a forecast 22:00–06:00 mean of 10.5 °C against 10.1 on both deep pre-clean nights. **Measured actual: 11.8 °C** (`tools/outdoor_history.py`). So the ΔT was **not** comparable and the confound the design was built to exclude is present after all. *The standing instruction to confirm retrospectively against measurement, never on the forecast, has now paid for itself three times — treat it as a rule, not a caution.*
  - **⚠️ And read the size honestly: +0.89 °C is LESS than a passive envelope would give for a 1.7 °C warmer night.** That is not proof of failure — the building's 250 mm walls mean one night's outdoor step does not fully propagate — but it is the opposite of a result that clears the bar with room to spare.
  - **⛔ Recovery is far short of target.** The confirmation criterion was the room heading toward **~17.3 °C** within a day. The grow room is at **15.96**, against **17.75 on 07-30**. Roughly a third of the lost ground, at best.
  - **⛔ Humidifier duty did NOT come off its pin** — the other half of the predicted signature. Overnight **91.3%** on the post-clean night (100% on 08-03, 87.6% on 08-02), and **98.9% overnight / 97.7% overall** across the 48h window. No headroom, no improvement.
  - **⛔⛔ THIRD CONFOUND, AND IT IS THE ONE THAT KILLS THE TEST: 08-04 WAS A TUESDAY — the weekly heavy-access day for packing, removing bags and taking the last harvest (operator, 2026-08-05). THERE IS A RECURRING TUESDAY WARM BUMP, AND IT HAS A CLEAN CONTROL CASE.**
    - **Grow-room overnight means, Tuesday minus the Monday before:** 07-28 **17.85 vs 17.05 = +0.80**; 08-04 **15.96 vs 15.07 = +0.89**. **Near-identical bumps.**
    - **🎯 07-28 IS THE CONTROL — no filter was cleaned that week, and the weather moved the WRONG WAY.** Outdoor fell 11.8 → 10.2 °C (**−1.6**) between Mon 07-27 and Tue 07-28 while the grow room *rose* 0.80 °C. **Weather cannot produce that, and no maintenance was performed. The bump is the access day itself.**
    - **The bump decays:** Wed 07-29 fell back to 17.35 (**−0.50** off the Tuesday peak).
    - **✅ THE TUESDAY CADENCE IS CONFIRMED FROM THE LEDGER, NOT FROM RECOLLECTION** (`v_batch_bag_state`, read 2026-08-05). **Every substrate batch on record was packed on a Tuesday** — W26 06-23, W27 06-30, W28 07-07, W29 07-14, W30 07-21, W31 07-28, W32 08-04 (only W25, 06-18, is off-cadence). **Both batch removals were Tuesdays too**: W23 on 07-28 11:15 SAST, W25 on 08-04 13:58 SAST. **The access day is a fixed weekly rhythm and is already captured — future experiment windows can and must be checked against it.**
    - **🎯 AND THE TUESDAY STEP LANDS IN THE GROW ROOM, WHICH IS THE ROOM UNDER INVESTIGATION.** Fresh bags are packed into the **grow** room — `moved_to_fruiting` is **0** for W29, W30, W31 and W32. So each Tuesday adds a batch of freshly-packed, actively-colonising blocks to the *same room* whose heat source the aircon investigation is trying to explain, and removes a spent one. **This is not a passing disturbance to discount; it is a recurring step change in the grow room's own thermal load, on the exact day the filter was cleaned.**
    - **➡️ So the +0.89 °C on 08-04 is fully accounted for by the ordinary Tuesday effect (+0.80 measured the week before), with no residual left to attribute to the filter.** The clean happened at 09:30 on the one day of the week the rooms are opened up all day. **The single-variable test was never single-variable — the confound is weekly, predictable, and was in the recorder the whole time.**
    - **The underlying decline is real and untouched — the week-over-week shift is uniform across matched weekdays:** Mon 17.05 → 15.07 (**−1.98**), Tue 17.85 → 15.96 (**−1.89**). **A ~1.9 °C/week loss, on top of which Tuesday adds a ~0.85 °C one-night bump.** Reading the bump as recovery inverts the picture.
  - **⚠️ Duty corroborates the Tuesday effect, and points the same way:** overnight duty on Tue 07-28 was **66.5% — the lowest of that week** (Mon 76.3, Sat/Sun ~74.8), and Tue 08-04's 91.3% sits below Mon 08-03's 100%. **The access day leaves the room warmer AND the humidifier working less.** Mechanism not established — see the open question below; **do not write one down until the operator confirms what physically changes in the room on a Tuesday.**
  - **📏 DOCTRINE NOTE — sparse `humidifier_duty_1h` logging is itself the pin signal, not missing data.** The sensor only writes on change, so a pinned humidifier stops logging: n=228 on Tue 07-28 (cycling healthily) against **n=1 on Mon 08-03** — that lone "100.0%" is not a thin sample to be distrusted, it is the room sitting at 100% all night. **Read n alongside the mean; a collapsing n is a leading indicator of the pin.**
  - **✅✅ VERDICT 2026-08-06 — THE FILTER CLEAN WORKED. The Wednesday-night test passed cleanly, and it was the test designed to fail if it had not.** *(This supersedes the 08-05 verdict of "no surviving evidence in its favour", which was correct on the one confounded Tuesday night then available. The Wednesday night is the discriminating datum.)*

    | Night | Grow room | Outdoor | Note |
    |---|---:|---:|---|
    | 08-01 Sat | 15.61 | 9.2 | declining |
    | 08-02 Sun | 15.32 | 10.1 | declining |
    | 08-03 Mon | 15.07 | 10.1 | declining |
    | 08-04 Tue | 15.96 | 11.8 | **filters cleaned 09:30** — confounded by the access day |
    | 08-05 Wed | **16.28** | **11.7** | **the clean test** |

    - **🎯 THE PREDICTION WAS EXPLICIT AND IT WAS FALSIFIED IN THE RIGHT DIRECTION.** Off the 07-28 → 07-29 precedent, an *unimproved* room should have shed the Tuesday bump and **fallen to ~15.4–15.5**. It **rose to 16.28** — about **+0.8 above the no-improvement prediction**, and **+1.7 above the pre-clean decline trend extrapolated** (−0.25 to −0.29/night from Monday's 15.07 gives ~14.5 by Wednesday).
    - **✅ WEATHER IS EXCLUDED, AND MORE STRONGLY THAN PLANNED.** Outdoor was **flat: 11.8 → 11.7**. Better still, the **forecast said 13.8 and the measured night came in at 11.7** — 2.1 °C *colder* than forecast, the fourth miss on the trot, but this time in the direction that makes the result harder, not easier. **The room warmed on a night that was marginally colder.**
    - **✅ THE DECOUPLING SIGNATURE IS PRESENT.** Room-minus-outdoor widened **4.16 → 4.58 K** while outdoor held. A room tracking the weather cannot do that; a regulating heat source can. **This is the test set up on 08-05 that needed no matched night, and it fired.**
    - **✅ THE CAUSAL ORDERING IS RIGHT — the grow room leads and the fruiting room follows.** The fruiting-minus-grow offset has inverted through the episode: **+0.22, +0.10, 0.00, −0.34, −0.49** across 08-01 → 08-05. During the decline the fruiting room sat *above* the grow room; now that the grow room is being heated it sits *below* it. **The room with the heat source leads in whichever direction heat is flowing — exactly the documented coupling, with its sign flipped.**
  - **⬜ RECOVERY IS REAL BUT INCOMPLETE — about 1 °C short.** Pre-decline the grow room ran a ~**17.25** overnight mean (07-26 → 07-31). It is at 16.28 and rising, with the rate decelerating (+0.89, then +0.32), so it is approaching an equilibrium that may or may not be the old one. **Do not close the item until it settles; if it asymptotes near ~16.5 the filter was a partial fix and something else remains.**
  - **⚠️ HUMIDIFIER DUTY DID NOT COME OFF ITS PIN (91.3 → 93.7%), BUT THAT PREDICTION WAS BAD PHYSICS AND SHOULD NOT BE READ AS A REFUTATION.** It was written expecting duty to fall as the room recovered. **At constant RH a WARMER room needs MORE absolute moisture, not less** — so a recovering room should raise humidifier demand, not lower it. The duty leg of the confirmation criteria was wrong when it was written; **the temperature leg is the one that carries the verdict.**
  - **⏳ AND THE CLEAN WINDOW HAS NOW CLOSED — reading it today was not optional.** Outdoor jumps to a **~15.3 °C** mean tonight, up 3.6 °C. **Every night from here is confounded by a warming trend, so 08-05 was the last cleanly interpretable night. The verdict rests on it.**
  - **✅ Room in band through the test:** RH 91.5%, VPD 0.2 kPa, overnight minimum 15.3 °C — back above the 15 °C floor and clear of the ESP32's 14 °C `temp_floor`.
  - **➡️ THE NEXT DISCRIMINATOR IS BETTER THAN WAITING FOR A MATCHED NIGHT — and matched nights are not coming: outdoor is already at a 13.8 °C mean tonight and warming.** Over the healthy period 07-26 → 07-31 the grow room's overnight mean regressed on outdoor temperature with a slope of **+0.02 °C/°C — statistically nil.** *A working aircon regulates, so a healthy room is decoupled from outdoors.* **That is the test: over the next 2–3 nights, does the room climb toward ~17.3 °C independently of outdoor, or does it merely track outdoor upward?** Climbing while outdoor holds or falls confirms the filter. Tracking outdoor 1:1 means the aircon is still weak and the remaining candidates — refrigerant, fouled coil, changed setpoint — are live. **This needs no matched night, which is what makes it usable now.**
  - **⛔ Do NOT read this afternoon as the result.** The grow room climbs naturally from ~11:00 to ~16:00 every day (daily peaks 19.2 → 18.6 → 18.0 → 18.0 through the decline), so a rise today proves nothing. **The discriminator is the overnight window**, where the pre-clean nights are already in the recorder and directly comparable via `tools/arm_read.py`.
  - **Pre-clean baseline, like-for-like 00:00–09:00 SAST** — fruiting 17.23 / 16.38 / 15.46 / 15.12 / **14.74** and grow 17.24 / 16.26 / 15.00 / 14.80 / **14.52** for 07-31 → 08-04. **As of 09:00 on 08-04, every hour from 06:00 was still colder than the same hour on 08-03**, so the decline had not yet turned of its own accord.
  - **⛔ FALSIFIED BY MEASUREMENT — this claim is kept only as the record of how the test was lost.** It read: *"Tonight is a well-matched night… Open-Meteo forecasts outdoor 22:00–06:00 at mean 10.5 °C, against 10.1 on both 08-02 and 08-03 — so ΔT is near-identical and cannot explain a recovery."* **The night came in at 11.8 °C measured.** The forecast had already been wrong by 3.1 °C and 3.6 °C on the two prior occasions it was checked; it was wrong by 1.3 °C again here, and the note warning about exactly this sat one line below the claim it should have blocked. **A forecast is never a control variable — do not design a single-variable test on one again.**
  - **The confirm/refute criteria as written were:** grow room recovers first, fruiting follows 0.2–0.5 °C above it, toward ~17.3 °C, humidifier duty off its pin; refuted by an overnight window at or below 08-03's on a comparable ΔT. **Outcome: the first two clauses passed, the ~17.3 °C and the duty clauses failed, and "comparable ΔT" never held — so neither branch fires.** Superseded by the decoupling test above, which does not need a matched night.
- **📋 Written up as a maintenance item — `HANDBOOK.md` §"Routine maintenance".** There was no maintenance list anywhere in these docs until 2026-08-04; recurring physical obligations were scattered through this file as one-off notes. The new section carries the failure signature above so it is recognisable next time, and collects the other recurring obligations (weekly `room_check.py`, the daily water-tank fill, Monday straw chopping, post-reflash fan confirmation). **Cleaning interval deliberately left unset until the first clean shows how dirty it actually is.**
- **⚠️ Hinges on:** *that the grow room's heat source changed.* **If the aircon is found running normally at its usual setpoint, the alternative is a new envelope leak in the grow room** — its external door or the rear drywall — which is the same smoke-pencil check already flagged for the divider-wall question. Either way the answer is in that room, not in the fruiting room.

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

### Scorecard, 48h to 2026-08-05 10:40

| KPI | State |
|---|---|
| Temperature | ⛔ **84.9% in band** — 14.20–16.50 °C, mean 15.55. **Decline arrested** (was 78.4%, trending down); the 14.20 min is the pre-clean night still inside the window |
| VPD | ✅ 100% in band — 0.13–0.25, mean 0.17 |
| Absolute humidity | ✅ 99.9% in band — 10.9–12.6 g/m³, mean 12.02 — still at the bottom of the band |
| RH | ⚠️ 75.3% in band, mean 90.48 — read via VPD/AH, not raw |
| Humidifier duty | ⛔ **97.7% overall, 98.9% overnight — PINNED and WORSE than a day ago** (was 93.7/95.4; KPI is under ~70%). Power 117.3 W avg, 2.81 kWh/day, **~R432/mo** |
| Bottom-shelf gradient | ✅ Flat — overnight `temp_shelf_delta` mean +0.1 |
| CO2 | ✅ displayed trough 450 ≈ **800 true** — on target |
| Sensor health | ✅ Clean — 0.0% bad on all three controller entities, 1.1% on the Inkbird |
| **Both** CO2 sensors | ⛔ Still reading ~**350 ppm low** — the primary since 07-25, the Inkbird since 07-27. The cross-check is blind; see the live issue below. |

**⚠️ `room_check.py` flagged a CO2 offset step of −51 ppm at 08-04 11:00 — this is almost certainly the filter cleaning, not drift.** The disturbance list puts someone in the room at 10:32–11:02 the same morning, ~1 h after the 09:30 clean. Per §6 doctrine the step detector flags but does not diagnose; a known physical event at the same timestamp is the explanation. **No action — but do not let it be re-read later as fresh evidence of sensor drift.**

**⚠️ Humidifier duty went the WRONG WAY and the arm-D revert is still not actioned.** The 08-01 recommendation to revert from arm E to **arm D (every fourth hole sealed, fan HIGH)** — worth ~13 duty points — remains outstanding. With duty now pinned at 98.9% overnight and costing ~R432/mo in power, this is the cheapest lever on the board and it is free. **⚠️ But do not run it while the aircon decoupling test is live** — that is the mistake the vent series already paid four nights for. Sequence it after the aircon verdict.

**Note the trap in that CO2 row: it looks like the best result of the whole vent series, and it is an artefact of the fault.** A colder room with a stronger stack effect flushes harder. Do not read arm E's configuration as vindicated by it.

- **Temperature was fixed by the fresh-air fan**, which buffers the fruiting room against the grow room. The aircon itself hasn't changed and is still not linked to HA. Consequence: aircon IR integration (TB11) is now a nice-to-have, not the only control path.
- **The humidifier was fixed by cutting a hole in one side of the tub** (2026-07-25). It had been running flat out feeding a sealed box — mist condensed on the tub walls and drained back. Same RH and AH across the step, roughly half the duty.
  - **⛔ CORRECTION 2026-08-05 — this file said "the discs were never worn". That was an INFERENCE presented as a fact, and it does not follow.** The tub result proves the tub was *a* bottleneck, and the larger one. **It says nothing about the condition of the discs**, which have never been measured. Do not carry "the discs are fine" forward as established.
  - **➡️ AND THE DISC SWAP IS AN ENERGY PLAY, NOT JUST SPARE CAPACITY — operator, 2026-08-05.** Disc output is what sets duty at a given RH target, and **duty is what the power bill is made of.** The humidifier draws **117.3 W average, 2.81 kWh/day, ~R432/mo** — about **28% of the fruiting room's entire ~10 kWh/day** and a material slice of what this file already calls the business's single largest cost. **A 10% duty reduction is ~R43/mo; 20% is ~R86/mo — on parts already bought, for zero cash.** Filing this as "redundancy only" understated it.
  - **⚠️ BUT IT CANNOT BE MEASURED YET, AND THE REASON IS SHARPER THAN SEQUENCING ETIQUETTE: at 98.9% overnight duty the humidifier is essentially never cycling off.** There are almost no ON/OFF transitions to compare, and **you cannot measure an improvement in a device that is already flat out.** Fit fresh discs now and the result is unreadable.
  - **➡️ The right metric is NOT duty — it is RH-lift per minute of ON time**, which isolates the humidifier from the room's leakiness and temperature. **That is derivable from the recorder with no new hardware** (which is also the cheapest version of what the power-monitoring plug was for). **It needs the room off the pin first.**
  - **🎯 AND LOWERING THE TUB SIDES OUTRANKS THE DISC SWAP — operator, 2026-08-05. The reason is evidential, not preference.** Cutting **one hole** in one side halved duty at the same RH. **The tub is the only humidifier intervention with a demonstrated effect on this room; disc wear remains an untested hypothesis.** Lowering the sides is the fuller version of the change that already worked — more escape area above the water line, less fog condensing on wall and draining back — and it acts on the **proven** bottleneck rather than the assumed one. **It is also free: no parts, just cutting.** Try the mechanism that has already paid before the one that has not.
  - **⚠️ Two constraints on how far to lower it.** (1) **The tub is the reservoir** — the ultrasonic discs need their operating depth, so the walls can come down to just above the working water line **plus a splash margin**, not to it. (2) **Watch for carryover**: too low and agitation may throw droplets into the airflow instead of fog, putting free water in the supply duct. The plenum's sloped base and drain absorb some of that, but wet duct walls or drips in the room are the signal to stop.
  - **⚠️ AND UNLIKE THE DISCS, THIS ONE IS IRREVERSIBLE.** A disc swap can be undone by refitting the old discs; a cut tub cannot be un-cut. **So lower it in STEPS, measuring between them** — the first hole already showed the response is large, so there is no need to go far in one go.

**➡️ Revised humidifier queue, cheapest-and-most-proven first:** aircon verdict → **arm D** (free, ~13 duty points) → **baseline the RH-lift rate** → **lower the tub sides one step** (free, proven mechanism) → **discs last**, only if still short. **Every step after the first is a duty/energy play on a load costing ~R432/mo.**
- **The fresh-air fan must run overnight.** Its load-bearing job is **positive pressure**, not CO2 venting — switching it off (tested 07-25) let cold dry air pool in through the front floor openings and crashed the bottom shelf within hours. It came back within an hour of the fan restarting.
- **Weekly health check: `stock-control/tools/room_check.py`.** In-band scorecard, humidifier duty overnight vs midday, CO2 trough-to-trough, two-sensor drift cross-check. Run it weekly and after anything physical changes. Doctrine in `MICROCLIMATE.md` §6.

### ⚠️ Live issue — primary CO2 sensor zero shift

#### 🔴🔴 READ THIS FIRST — OUTDOOR CHECK 2026-08-11 08:45 INVERTS THE WHOLE SECTION. **THE INKBIRD IS THE STABLE SENSOR; THE PRIMARY IS THE ONE THAT MOVES. ⛔ DO NOT WRITE +210 OR +350 TO `0x006B`.**

**The operator took the Inkbird outside and it settled at 403** — flat across eight reads (401, 403, 403, 405, 405, 407) with **temperature stable at 12–13 °C**, confirming genuine equilibration rather than a wedged reading. Operator's own read and the MQTT telemetry agreed exactly, which also clears the bridge of replaying stale values.

| | reading | implies |
|---|---:|---|
| Inkbird outdoors | **404** vs ~425 true ambient | **−21** |
| Indoors 08:40 — Inkbird | 555 | true room ≈ **576** |
| Indoors 08:40 — primary | 583 | **+7 — the primary is currently ACCURATE** |

- **✅ THE INKBIRD'S ZERO HELD. It did not drift down ~190.** Its outdoor zero is **reproducible — 401 previously, 404 today.**
- **🔴 THEREFORE THE PRIMARY MOVED, BY ~+233.** The delta went **+205 (08-08) → −28 (today)** while the Inkbird stayed at ambient. On 08-08 the primary was ~226 **low**; it now reads ~7 **high**.
- **⛔ WHICH IS WHY NO STORED CORRECTION MAY BE WRITTEN.** Both candidate values (+210 and +350) were derived when the primary was low. **Writing either now would over-correct a currently-accurate sensor by 200–350 ppm, and every ventilation decision reads off that number.** This ten-minute check is what prevented it.
- **🎯 AND THE TRUST HIERARCHY IN THESE FILES INVERTS.** The primary is described throughout as *"nominally authoritative"* and the Inkbird as *"secondary/verification only"* with a flaky reputation. **On the evidence the Inkbird's zero is reproducible across outdoor checks, while the primary's has now moved twice with no established cause — 07-25 and again in the 08-09/08-10 window.** ⚠️ *This does **not** promote the Inkbird to control authority (`DECISIONS.md` 2026-05-30 stands) — but it does mean the primary cannot be trusted as a stable reference, and **an unstable zero is worse than a constant offset, because a constant offset can be corrected and this cannot.***
- **➡️ CONSEQUENCE FOR THE ROOM, AND IT BEARS ON THE "ARE WE OVER-COMPENSATING FOR CO2?" QUESTION (operator, 2026-08-11):** if the primary is accurate, **the room is running ~490–580 true, not the 692–832 the candidate corrections implied — far below the 800 target, with large headroom.** The CO2 caution that has been bounding the vent and humidity work looks **materially overdone.** ⚠️ **Hinges on:** *this outdoor check being right.* **Size of the move if wrong: it reverses the vent-sealing constraint.**
- **⚠️ METHOD LIMIT, newly identified — outdoor checks must be TIME-OF-DAY MATCHED.** Ground-level outdoor CO2 varies diurnally: the nocturnal boundary layer traps respired CO2, so **evening readings run genuinely higher than morning ones.** The 08-08 check was at **20:05 and read 457–460**; today's at **08:45 reads 404**. **Both may be correct readings of different real ambient.** ➡️ **So this method is good to roughly ±30–40 ppm unless matched for time of day** — ample to settle a 233 ppm question, **not enough to calibrate to the ppm.** Earlier entries in this section compared such readings as though ambient were a constant. It is not.
- **⬜ WHY THE PRIMARY MOVED IS UNKNOWN, and the obvious candidate cannot be tested: THE CONTROLLER EXPOSES NO UPTIME OR LAST-BOOT SENSOR.** A reboot-triggered ABC re-baseline is the natural hypothesis given the 08-09 outage window, but **"did the ESP32 reboot?" is unanswerable from Home Assistant** — the entities go `unavailable` identically for a reboot and for a network dropout. **➡️ Add an `uptime` sensor to the next reflash payload.** It is two lines of ESPHome and would have answered this immediately.

#### 🔬 INKBIRD RECALIBRATED 2026-08-08 by the operator — the cross-check should be SIGHTED again, and two things below are now stale

**Recording it immediately because the delta is about to move ~350 ppm and that must not be re-read later as a fault.** The room has been in a common-mode error since 07-27: **both** sensors ~350 low, agreeing with each other, so `co2_shelf_delta` read a healthy ≈ 0 while both under-read. Recalibrating one of them breaks that tie **on purpose**.

- **✅ EXPECT `co2_shelf_delta` ≈ +350, AND THAT IS THE SIGNATURE OF SUCCESS, NOT A FAULT.** Inkbird now correct, primary still ~350 low, delta = Inkbird − primary. **A delta that stays near 0 would mean the recalibration did NOT take.** *(This file established there is **zero real vertical gradient** between the shelves — both historical "gradients" reconciled to calibration disagreement within a few ppm. So the delta is now a live readout of the primary's zero error and nothing else.)*
- **🎯 AND IT UN-INVERTS THE POST-REFLASH VERIFICATION TEST — the original test is VALID AGAIN.** With both sensors wrong together, a successful +350 write would have driven the delta to ≈ −350, the exact signature the old text called failure; that is why the test was killed. **With the Inkbird correct, writing +350 to `0x006B` should collapse the delta from ≈ +350 back to ≈ 0** — which is the original test, working as originally written. ⚠️ **Conditional on the recalibration being sound.** The single-sensor check (primary's own displayed value jumps ~+350) remains valid regardless and is still the safer one.
- **⛔ DO NOT REVISE THE +350 `0x006B` FIGURE on the strength of whatever the new delta reads.** It rests on the 24h co-location *and* the outdoor validation of the Inkbird **before** its 07-27 step. If the new delta comes in materially off +350, that is evidence about **this recalibration**, not about the primary.
- **⚠️ IT IS ONLY SOUND IF IT WAS DONE IN FRESH OUTDOOR AIR (~425 ppm).** Recalibrating in room air at ~800 sets the zero ~375 high, and the Inkbird would then read **~50 outdoors** and ~425 in a room that is really at 800 — wrong in a new direction, and it would look plausible on the dashboard. **This is the one thing to confirm.**
- **⬜ VALIDATE BEFORE TRUSTING IT AS A REFERENCE: take it outdoors, expect 400–430.** The standing lesson holds — **the Inkbird's zero does not survive handling** (it has moved twice, 07-27 and again on return to the shelf), so it must be re-validated outdoors after every handling, including this one. **Log the delta on its return to the bottom shelf** so any step is visible.

**🔴 MEASURED 2026-08-10 — THE RECALIBRATION DID NOT HOLD, AND THE ROOM-AIR EXPLANATION IS RULED OUT.** Readings at 14:18 UTC: **Inkbird 504, primary 489, `co2_shelf_delta` +15.** The block above names **+350 as the signature of success** and says plainly that **"a delta that stays near 0 would mean the recalibration did NOT take."** It reads +15.

- **⛔ The predicted failure mode is NOT the cause.** The entry above singles out calibrating in room air as the thing to confirm. **The operator confirms it was done outdoors (2026-08-10).** So the sub-500 reading needs a different explanation.
- **✏️ NARROWED TO ONE CANDIDATE, same day.** A reboot/ABC re-baseline was offered first and is now **withdrawn: the Inkbird has an internal battery** (operator, 2026-08-10), so it did not lose power during the 08-09 event — and nobody handled it. **The "freeze" was purely the bridge polling a dead IP; the device itself ran untouched throughout.** No reboot, nothing to re-baseline.
- **⛔⛔ THE TWO BULLETS THAT STOOD HERE ARE FALSIFIED — the 2026-08-11 outdoor read settles it. THE INKBIRD'S ZERO DOES SURVIVE BEING CARRIED.** *(They asserted "the zero moves when the unit is CARRIED", called a third recurrence of "correct outdoors, wrong once back inside", and concluded that **"calibrate outdoors and carry it back CANNOT WORK for this device"**, making it *"unusable as a CO2 reference by this method."*)*
  - **It travelled out on 08-11 and read 404 against ~425 ambient — its zero was intact.** The delta collapse was **the primary moving +233**, not the Inkbird drifting on the journey. **The drift was attributed to the wrong sensor, and a whole failure mechanism was built on that misattribution.**
  - **➡️ THE PRACTICAL CONSEQUENCE RUNS THE OPPOSITE WAY: the Inkbird is PORTABLE, which makes it usable as a TRAVELLING REFERENCE — a transfer standard.** Take it out, verify against ambient, bring it in, read `co2_shelf_delta`. **If the delta moves while its outdoor zero holds, the primary drifted.** That is the procedure that just worked, and it is the only one available that has an absolute anchor.
  - **⚠️ The lesson is the recurring one in this file: a plausible mechanism is not evidence.** *(Same shape as the "spore fouling" fan diagnosis in `DECISIONS.md` 2026-07-17.)* The Inkbird had a bad reputation, the timing fitted, and no one asked whether the **other** sensor could have moved instead. **When two instruments disagree, establish which one moved against an absolute reference before theorising about mechanism.**
- **⛔ AND THE "CANNOT SIT AT AMBIENT" ARGUMENT IS WEAKER THAN IT LOOKS — it was used to distrust the correct reading.** *(It held that a respiring crop cannot sit near ~425, so both sensors reading 490–505 must be a common-mode ~350 error.)* **The room is ~65–150 above ambient, which is not "at ambient"** — and on a high-ventilation night that is entirely plausible. **The physical-impossibility check is still the right instinct** (`DECISIONS.md` 2026-07-27) **but it only refutes readings at or BELOW ambient, not modestly above it.** Used more loosely than that, it argued away a sensor that was telling the truth.
- **⛔ This still does NOT revise the +350 figure for `0x006B`**, per the prohibition above. It is evidence about the recalibration, not about the primary.
- **➡️ Do the outdoor read AFTER the 08-10→08-11 night, not before.** Handling the sensor removes the only instrument for the live vent experiment (see Room state) during its one clean window, and a very cold night is both the strongest gradient signal available **and** a poor calibration temperature for a device that operates at 17 °C. **Batch day disturbs the room anyway — that is the free slot for handling it.** Record the air temperature the calibration is done at.
- **✅ The vent experiment is unaffected by any of this.** Its metrics are `temp_shelf_delta` and `rh_shelf_delta` (−0.1 and +0.1, both live), which come from different elements on the same device and do not depend on the CO2 zero.
- **✅ Timing is fine.** The 07-28 prohibition — *"do not recalibrate the Inkbird while this runs"* — was tied to the **vent experiment**, which closed at arm E on 08-01. Nothing is running that this disturbs.

**📋 BASELINE CAPTURED FROM THE RECORDER BEFORE THE MOVE — so the step is measurable rather than remembered.** Hourly means, Inkbird − primary, 08-07 11:00 → 08-08 09:00 SAST: the delta sat in a **flat −12 to −71 band for 22 hours** (overnight 00:00–06:00: −19, −12, −19, −23, −31, −26, −18). **That is the blind common-mode state, confirmed as the starting point.**

| 15-min bucket (SAST) | primary | Inkbird | **delta** |
|---|---:|---:|---:|
| 08:30 | 499 | 515 | +15 |
| 08:45 | 493 | 519 | +26 |
| 09:00 | 492 | 509 | +16 |
| **09:15** | 525 | **657** | **+132** |
| **09:21 spot** | **545** | **731** | **+186** |

**⛔ DO NOT SCORE IT ON THESE NUMBERS — the step began at ~09:15 and the readings above are a sensor mid-transition, not a result.** Two things are moving at once: the calibration itself, and the sensor **physically re-equilibrating to room air after being in fresh air**. The 07-26 precedent is explicit — *"it rose for ~4h as the recalibration settled, then held a 340–360 band for twenty hours."*

**🎯 PRE-REGISTERED READ, written 2026-08-08 09:25 before the outcome is known. Re-read the settled delta from ~13:30 SAST, on hourly means, not a spot value.**

| Settled `co2_shelf_delta` | Verdict |
|---|---|
| **≈ +350** (say +300 to +400) | ✅ **Clean.** Recalibration took, Inkbird is a trustworthy reference again, cross-check is sighted, and the original post-reflash test is valid as written |
| **+150 to +300** | ⚠️ **Ambiguous — two causes, and they need separating.** Either the recalibration only partly took, **or the primary's error is genuinely smaller than +350.** ➡️ **The outdoor check discriminates: if the Inkbird reads 400–430 outdoors it is sound, and the `0x006B` figure is what needs revising, not the Inkbird** |
| **≈ 0** | ⛔ Recalibration did not take. Nothing has changed; the check is still blind |
| Inkbird settles **below ~450 in the room** | ⛔ **Calibrated in ROOM air, not fresh air** — zero now set ~350 high, wrong in a new direction. Redo it outdoors |

**⚠️ Hinges on:** *the +350 `0x006B` figure being right in the first place.* It rests on a 24h co-location and one outdoor validation, both from 07-26/27. **If the settled delta lands well short of 350 and the Inkbird passes its outdoor check, then `0x006B` should be written with the NEW number, not 350** — and writing 350 would over-correct the primary by that difference.

**✅ OUTDOOR CHECK PASSED — operator, 2026-08-08: calibrated OUTSIDE, read 401, now back on the bottom shelf.** That is inside the 400–430 band this file specified in advance, so **the recalibration was done in the right air and the Inkbird is validated as a reference.** It also reproduces its own prior behaviour almost exactly: it read **400–410 outdoors on 07-27** against a true ambient of ~425–430. **The same ~20–25 ppm under-read, twice, is a stable characteristic rather than a fault.**

- **🎯 SO THE EXPECTED SETTLED DELTA SHARPENS TO ≈ +326, NOT +350.** If the Inkbird is ~24 low and the primary ~350 low, then Inkbird − primary = **+326**. Still inside the pre-registered "clean" band (+300 to +400), but **+326 is the number to expect, and +350 would actually be slightly high.**
- **🔑 AND THE AMBIGUOUS BRANCH IS NOW HALF-RESOLVED IN ADVANCE, WHICH IS THE REAL VALUE OF THE OUTDOOR CHECK.** The +150 to +300 outcome had two candidate causes. **The outdoor pass eliminates one of them:** a settled delta materially below ~300 can no longer be blamed on a partial or botched recalibration. **It would mean the primary's zero error is genuinely smaller than 350 — and `0x006B` must then be written with the measured figure, not 350.**
- **⛔⛔ BUT THE 07-27 FAILURE IS SET UP TO REPEAT, STEP FOR STEP — THIS IS THE THING TO WATCH.** Today's sequence is **identical** to the one that failed: recalibrate outdoors → validate against ambient (400–410 then, **401 now**) → **return to the bottom shelf**. On 07-27 the Inkbird then **stepped DOWN ~330 ppm at the moment it was returned**, and the outdoor validation it had just passed became worthless within hours.
  - **➡️ SO SETTLING AT ~+326 IS NOT THE TEST. HOLDING THERE IS.** The pre-registered read above scores the delta at ~13:30; **that is necessary but not sufficient. Re-read it again at 24h (2026-08-09 morning).** A delta that climbs to ~326 and then decays back toward 0 is the 07-27 failure recurring, and it means the Inkbird's zero does not survive being moved **even when the recalibration itself was correct.**
  - **If it does recur, that is the trigger the "third CO2 sensor" decision has been waiting for** — not because detection is missing, but because it would establish that **this sensor cannot hold two jobs**: it cannot both live on the bottom shelf and serve as a movable calibration reference. Spec is already recorded under *Decided against*. **Do not buy on one recurrence; record it and see.**
- **✅ Bottom-shelf monitoring is live again** and, with vertical gradient established at ≈ 0, `co2_shelf_delta` is once more a direct readout of the **primary's zero error** rather than a mix of gradient and calibration.

**📊 SETTLED READ, 2026-08-08 19:56 — ~10.5 h after the step. IT LANDED IN THE AMBIGUOUS BAND, AT ≈ +200, NOT +326.** Hourly means, Inkbird − primary:

| hour SAST | 09 | 10 | 11 | 12 | 13 | 14 | 15 | 16 | 17 | 18 | 19 |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| **delta** | 176 | 222 | 208 | 209 | 235 | 210 | 210 | 195 | 191 | 194 | 204 |

**✅ IT SETTLED AND IT HELD — which is the part that matters most, because it is what failed on 07-27.** From 10:00 the delta sits in a **191–235 band with no trend** (mean ~205 over ten hours). **On 07-27 the Inkbird collapsed ~330 ppm within hours of returning to the shelf. That has NOT happened.** ⬜ **The 24 h confirmation is still due 2026-08-09 morning** — do not close this until then.

**🔴 BUT IT FALSIFIES THE +350 FIGURE, AND THAT HAS A DIRECT CONSEQUENCE: DO NOT WRITE +350 TO `0x006B`.** The pre-registered rule said a settled delta materially below ~300, **with the outdoor check passed**, means the primary's zero error is genuinely smaller than 350. Both conditions are met.

- **Cross-check on the room's true value, independent of the delta:** the Inkbird reads **401 outdoors against a true ambient of ~425**, so it sits ~24 low. At 19:00 it read **759**, putting the room at **~783 true**. The primary read **554**. **Primary error ≈ 229.** The delta and the absolute route agree at roughly **+200 to +230, not +350.**
- **⛔ Writing +350 would OVER-correct by ~120–150 ppm**, making the room display ~900 when it is really ~780 — and every ventilation decision reads off that number. **The vent series was argued to the ppm on figures like these.**

**⚠️ TWO EXPLANATIONS REMAIN, AND ONE CHEAP TEST SEPARATES THEM. Do not write any value until it is run.**

1. **The primary's error really is ~+205–230**, and the original +350 was wrong — it came from a single 24 h co-location whose reference sensor stepped twice afterwards.
2. **The Inkbird has partially drifted down again**, ~150 ppm, the same failure as 07-27 but milder. **The 401 outdoor reading does NOT rule this out** — it was taken *at* calibration, which is precisely when a sensor reads correctly by construction. **07-27 also passed its outdoor check and then drifted.**

**➡️ THE DISCRIMINATOR — take the Inkbird OUTSIDE AGAIN and read it. Free, ~10 minutes, settles it outright.**
- **Still ~400–430** → its zero held, explanation 1 is right, and **`0x006B` should be written with ~+210, not +350.**
- **Now ~250–290** → it drifted ~150 after return, explanation 2 is right, **the +350 stands**, and the standing lesson hardens: *this sensor cannot be moved and then trusted, even after a clean calibration.* That would also be the second recurrence, which is the trigger to reconsider a third sensor.

**⚠️ Hinges on:** *the primary itself not having drifted since 07-27.* Nothing has cross-checked it in twelve days, and its own zero moved once already on 07-25 for reasons never established. **If both sensors have moved, neither the +350 nor the +210 is trustworthy and the outdoor check is the only sound reference.**

> **✅⛔ RESOLVED 2026-08-11, AND THE "HINGES ON" ABOVE IS THE CLAUSE THAT BROKE — the table read the sensor right and the ACTION wrong.**
> **It read 404, i.e. the first branch — the Inkbird's zero held.** But that branch's instruction, *"write ~+210"*, **is VOID**, because the assumption named directly above it failed: **the primary had drifted, by ~+233, in the three days since.** ⛔ **Anyone following this table today would write +210 to a sensor that is already accurate.**
> **➡️ The hinges-on discipline did its job — it identified the load-bearing assumption in advance, and that assumption is exactly the one that broke.** The failure was not in the reasoning but in never testing the clause: *"nothing has cross-checked it in twelve days."* **A stated assumption that is never scheduled for a check is a prediction, not a control.**

#### ✅✅ DISCRIMINATOR RUN 2026-08-08 20:05–20:15 — THE INKBIRD'S ZERO HELD. EXPLANATION 1. **`0x006B` IS ~+210, NOT +350.**

**The operator took it outside and it settled at 457–460**, flat across four consecutive reads a minute apart, having fallen 760 → 491 → 476 → 464 → 460 over ten minutes as it equilibrated.

| Outcome predicted in advance | Reading | Verdict |
|---|---|---|
| ~400–430 → zero held, `0x006B` ≈ +210 | **457–460** | ✅ **this branch** |
| ~250–290 → drifted ~150, +350 stands | — | ⛔ **decisively excluded** |

- **⛔ THE 07-27 FAILURE DID NOT RECUR.** That is the result this test existed to get. The sensor was calibrated outdoors, returned to the bottom shelf, ran ten hours in a 191–235 band with no trend, and then **re-read outdoors near ambient.** On 07-27 the same sequence produced a ~330 ppm collapse. **This time the zero survived handling.**
- **🎯 SO THE PRIMARY IS THE ONE THAT IS WRONG, BY ~205–230 — AND THE ORIGINAL +350 IS FALSIFIED.** Two independent routes agree: the ten-hour settled delta (**~205**) and the absolute route via room-minus-primary (**~229**). **The +350 rested on a single 24 h co-location whose reference sensor then stepped twice; it does not survive a reference that holds.**
- **➡️ ACTION WHEN THE ESP32 IS NEXT FLASHED: write ~+210 to `0x006B`, NOT +350.** Writing 350 over-corrects by ~120–150 ppm — the room would display ~900 while sitting at ~780, and **every ventilation decision in this file is argued at that resolution.** ⬜ Confirm against the 24 h hold first (2026-08-09 morning).
- **✅ And the post-reflash verification test is valid as originally written**, now that the two sensors genuinely differ: after the write, `co2_shelf_delta` should collapse from ~+205 to ≈ 0. The single-sensor check (primary's own displayed value rises ~+210) remains the safer confirmation.

**↩️ RETURNED TO THE BOTTOM SHELF 2026-08-08 ~20:20 SAST, logged as the standing instruction requires** — this is the exact action that broke it on 07-27, so the timestamp is the thing that makes any step visible. **First reading back in, 20:26: Inkbird 737, primary 562, delta 175**, still climbing out of outdoor air toward room level. **No collapse in the first six minutes. ⬜ The 24 h hold check on 2026-08-09 morning is what closes this** — expect the delta back in the 191–235 band.

**⚠️ ONE METHOD CORRECTION, so 457–460 is not later misread as the sensor sitting ~30 ppm HIGH: THE OUTDOOR CHECK MUST BE DONE IN DAYLIGHT.** The *"expect 400–430"* band in this file was set from **daytime** ambient. **Outdoor CO2 near ground level is genuinely elevated at night** — a stable nocturnal boundary layer plus soil and plant respiration routinely puts a suburban garden at 450–550 after dark, against ~420–430 by day. **This read was taken at 20:10.** So 457–460 at night and 401 at ~09:00 are consistent with the *same* sound sensor, and **neither reading establishes an absolute offset.** ➡️ **Amend the standing instruction: re-validate outdoors in daylight, in open air, and treat a night-time check as directional only.** It was still decisive here, because a 150 ppm drift would have read ~300 whatever the hour.

`sensor.fruiting_room_fruiting_room_controller_co2` took a **one-off ~90 ppm downward zero shift** at ~08:35 on 2026-07-25. It is a single discrete step, not a runaway — the Inkbird-minus-primary offset went from a settled ~+185 to a settled ~+276 and has held there. Trigger unknown; a power cycle is ruled out (no reporting gap).

- **Carry it as an explicit +350 ppm mental offset** (was +90 until the 2026-07-27 co-location corrected it). It is applied nowhere in software.
- **Consequences while uncorrected:** variac tuning should target a **displayed ~450**, not 800 and not the ~710 previously recorded — the old figure would badly over-ventilate. **The room is already near target**: primary ~417 displayed ≈ ~765 true, so expect far less tuning headroom than assumed. The HA alarm's `co2_high` leg needs a true ~1846 to fire — more deeply unarmed than previously thought. **Do not flash the shelved proportional-CO2 firmware** while the sensor is off.
- **The fix goes on the ESP32 via register `0x006B`, not in Home Assistant** (decided 2026-07-26, rationale in `DECISIONS.md`). **⚠️ Do not add an HA template sensor as a stopgap** — that reverses the decision and creates the invisible trap it was made to avoid. The wait is acceptable because CO2 currently drives nothing.
- **The SEN0659 exposes only four registers** — CO2 read, address, baud, and `0x006B` correction (±1000 signed). There is **no ABC-disable and no calibration command**, so periodic re-checking is permanent for the life of this sensor. "Disable ABC" is not available.
- **🔬 Co-location READ OUT 2026-07-27 11:30 — the +90 prediction is FALSIFIED. The settled delta is +346.** 24h mean over 1,439 minutes (07-26 11:30 → 07-27 11:28): primary 461.4, Inkbird 807.0, **delta +345.5** (last 12h +352.8, last 6h +356.1). It rose for ~4h as the recalibration settled, then held a 340–360 band for twenty hours, tracking every diurnal move in lockstep. **A rock-stable additive constant between two co-located sensors is the signature of a zero-point error, not gradient and not noise.**
  - **Reinterpretation:** most of the old apart-delta of +185 was never vertical gradient — it was sensor-to-sensor calibration disagreement all along. The 07-25 step added a real ~90 on top, and the fresh-air recalibration lifted the Inkbird ~70 (it had ABC-drifted low, as it will again).
  - **Independent confirmation that does not require trusting the Inkbird:** the primary reads 400–460 ppm against an outdoor ambient of ~425. **A ventilated room full of respiring mushrooms cannot sit at or below outdoor ambient** — so the primary is reading far low whatever the Inkbird says. The Inkbird's ~760–800 is an unremarkable fruiting-room value.
  - **✅ Dependency CLOSED 2026-07-27 — the Inkbird's calibration is sound.** Taken outside, it read **400–410** against a true ambient of ~425–430. That rules out the failure mode that mattered: had it been recalibrated in indoor air at ~700, it would have read ~125 outdoors, not ~405. **The `0x006B` value is confirmed at ~+350.** (Strictly the Inkbird itself sits ~20 ppm low against true ambient, so the fully-corrected figure is nearer +366 — but that is inside the SEN0659's own ±50 ppm accuracy spec, so **+350 is the number; chasing the last 20 ppm is false precision.**)
  - **✅ The whole history now reconciles on gradient ≈ 0.** Calibration disagreement co-located = +346, of which ~70 came from the recalibration, so the pre-recalibration disagreement was ~+276 — exactly the apart-delta measured after the 07-25 step, leaving **zero real vertical gradient**. Back it out one more step and the pre-step disagreement was ~+186 against an apart-delta of +185. **Both historical "gradients" were calibration disagreement to within a few ppm. There has never been a measurable CO2 gradient between the shelves.**
  - *(The 07-21 "baseline" was never a CO2 one — it used the temp/RH sensor 3.85 m away. Don't rely on its +70 ppm figure.)*
  - **↩️ Inkbird returned to the bottom shelf 2026-07-27 ~12:00**, below the temp/humidity sensor. The `*_shelf_delta` sensors mean what their names say again and the bottom shelf is monitored again.
  - **⛔ THE "+346 NEW BASELINE" IS FALSIFIED — the Inkbird's zero moved too. Found 2026-07-28 by the weekly `room_check.py`.** The predicted post-move baseline of ≈ +346 never materialised. **At ~12:00 on 07-27 — the moment the Inkbird was returned to the bottom shelf — the Inkbird stepped DOWN ~330 ppm while the primary held.** Hourly means: Inkbird 735 (11:00) → 481 (12:00) → 419 (13:00); primary 409 → 428 → 411 across the same hours. Over the 19 hours since, **the delta has settled at ≈ −5 ppm** (range +17 to −31), the two sensors tracking each other's diurnal shape in lockstep.
    - **One sensor stepped while the other held, and the temp shelf delta stayed flat** (Inkbird−top within ±0.5 °C throughout). That is `room_check.py`'s own discriminator for a calibration shift rather than a room event — and it coincides exactly with a physical handling of the Inkbird, which had been taken outdoors that morning.
    - **⚠️ Both sensors now read at or below outdoor ambient — which is physically impossible for this room.** Current readings are ~430–520 on both, against ~425 ambient. **The same argument that convicted the primary on 07-27 now convicts the Inkbird: a ventilated room full of respiring mushrooms cannot sit at ambient.** The Inkbird is now under-reading by roughly the same ~350 as the primary.
    - **The +350 correction for the primary still stands.** It rests on the 24h co-location *and* on the outdoor check that validated the Inkbird **before** this step (400–410 against ~425–430 true). That evidence is untouched by what the Inkbird did afterwards. **Do not revise `0x006B` downward** on the strength of the two sensors now agreeing — they agree because they are now wrong together.
    - **Mechanism not established.** ABC re-zeroing after the outdoor excursion is the obvious candidate, but it is not proven and should not be written down as fact. What *is* established: the Inkbird's zero is not stable across handling, so **it cannot be moved and then trusted as a reference without re-validating it outdoors each time.**
  - **⛔ THE POST-REFLASH VERIFICATION TEST IS DEAD — and if used as written it will actively mislead.** It said: write +350 to `0x006B`, expect `co2_shelf_delta` to collapse to ≈ 0 as proof the write took; ≈ −350 would mean the sign encoding was wrong. **The delta already reads ≈ 0, before any flash.** So a successful write would push it to ≈ **−350** — the exact signature the old text calls a sign-encoding failure — and a *failed* write would leave it at ≈ 0, the signature it calls success. **The test is inverted. Do not use it.**
    - **Replacement check, and it needs no second instrument:** after writing +350, the **primary's own displayed value** should jump ~+350 (to ~800 overnight trough, not ~450). That is a before/after on one sensor and cannot be confused by the Inkbird's state. Confirm against the pre-flash hourly means recorded above.
    - **Re-validate the Inkbird separately** whenever it next matters: take it outdoors, confirm it reads ~400–430, and only then treat it as a reference again.
  - **The "free bonus" horizontal-uniformity read did not work — don't retry it this way.** With the Inkbird on the left wall and the primary on the right, `temp_shelf_delta` / `rh_shelf_delta` should have measured horizontal uniformity. But the Inkbird reports temperature at **1 °C resolution** and logged only **61 points in 24h** (going stale by 10:18), so subtracting its +0.9 °C offset is meaningless against 1 °C quantisation. Horizontal uniformity needs its own method and a sensor with usable resolution.
- **Ongoing drift detection is built and free — ⛔ it was BLIND from 07-27, and the 2026-08-08 recalibration is the fix.** `sensor.co2_shelf_delta` catches a *step*, meaning one sensor moved relative to the other. It caught the 07-25 primary shift and it caught the 07-27 Inkbird shift. **What it could not catch was the state the room then sat in: both sensors wrong by the same ~350, so the delta read a healthy ≈ 0 while both under-read.** A common-mode error is invisible to a differential check, by construction — **and the only way out of it is to move one sensor's zero deliberately, which is what the recalibration did.**
  - **Until the recalibration is validated outdoors, keep using the physical-impossibility argument as the backstop** — if the room reads at or below the ~425 outdoor ambient, it is wrong, whatever the delta says. It needs no second instrument and it convicted both sensors in turn.
  - This is the concrete cost of the Inkbird holding two incompatible jobs (continuous bottom-shelf monitoring *and* cross-check reference), which the "Decided against" section already names. It does **not** yet meet that section's stated trigger for buying a third sensor — CO2 still controls nothing, so a wrong reading misleads a human but cannot mis-actuate. **Writing the `0x006B` correction is the fix; a third sensor is not.**

## Hardware — current configuration

- **Circulation fan: ACDC Dynamics WF-150**, mains 230V induction, inline mixed-flow. **⚠️ RUNNING ON HIGH, and BOTH duct end caps (supply and return) are OPEN — corrected here 2026-07-28; this entry previously said "running on LOW, do not raise to high", which had been stale since 07-21 and told readers the actual state was forbidden.**
  - **It is a recorded deliberate tradeoff, not drift.** `stock-control/docs/MICROCLIMATE.md` (Ducting): the return duct's end cap was removed on **2026-07-21, with the WF-150 put on high**, to cure a production humidity shortfall — the hole-only return was thought to be throttling circulation through the plenum and starving moisture delivery.
  - **⚠️ BUT THE JUSTIFICATION HAS BEEN SUPERSEDED.** On **2026-07-25** the real cause of that shortfall was found: **the humidifier was misting into a sealed tub**, condensing and draining back. Cutting a hole in the tub side fixed it at roughly half the duty, same RH. **So the fan is on high and two end caps are off to compensate for a problem that was somewhere else entirely.** The room is running further from the distributed-low-velocity design bet than intended, for a reason that no longer holds.
  - **The cost is crop quality, not power** — the WF-150 draws 23/26 W, so the speed difference is trivial on the bill. What it spends is the core design bet: low-velocity, well-mixed, **no direct draft on the caps** (`MICROCLIMATE.md` KPI 5 — too much airflow dries caps and raises local VPD).
  - **🎯 REVERT TEST, one variable at a time, after the floor-vent experiment resolves** (do not run concurrently — circulation changes would confound it). Cheapest and most reversible first: **(1) fan to LOW** — free, instant, watch overnight humidifier duty against the 76.3% baseline; if the tub fix did the real work, duty should hold. **(2) return duct end cap back on** — same metric, another 24h. **(3) supply duct end cap last**, since that has governed room behaviour since 07-10 and is the deepest change.
- **Fresh-air fan: 100mm 2-speed AC inline (ACDC)**, mains, **on HIGH** — ✏️ *corrected 2026-08-11; this line read "on LOW" and had been stale since the **2026-07-30 Arm C decision to leave it on HIGH**, where high beat low on every axis.* Governs five coupled jobs — CO2, temperature coupling to the grow-room aircon, grow-room ventilation, positive pressure, humidifier drying load. **It is a 2-speed switch: there is no "slightly slower" without fitting the variac, which has been rejected on measurement twice.**
- **Both fans run off-controller** (mains, not on MOSFET/GPIO). The ESP firmware does not bind relay sockets 1 and 4 to them, so `switch.…_socket_1` / `_socket_4` read `off` while the fans run on manually-forced power.
- **The HA fan entities `fan.*_circ_fan` and `fan.*_fresh_fan` drive nothing.** Masked by an entity-registry name override reading "PHANTOM … drives nothing"; `entity_id`s unchanged so automations are unaffected.
- **No tacho on either fan** — HA cannot tell a spinning fan from a dead one. **After any reboot, reflash or power event, physically confirm both fans are turning.**
- **⛔ Never buy another SEAFLO SFIB1-130-01** for a 24/7 position — a marine bilge blower rated 600–700h *intermittent*, i.e. a ~1–3 month consumable here. Both original fans died this way.
- **Sensors:** RS485 DFRobot SEN0659 (CO2) + SEN0438 (temp/RH) on the shared TB7 bus, Modbus addresses 1 and 2 (3 is free). Grow-room DHT22 monitoring-only. Inkbird as secondary/verification only, never control.
- **Home Assistant** — reach it as **`homeassistant.local`**, not by IP (see the network block below). ESP32 is on `pret208-ext` (D-Link extender, channel 11) and answers to **`fruiting-room-controller.local`**.
- **Lovelace can be edited programmatically** — via the WebSocket API (`lovelace/config`, `lovelace/config/save`, `url_path: fruiting-room`), **not** by writing `.storage` directly, which HA clobbers. Back up first; a save replaces the whole view.

### 🌐 THE NETWORK — rebuilt from scratch 2026-08-10 after a factory reset, and now addressed by NAME

**What happened.** Sunday 2026-08-09: no internet. Root cause was an **authentication failure at Openserve** (the fibre infrastructure provider) — **not a fault on this property, and nothing here caused or could have prevented it.** During Afrihost's troubleshooting the operator was instructed to **factory-reset the TP-Link EX511 main router**, and later to connect the workstation directly to the fibre box. The line came back. **The router's entire configuration did not** — and because nobody had a backup of it, the LAN silently re-addressed itself from `10.0.0.0/24` to `192.168.0.0/24`, breaking every hard-coded address in this repo at once. Rebuilt and verified 2026-08-10.

**✅ Current configuration — measured, not assumed:**

| | Value | Notes |
|---|---|---|
| LAN | `10.0.0.0/24`, router **`10.0.0.2`** | TP-Link EX511 in router mode |
| DHCP pool | **`10.0.0.120`–`10.0.0.200`** | **Deliberately above the reservations — see the trap below** |
| HA Pi | **`homeassistant.local`**, reserved `10.0.0.110`, MAC `2c:cf:67:65:1a:b7` | wired |
| Fruiting-room ESP32 | **`fruiting-room-controller.local`**, reserved `10.0.0.111`, MAC `80:f3:da:54:9b:14` | on `pret208-ext`, firmware 2025.10.5 |
| Inkbird | `10.0.0.107`, MAC `1c:90:ff:9d:9b:7a` | bridge add-on `device_ip` must match |
| Main SSID | **`pret208-2.4G`**, 2.4G **fixed channel 1**, 5G ch 36 | channel 1 is the printer's lifeline, `DECISIONS.md` 2026-07-22 |
| Extender | `pret208-ext` ch 11, `10.0.0.99` | D-Link, Ethernet-backhauled, **bridging not NAT-ing** |
| Printer | `10.0.0.106` | HP DeskJet 3835, 2.4GHz-only |

**🎯 THE STRUCTURAL CHANGE, AND THE REASON THIS DAY WAS WORTH SOMETHING: EVERYTHING IS NOW ADDRESSED BY mDNS NAME, NOT BY IP.** `homeassistant.local` and `fruiting-room-controller.local` are answered by the devices themselves over link-local multicast — **no router DNS, no internet, and they survive a subnet change.** They kept resolving on 2026-08-10 when every hard-coded address in these files was dead. `LEDGER.md`'s deploy path and panel URL were re-pointed at the hostname the same day, and the phone's home-screen icon should be too.

**⚠️ THE TRAP THAT COST AN EXTRA ROUND-TRIP: a DHCP reservation inside the active DHCP pool is not guaranteed.** `10.0.0.110` was reserved for the Pi while the pool still ran from `.100`, and **a phone with a randomised MAC already held that lease** — so the router quietly ignored the reservation and the Pi came up on `.114` instead. **Reservations must sit BELOW the pool**, which is why the pool now starts at `.120`.

**📌 THE STANDING LESSON: there was no router configuration backup, and a factory reset is one support call away.** ISP support asks for a reset as a matter of routine — it is their cheapest diagnostic and costs them nothing. **What it cost here was every static address on the property, silently**, on the day before a batch, discovered only because someone went looking. **⬜ But the recovery plan is NOT the router's own backup file, and it is worth being clear why.** A TP-Link `.bin` config is **tied to the firmware version that produced it** — after a firmware update the router will often refuse to restore it — so it is a shortcut, not a foundation. **The durable asset is the settings table above:** it is plain text, in git, readable by a successor, and it does not rot. Restoring from it by hand is the ~15-minute job that was actually done on 2026-08-10.

**➡️ So the complete recovery kit is: the table above, plus three secrets that must NOT be in git** (`SAFETY.md`) — the **`pret208-2.4G` WiFi password**, the **router admin password**, and the **Afrihost PPPoE username/password**. Put those in a **Bitwarden secure note**, which works on the free tier. ⚠️ **Bitwarden *attachments* require a paid plan**, so if the `.bin` is kept at all, keep it the way the Aegis backup is kept — local copy plus a second copy on Google Drive. **The `.bin` can carry the PPPoE and WiFi credentials in the clear; it never goes in a repo.**

**🔍 And the failure that started it was invisible from inside.** A PPPoE authentication failure at the ISP looks, from the LAN, exactly like a working network: the router is up, WiFi is up, devices have addresses. **Anything cloud-hosted simply reports an error that does not mention the network** — which is how the outage was misread for a while. Home Assistant, by contrast, is on the LAN and *should* stay reachable through any WAN outage; it did not, only because it was being reached by an address that had moved. **With mDNS names in place that specific failure cannot repeat.**

### ⚠️ Next reflash — read this whole block before touching the firmware

Nothing here is urgent alone. The point is that these are all **gated on the same reflash**, so do them together in one attended session rather than discovering them one at a time.

**Decide first: which ESPHome toolchain owns the controller.** The running firmware was built by the **HA add-on's ESPHome 2025.10.5**; the laptop has **2026.6.5** and a stale 07-10 build that is not what's deployed. Flashing from the laptop jumps ~8 months of versions on a controller whose RS485 sensors depend on a hand-written raw-UART lambda. The repo yaml is byte-identical to the device's source, so there's no drift — just a version decision to make deliberately. **Low-risk option: reflash from the HA add-on at the version that built the running firmware** — confirm it hasn't auto-updated first.

**Payload:**
1. **⛔⛔ WRITING THE CO2 CORRECTION TO `0x006B` IS SUSPENDED — DO NOT WRITE ANY VALUE (2026-08-11).** *(This item previously read "the value is **+350**, measured and confirmed 2026-07-27… no dependencies left." **That is withdrawn.** The outdoor check of 2026-08-11 found the primary reading **~+7, i.e. accurate**, having moved ~+233 since 08-08. **Writing +350 — or the later +210 — would over-correct a currently-accurate sensor by 200–350 ppm.**)* **The blocker is no longer the value; it is that the primary's zero MOVES.** A stored offset only helps a sensor with a *constant* error, and this one has shifted twice with no established cause. **Re-establish stability across at least two time-of-day-matched outdoor checks before writing anything.** Full working: the live-issue block above. *(Kept for whenever it is unblocked: needs Modbus function `0x06`, which the present read-only lambda cannot do; encoding ±1000 signed, positive 0–1000, negative 64535–65535.)*
   - **➡️ ADD AN `uptime` SENSOR WHILE THE FIRMWARE IS OPEN.** Two lines of ESPHome. **"Did the controller reboot?" is currently unanswerable from HA** — entities go `unavailable` identically for a reboot and a network dropout — and that blind spot is exactly what stopped the 08-11 investigation from testing a reboot/ABC re-baseline as the cause of the primary's shift.
2. **Bind relay socket 1 to the fresh-air fan.** ⚠️ Socket 4 is the circulation fan — **do not actuate it on a guess**; cutting it crashed RH before.
3. **Relabel or remove the phantom fan entities at source**, so the fix survives independently of HA's registry.
4. **Consider the GPIO21 tacho** if the fan rework is in scope — it is what makes a fan death alarmable.
5. **⚠️ An uncommitted variable-speed draft is HELD in the working tree** of `stock-control/esphome/fruiting-room-controller.yaml`. It rewrites fan control for a 12V ebm-papst that was never bought. **Check `git diff` before flashing; do not ship it by accident.**
6. **After the flash, physically confirm both fans are turning.** A reflash is exactly what killed the circulation fan on 07-16.

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

  **The build, as it actually stands (operator, 2026-08-10):** a **polystyrene tub with a matching polystyrene lid**; a **10 mm foam plastic mat with a hole per bottle** suspending **11 bottles** so they **do not touch the tub floor**, submerged to the neck; **~28 L** of water to that level; a **Dophin AH-1008-4, 150 W** aquarium heater. **No pump and no thermostat controller yet.**

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
