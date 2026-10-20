---
name: performance-testing
description: "Measure frame time, resource use, stutter and load performance with reproducible workloads."
---

# Game performance measurement

**Primary role:** Game Developer executes; Director reviews. **Use when:** a feature affects rendering/simulation cost or a platform-performance gate is due.

## Required inputs

- Performance targets from project profile.
- Representative scene/build and runtime profiling tools.
- Hardware/OS settings and a repeatable test route.

## Procedure

1. Define success using measurable targets: frame-time percentiles, CPU/GPU, memory, load duration or draw calls.
2. Choose representative worst/typical scenes and keep resolution/graphics settings fixed.
3. Warm up the game if appropriate and capture multiple runs with identifiable build and hardware.
4. Attribute bottlenecks using actual profiler data, not surface-level FPS observations only.
5. Compare metrics to budget and record variance/confounding factors.
6. Deliver a concise priority list for `performance-optimization`, then rerun after changes.

## Deliverables

- Performance results with hardware/build/scenario context.
- Budget comparison and recommended bottlenecks to investigate.

## Validation / done criteria

- [ ] Numbers can be reproduced under documented conditions.
- [ ] Important tails/stutters are not hidden by averages.
- [ ] Measurements come from real runs or are explicitly missing.

## Guardrails

- Do not invent FPS, memory or profiling data.
- Do not conclude a GPU bottleneck from CPU timings alone.

**Related skills:** performance-optimization, asset-pipeline, regression-testing.

## Godot integration

For scene work, follow `protocols/mcp-routing.md`. The Cline Director performs MCP operations; workers return file outputs and integration requests. Record evidence through `engine-validation`.
