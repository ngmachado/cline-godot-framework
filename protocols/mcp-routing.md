# Godot MCP routing

**Owner: Game Director.** This is a coordination convention, not a mutex or security boundary.

## Access model

The Cline main session performs all Godot MCP calls. Ordinary subagents receive no MCP tools: Developer and Artist work on assigned files and return `requires_director_mcp_action` with requested operations. Do not delegate an MCP-only task to a worker. Keep a single main session responsible for an editor instance.

## Before changes

1. Read `project/ENGINE_PROFILE.md` as recorded context; verify the current project, client, plugin, and actual tool inventory.
2. Use `engine-capability-probe` and read-only metadata/scene inspection. Confirm the absolute project path, not merely its display name.
3. Define target paths, approved operations, checkpoint, expected readback, and validation. The Director holds the editor write slot; record that in the task.
4. Use `godot-editor` for editor operations. Integrate completed worker file changes before runtime testing.

## Execute and recover

Use only observed tool schemas. Save and read back changes, then run `engine-validation`. After a timeout inspect before retrying. Re-probe after an editor/project switch, reconnect, or reload that invalidates access. Do not silently switch projects or providers.

Developer may perform authorized source edits and command-line checks; editor operations through MCP belong to the Director. If MCP is missing, file-only review or source work may continue where authorized. Label editor integration unavailable. A CLI or manual fallback must be reported explicitly; it does not establish MCP success.

## Scope and approvals

Normal additive changes within the user's approved task proceed under host permissions. Obtain any missing authorization for destructive changes, dependency upgrades, external publishing, or spending; existing authorization need not be requested again. Checkpoint valuable content before changes. Do not expose the bridge remotely or broadly auto-approve write-capable tools.

## Evidence

Record client surface/version, engine/toolkit/bridge versions, project path, editor/runtime connections separately, actual calls/results, and artifact paths. Copy `templates/qa-report.md` to a task-specific report under `project/reports/`, or record concise results in `project/TEST_PLAN.md`; leave the template blank. Recording a report is a file write: omit it during explicitly read-only work and return findings in chat instead.

Setup: `integrations/godot/SETUP.md`. Acceptance: `protocols/acceptance.md`.
