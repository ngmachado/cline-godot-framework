---
name: physics-systems
description: "Implement and verify gameplay physics, collision layers, rigid-body movement and deterministic interactions where needed."
---

# Physics and collision systems

**Primary role:** Game Developer. **Use when:** movement, collision, jumping, vehicles, projectiles or physical simulation are required.

## Required inputs

- Physics engine/profile, unit scale and timestep.
- Approved mechanics and interaction/collision requirements.
- Character scale and collision shape conventions.

## Procedure

1. Classify bodies as static, kinematic/character or dynamic according to required behavior.
2. Define coordinate units, collision layers/masks, interpolation and time-step dependencies.
3. Implement movement/forces and contact handling without frame-rate-dependent errors.
4. Add tests for edge contacts, high velocity, slopes, moving platforms, tunneling and sleeping as relevant.
5. Check camera feel, animation and gameplay response in actual runtime, including target FPS extremes.
6. Profile expensive collision checks and document known approximation limits.

## Deliverables

- Physics configuration and implementation.
- Collision matrix, edge-case tests and runtime results.

## Validation / done criteria

- [ ] Units and collision categories are explicit.
- [ ] Stable expected behavior across supported frame rates.
- [ ] Relevant contacts, cancellation and boundary cases verified.

## Guardrails

- Do not use physics realism as a substitute for approved game feel.
- Do not claim deterministic cross-platform physics without evidence.

**Related skills:** gameplay-programming, animation-integration, performance-testing.
