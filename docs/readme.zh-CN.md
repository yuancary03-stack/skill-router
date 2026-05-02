# Skill Router

Skill Router 是一个小型“技能路由器”：在开始任务前，先判断应该使用哪个已安装 skill、规则或工作流。

它的目标是节省上下文：优先选择 1 个主 skill，只在确实有帮助时增加辅助 skill，避免一次性加载所有 skill。

## Codex 安装

```powershell
Copy-Item -Recurse .\codex\skill-router $env:USERPROFILE\.codex\skills\skill-router
```

重启 Codex 后调用：

```text
$skill-router 帮我实现这个功能……
```

## Claude 安装

```powershell
Copy-Item -Recurse .\claude\.claude\skills\skill-router .\.claude\skills\skill-router
```

然后这样使用：

```text
Use skill-router to choose the best skill for this task...
```

## Cursor 安装

```powershell
New-Item -ItemType Directory -Force .\.cursor\rules
Copy-Item .\cursor\skill-router.mdc .\.cursor\rules\skill-router.mdc
```

## 默认路由

- 写代码、重构：`using-superpowers`
- 测试先行开发：`test-driven-development`
- Bug 和异常行为：`systematic-debugging`
- UI/UX 和视觉优化：`ui-ux-pro-max`
- 高保真 HTML 原型：`huashu-design`
- 工程判断和避免过度设计：`karpathy-guidelines`
- 完成前验证：`verification-before-completion`

