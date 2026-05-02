# Skill Router

Skill Router is a small meta-skill that chooses the best installed skill, rule, or agent workflow for a user request before doing the work.

It avoids loading every skill into context. It selects one primary skill and only adds supporting skills when they materially help.

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

## Quick Start

Install the Codex version:

```powershell
Copy-Item -Recurse .\codex\skill-router $env:USERPROFILE\.codex\skills\skill-router
```

Restart Codex, then call:

```text
$skill-router Help me choose the best skill for this task...
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

