# Game development skill registry — 34 reusable skills

Only **3 roles**: Director, Developer, Artist. Skills are task procedures, not additional standing agents. Consult `.cline/skills/<skill>/SKILL.md` for full instructions; use only relevant skills on a given task.

| Role / area | Skills | Purpose |
|---|---|---|
| **Game Director** | `game-concept`, `game-mechanics`, `world-design`, `level-design`, `narrative-design`, `game-balancing`, `task-planning`, `vertical-slice` | Scope, rules, world, planning, creative decisions |
| **Game Developer** | `game-architecture`, `gameplay-programming`, `physics-systems`, `npc-ai`, `engine-integration`, `animation-integration`, `performance-optimization`, `build-management` | Game code, systems, scenes, integrations |
| **Creative Artist** | `art-direction`, `character-design`, `environment-design`, `asset-generation`, `asset-pipeline`, `animation-design`, `visual-effects`, `ui-design`, `audio-design` | Visual/audio identity, assets and technical preparation |
| **Shared QA** | `automated-testing`, `gameplay-testing`, `bug-analysis`, `performance-testing`, `balance-analysis`, `regression-testing` | Technical/design/gameplay checks; not a fourth role |
| **Engine MCP (new)** | `engine-capability-probe`, `godot-editor`, `engine-validation` | Correct project/editor connection, safe editor operations and real verification |

## Routing examples

| Director receives | Skills to consider |
|---|---|
| “Start a new game” | `game-concept`, `game-mechanics`, `vertical-slice`, `task-planning` |
| “Connect to Godot” | `engine-capability-probe`, `godot-editor`, `engine-validation` |
| “Make a village” | `world-design`, `level-design`, `environment-design`, `asset-pipeline`, engine skill, `engine-validation` |
| “Add pursuing NPC” | `game-mechanics`, `npc-ai`, `gameplay-programming`, `animation-integration`, engine skill, `automated-testing`, `engine-validation` |
| “Create a character” | `character-design`, `asset-generation`, `animation-design`, `asset-pipeline`, engine skill, `gameplay-testing` |
| “Fix a crash” | `bug-analysis`, implementation skill, `regression-testing`, `engine-validation` |
| “Make a release build” | `build-management`, `performance-testing`, `regression-testing`, `engine-validation` |

## Engine rules

`engine-integration` is the common capability; `godot-editor` adds editor-specific MCP procedures. Start with `engine-capability-probe` before any new connection's first write, and finish with `engine-validation` before Director claims an engine feature is working.


**Docs:** `protocols/skill-selection.md`, `protocols/mcp-routing.md`, `integrations/`, [README tutorial](README.md#1-configure-clines-roles-and-skills).

For the Godot workflow, the main operational skills are `engine-capability-probe`, `godot-editor`, and `engine-validation`. Use gameplay/art skills only when the task calls for them; the library is not a list to load in full.
