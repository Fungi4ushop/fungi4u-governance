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
- **Barcode: R176 once-off**, a GS1 SA single GTIN, no renewal.
- **Next action, and it scopes everything else: get Spar's full supplier requirement list.** The barcode is unlikely to be the only blocker, and their onboarding checklist tells you exactly which regulations bind — so you comply with what's required rather than everything imaginable.
- **Risk:** Spar would be onboarded on an expectation. Ledger production data started only on 07-24, so committable volume can't yet be proven. Failing to supply a Spar is worse than never approaching one.
- **Fridge is at its limit** — a capacity constraint on growth. ~R8,000 second-hand, storage only. Gutting a glass unit (lights ~72W, door heater ~80W, insulate glass) saves ~R707/mo at R5.12/kWh.

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
| Primary CO2 sensor | ⚠️ Reads ~90 ppm **low** |

- **Temperature was fixed by the fresh-air fan**, which buffers the fruiting room against the grow room. The aircon itself hasn't changed and is still not linked to HA. Consequence: aircon IR integration (TB11) is now a nice-to-have, not the only control path.
- **The humidifier was fixed by cutting a hole in one side of the tub** (2026-07-25). It had been running flat out feeding a sealed box — mist condensed on the tub walls and drained back. Same RH and AH across the step, roughly half the duty. **The discs were never worn**, so the queued disc swap and spare 12-disk unit are redundancy only, and the humidifier power-monitoring smart plug lost most of its purpose.
- **The fresh-air fan must run overnight.** Its load-bearing job is **positive pressure**, not CO2 venting — switching it off (tested 07-25) let cold dry air pool in through the front floor openings and crashed the bottom shelf within hours. It came back within an hour of the fan restarting.
- **Weekly health check: `stock-control/tools/room_check.py`.** In-band scorecard, humidifier duty overnight vs midday, CO2 trough-to-trough, two-sensor drift cross-check. Run it weekly and after anything physical changes. Doctrine in `MICROCLIMATE.md` §6.

### ⚠️ Live issue — primary CO2 sensor zero shift

`sensor.fruiting_room_fruiting_room_controller_co2` took a **one-off ~90 ppm downward zero shift** at ~08:35 on 2026-07-25. It is a single discrete step, not a runaway — the Inkbird-minus-primary offset went from a settled ~+185 to a settled ~+276 and has held there. Trigger unknown; a power cycle is ruled out (no reporting gap).

- **Carry it as an explicit +90 ppm mental offset.** It is applied nowhere in software.
- **Consequences while uncorrected:** variac tuning should target a **displayed ~710**, not 800. The HA alarm's `co2_high` leg needs a true ~1590 to fire. **Do not flash the shelved proportional-CO2 firmware** while the sensor is off.
- **The fix goes on the ESP32 via register `0x006B`, not in Home Assistant** (decided 2026-07-26, rationale in `DECISIONS.md`). **⚠️ Do not add an HA template sensor as a stopgap** — that reverses the decision and creates the invisible trap it was made to avoid. The wait is acceptable because CO2 currently drives nothing.
- **The SEN0659 exposes only four registers** — CO2 read, address, baud, and `0x006B` correction (±1000 signed). There is **no ABC-disable and no calibration command**, so periodic re-checking is permanent for the life of this sensor. "Disable ABC" is not available.
- **🔬 Co-location baseline running since 2026-07-26 ~11:40** — the Inkbird was fresh-air recalibrated and hung beside the primary CO2 sensor. *(The 07-21 "baseline" was never a CO2 one — it used the temp/RH sensor 3.85 m away. Don't rely on its +70 ppm figure.)*
  - **Do not read the offset before ~2026-07-27 midday.** A freshly recalibrated NDIR sensor is anchored near 400 ppm and reads low for ~a day. An early reading would make the primary look correct — the exact opposite of the truth.
  - **Read it as a 24h mean across a full diurnal cycle**, not a snapshot.
  - **Falsifiable prediction, recorded in advance:** the settled co-located delta should be **≈ +90**. Near 0 means the diagnosis was wrong and the whole +276 is real gradient. Whatever it lands on is the number for `0x006B`.
  - **Don't leave it co-located past ~48h** — the Inkbird has the same ABC weakness and will start drifting low again. Then return it to the bottom shelf.
  - **While co-located, the three `*_shelf_delta` sensors do not mean what their names say** — they read sensor-vs-sensor disagreement, not a top-vs-bottom gradient, and **the bottom shelf is unmonitored** until the Inkbird goes back.
  - **Free bonus:** with the Inkbird on the left wall and the primary temp/RH on the right, `temp_shelf_delta` / `rh_shelf_delta` now measure **horizontal room uniformity** — a documented blind spot. Read it at the same time, subtracting the Inkbird's own offsets (temp **+0.9 °C**, AH **−0.3 g/m³**), and compare in **AH, not raw RH**. Not available again once the sensor moves back.
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
1. **Write the CO2 correction to register `0x006B`.** Needs Modbus function `0x06`, which the present read-only lambda cannot do. Measure the true offset from the co-location first. Encoding: ±1000 signed, positive 0–1000, negative 64535–65535.
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

- **GSM cellular alarm** — battery-backed 4G dialler on the controller's breaker, thresholds moved local into the ESP32. **The single biggest risk-reducer:** the room has *no* monitoring at all when its power or internet fails, which is exactly when it has failed. Must be 4G/LTE — SA completes 2G/3G shutdown by end-2027. Candidate: Interlynx S150; confirm the 4G module and MTN/Vodacom bands before ordering. The HA phone push (`fruiting_room_alarm.yaml`) stays a best-effort extra only.
- **Variac tuning** — the variable-speed fresh-air solution is the operator's existing variac on the installed inline fan (no new part). Outstanding: dial down step by step to the **lowest speed that still holds CO2 (displayed ~710 given the sensor offset), a flat bottom-shelf gradient, grow-room ventilation and ≥15 °C, while humidifier duty stays off 100%.** Don't go so low the induction motor stalls. Attended only — no GSM alarm yet.
- **Supabase environmental telemetry** — sensors go to HA only. Load-bearing for *proving* consistency to Spar, but a build.
- **Door sensor (TB10) and IR transmitter (TB11)** — wiring and terminals exist, devices not mounted.
- **Grow-room supply duct** — the plenum feeds two ceiling ducts, only the fruiting-room side exists. Also confirm whether the new fan actually re-ventilates the grow room.
- **Solar monitoring** — fully scoped in `stock-control/docs/SOLAR.md` (Sunsynk SG01LP1 5kW, Waveshare RS485-TO-ETH → kellerza add-on → MQTT → HA, ~R750–1,100). **Deferred on cost, not bought.** Water remains intent-only.
- **Liquid culture and grain spawn stages are undocumented anywhere.** Ask rather than assume.

## Smaller open items

- **Inkbird housekeeping** — it's live but on **no dashboard**; add an entities card. Delete the 3 dead orphans (`sensor.co2`, `sensor.inkbird_temp`, `sensor.inkbird_humid`) and the dead "Inkbird CO2" device, which is why the companion app shows "unavailable" — the working sensors have `device_id = null` and aren't on that page. Optionally add a shared `device:` block in `configuration.yaml` to group them.
- **Plug-meter sweep** — the **cold-storage fridge is still unmeasured, and it is a *business* load**, not a house one. Needed for the true business total and to price the ~R707/mo gutting saving. Then the house always-on suspects, 24h each. Read kWh over 24h, not instantaneous watts; set cost to R5.12/kWh.
- **DHCP reservation** for the HA Pi's Ethernet MAC at 10.0.0.110.
- **Fix the TP-Link 2.4G channel** to 1 rather than Auto, so an outage reboot can't re-pick congested channel 2.
- **RS485 poll timing** — seen once at 341 ms against a 340 ms budget (two back-to-back 150 ms blocking delays in one tick). No functional failure yet; if it worsens, split the two sensor queries across alternating ticks.
- **Watch the WF-150 and fresh-air fan bearings** in the ~90% RH airstream. Better than the SEAFLO, not immortal.
- **Lower-shelf crop observation** — verdict due ~2026-07-29. Largely mooted now the bottom shelf matches the top.
- **Drain-grate seal** — likely unneeded now positive pressure fixed the bottom shelf. Revisit only if the gradient returns.

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
