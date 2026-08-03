# Data Collection Protocol

This document specifies what signals are collected per device, in what form,
and how long they are retained.

## Principle

All signals collected are **aggregated/derived**, never raw. See
[`../PRIVACY.md`](../PRIVACY.md) for the full statement of what is explicitly
excluded (raw audio/video, meeting/chat content, coworker identity,
performance labels).

## Per-device signal list (derived form only)

| Device | Derived signals (examples) | Raw form ever stored? |
|--------|------------------------------|-------------------------|
| Snapdragon X Elite laptop | screen-active minutes, app-switch frequency, local scoring output | No |
| Samsung Galaxy S25 Ultra | check-in responses, notification-pressure simulation events | No |
| WRD6100 watch | activity level, stillness duration, motion variability, HR trend, skin temperature trend | No |
| RB3 Gen 2 Vision Kit | ambient lux level, motion/environment load | No — no raw video by default |
| Arduino UNO Q | button press events, knob position, distance/presence reading, thermo reading | No |

Exact field-level definitions live in [`shared/schemas/`](../shared/schemas/).

## Retention

- **Local only, by default.** All derived signals and scoring outputs are
  stored on the user's own Snapdragon X Elite laptop.
- **No cloud upload by default.** There is no default cloud sync, backup, or
  telemetry path for personal signal data in this project.
- TBD — exact local retention window (e.g. rolling N days) once the scoring
  engine's data needs are finalized.

## Access

- Only the user, via the local privacy dashboard, has access to their own
  collected signals in the current design.
