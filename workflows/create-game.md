# Workflow: Create a new game

**Owner:** Game Director. **Trigger:** new game request with no established playable project.

## Stage 1 — Concept and boundaries (Director)

1. Read the user's brief and the repo's existing content. Use `game-concept` to define audience, fantasy, core loop, camera, controls, platforms and three design pillars.
2. Document unknowns as assumptions. Seek approval only for material ambiguity with divergent creative or paid consequences.
3. Use `game-mechanics`, `narrative-design` (if needed) and `game-balancing` to define **one** representative playable loop.
4. Record the concept in `project/GAME_VISION.md` and `project/GAME_DESIGN.md`.

**Gate:** There is a specific player goal and a testable mechanic, not only a pitch.

## Stage 2 — Technical/art foundations (Developer + Artist)

1. Director selects `vertical-slice` and `task-planning`; split implementation into independent scoped tasks.
2. Developer uses `game-architecture` and `engine-integration` to prepare project source files and integration instructions appropriate for `project/ENGINE_PROFILE.md`. Director performs required editor setup through MCP.
3. Artist uses `art-direction`, `asset-generation` and `asset-pipeline` to set one consistent visual treatment and minimal assets/placeholders.
4. Agree on coordinate units, asset naming, import formats, expected animations and budgets before parallel tasks begin.

**Gate:** Playable scene structure and importable asset plan exist; no write-scope collision.

## Stage 3 — Vertical slice

1. Developer implements input and primary mechanic with tests.
2. Artist provides needed assets and feedback cues; Developer prepares source integration and instructions. Director performs asset imports and scene assembly through MCP.
3. Run actual build/playtest if host environment permits. Use `automated-testing`, `gameplay-testing` and `performance-testing` as relevant.

**Gate:** Core loop is playable or explicitly blocked with reasons and evidence.

## Stage 4 — Director acceptance and next plan

1. Compare reality against design pillars and acceptance criteria.
2. Record decisions/changes, risks, tests and next priorities in `project/PROJECT_STATUS.md` and `project/TASK_BOARD.md`.
3. Report exactly what works, what was not tested, and what the user can do next.

**Definition of done:** An integrated, demonstrable vertical slice is available, or the Director reports the concrete blocker without claiming completion.

## Godot integration gate

Follow `protocols/mcp-routing.md` before editor work and `protocols/acceptance.md` before completion. The Director runs MCP operations and records actual engine-validation evidence.
