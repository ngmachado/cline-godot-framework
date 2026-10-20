# Workflow: Deliver a vertical slice

**Owner:** Game Director. **Primary skill:** `vertical-slice`.

## Choose the slice

- Exactly one representative player fantasy/core loop with a clear objective, beginning and end.
- Include the minimum input, mechanics, feedback, art/audio, UI and progression required for a believable demonstration.
- Exclude full-world content, extensive cosmetics and speculative infrastructure unless necessary for this experience.

## Execution gates

1. **Design gate:** one-page slice brief, acceptance criteria, defined duration and target hardware.
2. **Integration gate:** Developer's runtime and Artist's assets agree on names, formats, scale, animations and interface events.
3. **Verification gate:** run tests and launch the slice if tooling exists; capture real evidence and failures.
4. **Experience gate:** Director assesses clarity, moment-to-moment feedback, pacing and whether the core loop suggests a compelling game. Label unplayed conclusions as hypotheses.
5. **Decision gate:** accept, revise the loop, or discontinue based on evidence. Do not expand features merely because the scene launches.

**Deliverables:** playable build/scene when feasible, slice spec, list of assets and dependencies, QA report, performance notes, and a concrete next decision.

## Godot integration gate

Follow `protocols/mcp-routing.md` before editor work and `protocols/acceptance.md` before completion. The Director runs MCP operations and records actual engine-validation evidence.
