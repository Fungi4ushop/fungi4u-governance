# Decisions

Purpose: record *why* things are built the way they are, so a decision doesn't get accidentally reversed by someone (including a future AI session) who wasn't there for the reasoning. Plain chronological list — no IDs, no formal approval process, no versioning ceremony. Add a short entry here whenever future-you or a successor would otherwise have to guess "why is this like this?"

---

**2026-01-26 — Stock ledger is append-only.** Rows are never edited or deleted, only added. All stock movement goes through SQL functions, not direct table edits. Historical truth must never change after the fact — if a mistake is made, correct it with a new entry, not by rewriting history.

**2026-01-26 — Physical safety logic runs locally, on the device, not in Home Assistant.** Home Assistant is a supervisory/monitoring layer, not the authority. If the network, Supabase, or Home Assistant goes down, the climate control hardware must keep enforcing its own safety limits regardless. Manual override must always be physically possible.

**2026-01-26 — The three domains (economic ledger, biological tracking, physical processing) are kept separate and must not be mixed.** Yield is calculated from measured values only, never estimated in the UI.

**2026-05-30 — Senseair S8 (via ESPHome) is the primary CO2 sensor; the Inkbird device is secondary/verification only.** Do not treat Inkbird readings as authoritative, and do not block operations on the Inkbird bridge being up.

**2026-01-26 — Environmental control priority when conflicts arise: Temperature > CO2 > Humidity.** Humidity may drift from target to protect temperature; CO2 control normally takes priority over temperature, but an approved temperature safety limit always wins over a CO2 target. Full reasoning in `MICROCLIMATE.md`.

**2026-01-26 — Fresh air is introduced into the plenum and mixed before reaching the room, not injected directly.** Chosen to reduce direct airflow disturbance on the mushrooms and to support future CO2 management. The original direct-injection fan is retired in favor of this approach.

**Date unknown (before 2026-06-26) — Replaced the Sonoff-based relay switching with a ULN2803 relay driver subsystem.** The old Sonoff wiring (W8–W17) is fully retired; see `HARDWARE_REFERENCE.md` for the current relay wiring. If you find any reference to Sonoff relays elsewhere, it's stale.

**2026-07-06 — Inkbird bridge's Tuya protocol version corrected from 3.5 to 3.4**, matching the device's actual firmware (confirmed via the LocalTuya integration's stored diagnostics). This was silently causing every connection attempt to fail.

**2026-07-06 — Chose DFRobot SEN0659 (RS485 CO2) and SEN0438 (RS485 temp/humidity) to replace the DHT22 pair.** Both confirmed as the actual sensors, register maps and addressing documented in `HARDWARE_REFERENCE.md`. The CO2 UART reservation (TX2/RX2) is kept, but its reasoning changed: it's no longer earmarked for a specific planned sensor (the new CO2 sensor is RS485, sharing the TB12 bus with the temp/humidity sensor instead) — it's now just a low-cost hedge in case a future sensor is needed and buying another RS485 device isn't worth it.

**2026-07-06 — Retired the `operational-core`, `fungi4u-governance`, and `mcp-engineering-platform` governance repos** in favor of this simplified handbook/status/decisions/safety document set. The prior structure (constitution, amendment process, document lifecycle model, bespoke AI-engineering platform) had grown to significantly exceed the size and complexity of the actual business it was meant to govern, and its own decision log contained no entries about the business itself — only about the governance process. See `HANDBOOK.md`.
