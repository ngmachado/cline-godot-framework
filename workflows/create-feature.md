# Workflow: Add or change a gameplay feature

**Owner:** Game Director. **Trigger:** a new mechanic, NPC ability, interaction, combat feature, inventory feature or behavior change.

1. **Define:** use `game-mechanics` to specify player intent, triggers, states, failure paths, feedback, difficulty parameters and explicit acceptance criteria in `project/GAME_DESIGN.md`, using `templates/feature-spec.md` as the format.
2. **Analyze:** Developer inspects current architecture and estimates impacted systems. Director decides what can remain unchanged.
3. **Split:** assign code and integration preparation to Developer; art/audio/animation work to Artist, with declared interfaces and independent file ownership.
4. **Implement:** Developer uses `gameplay-programming`, plus `npc-ai` / `physics-systems` / `animation-integration` as needed. Artist uses appropriate creative skills.
5. **Integrate:** Developer prepares source edits and integration instructions for production or placeholder assets; Director imports assets and assembles the playable scene through MCP. Document missing capabilities rather than guessing.
6. **Verify:** use `automated-testing` and `gameplay-testing`; run `regression-testing` for affected systems. For art-heavy work, Artist verifies asset formats and consistency.
7. **Accept:** Director checks criteria, actual evidence and project fit. Return failed criteria to the responsible worker, not straight to the user.
8. **Record:** update design, decisions, task board and known limitations.

**Completion means:** integrated behavior exists and is validated to the extent explicitly evidenced. A passing unit test alone does not prove good gameplay feel.

## Godot integration gate

Follow `protocols/mcp-routing.md` before editor work and `protocols/acceptance.md` before completion. The Director runs MCP operations and records actual engine-validation evidence.
