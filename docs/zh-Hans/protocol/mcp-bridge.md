---
title: MCP Bridge
status: MVP
---

# MCP Bridge

MDP server 暴露的是一组稳定的 MCP tool surface，而不是按 capability 动态生成 tools。

Bridge tools 包括：

- `listClients`
- `callClients`
- `listTools`
- `callTools`
- `listPrompts`
- `getPrompt`
- `listSkills`
- `callSkills`
- `listResources`
- `readResource`

这样的 bridge surface 可以让 host 侧保持稳定，同时允许 client registry 在运行时动态变化。
