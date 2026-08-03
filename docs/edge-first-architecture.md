# Edge-First Architecture

Seventh Sense is built edge-first: inference happens on-device, primarily on
the Snapdragon X Elite laptop, rather than in a cloud service.

## Why local-first

- **Privacy.** Signals about a person's stress, focus, and fatigue are
  sensitive by nature. Keeping inference on-device means the raw and derived
  signals never have to leave the user's own hardware to produce a result.
- **Latency.** Interventions are only useful if they arrive close to the
  moment they're needed. Round-tripping to a cloud service adds latency and
  a network dependency that a real-time cognitive-state loop can't afford.
- **No connectivity dependency.** The system should keep working on a plane,
  in a low-signal office, or anywhere else the network is unreliable.
- **User ownership.** A local-first digital twin is a user-owned artifact,
  not a byproduct sitting in a third-party's data warehouse.

## Where QUAD fits (Windows-side NPU path)

The Windows control surface targets the Snapdragon X Elite's Hexagon NPU for
the fusion/scoring model's inference. [QUAD](https://github.com/CBN-AI-TEAM/QUAD)
(Qualcomm's model conversion/profiling MCP tooling) is the intended path for:

- **Model conversion** — converting the scoring engine (once trained) from
  its source framework into a QNN/SNPE artifact suitable for the Hexagon NPU,
  via QUAD's `convert_model` tool.
- **Profiling** — measuring on-device latency, throughput, and (where
  available) power characteristics of the scoring model on the actual NPU,
  via QUAD's `profile_workload` tool, to substantiate the Technical
  Implementation scoring criteria (see
  [`judging-rubric-mapping.md`](judging-rubric-mapping.md)).
- **Orchestration** — deciding whether a given stage of the pipeline runs on
  CPU, GPU, or NPU, via QUAD's `orchestrate_workload` tool, once there is more
  than one candidate execution target.

This integration is not yet implemented — TBD once the scoring engine exists
in a convertible form (ONNX or equivalent). See
[`models/scoring-engine/README.md`](../models/scoring-engine/README.md).

## Non-goals

- No requirement on cloud connectivity for core scoring/intervention loop.
- No raw signal upload to any server by default (see [`../PRIVACY.md`](../PRIVACY.md)).
