# Keeping shared project context coherent

## Source-of-truth documents

- `project/GAME_VISION.md`: high-level intent and immutable (unless approved) pillars.
- `project/GAME_DESIGN.md`: mechanic definitions and player-facing rules.
- `project/ART_DIRECTION.md`: visual/audio identity and asset specifications.
- `project/ARCHITECTURE.md`: game systems, interfaces and technical decisions.
- `project/ENGINE_PROFILE.md`: actual engine, versions, targets, verified commands, tools.
- `project/DECISIONS.md`: dated decisions and why they were made.
- `project/TASK_BOARD.md` and `project/PROJECT_STATUS.md`: execution truth.

## Rules

- Before delegating, Director links the latest applicable approved specs in each task; never rely solely on chat memory.
- Workers should read task-specific context, not every document indiscriminately.
- If a worker discovers a contradictory source, report it to Director instead of picking a preferred version.
- Changes to gameplay rules, art identity or platform target require an entry in `project/DECISIONS.md` and updates to affected specs.
- A task's output is not canonical until Director accepts it and updates the source of truth.
- Preserve reproducibility: record asset prompts/settings/seeds when available, engine/plugin versions, and tested commands.
- At session start, Director inspects repo and task state; if repository state is inaccessible, state that limitation explicitly.
