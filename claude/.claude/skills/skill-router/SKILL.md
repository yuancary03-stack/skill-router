---
name: skill-router
description: Universal skill router for choosing the best available skill, agent, rule, mode, or workflow before doing a task. Use when the user asks to automatically choose skills, route a request, use available abilities intelligently, decide which expert mode applies, or handle mixed coding/design/debugging/review/planning/prototype/document tasks without manually naming every skill. Works by capability discovery first, known aliases second.
---

# Skill Router

## Overview

Route by capability, not by a fixed personal skill list. Choose the smallest useful set of available skills or workflows for the task, load only those instructions, then continue with the work.

## Routing Workflow

1. Identify the task's capabilities: coding, debugging, testing, review, planning, UI/UX, visual design, prototype, docs, data, browser automation, deployment, GitHub/CI, security, Figma/design handoff, skill creation, or mixed.
2. Honor any explicitly named skill, rule, mode, or agent first.
3. Inspect available metadata when needed. Prefer names and descriptions; do not read every skill body.
4. Pick one primary workflow by capability match. Add at most two supporting workflows when they materially help.
5. Read or activate only the chosen instruction bodies.
6. If no skill fits, say so briefly and proceed normally.

## Capability Routing

Use this generic map first. The examples are aliases, not requirements.

| Capability | Look for metadata mentioning | Example aliases |
| --- | --- | --- |
| Coding and implementation | code, implement, refactor, development | engineering workflow, `using-superpowers` |
| Test-first work | test-driven, TDD, unit tests | `test-driven-development` |
| Debugging | debug, bug, failing test, error, broken | `systematic-debugging` |
| Planning | plan, roadmap, decomposition | `writing-plans`, `executing-plans` |
| Verification | verify, QA, validation, completion | `verification-before-completion` |
| Review | review, PR comments, critique | review workflow |
| UI/UX | UI, UX, layout, accessibility, component | UI/UX skill |
| Visual design | brand, visual, style, design system | design skill |
| Prototypes | prototype, demo, animation, motion | prototype skill |
| Figma/design handoff | Figma, node, design-to-code | Figma workflow |
| Documents/data/slides | document, spreadsheet, presentation | document/data/deck workflow |
| Browser automation | browser, screenshot, Playwright | browser workflow |
| Deployment | deploy, hosting, Vercel, Netlify | deployment workflow |
| GitHub/CI | GitHub, PR, Actions, CI, checks | GitHub workflow |
| Security | security, threat model, best practices | security workflow |
| Skill authoring | create skill, edit skill, plugin | skill/plugin workflow |

## Scoring

When several skills match, choose by:

1. Explicit user request.
2. Strongest metadata match to the task.
3. Narrower specialist over broad generalist.
4. Entry/router skill over sub-skill when the package already has its own router.
5. Lower context cost when two choices are otherwise equivalent.

## Mixed Requests

- UI implementation: choose UI/UX for design decisions and engineering for code execution.
- Debugging a UI: fix behavior first; add visual polish only if requested.
- Prototype with motion: choose prototype/motion as primary; add verification before delivery.
- Ambiguous product idea: choose planning or brainstorming first.
- CI failure: choose GitHub/CI or debugging first, then verification.

## Communication

Briefly name the selected capability and workflow, then continue into the work. Do not turn routing into a long discussion unless the user only asked which skill to use.

