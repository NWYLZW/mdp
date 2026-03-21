---
title: VSCode 插件
status: Draft
---

# VSCode 插件

如果能力依赖工作区状态、编辑器选区、诊断信息或插件自身命令，VSCode 插件会是 MDP 很自然的一类宿主运行时。

## 适合暴露的能力

常见场景包括：

- 把当前文件或选区作为 resource 暴露
- 把扩展命令暴露成 tool
- 把评审、修复、重构流程封装成 skill

## 推荐接入方式

建议把 MDP client 直接运行在 extension host 进程里，而不是再额外拆一个远程服务。

这样可以保持：

- 编辑器状态留在本地
- capability 元数据清晰可见
- MCP 集成统一经过 MDP server

## 当前仓库状态

当前仓库已经内置一个 VSCode 插件应用，目录在 `apps/vscode-extension`。

这个 app 会把 MDP client 跑在 extension host 里，并默认暴露：

- `vscode.getWorkspaceContext`
- `vscode.findWorkspaceFiles`
- `vscode.readWorkspaceFile`
- `vscode.searchWorkspaceText`
- `vscode.getDiagnostics`
- 带 allowlist 的 `vscode.executeCommand`
- 作为 prompt 的 `vscode.reviewSelection`
- 作为 skill 的 `vscode.reviewActiveEditor`
- 当前文档、选区和工作区目录 resources

如果你要让 VSCode 运行时把能力注册到 MDP server，这个 app 现在就是默认起点。

## 配置项

这个扩展目前提供了一组 `mdp.*` 设置项：

- `mdp.serverUrl`
- `mdp.autoConnect`
- `mdp.autoReconnect`
- `mdp.reconnectDelayMs`
- `mdp.clientId`
- `mdp.clientName`
- `mdp.authToken`
- `mdp.allowedCommands`
- `mdp.findFilesMaxResults`
- `mdp.textSearchMaxResults`
- `mdp.resourceTextLimit`
- `mdp.diagnosticResultLimit`

## 构建

可以这样构建扩展：

```bash
pnpm --filter @modeldriveprotocol/vscode-extension build
```

构建后的入口位于 `apps/vscode-extension/dist/extension.js`。

- [JavaScript / 简易上手](/zh-Hans/sdk/javascript/quick-start)
- [MCP 定义](/zh-Hans/sdk/javascript/mcp-definitions)
- [Skills 定义](/zh-Hans/sdk/javascript/skills-definitions)
