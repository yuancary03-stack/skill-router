---
name: skill-router
description: Route a user request to the best available skill, agent, rule, or workflow before doing the work. Use when the user asks to automatically choose skills, decide which expert mode applies, use all available abilities intelligently, or handle mixed coding/design/debugging/review/planning/prototype/document tasks without manually naming every skill.
---

# Skill Router

## Overview

Choose the smallest useful set of available skills or workflows for the task. Prefer one primary skill and at most two supporting skills unless the user explicitly asks for a broader workflow.

## Routing Workflow

1. Identify the task type: coding, debugging, UI/UX, high-fidelity prototype, document, spreadsheet, presentation, Figma/design handoff, planning, review, or mixed.
2. Honor any skill, rule, mode, or agent the user explicitly named first.
3. Select the best primary workflow using the map below.
4. Add supporting workflows only when they materially change the result.
5. Do not load every skill. Read or activate only the chosen skill bodies.
6. If a skill is installed on disk but not automatically loaded, read its instructions manually and mention that the client may need a restart or install step for automatic activation.

## Primary Routing Map

- General coding, implementation, refactoring, branch work: use the engineering workflow or `using-superpowers` if installed.
- Test-first implementation: use `test-driven-development`.
- Bugs and broken runtime behavior: use `systematic-debugging`.
- Large or ambiguous work needing sequencing: use `writing-plans`, then `executing-plans`.
- Final checks before claiming completion: use `verification-before-completion`.
- Code review: use review workflow, `requesting-code-review`, or the client-native review mode.
- Applying review comments: use `receiving-code-review`.
- Conservative engineering judgment and avoiding overcomplication: use `karpathy-guidelines`.
- Web/mobile UI, components, dashboards, landing pages, accessibility, visual polish: use `ui-ux-pro-max` or the closest UI/UX skill.
- High-fidelity HTML prototypes, interactive demos, animation demos, design variants, visual direction exploration: use `huashu-design`.
- Figma URLs or design-to-code handoff: use the Figma workflow first.
- Creating or editing skills: use the skill creation workflow.

## Mixed Requests

- UI implementation: route design decisions through the UI/UX skill, then execute with the engineering workflow.
- High-fidelity prototype with motion: use the prototype/design skill as primary and verify interactions before delivery.
- Debugging a UI: fix behavior first with debugging, then polish visuals if requested.
- Ambiguous product idea: brainstorm or plan first, then route to implementation or design.

## Communication

Briefly name the chosen skill or workflow and why, then continue into the actual work. If no installed skill fits, say so once and proceed normally.

