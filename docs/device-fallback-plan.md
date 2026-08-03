# Device Fallback Plan

Every device in Seventh Sense has a mock data path so a demo can proceed even
if a given piece of hardware isn't available, isn't connected, or fails at
demo time. This directly maps to the `mock/` folders under `apps/`.

## Fallback matrix

| Device | If unavailable... | Mock data source |
|--------|--------------------|-------------------|
| Snapdragon X Elite laptop | N/A — this is the control surface; no fallback | N/A |
| Samsung Galaxy S25 Ultra (phone companion) | Fall back to the web companion in a browser tab on the laptop | `apps/phone-companion/web-fallback/` |
| WRD6100 watch | Replay synthetic watch stream | `apps/watch-ingestion/mock/`, `shared/sample-data/synthetic_watch_stream.csv` |
| RB3 Gen 2 Vision Kit | Replay synthetic context frames | `apps/rb3-vision-context/mock/`, `shared/sample-data/synthetic_rb3_context.csv` |
| Arduino UNO Q | Simulate intervention dispatch in a UI panel instead of on physical hardware | TBD — software simulator, see `firmware/arduino-unoq/README.md` |

## Principles

- Every mock source should conform to the same schema as the corresponding
  live source (see [`shared/schemas/`](../shared/schemas/)) so the fusion/
  scoring layer cannot tell the difference.
- Mock/demo mode should be a deliberate, visible toggle — not a silent
  fallback — so judges and users always know which mode is active. See
  [`demo-mode-vs-live-mode.md`](demo-mode-vs-live-mode.md).
- TBD — finalize exact mock playback timing/loop behavior per device.
