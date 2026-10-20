---
name: engine-validation
description: "Validate that a Godot MCP-created feature exists in the right scene, compiles, runs and satisfies acceptance evidence; use after integrations or before declaring a feature complete."
---

# Engine runtime and integration validation

**Owner:** Game Director, with Developer performing technical checks and Artist checking creative delivery. Uses `protocols/acceptance.md` and `project/TEST_PLAN.md`.

## Preconditions
Task contract, intended engine+scene, integration paths, expected behavior, required checks and tool permissions.

## Gates
1. **Project identity:** confirm editor instance, project path and engine version.
2. **Persistence:** ensure changed assets/scripts/scenes are saved, versioned or explicitly named as provisional. Read back hierarchy/assets through MCP or files.
3. **Compilation/import:** collect actual Godot script-check/import results; record exact mechanism used.
4. **Runtime launch:** start a real scene/build and observe successful start/stop where tools permit. Separate “scene launched” from “feature works.”
5. **Interaction behavior:** validate inputs, triggers, transitions, collision/nav, failure cases and expected feedback via available tests, controlled actions or human-guided playtest.
6. **Presentation:** check readability, scale, materials, animation and audio integration against art direction. Screenshot/screen capture only counts if an actual frame was captured.
7. **Regression:** check affected adjacent mechanics, persistence, serialization/build, and errors after stopping the game.

## Evidence format
Record result per gate as `pass | fail | blocked | not-run`, with actual command or MCP operation and result reference, e.g. log path / test report / screenshot path. Copy `templates/qa-report.md` to a task-specific report under `project/reports/`, or record concise results in `project/TEST_PLAN.md`. Leave the reusable template blank. A successful MCP connection is NOT evidence of any gate after project identity.

## Failure policy
Treat missing evidence as `not-run`, not `pass`. Stop release/acceptance for blocking compile/runtime errors. Loop back to owning role for remediation, maximum two undiagnosed retries.

## Completion
Director signs off only on demonstrated criteria; manual enjoyment/fun is a hypothesis until real people play. Maintain `project/PROJECT_STATUS.md` and link evidence paths.
