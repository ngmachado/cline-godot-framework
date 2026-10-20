---
name: game-architecture
description: "Design game-system ownership, interfaces, event flow and modular structure aligned to the existing engine."
---

# Game systems architecture

**Primary role:** Game Developer. **Use when:** a new gameplay system or project structure requires technical design.

## Required inputs

- Engine version/profile and current repository.
- Approved gameplay spec and target performance/platform constraints.
- Existing scenes, persistence rules and reusable components.

## Procedure

1. Inspect the actual code, Godot scene tree, reusable scenes, resources and existing conventions.
2. Identify state owners, lifetimes, update order, event boundaries and failure semantics.
3. Choose simplest stable design consistent with engine idioms; explain alternatives for risky architectural decisions.
4. Specify APIs/events, data schema, asset hooks and cross-system dependencies.
5. Define test seams and profiling points before significant implementation.
6. Update `project/ARCHITECTURE.md` and request Director approval for material migrations.

## Deliverables

- Architecture notes/diagram in Markdown and interface contracts.
- Migration impact and test strategy.

## Validation / done criteria

- [ ] No unowned mutable state or ambiguous authority for gameplay variables.
- [ ] Interfaces support feature acceptance criteria and asset pipeline.
- [ ] Architecture fits engine/version actually in use.

## Guardrails

- Do not introduce unnecessary abstraction for a small prototype.
- Never assume a Godot node/resource API without inspecting engine/profile.

**Related skills:** gameplay-programming, engine-integration, automated-testing.
