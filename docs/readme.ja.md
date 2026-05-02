# Skill Router

Skill Router は、作業を始める前に最適なインストール済み skill、ルール、またはワークフローを選ぶ小さなメタ skill です。

コンテキストを節約するため、主 skill を 1 つ選び、必要な場合だけ補助 skill を追加します。

## Codex へのインストール

```powershell
Copy-Item -Recurse .\codex\skill-router $env:USERPROFILE\.codex\skills\skill-router
```

Codex を再起動してから呼び出します。

```text
$skill-router この機能を実装して……
```

## Claude へのインストール

```powershell
Copy-Item -Recurse .\claude\.claude\skills\skill-router .\.claude\skills\skill-router
```

## Cursor へのインストール

```powershell
New-Item -ItemType Directory -Force .\.cursor\rules
Copy-Item .\cursor\skill-router.mdc .\.cursor\rules\skill-router.mdc
```

## 既定のルーティング

- コーディング、リファクタリング: `using-superpowers`
- テスト先行の実装: `test-driven-development`
- バグや異常動作: `systematic-debugging`
- UI/UX と見た目の改善: `ui-ux-pro-max`
- 高忠実度 HTML プロトタイプ: `huashu-design`
- エンジニアリング判断: `karpathy-guidelines`
- 完了前の検証: `verification-before-completion`

