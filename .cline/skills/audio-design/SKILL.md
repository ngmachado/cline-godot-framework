---
name: audio-design
description: "Define and produce music, SFX, spatial audio and ambience tied to game events and atmosphere."
---

# Game audio and sound direction

**Primary role:** Creative Artist. **Use when:** a game needs audio feedback, footsteps, ambience, UI sounds or adaptive music.

## Required inputs

- Art/narrative direction, gameplay event names and camera context.
- Target platform, mixing/spatialization capabilities and asset/license restrictions.
- Accessibility requirements for non-audio cues.

## Procedure

1. Classify sounds by function: navigation, danger, impact, progression, UI, ambient and musical mood.
2. Define event mapping, priority, timing, spatial position, loop behavior and ducking/mixing rules.
3. Specify output formats, sample rates, channel count, loudness and looping points compatible with engine.
4. Produce or source assets only through available authorized tools; document licenses/provenance.
5. Coordinate with Developer on middleware/native-engine event integration and pause/transition behavior.
6. Validate on target speakers/headphones when feasible, testing clipping, fatigue, dialogue intelligibility and silent-mode alternatives.

## Deliverables

- Audio identity guide and event-to-asset mapping.
- Actual audio files or labeled design briefs, with import and rights notes.

## Validation / done criteria

- [ ] The design specifies cue priority, mixing targets and non-audio alternatives for gameplay-critical information.
- [ ] Event mapping, loop points and transition rules are explicit.
- [ ] Supplied audio files, when required, have format, clipping and loop checks recorded.

A design brief can complete a specification-only task. Verify cue audibility, transitions and priority in the integrated game through `gameplay-testing`; a brief does not establish runtime behavior.

## Guardrails

- Do not claim audio files exist if only prompts/scripts were produced.
- No unlicensed music/samples in shipping bundles.

**Related skills:** art-direction, gameplay-programming, gameplay-testing.
