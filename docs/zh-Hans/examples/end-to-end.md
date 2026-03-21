---
title: 端到端
status: MVP
---

# 端到端

主要流程请优先阅读[快速开始](/zh-Hans/guide/quick-start)。这个页面保留下来，是为了给旧链接提供一个更紧凑的兼容摘要。

## 最小端到端流程

一个完整的 MVP 流程是：

1. 启动 server
2. 在你的 MCP 工具里配置 bridge server
3. 启动 client
4. 注册 capabilities
5. 打开一个 Agent 对话
6. 让它列出 clients 或调用某个 tool
7. 通过 server 返回结果

只要这条路径跑通，协议就已经具备继续扩展到更多运行时的基本形状。
