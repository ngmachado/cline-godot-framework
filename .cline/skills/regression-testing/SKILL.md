---
name: regression-testing
description: "Ensure recent changes do not break previously working gameplay, assets, builds or persistence."
---

# Game regression verification

**Primary role:** Game Developer executes; Director reviews. **Use when:** features are merged, bugs fixed, engine updated or release candidates are prepared.

## Required inputs

- Changed paths and dependency graph.
- Known-good scenarios and existing tests/build results.
- Regression-sensitive saves, scenes, assets and input paths.

## Procedure

1. Map the change to likely adjacent systems and critical player journeys.
2. Select smoke tests plus targeted automated/integration tests for impacted components.
3. Run existing tests on the current change and compare to baseline; mark unknown baseline clearly.
4. Check scene import, animation links, saved data compatibility and build/package outcomes as relevant.
5. If a regression is found, produce exact repro and identify likely introducing change.
6. Report pass/fail/not-run matrix to Director and add permanent test coverage for newly discovered failure modes.

## Deliverables

- Regression matrix and reproducible failures.
- Evidence of unchanged critical paths or disclosed gaps.

## Validation / done criteria

- [ ] Tests target realistic affected dependencies, not only the changed function.
- [ ] Baseline/new failure differences are clear.
- [ ] Untested platforms/scenes are explicitly listed.

## Guardrails

- Do not call a change regression-safe solely because unit tests pass.
- Do not invent baseline build results.

**Related skills:** automated-testing, bug-analysis, build-management.

## Godot integration

For scene work, follow `protocols/mcp-routing.md`. The Cline Director performs MCP operations; workers return file outputs and integration requests. Record evidence through `engine-validation`.
