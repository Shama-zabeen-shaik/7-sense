# Performance Metrics (Skeleton)

Metrics to be measured once the scoring engine and control surface exist.
Ties directly to the **Technical Implementation (40 pts)** judging category —
see [`judging-rubric-mapping.md`](judging-rubric-mapping.md).

## Latency

- TBD — end-to-end latency from signal arrival to intervention dispatch.
- TBD — scoring-model inference latency on NPU vs. CPU (via QUAD
  `profile_workload`).

## Throughput

- TBD — sustained signal ingestion rate across all connected devices.

## Power / energy efficiency

- TBD — power draw comparison across execution targets (CPU/GPU/NPU) via
  QUAD `orchestrate_workload`, where measurable.

## Resource utilization

- TBD — CPU/NPU/memory utilization on the Windows control surface under
  sustained multi-device load.

## Methodology (to fill in)

- TBD — measurement tooling, sample size, and reporting format once
  benchmarks are run. No numbers are recorded here yet — do not fabricate
  benchmark results before real measurements exist.
