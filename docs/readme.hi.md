# Skill Router

Skill Router एक छोटी meta-skill है जो काम शुरू करने से पहले सबसे उपयुक्त installed skill, rule या workflow चुनती है।

यह context बचाने के लिए बनाई गई है: एक primary skill चुनें, और supporting skills तभी जोड़ें जब वे सच में मदद करें।

## Codex में Install करें

```powershell
Copy-Item -Recurse .\codex\skill-router $env:USERPROFILE\.codex\skills\skill-router
```

Codex restart करें, फिर call करें:

```text
$skill-router इस feature को implement करने में मदद करो...
```

## Claude में Install करें

```powershell
Copy-Item -Recurse .\claude\.claude\skills\skill-router .\.claude\skills\skill-router
```

## Cursor में Install करें

```powershell
New-Item -ItemType Directory -Force .\.cursor\rules
Copy-Item .\cursor\skill-router.mdc .\.cursor\rules\skill-router.mdc
```

## Default Routing

- Coding और refactoring: `using-superpowers`
- Test-first development: `test-driven-development`
- Bugs और broken behavior: `systematic-debugging`
- UI/UX और visual polish: `ui-ux-pro-max`
- High-fidelity HTML prototypes: `huashu-design`
- Engineering judgment: `karpathy-guidelines`
- Final verification: `verification-before-completion`

