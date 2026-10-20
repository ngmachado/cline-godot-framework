---
name: bug-analysis
description: "Isolate defects with reproducible steps, evidence and narrowly scoped correction plans."
---

# Bug reproduction and root-cause analysis

**Primary role:** Game Developer (Director triages). **Use when:** a crash, broken interaction, visual defect or inconsistent result is reported.

## Required inputs

- Observed symptoms, expected outcome and environment/build identity.
- Logs/screenshots/video when provided.
- Relevant repository files and recent changes.

## Procedure

1. Capture exact steps, initial state, recurrence frequency and severity.
2. Reproduce in the smallest available scene/test; if unavailable, label observations as hypotheses.
3. Narrow the issue by checking state transitions, recent changes, engine imports and dependencies.
4. Identify cause with trace/log/debug evidence where possible and write a failing test when viable.
5. Propose minimal fix with impact assessment; implement under the appropriate role and skill.
6. Retest original repro and nearby regressions; save a task-specific bug report under `project/reports/` using `templates/bug-report.md` as the format; leave the template blank.

## Deliverables

- Bug report with reproduction, diagnosis, fix status and evidence.
- Targeted regression test or reason unavailable.

## Validation / done criteria

- [ ] Expected vs observed behavior is explicit.
- [ ] Cause and fix claims are supported by a repeatable test or disclosed uncertainty.
- [ ] Neighboring systems have a regression check.

## Guardrails

- Do not rewrite architecture speculatively before isolation.
- Do not claim fixed if reproduction cannot be rerun.

**Related skills:** regression-testing, automated-testing, engine-integration.

## Godot integration

For scene work, follow `protocols/mcp-routing.md`. The Cline Director performs MCP operations; workers return file outputs and integration requests. Record evidence through `engine-validation`.
