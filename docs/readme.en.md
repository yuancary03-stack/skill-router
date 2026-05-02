# Skill Router

Skill Router chooses the best installed skill, rule, or workflow for a request before doing the work.

It is designed to save context: choose one primary skill, add only useful supporting skills, and avoid loading every skill at once.

## Install For Codex

```powershell
Copy-Item -Recurse .\codex\skill-router $env:USERPROFILE\.codex\skills\skill-router
```

Restart Codex, then call:

```text
$skill-router Help me implement this feature...
```

## Install For Claude

```powershell
Copy-Item -Recurse .\claude\.claude\skills\skill-router .\.claude\skills\skill-router
```

Then ask:

```text
Use skill-router to choose the best skill for this task...
```

## Install For Cursor

```powershell
New-Item -ItemType Directory -Force .\.cursor\rules
Copy-Item .\cursor\skill-router.mdc .\.cursor\rules\skill-router.mdc
```

## Routing Defaults

- Coding and refactoring: `using-superpowers`
- Test-first work: `test-driven-development`
- Bugs and broken behavior: `systematic-debugging`
- UI/UX and visual polish: `ui-ux-pro-max`
- High-fidelity HTML prototypes: `huashu-design`
- Engineering judgment: `karpathy-guidelines`
- Final checks: `verification-before-completion`

