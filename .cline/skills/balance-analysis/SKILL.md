---
name: balance-analysis
description: "Analyze difficulty, reward economy and progression with tests, simulation or actual play observations."
---

# Gameplay balance evaluation

**Primary role:** Game Director with Developer support. **Use when:** difficulty, resource flows, damage curves, progression or exploits need evaluation.

## Required inputs

- Current mechanic constants, progression rules and intended player skill level.
- Available telemetry, repeatable simulations or real playtest observations.
- Design goals and constraints from `project/GAME_DESIGN.md`.

## Procedure

1. State a falsifiable balance hypothesis (e.g., encounters are too lethal after checkpoint 3).
2. Select relevant metrics: failure rate, kill time, resource surplus, retries, choice distribution or pacing.
3. Use repeatable tests/simulations for deterministic rules; state assumptions and seed distributions.
4. Identify outliers, exploits, dominant strategies and bottlenecks; distinguish model output from real player behavior.
5. Suggest small parameter adjustments and expected effects for Director review.
6. Record changed constants and plan before/after tests including real playtests where possible.

## Deliverables

- Balance hypothesis, measurement table and proposed parameter changes.
- Limitations of simulation vs actual player evidence.

## Validation / done criteria

- [ ] Comparisons control for key variables.
- [ ] Proposed adjustments respect mechanics and available game data.
- [ ] No simulated findings are misrepresented as user-study results.

## Guardrails

- Do not autonomously rebalance approved player-facing rules.
- Do not infer enjoyment from survival or win rates alone.

**Related skills:** game-balancing, gameplay-testing, automated-testing.
