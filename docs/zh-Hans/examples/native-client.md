---
title: 原生客户端
status: Draft
---

# 原生客户端

这个路径被保留下来，主要是为了兼容旧链接。当前文档结构更推荐从运行时集成页和通用嵌入页开始。

## 推荐入口

- [嵌入方式](/zh-Hans/client/embedding)
- [VSCode 插件](/zh-Hans/apps/vscode-extension)
- [JetBrains 插件](/zh-Hans/apps/jetbrains-plugin)

## 这个页面指的是什么

原生 client 可以在不把内部应用 API 变成公共远程服务的前提下，把它们暴露出来。

合适的场景包括：

- Android view 与 service 方法
- iOS 应用状态与动作
- Qt slot 或 facade 方法

server 只看到协议层元数据和路由调用结果。
