# Device Integration

Phase 1 skeleton — one section per device. Protocol/transport details marked
TBD where not yet confirmed against the actual device SDK.

## 1. Snapdragon X Elite laptop (Windows control surface)

- **Role:** Local fusion/scoring, orchestration, performance metrics,
  privacy dashboard.
- **Integration path:** Native Windows app (packaged as `.EXE`). Hosts the
  local WebSocket hub described in
  [`shared/protocol/websocket-events.md`](../shared/protocol/websocket-events.md).
- **Transport:** Acts as the hub other devices connect to (WebSocket for
  phone/watch/RB3, serial for Arduino UNO Q).
- **Status:** TBD — verify against device SDK for NPU inference bindings
  (see [`edge-first-architecture.md`](edge-first-architecture.md)).

## 2. Samsung Galaxy S25 Ultra (phone companion)

- **Role:** User check-ins, notification-pressure simulation, intervention
  display.
- **Integration path:** Prefer a web companion (browser-based) over a native
  APK unless a native capability proves necessary.
- **Transport:** TBD — likely WebSocket to the laptop hub over local network.
- **Status:** TBD — verify against device SDK / browser capability set.

## 3. WRD6100 SKU1 DVT1.1 watch

- **Role:** Body/activity context — activity level, stillness duration,
  motion variability, HR trend (if accessible), skin temperature trend (if
  accessible). No diagnosis, no medical claims.
- **Integration path:** TBD — verify against device SDK for the available
  data channels and pairing/companion-app requirements.
- **Transport:** TBD.
- **Status:** Not started. See
  [`apps/watch-ingestion/README.md`](../apps/watch-ingestion/README.md).

## 4. RB3 Gen 2 Vision Kit

- **Role:** Environmental context — lighting level, motion/environment load,
  non-identifying privacy-safe features only. No face recognition. No raw
  video storage by default.
- **Integration path:** TBD — verify against device SDK for the camera/vision
  pipeline API.
- **Transport:** TBD.
- **Status:** Not started. See
  [`apps/rb3-vision-context/README.md`](../apps/rb3-vision-context/README.md).

## 5. Arduino UNO Q

- **Role:** Physical intervention layer — pixels, buttons, knob, distance,
  thermo, buzzer.
- **Integration path:** Serial command protocol from the Windows control
  surface. See
  [`shared/protocol/serial-commands.md`](../shared/protocol/serial-commands.md).
- **Transport:** USB serial (TBD baud rate / framing — verify against device
  SDK once firmware is written).
- **Status:** Not started. See
  [`firmware/arduino-unoq/README.md`](../firmware/arduino-unoq/README.md).

## See also

- [`device-fallback-plan.md`](device-fallback-plan.md) — mock data path per
  device if it isn't available at demo time.
