---
name: ui-design
description: "Design menus, HUD, prompts and interaction feedback with accessible input and visual hierarchy."
---

# Game UI and HUD design

**Primary role:** Creative Artist. **Use when:** health bars, inventory UI, dialogue interfaces, settings, menus or HUD elements are needed.

## Required inputs

- User flow, game input methods and relevant mechanic states.
- Design system, intended screen sizes and localization needs.
- Accessibility needs and engine UI conventions.

## Procedure

1. Enumerate UI states, entry/exit actions, navigation order and required player information.
2. Define hierarchy and safe-area/contrast rules for actual game camera/background.
3. Create layouts with keyboard/gamepad/touch focus paths and accessible equivalents for color-only cues.
4. Specify responsive behavior, subtitles/text scaling, localization expansion and controller prompts.
5. Produce actual assets or annotated designs, with component names/events for Developer.
6. Validate in-engine legibility, focus navigation, error/empty states and feedback timing when possible.

## Deliverables

- UI flow, screen/state designs and component/event specifications.
- Asset handoff plus accessibility and implementation notes.

## Validation / done criteria

- [ ] No critical information relies on color alone.
- [ ] Focus/navigation and text-scaling behavior are specified for intended devices.
- [ ] UI states map to agreed gameplay variables/events.

Design completion establishes an implementable handoff. Verify navigation, text scaling and legibility on the integrated UI through `gameplay-testing`; record those results separately.

## Guardrails

- Do not treat a static mockup as an implemented menu.
- Do not add dark patterns or unapproved monetization UI.

**Related skills:** game-mechanics, asset-pipeline, gameplay-testing.
