# Safety & Continuity

Read this before changing anything, and especially before touching the stock ledger or the fruiting room's physical control systems.

## If you are taking over this system

This business runs on three things: a stock ledger, a climate-controlled fruiting room, and your own judgment. It's built to be simple, layered, and hard to break by accident. Keep it that way — favor clarity and stability over adding features.

## What must never be touched

- The stock ledger is **append-only**. Never edit or delete a row directly. All stock movement goes through the existing SQL functions.
- No UI logic may bypass database rules. The control panel (`index.html`) is a thin input layer, not where the rules live.
- Do not calculate yield in the UI — it's derived from measured values in the database only.
- Do not merge biological tracking (substrate/flushes) into ledger logic — keep the domains separate.

## Where the truth lives

- The **Supabase database** is authoritative for stock. If something looks wrong, check the database first, not the web page.
- **Device-level control logic** (on the ESPHome/fruiting-room controller) is authoritative for physical safety. Home Assistant supervises and displays; it does not override the device's own safety enforcement. If Home Assistant, the network, or Supabase goes down, the physical safety limits (temperature/humidity bounds, fan control) must keep working regardless.
- **Manual override must always be physically possible** on the climate control hardware. If you can't manually override something in an emergency, that's a defect to fix, not a limitation to work around.

## Credentials

All real credentials belong in **one password manager** (Bitwarden). They are never stored in:
- Git repositories
- Markdown documentation
- Application code
- Chat history

If you find a credential in any of those places, rotate it and move it to the password manager.

## If restarting after a long delay

1. Read `STATUS.md` for the current honest state of things.
2. Confirm Supabase access and that the snapshot view (`v_operational_snapshot`) returns data.
3. Confirm Home Assistant is reachable and the fruiting room controller is reporting.
4. Only then make any changes.

## Recovery — what you need to get everything back

The system is fully recoverable with access to **four** things:
- **Bitwarden** (all credentials — master password required)
- **Aegis** (TOTP authenticator app — required to actually log into Bitwarden, GitHub, and Supabase, since all three have TOTP enabled). Aegis itself has an encrypted backup stored locally plus a secondary copy on Google Drive.
- **GitHub** (all code and configuration)
- **Supabase** (all business data)

Recovery codes for Bitwarden/GitHub are stored in a Bitwarden hidden custom field, plus an offline paper copy. Supabase's service role key and publishable key are stored in Bitwarden.

No single local device or laptop is a point of failure — everything of lasting value lives in one of these four places. **Losing Aegis without its backup is the one way this recovery chain actually breaks** — the encrypted local backup and the Google Drive copy both matter.

## Future hardening (not urgent, worth doing eventually)

- SSH key management audit
- GitHub Personal Access Token rotation policy
- Supabase key rotation policy
- Periodic backup verification (actually test restoring from the Aegis backup occasionally, don't just assume it works)

## Do not

- Manually adjust stock tables.
- Calculate yield outside the database.
- Store secrets in Git, chat, or documentation.
- Introduce automation or complexity to the physical control systems without first understanding the existing safety design (local enforcement, manual override, fail-safe on disconnection).
- Let a sensor that's explicitly secondary (e.g. the Inkbird) become something operations quietly depend on.

If in doubt, stop and re-read this document before proceeding.
