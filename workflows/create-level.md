# Workflow: Create or revise a level

**Owner:** Game Director. **Primary skills:** `level-design`, `environment-design`, `engine-integration`, `asset-pipeline`, `gameplay-testing`.

1. Director defines the experience: level purpose, expected duration, entrances/exits, essential encounters, pacing, navigation and success/failure conditions.
2. Produce a blockout specification before asking for detailed final art. Identify critical sightlines, path widths, camera constraints, accessible routes and interaction zones.
3. Developer prepares blockout source files, trigger/navigation code, checkpoint behavior, loading transitions and integration instructions. Director assembles the blockout and performs editor navigation setup through MCP.
4. Artist defines landmark hierarchy, environmental assets, material/lighting palette and visual guidance consistent with `project/ART_DIRECTION.md`.
5. Developer prepares incremental asset integration edits and instructions; Director imports and places assets through MCP. Together, avoid replacing readable blockout shapes with attractive but obstructive geometry.
6. Test traversal, softlocks, spawn positions, occlusion, loading, performance and player signposting. Verify the level from the intended camera.
7. Director reviews pacing and objectives with actual play evidence where possible, accepts or revises, and records changes.

**Pass criteria:** playable beginning-to-end path, no known critical softlock, comprehensible objectives, integrated visual guidance, and disclosed untested routes.

## Godot integration gate

Follow `protocols/mcp-routing.md` before editor work and `protocols/acceptance.md` before completion. The Director runs MCP operations and records actual engine-validation evidence.
