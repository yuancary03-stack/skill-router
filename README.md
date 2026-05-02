# Skill Router

**One entry skill that helps an AI agent choose the right skill before it starts working.**

Skill Router is a lightweight meta-skill for people who install many AI coding/design skills and do not want to manually decide which one to invoke every time. It reads the task, chooses the smallest useful skill set, and avoids loading every skill into context.

```text
$skill-router Build a settings page, polish the UI, and verify it before delivery.
```

## Why It Exists

Modern agent setups can quickly grow into a toolbox of specialized skills: coding workflows, debugging flows, UI/UX guides, prototype builders, Figma helpers, review checklists, and deployment tools. The hard part becomes knowing which one to use.

Skill Router gives you a single front door:

- Choose one primary skill for the task.
- Add supporting skills only when they materially help.
- Avoid context bloat from loading everything.
- Keep mixed requests, like "debug this UI and polish it", routed cleanly.

## Works With

| Platform | Included path | Use for |
| --- | --- | --- |
| Codex | `codex/skill-router/` | OpenAI Codex skills |
| Claude | `claude/.claude/skills/skill-router/` | Claude-style skill folders |
| Cursor | `cursor/skill-router.mdc` | Cursor project rules |

The repository also keeps a Codex-compatible `SKILL.md` at the root for direct local use.

## Quick Install

### Codex

```powershell
Copy-Item -Recurse .\codex\skill-router $env:USERPROFILE\.codex\skills\skill-router
```

Restart Codex, then call:

```text
$skill-router Help me choose the best skill for this task...
```

### Claude

```powershell
Copy-Item -Recurse .\claude\.claude\skills\skill-router .\.claude\skills\skill-router
```

Then ask Claude:

```text
Use skill-router to choose the best skill for this task...
```

### Cursor

```powershell
New-Item -ItemType Directory -Force .\.cursor\rules
Copy-Item .\cursor\skill-router.mdc .\.cursor\rules\skill-router.mdc
```

Then reference it in prompts or let Cursor apply it as a project rule.

## Routing Defaults

| Task | Default route |
| --- | --- |
| Coding, implementation, refactoring | `using-superpowers` |
| Test-first feature work | `test-driven-development` |
| Bugs, failing tests, broken behavior | `systematic-debugging` |
| Large or ambiguous tasks | `writing-plans` -> `executing-plans` |
| UI/UX, dashboards, components, visual polish | `ui-ux-pro-max` |
| High-fidelity HTML prototypes and animation demos | `huashu-design` |
| Conservative engineering judgment | `karpathy-guidelines` |
| Final checks before delivery | `verification-before-completion` |

You can edit the routing table in `SKILL.md` to match your own installed skills.

## Example Prompts

```text
$skill-router Implement OAuth login and add tests.
```

```text
$skill-router Review this dashboard UI and improve the layout.
```

```text
$skill-router This React component is broken. Debug it, fix it, and verify the result.
```

```text
$skill-router Create a high-fidelity mobile app prototype from this idea.
```

## Repository Layout

```text
skill-router/
  SKILL.md
  agents/openai.yaml
  codex/skill-router/
  claude/.claude/skills/skill-router/
  cursor/skill-router.mdc
  docs/
```

## Languages

- [English](docs/readme.en.md)
- [简体中文](docs/readme.zh-CN.md)
- [繁體中文](docs/readme.zh-TW.md)
- [日本語](docs/readme.ja.md)
- [한국어](docs/readme.ko.md)
- [Español](docs/readme.es.md)
- [Français](docs/readme.fr.md)
- [Deutsch](docs/readme.de.md)
- [Português do Brasil](docs/readme.pt-BR.md)
- [Русский](docs/readme.ru.md)
- [العربية](docs/readme.ar.md)
- [हिन्दी](docs/readme.hi.md)

## License

MIT

