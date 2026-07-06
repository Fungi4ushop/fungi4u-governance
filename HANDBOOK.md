# Fungi4u Handbook

## What this is

A grey oyster mushroom cultivation business, run from home in Pretoria. One operator. The goal: run it well enough that it could be handed over to someone else at any time — a child, a hired hand, or sold — without that person needing to reconstruct anything from memory or chat history.

## The production cycle

**Note: this section only covers the part currently tracked in the ledger, starting from bulk substrate.** The real cultivation process starts earlier — a liquid culture cycle, then a grain spawn cycle, both feeding into the bulk substrate step below. Not yet documented here; to be added once written up properly (see `DECISIONS.md`/`STATUS.md` for how this document set evolves). If you're reading this and those stages still aren't written up, ask about them explicitly rather than assuming the process starts at substrate.

1. **Substrate batch inserted** — a batch of growing substrate bags is logged (batch ID, bag count, total weight).
2. **Flush 1 measured** — first harvest wave weighed and recorded against the batch.
3. **Flush 2 measured** — second harvest wave weighed and recorded.
4. **Harvest processed** — raw harvest weight converted into packed product (grey oyster, 250g packs) plus waste, recorded together in one step.
5. **Packed sold** — units sold are deducted from packed stock.

Every step above is logged through the control panel (`stock-control/index.html`) into the Supabase ledger. The ledger is the only source of truth — see `SAFETY.md`.

## The three systems

| System | Role | Where |
|---|---|---|
| **Stock ledger** | Records every substrate batch, flush, processing, and sale. Append-only — nothing is ever edited or deleted, only added. | Supabase, driven by `stock-control/index.html` |
| **Climate control (fruiting room)** | Primary environmental control — temperature, humidity, CO2, fan and humidifier control. Runs on an ESPHome device with a Senseair S8 CO2 sensor as the authoritative sensor. Also has an **Inkbird CO2/temp/humidity sensor as a secondary, verification-only input** — never authoritative, and as of 2026-07-06 known to have a WiFi stability problem (see `STATUS.md`), so operations don't depend on it. Design and reasoning: `MICROCLIMATE.md`. Exact GPIO/wiring/terminal reference: `HARDWARE_REFERENCE.md`. | `stock-control/esphome/fruiting-room-controller.yaml` (primary); `stock-control/home-assistant/inkbird-mqtt-addon/` (secondary sensor bridge) |
| **Home Assistant** | The supervisory platform, separate from any one sensor or controller. Hosts the MQTT broker (Mosquitto), runs the Inkbird bridge add-on, provides dashboards/alarms/operator interaction, and (added 2026-07-05/06) exposes an MCP interface so an AI coding session can read live state directly. Not authoritative for safety — per `SAFETY.md`, the ESPHome device enforces its own limits regardless of whether Home Assistant is up. | Raspberry Pi (Home Assistant OS) on the home network |

## Where things live

- **Code and configuration**: four git repositories under `Fungi4ushop` on GitHub — `stock-control` (the one repo that does real work), plus `operational-core`, `fungi4u-governance`, and (soon to be retired/simplified) `mcp-engineering-platform`.
- **Business data**: Supabase (see `SAFETY.md` for access rules).
- **Physical control**: Home Assistant, running on a Raspberry Pi (Home Assistant OS) on the home network.
- **Credentials**: see "Credentials" below — do not go looking in Git or chat history for these.

## Credentials

All real account credentials (GitHub, Supabase, Home Assistant login, router admin, MQTT broker) belong in **one password manager** — Bitwarden, since that's already the one referenced as a critical recovery account elsewhere in this repo's history. If you find a credential anywhere else (a chat transcript, a config file, a browser's saved passwords), treat that as a temporary leak to clean up, not a legitimate second home for it.

Machine-local technical credentials created for AI-assisted engineering sessions (e.g. SSH keys for deploying to the Home Assistant host, GNOME-keyring entries used only by a coding assistant on one specific laptop) don't need to go in Bitwarden — they're disposable and regenerable, not business-critical.

## Starting a new AI chat about a specific system

You don't need to mention any document by name. A `CLAUDE.md` file at the top of the projects folder is loaded automatically at the start of every session and already tells the assistant which documents to check for which kind of task. Just say what you're working on:

> I'm working on [the ledger / the microclimate / the Inkbird bridge] for the Fungi4u mushroom business. Current objective: [state it].

That's the whole prompt. This replaces the old per-repo "Chat Initialization Template" that only existed for the ledger and required listing documents by hand — the same simple pattern now applies to any part of the business, with the document lookup happening automatically instead of manually.

## What replaced the old governance repos

`operational-core`, `fungi4u-governance`, and `mcp-engineering-platform` previously carried a full constitutional/amendment framework, a document lifecycle model, and a bespoke AI-engineering platform. None of it was about running the mushroom business, and the volume of process documentation had grown to dwarf the actual amount of working code and hardware it was meant to govern. It's been replaced by this handbook plus `STATUS.md`, `DECISIONS.md`, and `SAFETY.md`. If you're reading this after a long gap: start with `STATUS.md` for what's currently true, then `SAFETY.md` before changing anything.
