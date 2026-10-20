---
name: game-mechanics
description: "Formalize player-facing gameplay rules, state machines, controls and acceptance tests before coding."
---

# Game mechanics specification

**Primary role:** Game Director. **Use when:** a new mechanic, interaction, ability, combat action or gameplay rule is requested.

## Required inputs

- Approved game vision and relevant systems.
- Player intent and control context.
- Known technical and art constraints.

## Procedure

1. Express the player goal and how the mechanic contributes to the game’s pillars.
2. Define triggers, input mapping, states, transitions, failure/cancellation and interactions with other mechanics.
3. Specify tunable values with units, expected ranges and ownership; avoid unspecified magic numbers.
4. Describe feedback at decision points: animation, UI, sound, haptics or accessibility alternatives.
5. Write success, boundary and exploit cases as observable acceptance criteria.
6. Record a feature specification in `project/GAME_DESIGN.md` using `templates/feature-spec.md` as the format before implementation delegation.

## Deliverables

- Feature spec and state/transition model.
- Balancing parameters, required assets/events and acceptance cases.

## Validation / done criteria

- [ ] Rules and cancellation paths are unambiguous.
- [ ] Acceptance criteria can be checked in an actual build.
- [ ] Mechanic preserves approved design pillars.

## Guardrails

- Do not choose a technical architecture as a substitute for explaining player behavior.
- Material changes to approved difficulty or abilities need a Director decision.

**Related skills:** gameplay-programming, game-balancing, automated-testing.
