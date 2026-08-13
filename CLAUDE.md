# Fungi4u

A grey oyster mushroom cultivation business, run from home in Pretoria by one operator. Built for succession-readiness — someone else should be able to pick this up and run it, or decide not to, without reconstructing context from chat history.

## Always read first, for any task

- `fungi4u-governance/HANDBOOK.md` — what this business is and how it runs
- `fungi4u-governance/STATUS.md` — what's currently true (working / broken / in progress)
- `fungi4u-governance/DECISIONS.md` — why things are built the way they are
- `fungi4u-governance/SAFETY.md` — what must never be touched, and recovery basics

## ⚠️ Which file is authoritative for WHAT IS INSTALLED

**Before claiming anything about what hardware exists, is installed, or is running — read `stock-control/docs/HARDWARE_REFERENCE.md` §"CURRENT CONFIGURATION" (top of the file) FIRST.** It is the single source of truth for physical configuration, along with the network settings table.

**`STATUS.md` and `DECISIONS.md` are narrative.** They record how things came to be, and they describe **past** states as fully as present ones — often at far greater length, because a removal or a failure is a better story than a quiet replacement. **They are not an inventory. Do not infer current state from them.**

This is a real failure, not a hypothetical: on **2026-08-13** a session read three long write-ups of the fresh-air fan's *removal* (2026-07-18), never reached the one-line record of its *replacement* (2026-07-23), declared the room passively ventilated, and built two recommendations on it. **Do not copy configuration facts back into `STATUS.md`** — one home, or it drifts again.

## Read additionally, depending on the task

- **Climate control / microclimate / hardware / GPIO / wiring / RS485 / Modbus / sensor configuration work** → `stock-control/docs/HARDWARE_REFERENCE.md` (**current configuration first**, then the detail) and `stock-control/docs/MICROCLIMATE.md`
- **Stock ledger / substrate / flush / processing / sales work** → `stock-control/docs/LEDGER.md` (design, current honest state, and adoption roadmap — read first), plus `stock-control/index.html` and the Supabase schema/functions it calls (`substrate_batches`, `fn_process_oyster_packing`, `fn_post_stock_event`, `v_operational_snapshot`)
- **Inkbird sensor / MQTT bridge work** → `stock-control/home-assistant/inkbird-mqtt-addon/`
- **Liquid culture / grain spawn / cultivation technique** → not yet documented as of 2026-07-06. Ask rather than assume — see the note in `HANDBOOK.md`'s production cycle section.

## Rules for working in this project

- No overengineering. Match effort to the actual scale of a one-person home business, not an enterprise.
- Preserve the architectural boundaries already established (ledger append-only, safety logic local to the device, biology/economics/processing kept separate) — see `SAFETY.md` and `DECISIONS.md` before changing any of them.
- Measured values only — don't estimate or assume where a real number should be recorded.
- When you learn something that explains *why* a thing is built the way it is, add it to `DECISIONS.md`. When the current state of something changes, update `STATUS.md`. Don't create new process or ceremony beyond that.
