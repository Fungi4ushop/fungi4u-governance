# Fungi4u Handbook

## What this is

A grey oyster mushroom cultivation business, run from home in Pretoria. One operator. The goal: run it well enough that it could be handed over to someone else at any time — a child, a hired hand, or sold — without that person needing to reconstruct anything from memory or chat history.

## Objectives (why the work is prioritised the way it is)

The objectives form a chain, each supporting the one above it:

1. **Top objective — a business that can be handed over.** Someone else should be able to take it on, or decide not to, without reconstructing context from chat history. This is why the governance docs (`STATUS`, `DECISIONS`, `SAFETY`, `HARDWARE_REFERENCE`, `MICROCLIMATE`) exist and are kept current — the documentation is *direct* work toward this objective, not overhead.
2. **Supporting — R20,000 income per month.** A handoverable business must also be a viable one; R20,000/month is the target that makes it worth taking on.
3. **Supporting — onboard new clients.** Income grows by taking on more clients to supply.
4. **Supporting — improve yield.** Yield improvement is a *prerequisite* for onboarding new clients, not a competing concern: you cannot commit to reliably supplying a new client without the production capacity to back it. So yield gates client onboarding, which gates income. What matters is therefore **consistent, committable supply** — dependable volume a client can rely on — not just an occasional high flush.
5. **Supporting — microclimate improvement, then the monitoring/alarm and telemetry work that safeguards and measures it** (the telemetry matters precisely because *consistency* has to be proven and held, not just peaked).

Two legs, both required for the top objective: the business must be **viable** (earning toward R20,000/month) *and* **transferable** (documented). Neither substitutes for the other.

## The production cycle

**Note: this section only covers the part currently tracked in the ledger, starting from bulk substrate.** The real cultivation process starts earlier — a liquid culture cycle, then a grain spawn cycle, both feeding into the bulk substrate step below. Not yet documented here; to be added once written up properly (see `DECISIONS.md`/`STATUS.md` for how this document set evolves). If you're reading this and those stages still aren't written up, ask about them explicitly rather than assuming the process starts at substrate.

**Before step 1 — straw is cut on Mondays (added 2026-07-29).** The week's straw is chopped the **day before** the batch is made, using a **converted lawnmower** as the chopper. **Two bales of straw yield one 110 L drum of cut straw**, which is exactly one batch — so the weekly rhythm is *cut Monday, make Tuesday*. This step was previously undocumented; a successor reading only the numbered steps below would not know the substrate has to be prepared a day ahead, or with what. See `STATUS.md` for what still needs recording about the machine itself.

**Bagging — how a bag is actually made (added 2026-08-04, previously undocumented).** **Pasteurisation happens to the straw BEFORE bagging, not after**, so nothing about the bag or its closure has to survive heat. Each bag is cut from a **roll of plastic layflat tubing**. The **bottom end is closed with a tape device that uses PVC tape**; the bag is then filled, and the **top is closed with a cable tie**. Two different closure methods, two different consumables — and the tape device is **already proven on this same tubing**, which matters when one of the two runs out. See "Routine maintenance" for reorder points.

1. **Substrate batch inserted** — a batch of growing substrate bags is logged (batch ID, bag count, total weight). One batch a week, made on Tuesdays (~24 × 4kg bags from a 110L drum).
2. **Pickings recorded** — mushrooms are **not** harvested in one event: each is picked as it's ready, over several days, and cold-stored just above freezing. Each **picking** is weighed and logged against its batch. A "flush" is many pickings; a batch gives two flushes (separated by a ~1–2 week rest), then its bags are removed. Flush number is inferred by the system from the rest-gap between pickings, not entered.
3. **Harvest processed** — the accumulated raw stock (from cold storage) is cleaned and packed: raw is converted into packed product (grey oyster, 250g packs) plus waste. Processing consumes the whole accumulated raw balance, so it mixes pickings across batches.
4. **Packed sold** — units sold are deducted from packed stock.

Every step above is logged through the control panel (`stock-control/index.html`) into the Supabase ledger. The ledger is the only source of truth — see `SAFETY.md`. **Note (2026-07-11):** the ledger/panel is mid-migration to this model — the per-picking capture exists; the panel and processing rework are in progress (see `stock-control/docs/LEDGER.md` and `DECISIONS.md`). The system was built earlier but never used with real data; disciplined capture (Phase C) also awaits a harvest scale (a flush exceeds the kitchen scale).

## The three systems

| System | Role | Where |
|---|---|---|
| **Stock ledger** | Records every substrate batch, flush, processing, and sale. Append-only — nothing is ever edited or deleted, only added. | Supabase, driven by `stock-control/index.html` |
| **Climate control (fruiting room)** | Primary environmental control — temperature, humidity, CO2, fan and humidifier control. Runs on an ESPHome device with RS485/Modbus sensors as authoritative — a DFRobot SEN0659 for CO2 and a SEN0438 for temperature/humidity (an earlier plan named a Senseair S8 as the CO2 sensor, but it was never installed — see `DECISIONS.md`). Also has an **Inkbird CO2/temp/humidity sensor as a secondary, verification-only input** — never authoritative, and as of 2026-07-06 known to have a WiFi stability problem (see `STATUS.md`), so operations don't depend on it. Design and reasoning: `MICROCLIMATE.md`. Exact GPIO/wiring/terminal reference: `HARDWARE_REFERENCE.md`. | `stock-control/esphome/fruiting-room-controller.yaml` (primary); `stock-control/home-assistant/inkbird-mqtt-addon/` (secondary sensor bridge) |
| **Home Assistant** | The supervisory platform, separate from any one sensor or controller. Hosts the MQTT broker (Mosquitto), runs the Inkbird bridge add-on, provides dashboards/alarms/operator interaction, and (added 2026-07-05/06) exposes an MCP interface so an AI coding session can read live state directly. Not authoritative for safety — per `SAFETY.md`, the ESPHome device enforces its own limits regardless of whether Home Assistant is up. | Raspberry Pi (Home Assistant OS) on the home network |

## Routine maintenance

**This section exists because there was no maintenance list at all until 2026-08-04**, and a physical consumable was found degrading the crop environment with no alarm and no record that it needed attention. Recurring physical obligations were previously scattered through `STATUS.md` as one-off notes, which is how they get lost at handover. **A successor should be able to keep this operation alive from this list alone.**

### ⚠️ Grow-room air conditioner — filter cleaning

**This is the fruiting room's only heat source, and it has no telemetry of any kind.**

- **Why it is crop-critical, not comfort equipment.** The aircon is in the **grow room**, above the rear door — the fruiting room has never had its own temperature control and is conditioned *indirectly*, by air moving between the rooms (`stock-control/docs/MICROCLIMATE.md` §Fresh air, operator insight 2026-07-22). If this unit weakens, the fruiting room follows it down.
- **Why it loads faster than a domestic unit.** It shares a building with a room held at **90–95% RH**, full of grey-oyster spores, and straw is chopped on the property every Monday. That is an unusually dirty airstream.
- **⛔ Nothing will tell you it has degraded.** There is **no `climate.*` entity in Home Assistant** — the aircon is not linked to HA at all, and the IR transmitter (TB11) is wired but never mounted. No dashboard, alarm or automation observes this unit. **The only instrument that sees it is the weekly `room_check.py` temperature scorecard**, and only indirectly.
- **Interval: not yet established.** Set one after the first clean, based on how dirty the filter actually is. Do not invent a figure before then.

**The failure signature, recorded from the 2026-08-01 → 08-04 event so it is recognisable next time:**

- **Both rooms cool together over days** — fruiting room 17.29 → 14.73 °C daily mean, grow room 17.73 → 14.52 — with the fruiting room tracking the grow room **0.2–0.5 °C above it throughout**.
- **The outdoors moves the other way.** Outdoor nights *warmed* 8.2 → 12.8 °C across the same window. **Two rooms falling while the outdoors rises cannot be weather, and points at the shared heat source rather than at the fruiting room's own configuration.**
- **The decline decelerates toward a new equilibrium** (−0.85, −0.92, −0.34, −0.38 °C/day) rather than continuing to fall. **That distinguishes *weak* output from *absent* output** — a unit that is off or tripped keeps falling toward the envelope's no-heat balance point. The grow room also kept gaining heat each afternoon, confirming it was running.
- **Consequences seen:** fruiting room to **14.20 °C — below the 15 °C band floor and at the firmware's own `temp_floor`** — and the humidifier pinned at **95.4% overnight** chasing a colder, leakier room. Temperature in band fell from 99.8% to 78.4%.
- **What it is NOT:** humidity control was independently exonerated. RH held 90.4–91.2% throughout, and the absolute-humidity fall was predicted from temperature and RH alone to within **0.05 g/m³** on all five days.

**⚠️ Status as of 2026-08-04: the filter is the operator's diagnosis and the data is consistent with it, but the clean has not yet been done and the cause is UNCONFIRMED.** The recorder can only say "reduced heat output" — low refrigerant, a fouled coil, or a changed setpoint would look identical. The filter is the right first move because it is free, not because it is proven. **Confirmation test: clean it, change nothing else, and expect the grow room to recover first with the fruiting room following toward ~17.3 °C within a day.** If it does not recover, the filter was not the cause and the next candidates cost money. Re-run `room_check.py` ~24h after.

### ⚠️ Grow-room air conditioner — the fan MUST stay on manual HIGH

**Added 2026-08-12, the day the unit was properly diagnosed. `Alliance INAA18`, 5790 W heating — 3–5× oversized for the 17.7 m³ grow room, and healthy (16 °C supply-to-return rise, no ice, no condensate). It was still leaving the room 5–6 °C below its 21 °C setpoint on cold nights, and the reason is a feedback loop, not a fault in the unit.**

**Required settings: mode `HEAT` · fan `MANUAL HIGH` · setpoint 21 °C.**

**⛔ DO NOT PUT THE FAN BACK ON `AUTO`.** The unit's intake is on **top of the indoor unit, 100 mm below the ceiling**. In heating, its ~40 °C output is buoyant and rises — straight back into its own intake. That makes the air the thermostat senses run **~8 °C hotter than the room**, so the unit believes it has nearly arrived, throttles down, and on `AUTO` **drops the fan to low — which removes the jet's throw, so even less air reaches the floor and the recirculation gets worse.** A self-reinforcing loop that ends with the crop cold and the unit convinced it is finished.

- **✅ PROVEN 2026-08-13, AND THE SETTING IS WORTH 7.4 °C.** The night after it was set, the grow room's overnight mean went **14.48 → 21.84 °C** — from 5–6 °C below setpoint to *at* setpoint, with nothing else changed. **This is no longer a plausible theory; it is a measured intervention.** It also means the competing explanations (back-wall drywall, door leaks, unit capacity) are **not** what was holding the room down.
- **Manual HIGH breaks the loop** by denying the unit the ability to throttle its own airflow. **It is a workaround, and it reverts silently** — a power cut, a remote battery change, or someone "restoring auto" is enough. **⚠️ A silent revert now costs 7.4 °C in the grow room and ~3.3 °C in the fruiting room.**
- **⛔ Nothing will tell you it has reverted.** There is **no `climate.*` entity in Home Assistant** and no alarm on this unit; the only instrument that sees it is the weekly `room_check.py` temperature scorecard, and only indirectly. **Same failure shape as `DECISIONS.md` 2026-07-10, where an ESPHome `restore_mode` default silently defeated the room's continuous-circulation design.**
- **Also set the louvres as steeply DOWN as they go**, for the same reason: throw the air at the floor so it must warm the room before it can return.
- **➡️ The permanent repair is geometric** — deflect or duct the supply so it cannot reach the intake. **That is what would make `AUTO` safe again**, and it is the only version that does not depend on someone remembering a button. Until then, treat the setting as part of the equipment.

### Production consumables — reorder points

**Added 2026-08-04, after cable ties ran out on a Tuesday and blocked the bagging of an already-pasteurised batch.** These are cheap items whose absence stops production outright. **None of them appear in `stock-control/finance/CASHFLOW.md`'s cost list**, which is defensible on materiality but is also why nobody was watching the level.

| Consumable | Used at | Rate | Reorder at | Note |
|---|---|---|---|---|
| **Cable ties** | Closing the **top** of each filled bag | **~24/batch = ~24/week ≈ 104/month** | **100 left (one month's buffer)** | **Spec in use: SP30, 150 × 3.5 mm.** Measured price 2026-08-04: **R49.98 per 100 = R0.50/tie**, so **~R12/batch ≈ R52/month**. |
| **PVC tape for the bag-sealing device** | Closing the **bottom** of each tube | ~24/batch | Keep **one spare roll** unopened | The same stockout on this item would be worse — it has no equivalent fallback, whereas the tape device *can* substitute for cable ties |
| **Layflat tubing** | The bag itself | ~24/batch | Not established | Record consumption per roll to set one |

**⛔ THE TWO CLOSURE METHODS ARE NOT INTERCHANGEABLE — TESTED 2026-08-04. The tape device does NOT work on the top of a filled bag.** An earlier version of this entry called it "the first fallback if cable ties run out". **That was wrong, and it was wrong in the direction that matters** — it would have sent someone to try a dead end with pasteurised straw already waiting. *(Probable reason, inferred not measured: the device wants a thin flat neck, which the bottom end has while empty and the top end does not once it is over 4 kg of wet straw.)*

**➡️ So there is NO in-house fallback for cable ties. They are a single point of failure for bagging, and the reorder buffer above is the only protection.** Treat the 100-tie reorder point as real, not advisory.

**If a batch is ever genuinely stuck with no ties, in preference order:** (1) **PVC tape wrapped by hand** around the gathered neck — same material as the validated bottom closure, and the device's limitation is the *device*, not the tape; (2) **wire twist ties**, which cinch tight and repeatably; (3) **string or twine last** — it is the loosest and least repeatable. **Closure tightness is a contamination-control variable**, so **do not introduce an improvised closure during a batch whose contamination rate is being watched** (see `STATUS.md` on W30's 10.7% cull rate and W31 as the test) — a looser seal would confound exactly the measurement in progress. If one is unavoidable, **record it against the batch** so the result can be read honestly.

### Other recurring obligations, already documented elsewhere

Listed here so the list is complete; the detail stays where it lives.

| Item | Cadence | Where |
|---|---|---|
| **⚠️ Confirm the grow-room aircon is still `HEAT` · `FAN = MANUAL HIGH` · setpoint 21 °C** | After **any** power event, remote battery change, or if the room runs cold — and at handover | **See directly below** — this is a load-bearing setting, not a preference |
| **`room_check.py` room health check** | **Weekly**, and after anything physical changes | `todo.fungi4u`, `MICROCLIMATE.md` §6 |
| **Roof water tank fill** | **Daily, manual, ~18 min** — ⚠️ a single manual action stands between this business and no water, and nothing alarms on it | `STATUS.md` |
| **Straw chopping** | **Weekly, Mondays** — bespoke converted lawnmower, no backup and no spare | `HANDBOOK.md` production cycle, `STATUS.md` |
| **Confirm both fans physically turn** | After **any** reboot, reflash or power event — neither fan has a tacho, so HA cannot tell a spinning fan from a dead one | `STATUS.md`, `DECISIONS.md` 2026-07-17 |
| **Fan bearings in the ~90% RH airstream** | Watch — better than the SEAFLOs they replaced, not immortal | `STATUS.md` |

## Where things live

- **Code and configuration**: four git repositories under `Fungi4ushop` on GitHub — `stock-control` (the one repo that does real work), plus `operational-core`, `fungi4u-governance`, and (soon to be retired/simplified) `mcp-engineering-platform`.
- **Business data (operational)**: Supabase (see `SAFETY.md` for access rules) — the stock ledger tracks substrate/flush/processing/sales as operational stock and *units*, not money.
- **Accounting & finance**: **Sage** does the accounting — it's capable of full accounting (invoicing, expenses, VAT, etc.) but is **not well utilised yet**, and is **not currently connected to the stock ledger** (the Supabase ledger's "sales" are operational units; the actual money lives in Sage, entered separately — no automatic reconciliation between the two). The business bank account is at **Capitec**. Logins for both are in Bitwarden, not here.
- **Physical control**: Home Assistant, running on a Raspberry Pi (Home Assistant OS) on the home network.
- **Credentials**: see "Credentials" below — do not go looking in Git or chat history for these.

## Credentials

All real account credentials (GitHub, Supabase, Home Assistant login, router admin, MQTT broker, **Sage accounting, Capitec business banking**) belong in **one password manager** — Bitwarden, since that's already the one referenced as a critical recovery account elsewhere in this repo's history. If you find a credential anywhere else (a chat transcript, a config file, a browser's saved passwords), treat that as a temporary leak to clean up, not a legitimate second home for it.

Machine-local technical credentials created for AI-assisted engineering sessions (e.g. SSH keys for deploying to the Home Assistant host, GNOME-keyring entries used only by a coding assistant on one specific laptop) don't need to go in Bitwarden — they're disposable and regenerable, not business-critical.

## Starting a new AI chat about a specific system

You don't need to mention any document by name. A `CLAUDE.md` file at the top of the projects folder is loaded automatically at the start of every session and already tells the assistant which documents to check for which kind of task. Just say what you're working on:

> I'm working on [the ledger / the microclimate / the Inkbird bridge] for the Fungi4u mushroom business. Current objective: [state it].

That's the whole prompt. This replaces the old per-repo "Chat Initialization Template" that only existed for the ledger and required listing documents by hand — the same simple pattern now applies to any part of the business, with the document lookup happening automatically instead of manually.

## What replaced the old governance repos

`operational-core`, `fungi4u-governance`, and `mcp-engineering-platform` previously carried a full constitutional/amendment framework, a document lifecycle model, and a bespoke AI-engineering platform. None of it was about running the mushroom business, and the volume of process documentation had grown to dwarf the actual amount of working code and hardware it was meant to govern. It's been replaced by this handbook plus `STATUS.md`, `DECISIONS.md`, and `SAFETY.md`. If you're reading this after a long gap: start with `STATUS.md` for what's currently true, then `SAFETY.md` before changing anything.
