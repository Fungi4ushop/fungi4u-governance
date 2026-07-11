# Fungi4u

A grey oyster mushroom cultivation business, run from home in Pretoria by one operator. Built for succession-readiness — someone else should be able to pick this up and run it, or decide not to, without reconstructing context from chat history.

## Always read first, for any task

- `fungi4u-governance/HANDBOOK.md` — what this business is and how it runs
- `fungi4u-governance/STATUS.md` — what's currently true (working / broken / in progress)
- `fungi4u-governance/DECISIONS.md` — why things are built the way they are
- `fungi4u-governance/SAFETY.md` — what must never be touched, and recovery basics

## Read additionally, depending on the task

- **Climate control / microclimate / hardware / GPIO / wiring / RS485 / Modbus / sensor configuration work** → `stock-control/docs/MICROCLIMATE.md` and `stock-control/docs/HARDWARE_REFERENCE.md`
- **Stock ledger / substrate / flush / processing / sales work** → `stock-control/docs/LEDGER.md` (design, current honest state, and adoption roadmap — read first), plus `stock-control/index.html` and the Supabase schema/functions it calls (`substrate_batches`, `fn_process_oyster_packing`, `fn_post_stock_event`, `v_operational_snapshot`)
- **Inkbird sensor / MQTT bridge work** → `stock-control/home-assistant/inkbird-mqtt-addon/`
- **Liquid culture / grain spawn / cultivation technique** → not yet documented as of 2026-07-06. Ask rather than assume — see the note in `HANDBOOK.md`'s production cycle section.

## Rules for working in this project

- No overengineering. Match effort to the actual scale of a one-person home business, not an enterprise.
- Preserve the architectural boundaries already established (ledger append-only, safety logic local to the device, biology/economics/processing kept separate) — see `SAFETY.md` and `DECISIONS.md` before changing any of them.
- Measured values only — don't estimate or assume where a real number should be recorded.
- When you learn something that explains *why* a thing is built the way it is, add it to `DECISIONS.md`. When the current state of something changes, update `STATUS.md`. Don't create new process or ceremony beyond that.
