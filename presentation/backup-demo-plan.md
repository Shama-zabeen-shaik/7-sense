# Backup Demo Plan

What to show if live hardware fails during the demo.

## If a specific device fails

- Switch that device to demo mode (see `docs/demo-mode-vs-live-mode.md`) and
  continue — the rest of the pipeline should be unaffected. See
  `docs/device-fallback-plan.md` for the per-device mock path.

## If the Windows control surface itself fails

- TBD — fallback plan (e.g. pre-recorded screen capture) to be defined once
  a working build exists.

## If network/Wi-Fi is unavailable in the room

- TBD — confirm which parts of the pipeline require local network (phone/
  watch/RB3 over WebSocket) vs. USB-only (Arduino UNO Q serial) and prepare
  a USB-only fallback path.

## Recording as insurance

- TBD — record a full successful run ahead of time per
  `demo-video-checklist.md`, to fall back on if live demo fails entirely.
