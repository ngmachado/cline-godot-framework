---
name: npc-ai
description: "Implement NPC state machines, schedules, perception, navigation and recoverable behaviors from approved design."
---

# NPC and enemy behavior

**Primary role:** Game Developer. **Use when:** NPCs, enemies, companions or crowds need autonomy or reactive behavior.

## Required inputs

- Behavior spec including states, triggers and timers.
- Navigation graph/mesh and world-state interfaces.
- Animation states, collision rules and target count/performance budget.

## Procedure

1. Translate design into an explicit state chart or behavior tree with priority and interruption rules.
2. Define perception inputs and memory duration; avoid hidden omniscient AI unless designed.
3. Implement navigation destination choice, stuck detection, retries, unreachable targets and despawn handling.
4. Connect schedule/AI updates to persistent world time and save/load requirements when relevant.
5. Expose readable feedback, animation events and debug instrumentation.
6. Test transitions, lost targets, blocked paths, concurrent actors and deterministic seeds where possible.

## Deliverables

- Behavior code and state transition table.
- Reproducible edge-case tests and profiling notes.

## Validation / done criteria

- [ ] Tested blocked-path and lost-target scenarios reach the specified recovery or fallback state; untested cases and known failures are recorded.
- [ ] Perception and aggression match the approved spec.
- [ ] Performance is evaluated at intended NPC counts.

## Guardrails

- Do not make NPC behavior more aggressive or random without approval.
- Avoid unbounded replanning every frame.

**Related skills:** game-mechanics, gameplay-programming, automated-testing.
