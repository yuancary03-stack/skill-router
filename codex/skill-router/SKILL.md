---
name: skill-router
description: Universal skill router for choosing the best available Codex skill or small skill combination before doing a task. Use when the user asks to automatically choose skills, route a request, use installed skills intelligently, decide which expert mode applies, or handle mixed coding/design/debugging/review/planning/prototype/document tasks without manually naming every skill. Works by capability discovery first, known aliases second.
---

# Skill Router

## Overview

Route by capability, not by a fixed personal skill list. Choose the smallest useful set of available Codex skills for the task, load only those skills, then continue with the work.

## Routing Workflow

1. Identify the task's capabilities: coding, debugging, testing, review, planning, UI/UX, visual design, prototype, docs, data, browser automation, deployment, GitHub/CI, security, Figma/design handoff, skill creation, plugin creation, or mixed.
2. Honor any explicitly named skill first.
3. Inspect available skill metadata when needed. Prefer `name` and `description` frontmatter; do not read every skill body.
4. Pick one primary skill by capability match. Add at most two supporting skills when they materially help.
5. If a selected skill is available in the current Codex skill list, invoke it normally. If it is installed on disk but not loaded, read its `SKILL.md` and mention that Codex may need a restart for formal invocation.
6. If no skill fits, say so briefly and proceed normally.

## Capability Routing

Use this generic map first. The examples are aliases, not requirements.

| Capability | Look for skills whose metadata mentions | Common aliases |
| --- | --- | --- |
| Coding and implementation | code, implement, refactor, branch, development | `using-superpowers`, engineering workflow |
| Test-first work | test-driven, TDD, unit tests, regression tests | `test-driven-development` |
| Debugging | debug, bug, failing test, error, runtime, broken | `systematic-debugging` |
| Planning | plan, roadmap, milestones, decomposition | `writing-plans`, `executing-plans` |
| Verification | verify, validation, final check, QA, completion | `verification-before-completion` |
| Code review | review, PR comments, critique, risk scan | `requesting-code-review`, `receiving-code-review` |
| UI/UX | UI, UX, layout, accessibility, dashboard, component | `ui-ux-pro-max`, `design`, `ui-styling` |
| Brand and visual design | brand, visual, style, banner, design system | `brand`, `banner-design`, `design-system` |
| High-fidelity prototypes | prototype, demo, animation, HTML prototype, motion | `huashu-design` |
| Figma/design handoff | Figma, node, design-to-code, design system rules | `figma` |
| Documents | docx, document, redline, comments, formatting | document skills |
| Spreadsheets/data | xlsx, csv, spreadsheet, table, chart, formula | spreadsheet skills |
| Presentations | slides, PPTX, deck, presentation | presentation skills |
| Browser automation | browser, screenshot, Playwright, web test | browser or Playwright skills |
| Deployment | deploy, hosting, Vercel, Netlify, Cloudflare, Render | deployment skills |
| GitHub/CI | GitHub, PR, Actions, CI, checks, gh | `gh-fix-ci`, `gh-address-comments` |
| Security | threat model, security review, ownership, best practices | security skills |
| Skill/plugin authoring | create skill, edit skill, plugin, marketplace | `skill-creator`, `plugin-creator` |

## Discovery

If the best route is unclear, inspect installed skills lightly:

```powershell
Get-ChildItem $env:USERPROFILE\.codex\skills -Directory | ForEach-Object {
  $p = Join-Path $_.FullName 'SKILL.md'
  if (Test-Path $p) {
    Get-Content $p -TotalCount 8
  }
}
```

Use only the `name` and `description` frontmatter to decide. Read only the chosen skill's `SKILL.md`, not the whole skills directory.

## Scoring

When several skills match, choose by:

1. Explicit user request.
2. Strongest metadata match to the task.
3. Narrower specialist over broad generalist.
4. Entry/router skill over sub-skill when the package already has its own router.
5. Lower context cost when two choices are otherwise equivalent.

## Mixed Requests

- UI implementation: choose a UI/UX skill for design decisions and an engineering skill for code execution.
- Debugging a UI: debug behavior first; add UI polish only after the bug is fixed or if the user asked for it.
- Prototype with motion: choose a prototype/motion skill as primary; add verification before delivery.
- Ambiguous product idea: choose planning or brainstorming first, then route to implementation/design.
- CI failure: choose GitHub/CI or debugging first, then verification.

## Communication

Briefly name the selected capability and skill, then continue into the work.

Example:

```text
I will route this as debugging first and use the best installed debugging skill; I will add verification before delivery.
```

Do not present routing as a long discussion unless the user only asked which skill to use.

