# Delegation contract — Director to internal worker

The Director is the sole user interface. Workers receive a **self-contained task contract**, execute with the needed skills and return a structured handoff. Role files in `roles/` must be loaded explicitly by the host's worker-spawning mechanism.

## Required task fields

```yaml
id: npc-daily-routines
owner_role: game-developer
objective: Implement three NPC daily schedules in the village scene
approved_spec: project/GAME_DESIGN.md
skills: [npc-ai, gameplay-programming, automated-testing]
dependencies: [village-blockout-approved]
read_paths: [project/, scenes/village/]
write_paths: [scripts/npc/, tests/npc/]
inputs: [npc_schedule_data, world_navigation_interfaces]
deliverables: [scripts/npc/, tests/npc/, integration_instructions]
acceptance:
  - NPC transitions between timetable states deterministically
  - Interruption and blocked-path behavior are defined and verified
  - Existing save/load remains valid
verification:
  - Run project-configured automated tests
  - Exercise a playable village scene if an engine runtime is available
approval_needed: false
```

Use the task template in `templates/task.md` for Markdown task records. File paths above are illustrative, not guaranteed to exist.

## Workflow

1. Director declares a task `ready` only when inputs and dependencies exist; otherwise use `blocked`.
2. Worker acknowledges task ownership and file boundaries before editing.
3. Worker follows relevant skills and reports deviations as proposals rather than silent changes.
4. Worker returns **artifact paths**, changed files, tests (exact commands/status), integration notes, risks and missing evidence.
5. Director merges/coordinates changes and sends the result through `protocols/acceptance.md`.

## Concurrency and failure handling

- Run independent Artist/Developer tasks in parallel only if the host supports parallel workers and their write scopes do not overlap; otherwise serialize.
- A worker may not spawn agents or assign work to another role; request additional tasks through the Director.
- If blocked by missing tools, assets or unclear approved design, stop the affected task and report the blocker. Never fabricate an artifact.
- Retry failed implementation after diagnosis; after two ineffective retries, Director revises scope/architecture or asks for user direction.

## Standard return message (internal)

```text
TASK_ID:
STATUS: completed | blocked | needs-review
FILES_CREATED_OR_CHANGED:
SKILLS_USED:
VERIFICATION_RUN: exact commands and outcomes; list explicitly unrun checks
ARTIFACTS_AND_EVIDENCE:
INTEGRATION_NOTES:
DEVIATIONS_AND_RISKS:
REQUESTED_DIRECTOR_DECISIONS:
```

## Engine MCP task contract additions

For an editor-facing task, add: `engine`, `project_path`, `editor_instance`, `mcp_provider`, `mcp_capabilities_verified`, `target_scene_or_prefab`, `editor_write_owner`, `allowed_mcp_operations`, `readback_checks`, `last_verified_connection`. Populate from observed state, never defaults. Workers with no MCP access must report `requires_director_mcp_action` and a specific requested operation rather than assuming they edited the editor.

Persist each delegated contract and returned handoff under `tasks/`, including small tasks used in the demonstration. Distinguish a worker handoff status from the task-board state. During read-only work, return contracts and reports in chat instead of creating files.
