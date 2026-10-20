# Workflow: Playtest and polish

**Owner:** Game Director. **Primary skills:** `gameplay-testing`, `balance-analysis`, `performance-testing`, `game-balancing`, `ui-design`, `visual-effects`.

1. Director defines what the session is trying to learn: onboarding, readability, difficulty, navigation, feel or performance.
2. Create an unbiased task script with player goals but without explaining the intended solution. Define metrics such as completion time, failure points, retries and qualitative comments.
3. Developer packages a testable build and captures logs/telemetry if available. Artist prepares polished or consistently representative visuals without hiding unimplemented mechanics.
4. Conduct a real player session if possible; do not simulate a human player and report it as empirical evidence.
5. Triage findings by severity and impact. Separate defects from player-experience hypotheses.
6. Director creates narrow corrective tasks; Developer/Artist implement. Repeat targeted tests and regressions.
7. Record what changed and whether player outcomes improved; if sessions cannot be run, explicitly flag that the design remains unvalidated by players.

**Exit:** priorities are documented, critical blockers addressed, and player feedback is traceable to actual sessions where claimed.

## Godot integration gate

Follow `protocols/mcp-routing.md` before editor work and `protocols/acceptance.md` before completion. The Director runs MCP operations and records actual engine-validation evidence.
