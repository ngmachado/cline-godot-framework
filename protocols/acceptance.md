# Acceptance and QA protocol (without a dedicated QA agent)

**Owner:** Game Director. Validation skills can be executed by Developer and Artist, and reviewed by the Director. Use only the existing three roles; do not spawn an extra reviewer.

## Three distinct levels of evidence

1. **Technical correctness:** code compiles/runs, automated checks pass, assets import, transitions/persistence work, error budget is understood.
2. **Game-design correctness:** mechanic matches approved rules, communicates feedback, has appropriate challenge, respects accessibility and level progression.
3. **Player experience:** actual hands-on playtesting or recorded gameplay evidence supports clarity, responsiveness, and feel. Not derivable from static inspection alone; Director must label subjective conclusions as hypotheses until played.

## Mandatory gates

- **Gate A: Specification.** Requirements and acceptance criteria are approved or within delegated scope.
- **Gate B: Integration.** For implementation tasks, code/assets are actually placed in the project and no conflicting changes remain. For specification-only tasks, the agreed design artifact is recorded and ready for implementation; this does not establish runtime integration.
- **Gate C: Evidence.** Tests, validation results and limitations are recorded; tests not run are marked not run.
- **Gate D: Director decision.** Director marks `accepted` with evidence or returns the task for changes.

## Status state machine

`proposed → ready → in_progress → review → accepted → done`

Other transitions: `ready/in_progress/review → blocked`; `review → in_progress` on rejection. `done` requires accepted work **and** updated project records.

## Example evidence checklist

- [ ] Feature maps to approved design / art direction
- [ ] User-visible behavior exists in a runnable scene or appropriate artifact
- [ ] Relevant tests executed, results linked; failures triaged
- [ ] Asset provenance and budgets checked where applicable
- [ ] Critical paths/edge cases covered
- [ ] Regression checks run or explicitly unavailable
- [ ] Real playtest recorded when claiming player-experience quality
- [ ] Known limitations disclosed

If a gate cannot be satisfied, use board state `review` or `blocked`; never silently change acceptance criteria.

## Engine MCP evidence gates

For Godot scene modifications, require evidence of **correct project**, **persisted scene/assets**, **compilation/import status**, **runtime launch**, **interaction criteria** and **regression impact**. Use `engine-validation`. A successful read-only MCP probe only satisfies the project identity/capability check; successful script generation alone does not satisfy scene integration or runtime. Record each gate as `pass`, `fail`, `blocked` or `not-run` with a real artifact/log/test output. The Game Director cannot mark runtime acceptance `pass` when an editor/runner is unavailable.
