---
title: 概览
status: MVP
---

# 服务端概览

server 被刻意设计成轻量层。

它的职责包括：

- 管理 client sessions
- 维护内存 registry
- 按类型与名称索引 capabilities
- 暴露 MCP bridge tools
- 把调用路由到 client 并回收结果

server 不应该关心 client 是用 Swift、Kotlin、C++、JavaScript 还是 Python 实现的。
