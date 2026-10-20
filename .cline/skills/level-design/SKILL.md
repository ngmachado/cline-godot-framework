---
name: level-design
description: "Design playable level structures, blockouts, navigation and encounters with clear pacing and guidance."
---

# Level layout and pacing

**Primary role:** Game Director. **Use when:** a level, dungeon, hub, arena or traversal section must be created or revised.

## Required inputs

- Player abilities and camera model.
- Intended entry/exit, challenge, duration and progression.
- Engine and scene constraints from `project/ENGINE_PROFILE.md`.

## Procedure

1. Specify the level purpose and player learning objective.
2. Create a blockout plan with routes, key encounters, checkpoints, shortcuts, line of sight and interaction surfaces.
3. Identify path widths, cover, hazards, traversal affordances and accessibility considerations.
4. Place landmarks and feedback cues so players can navigate without relying solely on prompts.
5. Define spawn/reset, victory, failure, softlock prevention and load transitions.
6. Give Developer a testable blockout contract and Artist an environment/lighting brief.

## Deliverables

- Level brief, blockout description, objective flow and encounter list.
- Navigation and softlock acceptance cases.

## Validation / done criteria

- [ ] Planned routes and dimensions account for specified player capabilities.
- [ ] The brief defines landmarks, camera constraints and checks for discovering objectives and exits.
- [ ] Encounter order and pacing goals are explicit enough to implement and test.

These criteria establish a design ready for implementation. After integration, use `gameplay-testing` to verify traversal, camera readability and pacing; record results separately. A completed brief does not establish a playable level.

## Guardrails

- Do not require final art before validating the layout.
- Never report level readability without viewing or playing an actual integration.

**Related skills:** world-design, environment-design, engine-integration, gameplay-testing.

## Godot integration

For scene work, follow `protocols/mcp-routing.md`. The Cline Director performs MCP operations; workers return file outputs and integration requests. Record evidence through `engine-validation`.
