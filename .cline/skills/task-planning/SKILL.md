---
name: task-planning
description: "Decompose a game objective into evidence-driven tasks with ownership, dependencies, file boundaries and approvals."
---

# Game task planning

**Primary role:** Game Director. **Use when:** a request spans multiple changes, roles, assets or steps.

## Required inputs

- Approved objective and current task state.
- Project specs, repository layout and host tool availability.
- Known time, platform and production constraints.

## Procedure

1. Define a smallest verifiable milestone; avoid overbuilding future systems.
2. Break work into task contracts with concrete artifacts, tests and acceptance criteria.
3. Identify dependency edges and mutually exclusive writable paths.
4. Assign each task to Director, Developer or Artist and attach only the necessary skills.
5. Schedule independent tasks concurrently only with host support and nonoverlapping writes.
6. Track state transitions and recovery plans in `project/TASK_BOARD.md`; update `project/PROJECT_STATUS.md` after verified progress.

## Deliverables

- Required contract and handoff record for every delegated task under `tasks/`, using `templates/task.md` as the format; keep the template blank. `project/TASK_BOARD.md` is the overview.
- Visible next action, blockers and required approvals.

## Validation / done criteria

- [ ] Every task has one accountable owner and measurable completion condition.
- [ ] Dependency chain yields an integrated runnable deliverable.
- [ ] No invented worker/process/tool capability.

## Guardrails

- Do not confuse planning with implementation.
- Do not delegate all the details back to the user.

**Related skills:** vertical-slice, automated-testing, bug-analysis.
