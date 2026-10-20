---
name: performance-optimization
description: "Improve frame time, memory, load time and resource usage using measured profiling evidence."
---

# Game performance optimization

**Primary role:** Game Developer. **Use when:** the game stutters, exceeds budgets or needs target-platform tuning.

## Required inputs

- Target platform/performance budget and profiling tools.
- Reproducible representative scene/build.
- Baseline frame-time, memory, load and rendering metrics if available.

## Procedure

1. Define user-visible performance failure and target measurement.
2. Capture repeatable baseline under representative gameplay conditions; separate CPU, GPU, memory and IO bottlenecks.
3. Select the highest-impact verified hotspot and propose minimal corrective change.
4. Optimize caching, lifecycle, scene structure, collision, batching/LOD or asset budgets as evidence warrants.
5. Reprofile under the same workload and check for visual/gameplay regression.
6. Document quantitative before/after, measurement method and trade-offs.

## Deliverables

- Profiling report with baseline and follow-up metrics.
- Scoped optimizations with regression results.

## Validation / done criteria

- [ ] Numbers are measured on named hardware/build with same test case.
- [ ] Change improves target metric or is rolled back.
- [ ] No invisible degradation of gameplay or visual readability.

## Guardrails

- Do not claim FPS improvements without real profiling.
- Do not reduce essential effects or simulation fidelity without Director consent.

**Related skills:** performance-testing, regression-testing, asset-pipeline.
