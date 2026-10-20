---
name: character-design
description: "Design characters with strong gameplay silhouettes, model/sprite specifications and animation-compatible features."
---

# Character and creature design

**Primary role:** Creative Artist. **Use when:** new player characters, NPCs, enemies, creatures or costume variants are needed.

## Required inputs

- Gameplay role, camera distance and relevant lore.
- Required movement/action states and combat readability needs.
- Art guide, collision/unit scale and format budget.

## Procedure

1. Define the character’s function and first-glance silhouette from actual player viewing angle.
2. Specify body proportions, important identifying traits, costume/material detail and color contrast.
3. Account for hitbox scale, contact points, weapon attachment and animation range of motion.
4. Choose 2D sprite/rigged 2D/3D requirements and turnaround/pose coverage according to intended pipeline.
5. Create an asset brief with idle, locomotion, attack/interact, damage and fallback states as needed.
6. Review readability against environment and UI colors, then pass technical specs to Developer before final production.

## Deliverables

- Character visual brief/reference set, technical constraints and state list.
- Asset requirements suitable for `asset-generation` or external creation.

## Validation / done criteria

- [ ] Silhouette conveys role at gameplay scale.
- [ ] Required states and attachment points are plausible for animation.
- [ ] Proportions/units match engine and art direction.

## Guardrails

- Do not conflate a concept image with a rigged character.
- Do not invent mechanics or lore changes while drawing.

**Related skills:** animation-design, asset-generation, asset-pipeline.

## Godot integration

For scene work, follow `protocols/mcp-routing.md`. The Cline Director performs MCP operations; workers return file outputs and integration requests. Record evidence through `engine-validation`.
