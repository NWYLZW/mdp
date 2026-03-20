---
title: 介绍
status: Draft
---

# 介绍

MDP 是一个发现协议，也是一个 RPC bridge 协议，用于把运行时本地能力暴露给 AI。

这个协议面向的是这样一类场景：真正有价值的能力已经存在于某个进程内部，例如：

- 移动端应用服务
- 桌面应用 facade
- iOS 或 Android 上的原生方法
- Qt 对象或 slot
- 浏览器运行时能力

MDP 不要求把这些能力预先固化成静态的 MCP tool 定义。相反，client 把能力元数据注册到一个轻量 server，server 再通过稳定的 MCP bridge tools 提供发现和调用。

## 范围

MDP 关注：

- client 注册
- capability discovery
- 路由调用
- 生命周期跟踪

它不规定应用业务逻辑，也不规定 UI 设计。
