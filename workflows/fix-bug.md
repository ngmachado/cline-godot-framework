# Workflow: Diagnose and fix a bug

**Owner:** Game Director. **Primary skills:** `bug-analysis`, `automated-testing`, `regression-testing`, then the relevant implementation skill.

1. Director captures symptom, impact, affected build/platform, steps to reproduce, expected vs actual outcome, and any logs/videos.
2. Developer reproduces in the narrowest available environment. If no runtime exists, label the reproduction unverified and use code inspection as preliminary evidence only.
3. Developer identifies likely root cause and produces a failing test or controlled reproduction when feasible. Avoid changing unrelated systems.
4. Director authorizes a narrow fix; Developer implements, retests and documents any migration/integration impact.
5. Run targeted regression checks for neighboring functionality and prior saved games/assets as applicable.
6. If the issue touches animations, materials, UI or audio, Artist validates the creative output after integration.
7. Director checks evidence, marks fixed only after appropriate verification, and updates known issues and task board.

**Escalation:** After two unsuccessful patches, re-evaluate the diagnosis; do not pile on speculative changes or claim a resolution.

## Godot integration gate

Follow `protocols/mcp-routing.md` before editor work and `protocols/acceptance.md` before completion. The Director runs MCP operations and records actual engine-validation evidence.
