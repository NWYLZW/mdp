---
title: 常见问题
status: Draft
---

# 常见问题

## MDP 只适用于 JavaScript 吗？

不是。JavaScript 只是其中一种适配路径。协议本身是语言无关的，应该适用于 Android、iOS、Qt、后端运行时和 Web client。

## 为什么不为每个 client capability 动态生成一个 MCP tool？

因为能力集合本身是动态的。稳定的 bridge surface 更容易理解、更容易做兼容，也更适合处理运行时内部的过程调用。
