---
name: animation-integration
description: "Connect gameplay state to animation graphs, transitions and timed events without desynchronization."
---

# Gameplay animation integration

**Primary role:** Game Developer. **Use when:** characters, enemies, objects or UI need animation playback synchronized to game logic.

## Required inputs

- Animation clips, rig/sprite sheets and event specifications.
- Gameplay state chart and engine animation system.
- Root motion, hitbox and interrupt/cancel requirements.

## Procedure

1. Confirm clip names, duration, looping, import settings, rigs and transforms.
2. Map gameplay states to clips and transitions with explicit priorities and fallback states.
3. Identify whether movement authority comes from gameplay physics or root motion.
4. Connect animation method tracks or signals to gameplay callbacks for damage, footsteps, VFX and audio, preserving the specified event timing.
5. Test interruption, rapid input, repeated transitions, blend artifacts and missing clips.
6. Measure timing at low/variable frame rates and document unavoidable differences.

## Deliverables

- Integrated animation state graph and event mapping.
- Transition tests / runtime evidence and remaining mismatches.

## Validation / done criteria

- [ ] Gameplay remains authoritative for critical outcomes unless explicitly designed otherwise.
- [ ] No stuck animation or missing fallback state in tested paths.
- [ ] Actual imported animations are distinguished from planned clips.

## Guardrails

- Do not use animation to silently alter approved attack ranges/timing.
- Do not infer runtime correctness from an artist’s still image.

**Related skills:** animation-design, gameplay-programming, gameplay-testing.

## Godot integration

For scene work, follow `protocols/mcp-routing.md`. The Cline Director performs MCP operations; workers return file outputs and integration requests. Record evidence through `engine-validation`.
