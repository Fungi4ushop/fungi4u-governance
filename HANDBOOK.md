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

1. **Substrate batch inserted** — a batch of growing substrate bags is logged (batch ID, bag count, total weight). One batch a week, made on Tuesdays (~24 × 4kg bags from a 110L drum).
2. **Pickings recorded** — mushrooms are **not** harvested in one event: each is picked as it's ready, over several days, and cold-stored just above freezing. Each **picking** is weighed and logged against its batch. A "flush" is many pickings; a batch gives two flushes (separated by a ~1–2 week rest), then its bags are removed. Flush number is inferred by the system from the rest-gap between pickings, not entered.
3. **Harvest processed** — the accumulated raw stock (from cold storage) is cleaned and packed: raw is converted into packed product (grey oyster, 250g packs) plus waste. Processing consumes the whole accumulated raw balance, so it mixes pickings across batches.
4. **Packed sold** — units sold are deducted from packed stock.

Every step above is logged through the control panel (`stock-control/index.html`) into the Supabase ledger. The ledger is the only source of truth — see `SAFETY.md`. **Note (2026-07-11):** the ledger/panel is mid-migration to this model — the per-picking capture exists; the panel and processing rework are in progress (see `stock-control/docs/LEDGER.md` and `DECISIONS.md`). The system was built earlier but never used with real data; disciplined capture (Phase C) also awaits a harvest scale (a flush exceeds the kitchen scale).

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
