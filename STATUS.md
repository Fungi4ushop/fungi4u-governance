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
- **Two additional sensors to be installed next** as part of the current climate-control rollout — details (type, placement, purpose) to be confirmed and documented once installed.
- **Inkbird CO2/temp/humidity sensor** — not reporting into Home Assistant. Root cause chain identified and partially fixed on 2026-07-06:
  - The custom MQTT bridge add-on had never actually been installed on the Home Assistant host, despite existing in `stock-control` for weeks. Now deployed to `/addons/local/inkbird_mqtt/`.
  - The bridge script hardcoded the wrong Tuya protocol version (3.5 instead of the device's actual 3.4). Fixed in `inkbird_mqtt.py` and pushed to the host.
  - The device's IP address has drifted across at least three different addresses over time (`10.0.0.13`, `10.0.0.23` reservation, `10.0.0.102` current lease) and a stale/unapplied DHCP reservation exists at the router for it.
  - **Underlying cause, confirmed 2026-07-06**: the device itself repeatedly drops its WiFi connection and only comes back after a physical power cycle. This is not a software/config bug — it's most likely the ~97% relative humidity environment it sits in causing WiFi module instability. Not yet fixed.
  - **Next step, not yet done**: put the Inkbird on a smart plug controlled by Home Assistant, with an automation to power-cycle it on a schedule or when it's detected unreachable. This is a workaround, not a fix, and appropriate given the Inkbird is explicitly a secondary/verification sensor, not the primary one.

## Recently cleaned up (2026-07-06)

- Replaced the `operational-core` / `fungi4u-governance` / `mcp-engineering-platform` governance apparatus with this handbook + status + decisions + safety document set (see `HANDBOOK.md` for why).
