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
