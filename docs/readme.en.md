# Skill Router

Skill Router chooses the best installed skill, rule, or workflow for a request before doing the work.

It is designed to save context: route by capability, choose one primary skill, add only useful supporting skills, and avoid loading every skill at once.

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

## Universal Routing

Skill Router does not require fixed skill names. It looks for capability words in skill metadata:

- Coding: code, implement, refactor, development
- Testing: test-driven, TDD, unit tests
- Debugging: debug, bug, failing test, runtime error
- Planning: plan, roadmap, decomposition
- Verification: verify, QA, validation, completion
- UI/UX: UI, UX, layout, accessibility, component
- Prototypes: prototype, demo, animation, motion
- GitHub/CI: GitHub, PR, Actions, CI, checks

Known skill names are aliases and examples, not requirements.
