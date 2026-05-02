# Skill Router

Skill Router est une petite meta-skill qui choisit la skill, la règle ou le workflow installé le plus adapté avant de commencer le travail.

Elle économise le contexte en choisissant une skill principale et en ajoutant des skills de support uniquement quand elles sont utiles.

## Installation Pour Codex

```powershell
Copy-Item -Recurse .\codex\skill-router $env:USERPROFILE\.codex\skills\skill-router
```

Redémarrez Codex, puis utilisez :

```text
$skill-router Aide-moi à implémenter cette fonctionnalité...
```

## Installation Pour Claude

```powershell
Copy-Item -Recurse .\claude\.claude\skills\skill-router .\.claude\skills\skill-router
```

## Installation Pour Cursor

```powershell
New-Item -ItemType Directory -Force .\.cursor\rules
Copy-Item .\cursor\skill-router.mdc .\.cursor\rules\skill-router.mdc
```

## Routage Par Défaut

- Code et refactorisation : `using-superpowers`
- Développement piloté par les tests : `test-driven-development`
- Bugs et comportements cassés : `systematic-debugging`
- UI/UX et finition visuelle : `ui-ux-pro-max`
- Prototypes HTML haute fidélité : `huashu-design`
- Jugement d'ingénierie : `karpathy-guidelines`
- Vérification finale : `verification-before-completion`

