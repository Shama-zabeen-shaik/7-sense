# Judging Rubric Mapping

Maps this repository's structure to the hackathon's judging rubric.

| Category | Points | Where addressed in this repo |
|----------|--------|-------------------------------|
| **Technical Implementation** (resource utilization, optimization, latency, performance, energy efficiency) | 40 | [`docs/performance-metrics.md`](performance-metrics.md), [`docs/edge-first-architecture.md`](edge-first-architecture.md), [`models/scoring-engine/`](../models/scoring-engine/), NPU path via QUAD conversion/profiling |
| **Application Use Case and Innovation** (problem solving, creativity, uniqueness, user experience) | 25 | [`README.md`](../README.md) problem statement, [`docs/architecture.md`](architecture.md), multi-device digital-twin concept, [`presentation/five-minute-script.md`](../presentation/five-minute-script.md) |
| **Deployment and Accessibility** (ease of installation, ease of use) | 20 | [`scripts/setup-dev.ps1`](../scripts/setup-dev.ps1), [`scripts/run-demo.ps1`](../scripts/run-demo.ps1), [`docs/demo-mode-vs-live-mode.md`](demo-mode-vs-live-mode.md), [`docs/setup-troubleshooting.md`](setup-troubleshooting.md), Windows `.EXE` packaging |
| **Presentation and Documentation** (clarity, code quality, documentation quality) | 15 | This `docs/` tree overall, [`README.md`](../README.md), [`presentation/`](../presentation/), [`CONTRIBUTING.md`](../CONTRIBUTING.md) |

Total: 100 points.

> Phase 1 note: this mapping is structural (which folder addresses which
> category) — actual scoring evidence (measured latency, recorded demo,
> etc.) lands in later phases.
