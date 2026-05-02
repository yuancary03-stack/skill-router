# Skill Router

Skill Router는 작업을 시작하기 전에 가장 적합한 설치된 skill, 규칙 또는 워크플로를 선택하는 작은 메타 skill입니다.

컨텍스트를 아끼기 위해 기본 skill 하나를 고르고, 실제로 도움이 될 때만 보조 skill을 추가합니다.

## Codex 설치

```powershell
Copy-Item -Recurse .\codex\skill-router $env:USERPROFILE\.codex\skills\skill-router
```

Codex를 다시 시작한 뒤 호출합니다.

```text
$skill-router 이 기능을 구현해 줘……
```

## Claude 설치

```powershell
Copy-Item -Recurse .\claude\.claude\skills\skill-router .\.claude\skills\skill-router
```

## Cursor 설치

```powershell
New-Item -ItemType Directory -Force .\.cursor\rules
Copy-Item .\cursor\skill-router.mdc .\.cursor\rules\skill-router.mdc
```

## 기본 라우팅

- 코딩과 리팩터링: `using-superpowers`
- 테스트 우선 개발: `test-driven-development`
- 버그와 이상 동작: `systematic-debugging`
- UI/UX와 시각적 개선: `ui-ux-pro-max`
- 고충실도 HTML 프로토타입: `huashu-design`
- 엔지니어링 판단: `karpathy-guidelines`
- 완료 전 검증: `verification-before-completion`

