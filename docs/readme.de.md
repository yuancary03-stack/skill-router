# Skill Router

Skill Router ist eine kleine Meta-Skill, die vor Beginn der Arbeit die passendste installierte Skill, Regel oder den passenden Workflow auswählt.

Sie spart Kontext, indem sie eine primäre Skill auswählt und nur dann unterstützende Skills ergänzt, wenn sie wirklich helfen.

## Installation Für Codex

```powershell
Copy-Item -Recurse .\codex\skill-router $env:USERPROFILE\.codex\skills\skill-router
```

Codex neu starten und dann aufrufen:

```text
$skill-router Hilf mir, dieses Feature umzusetzen...
```

## Installation Für Claude

```powershell
Copy-Item -Recurse .\claude\.claude\skills\skill-router .\.claude\skills\skill-router
```

## Installation Für Cursor

```powershell
New-Item -ItemType Directory -Force .\.cursor\rules
Copy-Item .\cursor\skill-router.mdc .\.cursor\rules\skill-router.mdc
```

## Standard-Routing

- Coding und Refactoring: `using-superpowers`
- Test-first-Entwicklung: `test-driven-development`
- Bugs und fehlerhaftes Verhalten: `systematic-debugging`
- UI/UX und visuelle Verfeinerung: `ui-ux-pro-max`
- High-Fidelity-HTML-Prototypen: `huashu-design`
- Technische Urteilsfähigkeit: `karpathy-guidelines`
- Abschlussprüfung: `verification-before-completion`

