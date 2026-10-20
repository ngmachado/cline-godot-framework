---
name: asset-pipeline
description: "Prepare and validate game-ready assets across generation, conversion, naming, metadata and engine import."
---

# Asset validation and import pipeline

**Primary role:** Creative Artist + Game Developer. **Use when:** an asset transitions from concept or source files to engine use, or an import fails.

## Required inputs

- Actual source assets; use `templates/asset-manifest.md` as the manifest format, leaving the template blank.
- Engine/import profile and art budgets.
- Usage role, dimensions, orientation, pivot, skeleton/clip and license data.

## Procedure

1. Inventory source files, dependencies, naming and relative paths; distinguish originals from converted game formats.
2. For 2D check dimensions, alpha, atlas layout, filtering, normals and spritesheet frames; for 3D check scale/axes, topology, UVs, materials, rig, bind pose, clips and LOD as applicable.
3. Validate texture budgets, triangle counts, animation loops and consistency with asset brief.
4. Create import metadata and a task-specific manifest alongside the delivered assets, linking source, transformed file, states and provenance.
5. Developer prepares authorized source edits, command-line checks and import instructions. Director performs editor imports through MCP and inspects resulting materials, pivot, animation and collisions with the workers’ criteria.
6. Report import/test results and issues; keep source artifacts available for iteration.

## Deliverables

- Complete asset manifest and engine-ready file(s), if generated.
- Import evidence, corrections needed and licenses/attributions.

## Validation / done criteria

- [ ] Source-to-import traceability exists.
- [ ] No missing required skeleton, texture, alpha or state for intended use.
- [ ] File is verified in-engine if claiming engine readiness.

## Guardrails

- Do not silently upscale/retopologize assets and lose source provenance.
- A single still image is not evidence that a model animates.

**Related skills:** asset-generation, engine-integration, animation-integration.

## Godot integration

For scene work, follow `protocols/mcp-routing.md`. The Cline Director performs MCP operations; workers return file outputs and integration requests. Record evidence through `engine-validation`.
