# Skill Router

Skill Router 是一個小型「技能路由器」：在開始任務前，先判斷應該使用哪個已安裝的 skill、規則或工作流。

它的目標是節省上下文：優先選擇 1 個主要 skill，只在確實有幫助時加入輔助 skill，避免一次載入所有 skill。

## Codex 安裝

```powershell
Copy-Item -Recurse .\codex\skill-router $env:USERPROFILE\.codex\skills\skill-router
```

重新啟動 Codex 後呼叫：

```text
$skill-router 幫我實作這個功能……
```

## Claude 安裝

```powershell
Copy-Item -Recurse .\claude\.claude\skills\skill-router .\.claude\skills\skill-router
```

## Cursor 安裝

```powershell
New-Item -ItemType Directory -Force .\.cursor\rules
Copy-Item .\cursor\skill-router.mdc .\.cursor\rules\skill-router.mdc
```

## 預設路由

- 寫程式、重構：`using-superpowers`
- 測試先行開發：`test-driven-development`
- Bug 與異常行為：`systematic-debugging`
- UI/UX 與視覺優化：`ui-ux-pro-max`
- 高保真 HTML 原型：`huashu-design`
- 工程判斷：`karpathy-guidelines`
- 完成前驗證：`verification-before-completion`

