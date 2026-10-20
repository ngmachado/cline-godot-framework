# Workflow: Engine editor MCP smoke test

**Owner:** Game Director. **Trigger:** after editor MCP setup, reconnect, version changes, or before first real scene automation.

## Phases
1. **Read-only:** Use `engine-capability-probe` to list actual connected tools, active project and scene tree. Fail closed for wrong/ambiguous project.
2. **Approval/checkpoint:** Confirm that limited additive edits are authorized; do not ask again when the task already grants them. Save a checkpoint. Use a disposable scene, not an existing authored level.
3. **Create:** Through chosen `godot-editor` skill, add a small, unambiguously test-owned object group (e.g., three named primitives/materials). Choose actual supported tools, not assumed names.
4. **Read-back:** Requery objects, parents, transforms, colors/materials; ensure scene persisted and no duplicates.
5. **Compile/import:** Read actual error state, run available static/engine checks.
6. **Runtime:** Try an actual scene launch, record pass/fail and logs separately from interaction testing. Capture visual evidence only if a real capture tool is available.
7. **Cleanup:** Ask approval to remove only test-owned objects, or retain disposable test scene labeled clearly. Don't delete unrelated content.
8. **Record:** Update `project/ENGINE_CAPABILITIES.md` using `templates/engine-capability-report.md` as the format, and update `project/PROJECT_STATUS.md`. Leave the reusable template blank.

## Success criteria
- Right project and editor identified.
- One read-only MCP query succeeded and was recorded.
- One authorized small editor change saved and read back, or clearly marked blocked/unverified.
- Compile/import and runtime status recorded separately; no claims of fun/playability.

## Cline-specific note
Ordinary Cline subagents don't have MCP. The Game Director must perform actual Editor MCP steps; Developer/Artist workers may create source files/assets in disjoint areas and return instructions.
