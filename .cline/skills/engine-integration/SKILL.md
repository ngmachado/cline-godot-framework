---
name: engine-integration
description: "Integrate code, scenes, imported assets and event wiring into a runnable engine project."
---

# Game engine integration

**Primary role:** Game Developer. **Use when:** features or assets are ready to enter a Godot project.

## Required inputs

- `project/ENGINE_PROFILE.md` with engine/version and verified commands.
- Code APIs, assets and relevant file/scene ownership.
- Asset dimensions, pivots, events and import settings.

## Procedure

1. Inspect the existing project hierarchy and dependencies; do not create a duplicate parallel architecture.
2. Developer prepares asset files, import settings and integration instructions using Godot conventions while preserving source artifacts and provenance. Director performs editor imports through MCP.
3. Developer makes authorized source edits for nodes, collisions, animation events, UI and audio signals; Director performs editor scene assembly and wiring through MCP.
4. Check broken references, scale/rotation/axis issues, state wiring and missing materials.
5. Developer runs authorized command-line checks; Director launches the relevant scene and runs editor checks through MCP. Record actual runtime/import errors and the mechanism used.
6. Provide reproducible import/setup steps, scene paths and missing dependencies.

## Deliverables

- Working project integration and changed scene/config paths.
- Import settings and runtime test evidence.

## Validation / done criteria

- [ ] No unresolved required asset or code references in delivered scene.
- [ ] Behavior and visual scale match source specifications.
- [ ] Real runtime or headless validation performed, or unavailability disclosed.

## Guardrails

- No imaginary engine command or API: consult exact project version.
- Do not mark a standalone image/model as integrated content.

**Related skills:** asset-pipeline, gameplay-programming, gameplay-testing.

## Godot integration

For scene work, follow `protocols/mcp-routing.md`. The Cline Director performs MCP operations; workers return file outputs and integration requests. Record evidence through `engine-validation`.
