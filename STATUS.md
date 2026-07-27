# Status

Last updated: 2026-07-26

**What this document is.** A plain answer to *what is true right now*. It is deliberately short.

- **History** lives in git (`git log -p STATUS.md`). Don't keep superseded entries here.
- **Why** things are built as they are lives in `DECISIONS.md`.
- **What to do next** lives in `todo.fungi4u` in Home Assistant — the actionable worklist, ordered by distance to income.
- If an entry here is only interesting because of how it was discovered, it belongs in `DECISIONS.md`, not here.

---

## Priority order — read this first

The objective is income for the family, via *committable* supply → new clients. Ranked by distance to that objective:

1. **Demand / new clients** — the Menlo Park Spar step. Demand is the binding constraint, not yield.
2. **Cheap yield levers** — single-variable airflow/humidity experiments.
3. **Everything else** — microclimate build-out, monitoring, telemetry, dashboards, doc hygiene. Enabler or insurance, not the front of the queue.

*(The harvest scale was #1 until it was bought on 2026-07-22.)*

**Standing test for any task:** does it move committable supply or a client this month? If not, it waits.

**The trap:** microclimate and monitoring work is more tractable and more enjoyable than sales, so it will keep pulling attention. Treat that pull as the cue to re-read this list. As of 2026-07-26 the room is fully in band and has no live crop emergency — so there is nothing here justifying more room work ahead of demand.

## Business snapshot

- **3 customers, ~31 punnets/week @ R40 → ~R5,370/mo.** Lynnpark 20 (cash on delivery), Vula 4 (monthly), Orchard 6–8 (prompt). About a quarter of the R20,000/mo objective.
- **Known costs ~R3,100/mo** (Jesca R1,430, Capitec fee R400, substrate R680, punnets R270, gas R320) **plus electricity ≈R1,400–1,560/mo** — the fruiting room measured at ~10 kWh/day, ~36% of the property. Electricity is the single largest cost, bigger than Jesca.
- **The operation is near true break-even, not comfortably positive.** Most of any transfer to Wessel reimburses power he already pays personally.
- **Filling the room is what turns power from a burden into leverage** — the room costs much the same half-full as full. This strengthens the demand case.
- The Lynnpark cash (~R800/wk) is the real margin and is **untracked**. Banking it is the cash equivalent of ledger discipline.
- The ~R34k of personal money that built the operation was one-off *capital*, not running cost.
- Full numbers: `stock-control/finance/CASHFLOW.md`. Money of record stays in Sage/Capitec.

## Sales & growth gate

**The gate has moved from yield to demand.** With grey oyster as the only product, the 3 existing customers won't take more however much is grown. Growth needs new customers. *(Product diversification is the other untested demand lever — not explored.)*

- **Menlo Park Spar** will test grey oyster on shelf **if there's a barcode on the label**. First new-client approach.
- **Barcode: ✅ PAID 2026-07-27 — R202.40** (R176 + R26.40 VAT) for a GS1 SA single GTIN, account `fungi4ushop@gmail.com` at **`gs1zace.gs1za.org`**. **⚠️ Buying the number is not the end of it — the GTIN must still be assigned to a product record** (brand, description, net content, category, target market) before it resolves to anything. An unassigned GTIN scans as an unknown item on a retailer's system, which is a worse failure than no barcode because it looks done. (GS1 SA is the only legitimate SA source — reseller-sold barcodes get rejected by the big retail chains). **One GTIN = one product *and* pack size**, so 250 g grey oyster is one number; a 500 g pack later is another R176.
  - **Once-off, on the balance of evidence — but worth one confirming question.** The public cost table and the cart line item (*"1 Number Licence (Once-Off Fee)"*, entrance fee R0) both read once-off; only a generic "Annual Renewal Fee" template field on the add-to-cart page said otherwise. **R202.40 payable** — R176 + R26.40 VAT.
  - **A GS1 account requires a completed company application, not just a user profile.** Registering an email gets you a login; the cart rejects it with "user not associated with an account" until the organisation application is done. Account opened 2026-07-27 under `fungi4ushop@gmail.com`.
- **Next action, and it scopes everything else: get Spar's full supplier requirement list.** The barcode is unlikely to be the only blocker, and their onboarding checklist tells you exactly which regulations bind — so you comply with what's required rather than everything imaginable.
- **⚠️ THE RISK HAS FLIPPED — supply → sell-through (2026-07-27).** The owner said directly: **give him the barcode and he will put it on the shelf to monitor demand.** That is a *trial*, not a supply agreement — small volumes, no committed quantity — so the old worry ("Spar onboarded on an expectation, committable volume unproven, failing to supply a Spar is worse than never approaching one") is largely defused. **The new failure mode is that it doesn't sell.** Presentation on shelf and shelf life now matter more than production volume: mushrooms that sit and degrade unsold report weak demand for reasons that are not demand.
- **This is the demand experiment, and it is nearly free.** That demand is the binding constraint is an *assumption* everywhere in these docs. A shelf trial measures it directly, at the store's risk. Treat the result as the most valuable data the business can currently obtain.
- **Terms as at 2026-07-27: mushrooms supplied FREE for the trial; Spar considering R59 shelf price.**
- **Free is cheap here, and the reason matters: demand is the constraint, not production.** Trial punnets do not displace sales to Lynnpark/Vula/Orchard — those three won't take more. So the real cost is **marginal, ~R7/punnet**, not the R40 otherwise booked. ~10/week for 4 weeks ≈ **R280 total** for the most valuable information the business can buy.
- **Three conditions on the free supply — the second is the one that gets skipped:** (1) **a defined end date** (4 weeks is a normal produce trial); (2) **agree the post-trial price NOW, in writing** — even WhatsApp: *"free for 4 weeks from [date], thereafter R40/punnet"*, because free arrangements without an agreed conversion date tend to continue, and the conversation only gets harder; (3) **weekly sell-through numbers, in units** — without this agreed up front you have funded an experiment and received an anecdote.
- **The downside of free: no skin in the game.** A retailer who paid for stock chases the sale. Free stock can sit in a poor spot and quietly underperform, so ask about placement and restock cadence explicitly.
- **R59 supports the existing price — the economics already work.** R59 shelf against R40 wholesale is R19, **32% of retail**, squarely in the normal fresh-produce band (30–40%). If he pushes for a full 40% margin he'd want ~R35, which still contributes ~R28 marginal — but **R40 is defensible at R59 and should be held.**
- **⚠️ Reading the result: the trial tests the product AND R59 together.** Weak sales at R59 is not the same finding as weak demand — it may be a price signal. If it underperforms, have the promotional-price conversation before concluding grey oyster doesn't sell in Menlo Park.
- **⚠️ Operational: free punnets still leave stock and must be recorded** as a stock-out event through the SQL functions (`SAFETY.md` — all movement goes through them). **Check whether a sample/promotional code exists in `stock_reason_codes` BEFORE the first delivery**, or reconciliation and yield figures will drift.
- **Cold storage is at its limit** — a capacity constraint on growth. The current unit is the **chest freezer** (business load; on the meter 07-27 → 07-28).
  - **⚠️ The ~R707/mo "fridge saving" is AVOIDED COST ON A PURCHASE NOT YET MADE — clarified 2026-07-27. It is R0/mo today.** There is no glass-door unit; the ~R8,000 second-hand buy is prospective. R707 is the gap between running *that* unit gutted vs ungutted (72 W lights + 80 W door heater ≈ R560/mo at R5.12/kWh, plus the cooling load to remove the heat they dump inside the cabinet — the arithmetic checks out). **Do not book it in `CASHFLOW.md` as a saving available from the existing setup.**
  - **⚠️ Challenge the glass-door choice before spending R8,000.** The gutting plan includes insulating over the glass — at which point you own a badly-made solid-door fridge, having paid labour to cancel the unit's own design premise. It is wanted for **storage only**, so a glass door is pure liability. **Price the alternatives first:** another chest freezer on an external thermostat (the form factor already working here, and the most efficient there is — cold air does not spill out when the lid opens), or a second-hand solid-door commercial unit. Glass-door is only right if it buys materially more capacity per rand, which it may given shop-closure supply. Check, don't assume.
  - **Timing: not urgent, and buying ahead of the Spar answer is backwards.** The trial is small volumes supplied free — it will not strain cold storage. Spending R8,000 at near break-even, before the trial says whether demand justifies more capacity, is the wrong order.
  - **The chest-freezer reading is the benchmark for any purchase** — kWh/day per litre of usable capacity. Without it there is nothing to judge a quote against.

## Regulatory & compliance — to verify, not confirmed

A landscape to check with each authority, **not legal advice**. It mostly gates the formal-retail (Spar) path; the existing informal customers presumably don't trigger most of it, so this rises in priority in proportion to the bet on Spar. Don't gold-plate.

- **Legal metrology (NRCS)** — selling *by weight* needs a trade-approved/verified scale. **But** pre-packed punnets at a fixed price may not trigger it; what bites then is accurate net-weight declaration. **Confirm which model applies before buying a verified scale.** The bench scale already bought is fine for internal yield measurement either way.
- **Food-handling premises** — a Certificate of Acceptability from municipal environmental health. Supermarkets often require it of suppliers.
- **Food labelling** — name, net weight, producer, batch/date, origin, barcode. Overlaps the Spar label work.
- **Business/tax registration** — CIPC / SARS / VAT threshold. May already be sorted.

## Room state (verified 2026-07-26 off 24–60h of recorder data)

**The room is in the best measured state it has been in.**

| KPI | State |
|---|---|
| Temperature | ✅ 100% in band — 16.5–17.9 °C, mean 17.25 |
| VPD | ✅ 100% in band — 0.15–0.26, mean 0.19 |
| Humidifier duty | ✅ 50–85% (was pinned 95–100%) |
| Bottom-shelf gradient | ✅ Flat |
| Primary CO2 sensor | ⚠️ Reads ~**350 ppm low** (measured & confirmed 2026-07-27) |

- **Temperature was fixed by the fresh-air fan**, which buffers the fruiting room against the grow room. The aircon itself hasn't changed and is still not linked to HA. Consequence: aircon IR integration (TB11) is now a nice-to-have, not the only control path.
- **The humidifier was fixed by cutting a hole in one side of the tub** (2026-07-25). It had been running flat out feeding a sealed box — mist condensed on the tub walls and drained back. Same RH and AH across the step, roughly half the duty. **The discs were never worn**, so the queued disc swap and spare 12-disk unit are redundancy only, and the humidifier power-monitoring smart plug lost most of its purpose.
- **The fresh-air fan must run overnight.** Its load-bearing job is **positive pressure**, not CO2 venting — switching it off (tested 07-25) let cold dry air pool in through the front floor openings and crashed the bottom shelf within hours. It came back within an hour of the fan restarting.
- **Weekly health check: `stock-control/tools/room_check.py`.** In-band scorecard, humidifier duty overnight vs midday, CO2 trough-to-trough, two-sensor drift cross-check. Run it weekly and after anything physical changes. Doctrine in `MICROCLIMATE.md` §6.

### ⚠️ Live issue — primary CO2 sensor zero shift

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
  - **⚠️ NEW BASELINE — `co2_shelf_delta` should now read ≈ +346, and that is NORMAL, not a gradient.** With the Inkbird recalibrated and the primary still uncorrected, the delta is almost entirely calibration disagreement. **Do not read it as a room problem.** Real gradient = `co2_shelf_delta` − 346.
  - **🎯 Post-reflash verification test, recorded in advance:** once **+350** is written to `0x006B`, **`co2_shelf_delta` should collapse to ≈ 0** (within ~±30). That is the free, immediate confirmation that the register write actually took — no second instrument, no waiting period. If it stays near +346 after the flash, the write silently failed; if it overshoots to ≈ −350, the sign encoding was wrong (positive is 0–1000, negative is 64535–65535).
  - **The "free bonus" horizontal-uniformity read did not work — don't retry it this way.** With the Inkbird on the left wall and the primary on the right, `temp_shelf_delta` / `rh_shelf_delta` should have measured horizontal uniformity. But the Inkbird reports temperature at **1 °C resolution** and logged only **61 points in 24h** (going stale by 10:18), so subtracting its +0.9 °C offset is meaningless against 1 °C quantisation. Horizontal uniformity needs its own method and a sensor with usable resolution.
- **Ongoing drift detection is already built and free:** `sensor.co2_shelf_delta` is the alarm. A *step* to a new settled value means one of the two sensors has moved — that is exactly how this was caught.

## Hardware — current configuration

- **Circulation fan: ACDC Dynamics WF-150**, mains 230V induction, inline mixed-flow, running on **LOW**. Do not raise to high — it over-ventilates the 110mm duct and breaks the low-velocity design bet.
- **Fresh-air fan: 100mm 2-speed AC inline (ACDC)**, mains, on LOW. Governs five coupled jobs — CO2, temperature coupling to the grow-room aircon, grow-room ventilation, positive pressure, humidifier drying load.
- **Both fans run off-controller** (mains, not on MOSFET/GPIO). The ESP firmware does not bind relay sockets 1 and 4 to them, so `switch.…_socket_1` / `_socket_4` read `off` while the fans run on manually-forced power.
- **The HA fan entities `fan.*_circ_fan` and `fan.*_fresh_fan` drive nothing.** Masked by an entity-registry name override reading "PHANTOM … drives nothing"; `entity_id`s unchanged so automations are unaffected.
- **No tacho on either fan** — HA cannot tell a spinning fan from a dead one. **After any reboot, reflash or power event, physically confirm both fans are turning.**
- **⛔ Never buy another SEAFLO SFIB1-130-01** for a 24/7 position — a marine bilge blower rated 600–700h *intermittent*, i.e. a ~1–3 month consumable here. Both original fans died this way.
- **Sensors:** RS485 DFRobot SEN0659 (CO2) + SEN0438 (temp/RH) on the shared TB7 bus, Modbus addresses 1 and 2 (3 is free). Grow-room DHT22 monitoring-only. Inkbird as secondary/verification only, never control.
- **Home Assistant** at **10.0.0.110** (wired). ESP32 is on `pret208-ext` (D-Link extender, channel 11).
- **Lovelace can be edited programmatically** — via the WebSocket API (`lovelace/config`, `lovelace/config/save`, `url_path: fruiting-room`), **not** by writing `.storage` directly, which HA clobbers. Back up first; a save replaces the whole view.

### ⚠️ Next reflash — read this whole block before touching the firmware

Nothing here is urgent alone. The point is that these are all **gated on the same reflash**, so do them together in one attended session rather than discovering them one at a time.

**Decide first: which ESPHome toolchain owns the controller.** The running firmware was built by the **HA add-on's ESPHome 2025.10.5**; the laptop has **2026.6.5** and a stale 07-10 build that is not what's deployed. Flashing from the laptop jumps ~8 months of versions on a controller whose RS485 sensors depend on a hand-written raw-UART lambda. The repo yaml is byte-identical to the device's source, so there's no drift — just a version decision to make deliberately. **Low-risk option: reflash from the HA add-on at the version that built the running firmware** — confirm it hasn't auto-updated first.

**Payload:**
1. **Write the CO2 correction to register `0x006B`** — the value is **+350**, measured and confirmed 2026-07-27 (co-location + outdoor reference check; no dependencies left). Verify afterwards with `co2_shelf_delta` ≈ 0. Needs Modbus function `0x06`, which the present read-only lambda cannot do. Encoding: ±1000 signed, positive 0–1000, negative 64535–65535.
2. **Bind relay socket 1 to the fresh-air fan.** ⚠️ Socket 4 is the circulation fan — **do not actuate it on a guess**; cutting it crashed RH before.
3. **Relabel or remove the phantom fan entities at source**, so the fix survives independently of HA's registry.
4. **Consider the GPIO21 tacho** if the fan rework is in scope — it is what makes a fan death alarmable.
5. **⚠️ An uncommitted variable-speed draft is HELD in the working tree** of `stock-control/esphome/fruiting-room-controller.yaml`. It rewrites fan control for a 12V ebm-papst that was never bought. **Check `git diff` before flashing; do not ship it by accident.**
6. **After the flash, physically confirm both fans are turning.** A reflash is exactly what killed the circulation fan on 07-16.

## Ledger

**In use since 2026-07-24** (Phase C). Supabase, captured via `stock-control/index.html`, hosted on the HA Pi at `/config/www/mushroom-control.html` → `http://10.0.0.110:8123/local/mushroom-control.html`, with a home-screen icon added via **Samsung Internet** (Chrome won't offer it for plain-HTTP LAN pages). Updating it = copy the repo's `index.html` over that file.

**Current data:** batches `SUB-2026-W23` and `SUB-2026-W25`–`W30`, reconciled against a physical bag count on 2026-07-26. Raw stock 2,366 g.

- **The packing date is recorded (`packed_at`) and the batch ID is derived from it**, enforced in the database against the ISO week. The panel asks for the packing date, shows the derived ID and the weekday live (batches are packed Tuesdays), warns on back-captures over 10 days old and on future dates. The free-text ID field is gone.
- **⚠️ Hard limit: one batch per ISO week.** The ID *is* the week, in both panel and database. Lifting it needs a suffix scheme both would have to learn.
- **Pickings before 2026-07-22 are not recoverable** — there was no scale. **Do not back-fill them**; `SAFETY.md` says measured values only, and partial data also breaks gap-based flush inference.
- **The 9 Jun batch is deliberately not in the ledger** (being physically discarded). Recording a batch purely to remove it would create a phantom zero-yield row dragging down every yield statistic. *The bags still need taking out — tracked on `todo.fungi4u`.*

### ⚠️ Open gap — the ledger cannot represent two things that actually happen

- **Batches split across rooms.** 23 Jun has 25 bags growing + 1 fruiting. A batch is not in one place.
- **Bags get culled for contamination.** Counted shortfalls: 18 Jun 22→21, 23 Jun 27→26, 21 Jul 28→25.
- **Consequences:** yield per bag is wrong (the denominator counts culled bags — the 21 Jul batch would be understated ~11%, and that is the number meant to prove committable supply); contamination rate is invisible; biomass for CO2 interpretation is overstated.
- **Fix shape:** an append-only **bag-movement table** (packed / moved to fruiting / culled / spent) with per-location counts derived. Mirrors the `stock_ledger` pattern but **must stay a separate table** — `SAFETY.md` forbids merging biological tracking into ledger logic.
- **⛔ The draft at `stock-control/supabase/drafts/20260726150000_batch_location_fruiting.sql` assumes whole-batch moves and is FALSIFIED by the split-batch finding. Do not apply it.**

## Not built / not installed

- **GSM cellular alarm** — battery-backed 4G dialler on the controller's breaker, thresholds moved local into the ESP32. **The single biggest risk-reducer:** the room has *no* monitoring at all when its power or internet fails, which is exactly when it has failed. Must be 4G/LTE — SA completes 2G/3G shutdown by end-2027. Candidate: Interlynx S150; confirm the 4G module, the MTN/Vodacom bands, **and a SIM plan that can't lapse for inactivity** before ordering — **the actual blocked step is getting a price from Interlynx, which has never been requested.** ⛔ SIM800/SIM800L are 2G-only and are ruled out (2026-07-27). The HA phone push (`fruiting_room_alarm.yaml`) stays a best-effort extra only.
- **Variac tuning — ⛔ DROPPED 2026-07-27, not deferred. Do not restart it without new evidence.** The plan was to dial the existing variac down to the lowest fresh-air fan speed that still held CO2. Three independent findings killed the savings case (reasoning in `DECISIONS.md`): (1) **no CO2 headroom** — the room runs at ~765 ppm true against an 800 target, ~35 ppm of slack, so it is not over-ventilating; (2) **no thermal driving force** — the fresh air comes from the *grow room*, measured over 72h at mean 17.97 °C against the fruiting room's 17.26 °C, a mean ΔT of just **+0.71 °C**, and *colder* for 20 of those 72 hours — order-25 W of sensible load against a room averaging ~417 W; (3) **the binding constraint is positive pressure, not CO2** — turning the fan off crashed the bottom shelf within hours (07-25), so the speed floor is set by pressure and may already bind. **Best case ~R20–60/mo against a real risk of re-crashing the bottom shelf.** *(The fridge gutting was cited here as a ~15× larger alternative — note it is avoided cost on an R8,000 purchase not yet made, not a saving available today. The comparison still holds directionally, but neither is money on the table right now.)* **Reopen only if CO2 is ever measured genuinely low with the fan at its pressure floor.**
- **Supabase environmental telemetry** — sensors go to HA only. Load-bearing for *proving* consistency to Spar, but a build.
- **Door sensor (TB10) and IR transmitter (TB11)** — wiring and terminals exist, devices not mounted.
- **Grow-room supply duct** — the plenum feeds two ceiling ducts, only the fruiting-room side exists. Also confirm whether the new fan actually re-ventilates the grow room.
- **Solar monitoring** — fully scoped in `stock-control/docs/SOLAR.md` (Sunsynk SG01LP1 5kW, Waveshare RS485-TO-ETH → kellerza add-on → MQTT → HA, ~R750–1,100). **Deferred on cost, not bought.** Water remains intent-only.
- **Liquid culture and grain spawn stages are undocumented anywhere.** Ask rather than assume.

## Smaller open items

- **Inkbird housekeeping** — it's live but on **no dashboard**; add an entities card. Delete the 3 dead orphans (`sensor.co2`, `sensor.inkbird_temp`, `sensor.inkbird_humid`) and the dead "Inkbird CO2" device, which is why the companion app shows "unavailable" — the working sensors have `device_id = null` and aren't on that page. Optionally add a shared `device:` block in `configuration.yaml` to group them.
- **Plug-meter sweep** — the **cold-storage unit is the CHEST freezer, and it is a *business* load**, not a house one (the house freezer is the **stand-up** one — don't confuse them and double-count). On the meter from 2026-07-27 07:30, read due 07-28 07:30. Needed for the true business total, and as the **benchmark** (kWh/day per litre) against which to judge any replacement quote — **it does not price the ~R707/mo gutting figure, which belongs to a glass-door unit not yet bought.** Then the house always-on suspects, 24h each. Read kWh over 24h, not instantaneous watts; set cost to R5.12/kWh.
- **`weather.forecast_home` is not reporting Pretoria** (found 2026-07-27). It forecast lows of 15.9–21.3 °C and highs of 26.8–29.6 °C for the week of 27 July; Pretoria late-July norms are ~5 °C min / ~19.6 °C max, and a 29.6 °C July day would be near-record. The HA home location or the weather integration is misconfigured. **Cosmetic today — nothing depends on it — but do not use it as an outdoor reference** (it was nearly used as one when sizing the floor-vent infiltration question).
- **DHCP reservation** for the HA Pi's Ethernet MAC at 10.0.0.110.
- **Fix the TP-Link 2.4G channel** to 1 rather than Auto, so an outage reboot can't re-pick congested channel 2.
- **RS485 poll timing** — seen once at 341 ms against a 340 ms budget (two back-to-back 150 ms blocking delays in one tick). No functional failure yet; if it worsens, split the two sensor queries across alternating ticks.
- **Watch the WF-150 and fresh-air fan bearings** in the ~90% RH airstream. Better than the SEAFLO, not immortal.
- **Lower-shelf crop observation** — verdict due ~2026-07-29. Largely mooted now the bottom shelf matches the top.
- **Drain-grate seal** — likely unneeded now positive pressure fixed the bottom shelf. Revisit only if the gradient returns.
- **Partially closing the front-wall floor vents — WORTH DOING, as a measured experiment. Confirmed 2026-07-27 that they open directly OUTDOORS.** *(An earlier note the same day said "no energy value" on the assumption they were purely the fan's relief path. That was wrong for this geometry — corrected below.)*
  - **Two exchange mechanisms the fan does not control.** **Stack effect:** room 17.25 °C against Pretoria winter nights of ~3–8 °C is a 10–14 °C difference across a *floor-level* opening, driving dense cold air inward continuously — **15–20× the 0.71 °C driving force in the grow-room loop**, and why the 07-25 fan-off test crashed the bottom shelf within hours rather than drifting. **Wind:** a front wall means gusts can locally reverse flow through the aperture regardless of fan pressure.
  - **The humidity cost is the concrete one.** Room 13.4 g/m³ absolute; the grow-room air the fan supplies is ~12.2 g/m³ (17.7 °C / 81%), a deficit of only ~1.2 g/m³. Pretoria winter outdoor air is realistically 5–8 g/m³. **Air entering through the holes instead of through the fan costs the humidifier 4–7× more per m³.**
  - **⛔ Do not seal them all** — the fan needs a relief path. **The limiting constraint is that CO2 headroom is only ~35 ppm** (room ~765 true vs 800 target), so choking the relief path pushes CO2 over target fast.
  - **🎯 Prediction recorded in advance.** *Good case (cutting uncontrolled infiltration):* humidifier duty drops, bottom-shelf gradient stays flat, CO2 rises <50 ppm. *Too far (choking the relief path):* CO2 climbs >100 ppm and keeps climbing. **CO2 is the discriminator — temperature and humidity look better in BOTH cases, which is the trap.** Watch `sensor.humidifier_duty_24h`, `co2_shelf_delta` and displayed CO2 against ~450 (= 800 true), over 24h, not a spot check. The Inkbird returned to the bottom shelf 2026-07-27 ~12:00, so gradient monitoring is live.
  - **Still worth doing regardless: a power-monitoring smart plug on the fresh-air fan.** Sealing softens the consequence of a fan death; the plug makes it *detectable*. The fan is an unmonitored single point of failure — no tacho, two predecessors dead in that position.

## Decided against (so it isn't re-litigated)

- **A third CO2 sensor — don't buy.** Detection already works free: `co2_shelf_delta` caught this drift. What co-location buys is *quantification*. The real problem is that the Inkbird has two conflicting jobs (continuous bottom-shelf monitoring vs cross-check reference) and can't do both at once — a third sensor resolves only that. **Trigger that would justify it: CO2 going back to *controlling* something.** Today a wrong reading misleads a human but cannot mis-actuate anything. **If it ever happens, the spec is: RS485/Modbus (not I2C — the sensors hang on ~1100mm drops off a Cat5e field run in ~90% RH; cable length is the whole reason this room is on RS485), address 3 on the existing bus, and it must expose a calibration/ABC-control register — treat that as a purchase criterion, not something to discover afterwards.**
- **Humidifier power-monitoring smart plug** — was justified mainly as disc-degradation early warning and to disambiguate capacity vs internal cutoff. The tub-hole finding answered both; mostly moot now.
- **Smart plug to power-cycle the Inkbird** — it has a rechargeable battery, so cutting mains doesn't reboot it. Its flakiness (brief self-recovering blips) is acceptable for a sensor that never controls anything.
- **12V DC fans for the fresh-air position** (ebm-papst 4312/2 axial, REF100-11/12 centrifugal) — all cost more and mounted worse than reusing the installed inline fan on the variac. If full ESP32 closed-loop is ever wanted, the easiest route is a **mains EC inline duct fan with 0–10V input**, not a DC blower.

## Worth investigating (not decided)

- **Ledger ↔ Sage reconciliation.** The ledger records operational *units*; money lives in Sage. Nothing connects them. Revisit once Phase C is carrying real numbers on both sides.

## Standing lessons

- **Look at the physical thing first.** The humidifier's cure was a hole in a plastic box, and it sat undiscovered behind three sessions of fan theory, sourcing sweeps and a rejected overnight experiment.
- **Reconcile against the physical thing before rewriting records.** The batch-ID session was about to repoint correct pickings; the operator's "the week numbers are all one off" is what caught it.
- **Use the HA recorder for anything about trends or reliability** — the add-on log retains only ~1–2h and structurally cannot show a diurnal cycle. **Never settle a diurnal question with a spot check.**
- **Never trust an HA fan percentage** — both fans are 2-wire with no tacho, and a commanded PWM says nothing about airflow. This is exactly what hid both fan deaths.
- **A repo edit does not reach the running HA automation.** The alarm's CO2 leg sat silently unarmed for days because the repo copy was fixed and the live automation wasn't.
- **HA numeric triggers are edge-triggered** — they fire on crossing a threshold, not on sitting beyond one, so they won't fire for a condition already in progress when they load.
