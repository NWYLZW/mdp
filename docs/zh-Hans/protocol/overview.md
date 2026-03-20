---
title: 概览
status: Draft
---

# 协议概览

MDP 同时是一个发现协议和一个 RPC bridge 协议。

client 提供能力，server 负责存储和索引，MCP host 则通过固定的 bridge surface 消费这些能力。

MDP 当前定义四类能力：

- `tools`
- `prompts`
- `skills`
- `resources`

每一类都可以描述不同类型的运行时本地能力或只读表面。
