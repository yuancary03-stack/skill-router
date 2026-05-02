# Skill Router

Skill Router 是一个小型“技能路由器”：在开始任务前，先判断应该使用哪个已安装 skill、规则或工作流。

它的目标是节省上下文：按能力而不是固定名称路由，优先选择 1 个主 skill，只在确实有帮助时增加辅助 skill，避免一次性加载所有 skill。

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

## 通用路由

Skill Router 不要求 skill 必须叫某个固定名字。它会优先查看 skill 元数据里的 `name` 和 `description`，按能力关键词选择：

- 写代码：code、implement、refactor、development
- 测试：test-driven、TDD、unit tests
- 调试：debug、bug、failing test、runtime error
- 计划：plan、roadmap、decomposition
- 验证：verify、QA、validation、completion
- UI/UX：UI、UX、layout、accessibility、component
- 原型：prototype、demo、animation、motion
- GitHub/CI：GitHub、PR、Actions、CI、checks

`using-superpowers`、`systematic-debugging`、`ui-ux-pro-max`、`huashu-design` 等只是别名和示例，不是硬性要求。
