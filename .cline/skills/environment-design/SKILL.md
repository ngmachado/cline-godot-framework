---
name: environment-design
description: "Design game spaces, modular environments, props, lighting and atmosphere while preserving level readability."
---

# Environment and atmosphere design

**Primary role:** Creative Artist. **Use when:** levels need scenery, architecture, environmental storytelling or consistent atmosphere.

## Required inputs

- Director-approved blockout and traversal requirements.
- Art direction, camera mode and performance budget.
- Reusable modules, level context and interactive object list.

## Procedure

1. Study the blockout and mark traversal, landmark, combat and interaction critical zones.
2. Define modular kit dimensions, trim/texture strategy, landmarks, props and foreground/background separation.
3. Create lighting and palette rules that direct attention without hiding hazards and objectives.
4. Specify atmosphere/fog, environmental storytelling and reusable set dressing.
5. Provide asset manifests with tiling, LOD, collision and draw-call considerations.
6. Validate readability from player camera and request blockout review if asset layout would cause occlusion or softlocks.

## Deliverables

- Environment art brief, modular kit list and lighting/layout guidance.
- Asset import budgets and interactive-prop requirements.

## Validation / done criteria

- [ ] Landmark placement and clearances respect the approved blockout.
- [ ] Tiling, scale and occlusion constraints are explicit in the handoff.
- [ ] Planned asset counts and budgets fit the declared production and performance targets.

These checks establish design readiness. Verify navigation, occlusion and performance after integration; record measured results separately from planning estimates.

## Guardrails

- Do not reshape approved traversal topology without Director/Developer coordination.
- Do not mistake a beautiful environment render for a tested level.

**Related skills:** level-design, art-direction, asset-pipeline.

## Godot integration

For scene work, follow `protocols/mcp-routing.md`. The Cline Director performs MCP operations; workers return file outputs and integration requests. Record evidence through `engine-validation`.
