# Workflow: Connect the current Godot project

**Owner:** Game Director.

1. Read `integrations/godot/SETUP.md`. Identify the exact folder containing `project.godot` and the local Cline/Godot versions.
2. Inspect existing plugin and MCP configuration; do not reinstall working components.
3. Run `engine-capability-probe` against the actual project and open scene. Report failures or ambiguity before changes.
4. If write capability needs verification and is authorized, use `workflows/engine-smoke-test.md` in a disposable scene.
5. Record actual observations in `project/ENGINE_PROFILE.md` and `project/ENGINE_CAPABILITIES.md`; mark untested capabilities explicitly. During review-only tasks, return findings without file writes.

Connection success does not establish scene persistence, runtime behavior, or human game feel.
