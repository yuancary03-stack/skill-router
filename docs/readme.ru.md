# Skill Router

Skill Router — это небольшая meta-skill, которая перед началом работы выбирает наиболее подходящий установленный skill, правило или workflow.

Она экономит контекст: выбирает один основной skill и добавляет вспомогательные только тогда, когда они действительно полезны.

## Установка Для Codex

```powershell
Copy-Item -Recurse .\codex\skill-router $env:USERPROFILE\.codex\skills\skill-router
```

Перезапустите Codex и вызовите:

```text
$skill-router Помоги реализовать эту функцию...
```

## Установка Для Claude

```powershell
Copy-Item -Recurse .\claude\.claude\skills\skill-router .\.claude\skills\skill-router
```

## Установка Для Cursor

```powershell
New-Item -ItemType Directory -Force .\.cursor\rules
Copy-Item .\cursor\skill-router.mdc .\.cursor\rules\skill-router.mdc
```

## Маршрутизация По Умолчанию

- Код и рефакторинг: `using-superpowers`
- Разработка через тесты: `test-driven-development`
- Баги и сломанное поведение: `systematic-debugging`
- UI/UX и визуальная доработка: `ui-ux-pro-max`
- HTML-прототипы высокой точности: `huashu-design`
- Инженерное суждение: `karpathy-guidelines`
- Финальная проверка: `verification-before-completion`

