# Architecture

> Phase 1 skeleton — section headers and a high-level diagram only. Detail
> lands as each module is implemented.

## System Diagram (high level)

```
 [Watch]        [RB3 Vision Kit]      [Phone Companion]     [Arduino UNO Q]
 WRD6100        environmental          check-ins,             pixels / buttons
 body/activity  context (lux,          notification-          knob / distance
 context         motion load)          pressure sim            thermo / buzzer
     |                |                     |                       ^
     |  local feature |  local feature      | local feature         |
     |  extraction    |  extraction         | extraction            | intervention
     v                v                     v                       | dispatch
     +--------------------+------------------+                      |
                          |                                         |
                          v                                         |
            +-------------------------------+                      |
            |  Snapdragon X Elite laptop    |----------------------->
            |  (Windows control surface)    |
            |  - local fusion / scoring      |
            |  - local reasoning /           |
            |    orchestration               |
            |  - performance metrics         |
            |  - privacy dashboard           |
            +-------------------------------+
```

## End-to-End Demo Flow

The demo sequence below is the concrete walkthrough of the diagram above —
each step names the device and the observable action, in order:

1. **Samsung Galaxy S25 Ultra** sends a user/context signal (check-in,
   notification-pressure simulation) — `phone_context_frame`.
2. **WRD6100 watch** sends body/activity context (activity level, stillness
   duration, motion variability) — `watch_feature_frame`.
3. **RB3 Gen 2 Vision Kit** sends environmental context (lighting level,
   motion/environment load) — `rb3_context_frame`.
4. **Snapdragon X Elite laptop** fuses all three signals and scores the
   user's state **locally** — no signal leaves the device for scoring.
5. **Arduino UNO Q pixels** shift from green → yellow → red as the scored
   state escalates — the ambient, glanceable readout.
6. A **blue breathing-pulse** pattern starts on the pixels — the ambient
   intervention cue, timed to a calming breath pace.
7. **Phone companion** shows a recovery prompt (the same intervention,
   surfaced where the user is looking).
8. **User presses the "Helpful" button** on the Arduino UNO Q — explicit
   feedback on whether the intervention worked, fed back into the loop.
9. **Windows dashboard** shows the score improving in response to the
   intervention + feedback.
10. **Performance panel** shows latency and resource usage for the whole
    loop — the on-device evidence for the Technical Implementation judging
    criterion (see [`performance-metrics.md`](performance-metrics.md)).

This is the sequence [`presentation/five-minute-script.md`](../presentation/five-minute-script.md)
walks through live; step timings for each item are TBD until the build exists.

## Layers

### 1. Sensing (per device)
TBD — see [`device-integration.md`](device-integration.md) for the per-device
signal list and transport.

### 2. Local feature extraction (per device)
TBD — each device reduces raw sensor data to derived, non-identifying feature
frames before anything leaves the device. See
[`shared/schemas/`](../shared/schemas/) for the frame contracts.

### 3. Transport / hub
TBD — see [`shared/protocol/websocket-events.md`](../shared/protocol/websocket-events.md)
and [`shared/protocol/serial-commands.md`](../shared/protocol/serial-commands.md).

### 4. PC-side fusion / scoring
TBD — see [`models/scoring-engine/`](../models/scoring-engine/) and
[`model-card.md`](model-card.md).

### 5. Intervention dispatch
TBD — scored state feeds back out to phone (notification/display), watch
(haptic, if supported), and Arduino UNO Q (ambient pixels, buzzer, etc.).

## Open questions

- TBD — verify against device SDK for exact transport bindings per device.
- TBD — finalize fusion model architecture (see `models/scoring-engine/model_card.md`).

## Related docs

- [`edge-first-architecture.md`](edge-first-architecture.md)
- [`device-integration.md`](device-integration.md)
- [`device-fallback-plan.md`](device-fallback-plan.md)
- [`demo-mode-vs-live-mode.md`](demo-mode-vs-live-mode.md)
