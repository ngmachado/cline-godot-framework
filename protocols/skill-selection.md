# Skill selection and loading

A role represents **accountability**; a skill is a **procedure**. No skill creates a new persistent role.

## Selector rules

1. Identify the intended artifact: design spec, code, playable scene, asset, test evidence, build, or issue report.
2. Consult `SKILLS_INDEX.md` and choose a small set of skills that cover the actual work.
3. Read each selected `.cline/skills/<name>/SKILL.md` before performing its procedure.
4. Assign task ownership by responsibility: Director for design/orchestration/acceptance, Developer for code and integration preparation, Artist for creative production.
5. QA skills are invoked in the same tasks or final review gates; no permanent QA agent.
6. Do not turn a descriptive skill file into an imaginary tool. If runtime or image generation is unavailable, follow the skill's fallback and label outcomes honestly.

## Typical bundles

- New concept: `game-concept`, `game-mechanics`, `task-planning`, `vertical-slice`.
- NPC feature: `npc-ai`, `gameplay-programming`, `animation-integration`, `automated-testing`, `gameplay-testing`.
- New level: `level-design`, `environment-design`, `asset-pipeline`, `engine-integration`, `gameplay-testing`.
- New character: `character-design`, `asset-generation`, `animation-design`, `animation-integration`, `gameplay-testing`.
- Bug: `bug-analysis`, a relevant implementation skill, `regression-testing`.
- Release: `build-management`, `performance-testing`, `regression-testing`, `gameplay-testing`.

## Engine adapter skill selection

1. On the first engine task, include `engine-capability-probe`.
2. Use `godot-editor` for verified Godot MCP scene operations. The Director executes them.
3. `engine-integration` remains the generic asset/code-to-scene integration workflow, and `engine-validation` is the final evidence layer.
4. If no MCP provider is connected, use direct project files, native CLI and engine docs where possible; mark MCP operations unavailable and **never fabricate a tool call**.
5. Reuse existing gameplay, art and QA skills; an editor bridge does not replace their requirements.

For the current Godot project, begin with `engine-capability-probe`, `godot-editor`, and `engine-validation` when doing live engine work. Add other skills only for their actual procedures. Applying an approved spec does not authorize creative exploration.
