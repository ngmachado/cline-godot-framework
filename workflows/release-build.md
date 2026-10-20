# Workflow: Prepare a release build

**Owner:** Game Director. **Primary skills:** `build-management`, `automated-testing`, `regression-testing`, `performance-testing`, `asset-pipeline`.

1. Confirm target platforms, build variant, engine/tool versions, licensing requirements and distribution constraints from `project/ENGINE_PROFILE.md`.
2. Developer produces a clean, reproducible build (or reports the exact missing tool/dependency); include test logs, dependency versions and artifact hashes when available.
3. Artist verifies final creative asset import, rights/attribution, readability and declared budgets; flag any placeholder or missing licenses.
4. Run smoke and regression tests, save/load and installation checks on supported target environments. Include performance baselines.
5. Director reviews all known critical defects, content-completeness criteria, accessibility risks and outstanding approvals.
6. **Never publish externally without user authorization.** Package artifacts and notes for review first.

**Outputs:** package path(s), checksums when available, exact build commands, known issues, test evidence, licensing/attribution notes, approval status.

## Godot integration gate

Follow `protocols/mcp-routing.md` before editor work and `protocols/acceptance.md` before completion. The Director runs MCP operations and records actual engine-validation evidence.
