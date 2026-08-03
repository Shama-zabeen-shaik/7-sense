# Seventh Sense

**A privacy-first, multi-device edge AI system — your Snapdragon-powered cognitive
performance copilot.**

Seventh Sense fuses body, behavior, and environmental signals from a constellation
of Snapdragon-powered devices into a personalized, user-owned digital twin of your
cognitive and physical state — stress, focus, fatigue — and delivers contextual,
local-first interventions to help you recover before you consciously notice you
need to.

## Problem Statement

Modern professionals often experience stress, cognitive overload, and fatigue
well before they consciously recognize it. By the time it's noticed, the
workday's momentum (or the meeting, or the deadline) has already been lost to
it. Existing wellness apps are single-device, cloud-dependent, and blind to the
context around a person — they see a heart-rate number, not the environment,
workload, and behavior that produced it. Seventh Sense is built to close that
gap: a human-state intelligence platform that reasons across multiple
Snapdragon-powered devices, entirely on-device, without shipping raw personal
data anywhere.

This is **not** a medical or diagnostic tool, and **not** an employee
monitoring tool. It is a personal wellness and productivity signal platform,
under the user's own control.

## Architecture at a Glance

Five Snapdragon-powered devices, each with a distinct role:

1. **Snapdragon X Elite laptop (Windows)** — control surface: local scoring,
   local reasoning/orchestration, performance metrics, privacy dashboard;
   packaged as a Windows `.EXE`.
2. **Samsung Galaxy S25 Ultra (Snapdragon 8 Elite)** — phone companion: user
   check-ins, notification-pressure simulation, intervention display.
3. **WRD6100 SKU1 DVT1.1 watch** — body/activity context: activity level,
   stillness duration, motion variability, HR trend and skin temperature
   trend where accessible.
4. **RB3 Gen 2 Vision Kit** — environmental context: lighting level,
   motion/environment load, non-identifying privacy-safe features only.
5. **Arduino UNO Q** — physical intervention layer: ambient pixels, buttons,
   knob, distance/presence sensing, thermo, and an optional buzzer.

See [`docs/architecture.md`](docs/architecture.md) for the full system diagram.

## Repo Layout

| Path | Contents |
|------|----------|
| `apps/` | Per-device applications (Windows control surface, phone companion, watch ingestion, RB3 vision context) |
| `firmware/` | Arduino UNO Q firmware and intervention modules |
| `shared/` | Cross-device schemas, sample synthetic data, and wire protocol docs |
| `models/` | Scoring engine (the fusion/scoring model) |
| `docs/` | Architecture, privacy, device integration, and judging docs |
| `scripts/` | Dev setup, demo run, test, and packaging scripts |
| `packaging/` | Windows packaging assets |
| `presentation/` | Demo script, judge Q&A, backup plan |
| `assets/` | Screenshots, diagrams, audio for the demo/README |

## Setup

TBD — filled in as each module lands. See [`scripts/setup-dev.ps1`](scripts/setup-dev.ps1)
for the current (Phase 1 skeleton) entry point.

## Status

Private repo — will be made public at final hackathon submission.

## Team

<!-- TODO: add team member names + emails -->

- **Shama Zabeen Shaik** — Team Lead (shamazab@qti.qualcomm.com)
- Dilshath Shaik (dilshath@qti.qualcomm.com)
- Manasa Bhupathiraju (mbhupath@qti.qualcomm.com)
- Gerard Louis Recinto (grecinto@qti.qualcomm.com)

<!-- TODO: confirm final roster and emails before public submission -->

## License

MIT — see [`LICENSE`](LICENSE).
