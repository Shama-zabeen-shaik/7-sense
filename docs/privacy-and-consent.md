# Privacy and Consent

This document expands on [`../PRIVACY.md`](../PRIVACY.md) with a skeleton of
the consent flow a user goes through before any signal is collected.

## Consent flow (skeleton)

1. **Onboarding screen.** Before any device is connected, the user sees a
   plain-language explanation of what Seventh Sense does and does not do:
   - What it does: fuses derived signals from connected devices into a
     personal stress/focus/fatigue estimate, on-device.
   - What it does not do: no medical diagnosis, no employer reporting, no
     raw audio/video/content collection.
2. **Per-device opt-in.** For each device (watch, phone, RB3 Vision Kit,
   Arduino UNO Q), the user explicitly enables it. Nothing is collected
   from a device until it is opted in.
3. **Per-signal-category opt-in (TBD).** Within a device, the user may be
   able to disable specific signal categories (e.g. disable HR trend on the
   watch while keeping activity level). TBD — depends on watch SDK
   capabilities.
4. **Visible status indicator.** The control surface's privacy dashboard
   shows, at a glance, which devices/signals are currently active.
5. **Revocation.** The user can disable any device/signal at any time, and
   previously collected local data can be cleared. TBD — exact data-clearing
   mechanism.

## Non-negotiables (see also `../PRIVACY.md`)

- No raw audio, video, meeting, or chat content is ever in scope for
  collection — this is not a configurable setting, it is an architectural
  boundary.
- No coworker identity data.
- No medical claims presented anywhere in the consent flow.

## Open items

- TBD — legal review of consent language once product scope is finalized.
- TBD — data export/deletion UX.
