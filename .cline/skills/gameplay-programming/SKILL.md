---
name: gameplay-programming
description: "Implement an approved player-facing mechanic while preserving architecture, tests and behavioral contracts."
---

# Gameplay implementation

**Primary role:** Game Developer. **Use when:** player controls, interactions, combat, inventories, abilities or other core gameplay code must change.

## Required inputs

- Approved feature spec, acceptance criteria and affected systems.
- Repository conventions and exact engine version.
- Asset/animation event contracts if relevant.

## Procedure

1. Locate the mechanic’s state owner and integration points; read existing code before editing.
2. Implement defined triggers, transitions, constraints and feedback hooks in the smallest coherent change.
3. Preserve error/cancellation behavior and existing invariants; avoid hidden game-design decisions.
4. Add automated tests for rules, boundaries and interruption as the engine permits.
5. Run authorized command-line tests and scene checks; request MCP-driven launch and interaction checks from Director. Record exact evidence and unrun checks.
6. Report changed paths, implemented states, missing assets and unverified scenarios to Director.

## Deliverables

- Integrated code/scripts and changed-file summary.
- Targeted tests, runtime evidence and limitations.

## Validation / done criteria

- [ ] Defined states and input paths are mapped to acceptance checks, with tested scenarios, results and gaps recorded.
- [ ] Existing public gameplay behavior is unchanged unless approved.
- [ ] Tests executed are recorded accurately.

## Guardrails

- Do not invent balancing numbers if designer-defined values exist.
- Do not equate static build success with good player experience.

**Related skills:** game-mechanics, automated-testing, regression-testing.

## Godot integration

For scene work, follow `protocols/mcp-routing.md`. The Cline Director performs MCP operations; workers return file outputs and integration requests. Record evidence through `engine-validation`.
