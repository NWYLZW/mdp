---
title: 架构
status: Draft
---

# 架构

最小可用架构包含三部分：

1. `MDP client` 暴露本地过程调用。
2. `MDP server` 存储 registry 状态并负责路由。
3. `MCP host` 只通过稳定的 bridge tools 与 server 通信。

```mermaid
flowchart LR
  host["MCP Host"] <--> server["MDP Server"]
  server <--> client["MDP Client"]
  client --> runtime["本地运行时：移动端、桌面端、Web、后端"]
```

最重要的边界是 server 必须保持轻量。它不承载应用特定逻辑，只承载 registry 和 routing 逻辑。
