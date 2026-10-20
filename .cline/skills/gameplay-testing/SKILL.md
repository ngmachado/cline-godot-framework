---
name: gameplay-testing
description: "Validate integrated mechanics, levels and feedback in a running game and distinguish test evidence from feel."
---

# Runtime gameplay verification

**Primary role:** Game Developer prepares scenarios and runs authorized command-line tests; Game Director performs MCP-driven execution and interaction, then reviews acceptance. **Use when:** a feature claims to be playable, interactions change, or a milestone needs an acceptance test.

## Required inputs

- Approved acceptance criteria and feature specs.
- A running test scene/build if available.
- Target controls, supported devices and relevant user flows.

## Procedure

1. Turn acceptance criteria into player actions and observable results, including cancel/retry/error paths.
2. Developer runs authorized command-line tests against the actual scene/build. Director performs launches and reproducible control sequences that require MCP. Record unsupported interaction checks as not-run.
3. Record observed transitions, feedback, navigation issues, softlocks and crashes with build identifier.
4. Check input remapping, timing and visually/audio-critical states when feasible.
5. Capture concrete evidence: logs, screenshots, video or test notes from real execution.
6. Separate objective rule violations from subjective game-feel concerns and suggest real human sessions for the latter.

## Deliverables

- Gameplay test matrix and reproducible issues.
- Runtime evidence and explicit not-run limitations.

## Validation / done criteria

- [ ] Feature can be reached and exercised in intended gameplay context.
- [ ] Core/edge interactions behave according to approved rules.
- [ ] Claims about fun or usability are marked hypotheses unless actual players were observed.

## Guardrails

- Do not invent player feedback or infer playability from screenshots/source.
- Do not replace runtime testing with mock outputs labeled as observed.

**Related skills:** automated-testing, balance-analysis, bug-analysis.

## Godot integration

For scene work, follow `protocols/mcp-routing.md`. The Cline Director performs MCP operations; workers return file outputs and integration requests. Record evidence through `engine-validation`.
