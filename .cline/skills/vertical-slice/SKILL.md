---
name: vertical-slice
description: "Select and deliver the smallest end-to-end representative gameplay experience before expanding scope."
---

# Playable vertical slice

**Primary role:** Game Director. **Use when:** the project needs a milestone, concept validation or demonstration build.

## Required inputs

- Game vision, target player loop and platform.
- Existing code/assets, known toolchain and available testing setup.
- Time/scope constraints and success criteria.

## Procedure

1. Select one representative interaction loop with clear beginning, challenge, feedback and end.
2. Enumerate the minimal required mechanics, UI, audio, visuals, persistence and transitions.
3. Prepare a Director-approved checklist excluding peripheral features and content.
4. Delegate technical foundations and creative assets with clear interfaces; use `workflows/vertical-slice.md`.
5. Integrate with actual runtime where possible; run automated checks and gameplay verification.
6. Compare demonstrated result to the original fantasy and decide iterate/expand/stop.

## Deliverables

- Slice brief and stage-gated task plan.
- Playable scene/build if executed, plus validation evidence and limitations.

## Validation / done criteria

- [ ] The slice demonstrates the intended core loop rather than disconnected tech demos.
- [ ] Necessary art and technical components integrate.
- [ ] No claim of playability without actual runtime evidence.

## Guardrails

- Do not extend to a full content pipeline before the loop is proven.
- Do not present an unbuilt plan as a completed vertical slice.

**Related skills:** game-concept, engine-integration, gameplay-testing.
