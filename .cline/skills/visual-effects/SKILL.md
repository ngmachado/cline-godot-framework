---
name: visual-effects
description: "Create and tune particles, shaders, hit feedback and environmental effects that improve gameplay clarity."
---

# Gameplay visual effects

**Primary role:** Creative Artist. **Use when:** combat hits, interactions, magic, weather, explosions or atmosphere need visual feedback.

## Required inputs

- Mechanic triggers, durations, critical feedback states.
- Art style, render pipeline and target device budgets.
- Layering, occlusion and accessibility constraints.

## Procedure

1. Map each effect to its gameplay function: confirm, warn, attract, reward or ambient.
2. Define onset, peak and decay with synchronization to game events and camera distance.
3. Choose feasible particles, mesh effects, sprites, shader parameters or post-processing for the engine.
4. Establish priority against HUD, enemies and interactables; define alternatives for flashing/high-contrast issues.
5. Build or specify effects; ask Developer to integrate and trigger them using actual event names.
6. Evaluate overdraw, frame-time, visual noise and readability in representative gameplay scenes.

## Deliverables

- VFX specification and event-to-effect table.
- Integrated effect/assets where tooling permits, with measured or untested budget status.

## Validation / done criteria

- [ ] Effects reinforce rather than obscure important game states.
- [ ] No unintended accessibility or extreme-flash hazards.
- [ ] Performance constraints and trigger correctness evaluated.

## Guardrails

- Do not let decorative effects alter collision/combat rules.
- Do not claim performance acceptable without testing target conditions.

**Related skills:** art-direction, animation-integration, performance-testing.
