---
name: automated-testing
description: "Write and execute tests for gameplay logic, APIs, deterministic state transitions and integration boundaries."
---

# Game automated testing

**Primary role:** Game Developer (Director reviews). **Use when:** code changes, bug fixes, core mechanic rules or CI gates need repeatable verification.

## Required inputs

- Feature/architecture specs and existing test suite.
- Real engine/toolchain plus commands from `project/ENGINE_PROFILE.md`.
- Affected modules and explicit acceptance criteria.

## Procedure

1. List invariant/transition, happy-path, boundary and invalid-state scenarios.
2. Choose appropriate unit, integration or headless scene tests based on dependencies and what can be isolated.
3. Write tests against observable behavior, using seeds/fakes only where valid.
4. Run test command and record exact version, parameters, exit status and relevant log excerpts.
5. Investigate flakes, order-dependence and false positives instead of rerunning until green.
6. Return a result matrix and untested scenarios to Director; keep new tests as regression guards.

## Deliverables

- Tests in repository and command/run log.
- Coverage-by-criterion matrix, passes/failures and non-runnable cases.

## Validation / done criteria

- [ ] Assertions check player/system behavior rather than implementation trivia.
- [ ] Relevant edge cases and failures are represented.
- [ ] Executed tests are separated from proposed tests.

## Guardrails

- Do not fabricate passing logs, coverage or screenshots.
- Unit tests alone cannot validate usability or game feel.

**Related skills:** gameplay-testing, regression-testing, bug-analysis.

## Godot integration

For scene work, follow `protocols/mcp-routing.md`. The Cline Director performs MCP operations; workers return file outputs and integration requests. Record evidence through `engine-validation`.
