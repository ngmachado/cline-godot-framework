---
name: animation-design
description: "Define motion styles, clips, poses, timing and loops for characters and interactive props."
---

# Animation design and motion language

**Primary role:** Creative Artist. **Use when:** character locomotion, attacks, reactions, creatures or environmental animations are needed.

## Required inputs

- Gameplay state list, input/response timing and camera angle.
- Character rig or sprite constraints and art direction.
- Target framerate, skeleton/atlas format, root motion expectations.

## Procedure

1. Translate gameplay states into a clip inventory with required transitions and interruption behavior.
2. Specify key poses, anticipation, action, recovery, follow-through and readability priority.
3. Set clip durations, repeat/hold behavior, contact events, in/out states and synchronization cues.
4. Plan directional variants, blend spaces or additive animations if required by gameplay camera.
5. Create clips/animation references with available tools and inspect loops, arcs, foot sliding, mesh clipping and joint limits.
6. Provide clip/state/event contracts to Developer for `animation-integration`; record missing production steps.

## Deliverables

- Animation brief and clip/state/event table.
- Actual clip files or explicitly labeled storyboard/production specs.

## Validation / done criteria

- [ ] Specified timing and cancellation rules match approved mechanics.
- [ ] Poses and motion references account for the intended camera and readability requirements.
- [ ] Rig or spritesheet requirements are documented; supplied clips, if part of the task, are checked against them.

A specification-only task can finish with an implementation-ready brief or storyboard. If clips are required, a brief alone does not complete the task. Verify imported playback, camera readability and transitions through `animation-integration` and record those results separately.

## Guardrails

- Do not claim a storyboard or image sequence is a runtime animation unless imported and played.
- Avoid adding actions not represented in mechanics spec.

**Related skills:** character-design, animation-integration, asset-pipeline.
