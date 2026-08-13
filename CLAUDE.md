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

### ⛔ TRIGGER: the operator mentions a physical change → RE-READ current-configuration BEFORE analysing

*"X was changed"* · *"we fitted Y"* · *"is Z fine?"* — **assume it is already recorded and you have forgotten. Read the section first, then respond.**

- **The rule above was not enough, and failed the same day it was written.** It fires on *"before claiming what hardware exists"*, which requires correctly classifying the question. The operator said *"the bottom duct was changed"*; the session heard *"something new happened, assess it"*, went to the recorder to date it, **attributed an unrelated door-open disturbance to it, and asked for hole counts that had been in the file for two days.** **A rule conditioned on recognising the situation does not fire when the situation is misread.** This one triggers on an observable event instead.
- **Assume no memory across a long session.** The relevant commits — `return cap on`, `return duct drilled to 69 × 12 mm` — were in the `git log` at that session's *first tool call*, and were gone forty messages later. **Rules that depend on recall will fail. Rules that force a re-read at the moment of use will hold.** The section is short and near the top of the file precisely so re-reading is cheap: **do it again rather than trusting that you read it earlier.**
- **This applies while editing that file too.** The same session *edited* `HARDWARE_REFERENCE.md` that morning and never read the block 250 lines below, which flatly contradicted the one it was moving.

### ⛔ EMPHASIS MARKS IMPORTANCE, NOT DECIDEDNESS — read to the end of the block before quoting it

**These documents deliberately preserve superseded reasoning, and they use 🎯 / ⛔ / bold caps on candidates, hypotheses and withdrawn claims exactly as heavily as on conclusions.** So **skimming for emphasis finds the loudest sentence, not the settled one** — and in a file that keeps the arguments it lost, the loudest sentence is often the one that got argued down.

- **The failure, 2026-08-13:** a session read **"🎯 THE FIX IS IN THE SAME TABLE: the WF-100"** and reported a replacement fan had been identified. **Four bullets later the same block says *"Still run the free revert test first… that either saves the purchase or proves it necessary"*, notes the flow figure is *"class-typical, not derived"*, and records that the manufacturer publishes no airflow at all — so the part cannot be sized against the duct even in principle.** The block argues *against* buying. **It was nearly written into the current-configuration summary as a decision.**
- **Before quoting a bolded claim, read to the end of its bullet group.** Look specifically for the qualifier that usually follows: *"still run the test first"*, *"hinges on"*, *"not derived"*, *"⛔ WITHDRAWN"*, *"do not act on this yet"*.
- **A candidate named is not a decision taken.** If it were decided, it would be in **CURRENT CONFIGURATION** — which is the whole reason that section exists.

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
- **⛔ AN ACTION IDENTIFIED IS AN ACTION QUEUED — put it on `todo.fungi4u` in the SAME session, not just in `STATUS.md`.** `STATUS.md` holds the reasoning; **the todo list is the only thing anyone acts from.** A finding written up beautifully in `STATUS.md` and never queued is a finding that will not happen.
  - **Why this is a rule:** on **2026-08-13** a session identified **nine** actionable items — a schema defect, a missing reason code, a firmware sensor, a drain standard, a trolley decision, a live experiment to read — and wrote all nine into `STATUS.md` prose. **None reached the list.** The gap was invisible because the write-up looked thorough.
  - **Rank by distance to income, and do not queue everything.** Enabler-tier work belongs in **one collecting backlog item**, not six separate ones — six make the queue look busy while nothing moves toward income. `STATUS.md`'s own trap warning applies to the todo list too: room and ledger work is more tractable than sales, so it will crowd it out if allowed.
  - **Clearing is fine; losing is not.** Complete a decided item with the decision and its reasoning in the description. **Re-scope a partly-run one rather than deleting it** — record what ran, what it showed, and what now blocks it.
- **⛔ CLOSING AN INVESTIGATION INCLUDES COMPRESSING IT — in the same commit, not later.** When a question is settled, `STATUS.md` keeps only: **the conclusion**, **what was ruled out and why** (this is the valuable half — it stops candidates being re-litigated), and **anything still live**. The blow-by-blow comes out. It is not lost: it is in git, and `HANDBOOK.md` §"Finding out what a document *used to* say" documents how to get it back. **Say in the commit message what you removed and where the conclusion now lives**, so `git log -S` finds it later.
  - **Why this is a rule and not a preference:** `STATUS.md` was cut to **21.5 KB on 2026-07-26** and regrew to **308 KB in 18 days — 14×.** It is a handover document; **no successor will read 308 KB**, so unchecked growth attacks objective #1 directly. The file's header has said *"deliberately short"* throughout, and that alone did not hold it. **Compressing at the moment of closure is cheap because you have just finished thinking about it; a periodic cleanup is expensive and keeps not happening.**
  - **Applies to your own output.** A long session that adds findings all day should compress the ones it closed before it stops.
