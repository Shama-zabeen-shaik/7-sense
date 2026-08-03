# Demo Mode vs. Live Mode

Seventh Sense supports two explicit run modes.

## Demo mode

- Uses scripted/synthetic data from [`shared/sample-data/`](../shared/sample-data/)
  played back on a loop or timeline.
- Purpose: a reliable, repeatable demo that doesn't depend on live hardware
  being present, paired, or behaving correctly in the room.
- Entry point (Phase 1 skeleton): [`scripts/run-demo.ps1`](../scripts/run-demo.ps1).
- Should be visibly labeled in the control surface UI (e.g. a "DEMO MODE"
  banner) so it's never mistaken for live data — TBD exact UI treatment.

## Live mode

- Uses real signals from connected devices (watch, RB3 Vision Kit, phone,
  Arduino UNO Q) over their respective transports.
- Purpose: the real system, for real use and for judged technical evaluation
  of actual device integration.
- Falls back per-device to demo/mock data if a device is unavailable — see
  [`device-fallback-plan.md`](device-fallback-plan.md).

## Switching between modes

TBD — exact toggle mechanism (config flag, UI switch, or per-device
override) to be finalized once the control surface exists.
