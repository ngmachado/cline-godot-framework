---
name: godot-editor
description: "Use a verified Godot MCP editor connection to inspect and safely modify Godot 4 scenes, nodes, scripts, animation and resources; use only for Godot projects after identity and capability checks."
---

# Godot editor operations via MCP

**Executor:** Game Director in the Cline main session. Developer prepares source; Artist prepares visual specifications/assets. Workers return integration requests. The tutorial uses NPGameDev Godot MCP Toolkit and its `@npgamedev/godot-mcp-server` bridge, installed and configured by the user. Follow `integrations/godot/SETUP.md` for the README setup instructions. Verify the actual connection and capabilities against `project/ENGINE_PROFILE.md`; the prescribed provider does not establish a working connection.

## Preconditions
- Godot project root has `project.godot`; the configured MCP provider and any required editor plugin or bridge are connected.
- Correct project/editor identity was confirmed by `engine-capability-probe`.
- Task contract defines scene path, root node expectations, writable files and acceptance tests.

## Procedure
1. Read the current scene tree and project metadata using dynamically discovered **read-only** tools. Use only inspection operations exposed by the connected provider; discover tool names and parameters at runtime. If required inspection is unavailable, report the limitation before editing.
2. Capture existing scene and resource paths; checkpoint changes. Prefer scene/node edits through MCP when supported and engine-native `.tscn` / `.gd` file edits when appropriate.
3. Add or edit nodes in dependency order, preserve NodePaths, script class names, signal connections, owner assignments, resource references, collision layers and autoloads.
4. Avoid editing `project.godot` while Godot is running solely to activate a plugin; use Project Settings → Plugins. Treat autoload/input map changes as configuration writes requiring review.
5. Save the scene and verify by reading the tree back; check script parse errors, import failures and project Output/Debugger logs.
6. Run the intended scene through the real Godot editor/test runner where available. Capture console/log evidence and distinguish a successful scene launch from successful interaction tests.
7. Report modified paths, tools actually invoked, scene/node changes, test commands and outcomes, missing assets and blockers.

## Validation
- [ ] Edited `.tscn` or node tree contains expected nodes under the correct parent.
- [ ] Scripts parse, resources and signal paths resolve, no blocking runtime errors.
- [ ] Actual scene run observed or marked not-run.

## Failure recovery
If the MCP server responds but the editor is unavailable, inspect the configured provider’s connection status and project resolution; do not continue with editor writes. Avoid blind retries after timeouts: read the scene tree first to identify partial success.

## Guardrails
Never mass-delete resources or reset project settings without explicit approval. Never treat an automatically generated node tree as a finished playable level.
