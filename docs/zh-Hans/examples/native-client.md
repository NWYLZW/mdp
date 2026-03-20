---
title: 原生客户端
status: Draft
---

# 原生客户端

原生 client 可以在不把内部应用 API 变成公共远程服务的前提下，把它们暴露出来。

合适的场景包括：

- Android view 与 service 方法
- iOS 应用状态与动作
- Qt slot 或 facade 方法

server 只看到协议层元数据和路由调用结果。
