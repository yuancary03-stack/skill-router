# Skill Router

Skill Router es una meta-skill pequeña que elige la skill, regla o flujo de trabajo instalado más adecuado antes de empezar.

Está pensado para ahorrar contexto: elige una skill principal y solo agrega skills de apoyo cuando aportan valor real.

## Instalación En Codex

```powershell
Copy-Item -Recurse .\codex\skill-router $env:USERPROFILE\.codex\skills\skill-router
```

Reinicia Codex y llama:

```text
$skill-router Ayúdame a implementar esta función...
```

## Instalación En Claude

```powershell
Copy-Item -Recurse .\claude\.claude\skills\skill-router .\.claude\skills\skill-router
```

## Instalación En Cursor

```powershell
New-Item -ItemType Directory -Force .\.cursor\rules
Copy-Item .\cursor\skill-router.mdc .\.cursor\rules\skill-router.mdc
```

## Rutas Predeterminadas

- Código y refactorización: `using-superpowers`
- Desarrollo con pruebas primero: `test-driven-development`
- Bugs y comportamiento roto: `systematic-debugging`
- UI/UX y pulido visual: `ui-ux-pro-max`
- Prototipos HTML de alta fidelidad: `huashu-design`
- Criterio de ingeniería: `karpathy-guidelines`
- Verificación final: `verification-before-completion`

