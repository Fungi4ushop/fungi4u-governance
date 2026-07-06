# Status

Last updated: 2026-07-06

This document replaces `BUSINESS_STATE.md`'s "Phase / Engagement" tracking with a plain answer to: what's actually true right now.

## Business stage

The ledger is technically ready for data capture (Stage 1 of the five-stage roadmap below), but **the actual current priority is microclimate improvement, ahead of and independent of that data**. Reasoning: existing experience already indicates the microclimate has enough room for improvement to nearly double yield — confident enough to act on now rather than wait months for ledger-driven measurement to confirm it. The five-stage roadmap describes where the ledger/data side is headed; it isn't a gate the operator is waiting on before improving the physical systems.

1. **Measured Discipline** (ledger side, current) — controlled ledger, flush tracking, processing measurement, manual mobile input.
2. **Stability Monitoring** (ledger side, next) — 4–8 weeks of real data, biological variance analysis, processing drift detection.
3. **Throughput Optimization** — substrate batch comparison, straw/spawn/environment adjustments, waste reduction.
4. **Automation Integration** — environmental telemetry overlay, data-driven environment tuning.
5. **Economic Forecasting** — predictive yield modeling, demand rhythm analysis, capacity planning.

**Actual current focus: the new climate control system is in early adoption — still has open issues, not yet stable.** Next concrete step is installing two additional sensors, then getting their readings captured (ideally into Supabase, not just Home Assistant — not yet built, see below) so the environment can be analyzed and optimized rather than adjusted by feel alone.

**Added complexity**: the fruiting room and grow room currently share one building, split by an interim divider wall (see `MICROCLIMATE.md` §4 "Interim Divider Wall"). The climate system has to work across this interim two-zone configuration, which makes the rollout more complex than a single dedicated room would be.

## What's working

- **Stock ledger** (Supabase, via `stock-control/index.html`) — operational. Substrate → flush → process → sale flow is in active use.
- **Fruiting room climate control** (ESPHome, Senseair S8 CO2 sensor) — operational. Confirmed live and reporting on 2026-07-06: ~14.4°C, ~97% RH, circulation fan 85%, fresh-air fan 80%.
- **Home Assistant** — operational, now with an MCP integration allowing an AI coding session to read live entity states directly (set up 2026-07-05/06) rather than relying on screenshots or guesswork.

## What's broken or in progress

- **Environmental telemetry is not yet flowing into Supabase.** Sensor readings currently go to Home Assistant only. The plan (see Business Stage above) is to also capture them in Supabase so the environment can actually be analyzed, not just observed live. Not yet built.
- **Inkbird CO2/temp/humidity sensor** — last known state: not reporting into Home Assistant, but this hasn't actually been re-checked since the fixes below were applied. Root cause chain identified and partially fixed on 2026-07-06:
  - The custom MQTT bridge add-on had never actually been installed on the Home Assistant host, despite existing in `stock-control` for weeks. Now deployed to `/addons/local/inkbird_mqtt/`.
  - The bridge script hardcoded the wrong Tuya protocol version (3.5 instead of the device's actual 3.4). Fixed in `inkbird_mqtt.py` and pushed to the host.
  - **Underlying cause, confirmed 2026-07-06**: the device itself repeatedly drops its WiFi connection and only comes back after a physical power cycle. This is not a software/config bug — it's most likely the ~97% relative humidity environment it sits in causing WiFi module instability. Not yet fixed.

## Next steps (not yet done, in no particular order)

- **Re-check whether the Inkbird bridge is actually publishing now**, after the protocol-version fix and redeployment — this was never re-verified in Home Assistant after the fix was applied.
- **Resolve the stale DHCP reservation**: the router has an unapplied reservation for the Inkbird's MAC (`1c:90:ff:9d:9b:7a`) at `10.0.0.23`, but its actual current lease is `10.0.0.102`. Low priority given the smart-plug plan below makes the exact address less critical, but it's an inconsistency nobody would otherwise know to look for.
- **Put the Inkbird on a smart plug controlled by Home Assistant**, with an automation to power-cycle it on a schedule or when detected unreachable. A workaround, not a fix — appropriate since it's explicitly a secondary/verification sensor, not the primary one.
- **Install the two RS485 sensors** (DFRobot SEN0659 CO2 + SEN0438 temp/humidity) replacing the DHT22 pair — register maps, wiring, and the addressing plan are documented in `stock-control/docs/HARDWARE_REFERENCE.md`.
- **Set the CO2 sensor's Modbus address before wiring it in** (per the addressing plan in `HARDWARE_REFERENCE.md`) so it doesn't collide with the temp/humidity sensor on the shared bus.
- **Write the actual ESPHome/Modbus sensor configuration** for both new sensors once physically installed — installing the hardware and writing the firmware config are two separate steps; only the first is currently planned in detail.
- **Decommission the DHT22 sensors** once the RS485 replacements are validated and reporting correctly.
- **Build the Supabase environmental telemetry pipeline** referenced above.
- **Liquid culture and grain spawn cultivation stages** are still not documented anywhere (see `HANDBOOK.md`'s production cycle note) — capture this whenever there's time, don't assume it exists.

## Planned future expansion (not started)

Two more physical systems are planned, beyond climate control: **solar** (optimizing use of excess daytime generation) and **water** (the property isn't on municipal supply). Structural pattern already agreed: each gets its own `docs/SOLAR.md` / `docs/WATER.md` in `stock-control`, following the same design-doc + hardware-reference-doc pattern as `MICROCLIMATE.md`/`HARDWARE_REFERENCE.md` — no new repos, no new process. Nothing built yet; this is intent, not a spec.

## Possible improvements (not decided, just worth investigating)

- **Automatic end-of-session reminder to update Status/Decisions.** Right now, keeping this document set current relies on remembering to ask "does this need updating?" at the end of a working session. Claude Code supports hooks that could prompt this automatically instead. Not set up — deliberately not added without being asked, since it's one more piece of configuration to maintain — but worth a look if the manual habit turns out to be unreliable in practice.

## Recently cleaned up (2026-07-06)

- Replaced the `operational-core` / `fungi4u-governance` / `mcp-engineering-platform` governance apparatus with this handbook + status + decisions + safety document set (see `HANDBOOK.md` for why).
