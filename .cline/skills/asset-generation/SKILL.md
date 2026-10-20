---
name: asset-generation
description: "Generate or specify original 2D/3D/audio assets with reproducible settings, clear rights and output type."
---

# AI-assisted asset creation

**Primary role:** Creative Artist. **Use when:** a game needs sprites, textures, objects, character art, 3D models or other production assets.

## Required inputs

- Approved art brief and exact deliverable type.
- Available creation tools, acceptable license terms and output folder.
- Target dimensions, resolution, alpha, geometry/rigging or audio requirements.

## Procedure

1. Choose the actual required artifact: concept, sprite, texture, model, rig, clip or audio—not a visually similar substitute.
2. Select an available generator/editor; if none exists, produce a detailed reproducible brief/prompt and clearly mark it as **not generated**.
3. Use consistent art/style references and technical settings; avoid unwanted text, logos, extra limbs or artifacts as appropriate.
4. Inspect produced files for format, alpha/background, fidelity, scale, loops or mesh usability.
5. Record tool/model, version, seed/settings/prompts if accessible and provenance/license restrictions.
6. Hand off files and a manifest to `asset-pipeline`; request a correction pass when requirements are unmet.

## Deliverables

- Actual generated file paths **or** clearly labeled generation specifications.
- Generation provenance/settings and technical quality notes.

## Validation / done criteria

- [ ] Output type matches task (e.g., animatable 3D mesh vs reference image).
- [ ] Required dimensions, compatibility and style checked.
- [ ] Rights/provenance status recorded for all candidate shipping assets.

## Guardrails

- Do not invent files when generator access is unavailable.
- Do not use a copyrighted character/logo or third-party model without authorization.

**Related skills:** asset-pipeline, art-direction, character-design.

## Godot integration

For scene work, follow `protocols/mcp-routing.md`. The Cline Director performs MCP operations; workers return file outputs and integration requests. Record evidence through `engine-validation`.
