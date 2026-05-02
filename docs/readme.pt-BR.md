# Skill Router

Skill Router é uma pequena meta-skill que escolhe a melhor skill, regra ou fluxo de trabalho instalado antes de começar.

Ela economiza contexto escolhendo uma skill principal e adicionando skills de apoio somente quando elas realmente ajudam.

## Instalação No Codex

```powershell
Copy-Item -Recurse .\codex\skill-router $env:USERPROFILE\.codex\skills\skill-router
```

Reinicie o Codex e chame:

```text
$skill-router Me ajude a implementar este recurso...
```

## Instalação No Claude

```powershell
Copy-Item -Recurse .\claude\.claude\skills\skill-router .\.claude\skills\skill-router
```

## Instalação No Cursor

```powershell
New-Item -ItemType Directory -Force .\.cursor\rules
Copy-Item .\cursor\skill-router.mdc .\.cursor\rules\skill-router.mdc
```

## Roteamento Padrão

- Código e refatoração: `using-superpowers`
- Desenvolvimento com testes primeiro: `test-driven-development`
- Bugs e comportamento quebrado: `systematic-debugging`
- UI/UX e polimento visual: `ui-ux-pro-max`
- Protótipos HTML de alta fidelidade: `huashu-design`
- Julgamento de engenharia: `karpathy-guidelines`
- Verificação final: `verification-before-completion`

