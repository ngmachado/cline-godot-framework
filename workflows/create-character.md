# Workflow: Create a playable or NPC character

**Owner:** Game Director. **Primary skills:** `character-design`, `asset-generation`, `asset-pipeline`, `animation-design`, `animation-integration`, `gameplay-testing`.

1. Director identifies gameplay role, personality, silhouette needs, required moves/states, relative scale, camera framing and lore constraints.
2. Artist prepares a character brief with reference direction, proportions, color/material rules, rig or sprite requirements, animations and rights/provenance.
3. Developer agrees to collision volumes, movement mechanics, state names, animation event hooks and engine-native import formats before final assets are produced.
4. Artist creates/curates the asset(s) with matching animatable structure or a clearly labeled placeholder. Run `asset-pipeline` checks.
5. Developer prepares source edits and integration instructions for controllers, hitboxes, movement/AI and animation transitions using `animation-integration`. Director imports assets and configures the character scene in the editor through MCP.
6. QA skills cover transitions, clipping, blend artifacts, pathfinding, attack readability, scale, performance and any accessibility constraints.
7. Director reviews gameplay silhouette and visual consistency, then accepts or requests corrections.

**Do not conflate:** concept illustration, in-game sprite, rigged 3D mesh, animation and engine-ready prefab/scene. Record what actually exists.

## Godot integration gate

Follow `protocols/mcp-routing.md` before editor work and `protocols/acceptance.md` before completion. The Director runs MCP operations and records actual engine-validation evidence.
