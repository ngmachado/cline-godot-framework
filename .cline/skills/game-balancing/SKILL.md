---
name: game-balancing
description: "Set and revise game difficulty, progression, resource economics and tunable values using evidence."
---

# Game balance design

**Primary role:** Game Director. **Use when:** challenge, pacing, rewards, cooldowns, enemy values or progression feel wrong.

## Required inputs

- Mechanic spec and current tunables.
- Player target, intended challenge and available telemetry/playtest observations.
- Known constraints and regression risks.

## Procedure

1. Identify the specific balancing objective and whether it concerns skill, randomness, pacing or economy.
2. Record current parameters with units, ranges and dependencies.
3. Model extreme cases including degenerate loops, resource starvation, exploits and overpowered strategies.
4. Change a small set of parameters while holding other variables stable.
5. Ask Developer to expose data/logging where available and use `balance-analysis` for measurement.
6. Compare test evidence to intended curve; document remaining hypotheses for real playtests.

## Deliverables

- Balancing rationale, parameter table and expected effects.
- Test scenarios with target outcome ranges.

## Validation / done criteria

- [ ] No parameter change contradicts explicit mechanics.
- [ ] Edge cases and exploits were evaluated.
- [ ] Data-backed conclusions are separated from subjective hypotheses.

## Guardrails

- Do not declare the game balanced on the basis of generated estimates alone.
- Avoid silent balance changes during bug fixes.

**Related skills:** balance-analysis, gameplay-testing, game-mechanics.
