---
name: skill-router
description: Route a user request to the best installed Codex skill or small combination of skills before doing the work. Use when the user asks to automatically choose skills, use all available skills intelligently, decide which skill applies, start a task with the right workflow, or handle mixed coding/design/debugging/review/planning/prototype/document tasks without manually naming every skill.
---

# Skill Router

## Overview

Choose the smallest useful set of skills for the task, load or invoke them, then proceed with the work. Prefer one primary skill and at most two supporting skills unless the user explicitly asks for a broader workflow.

## Routing Workflow

1. Identify the user's actual task: coding, debugging, UI/UX, design prototype, document, spreadsheet, presentation, Figma, skill/plugin work, planning, review, or mixed.
2. Honor any skill the user explicitly named first.
3. Select the best primary skill using the map below.
4. Add supporting skills only when they materially change the work.
5. If a selected skill is available in the current Codex skill list, invoke it normally. If it is installed on disk but not loaded in the current session, read its `SKILL.md` from `$CODEX_HOME/skills/<skill-name>/SKILL.md` and follow it as a manual fallback, telling the user a restart may be needed for formal invocation.
6. Do not load every skill. Avoid skill stacking when a single entry skill already routes internally, such as `using-superpowers`, `ui-ux-pro-max`, or `huashu-design`.

## Primary Skill Map

- General coding, implementation, refactoring, branch work: `using-superpowers`.
- Write new behavior with meaningful regression risk: `test-driven-development`.
- Bugs, failures, broken tests, confusing runtime behavior: `systematic-debugging`.
- Large or ambiguous work needing sequencing: `writing-plans`, then `executing-plans`.
- Final checks before claiming completion: `verification-before-completion`.
- Code review request or risk scan: `requesting-code-review`.
- Applying review comments: `receiving-code-review`.
- Conservative engineering judgment and avoiding overcomplication: `karpathy-guidelines`.
- Web/mobile UI, components, dashboards, landing pages, app screens, accessibility, visual polish: `ui-ux-pro-max`.
- Visual design specifics: `design`, `design-system`, `ui-styling`, `brand`, `banner-design`, or `slides` when the request is narrowly about that area.
- High-fidelity HTML prototypes, interactive demos, animation demos, design variants, visual direction exploration, HTML slide demos: `huashu-design`.
- Figma URLs, node IDs, design-to-code from Figma: `figma`.
- Creating or editing skills: `skill-creator`.
- Installing skills: `skill-installer`.
- Creating plugins: `plugin-creator`.
- Documents, spreadsheets, or presentations: use the matching document, spreadsheet, or presentation skill/plugin when available.

## Mixed Requests

- UI implementation: use `ui-ux-pro-max` for design direction and `using-superpowers` for engineering execution.
- High-fidelity prototype with interaction or animation: use `huashu-design` as primary; add `verification-before-completion` before delivery.
- Debugging a UI: use `systematic-debugging` first; add `ui-ux-pro-max` only after the behavior is fixed and visual quality is in scope.
- Ambiguous product idea: use `brainstorming` or `writing-plans` first; then route to implementation/design skills.
- Existing design from Figma to code: use `figma` first, then `ui-ux-pro-max` or `using-superpowers` depending on whether the next work is visual translation or implementation.

## Discovery Fallback

When the task might need a skill not listed above, inspect installed skills without reading all bodies:

```powershell
Get-ChildItem $env:USERPROFILE\.codex\skills -Directory | ForEach-Object {
  $p = Join-Path $_.FullName 'SKILL.md'
  if (Test-Path $p) {
    Get-Content $p -TotalCount 6
  }
}
```

Use the `name` and `description` frontmatter to decide. Read only the chosen skill's `SKILL.md`, not the whole skills directory.

## User Communication

Briefly name the selected skill or skills and why. Then continue into the task instead of stopping at routing, unless the user only asked which skill to use.

Example:

```text
I will use `using-superpowers` for the engineering workflow and `verification-before-completion` before delivery.
```

If no installed skill fits, say so in one sentence and proceed with normal Codex behavior.
