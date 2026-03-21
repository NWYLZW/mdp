---
title: 嵌入方式
status: Draft
---

# 嵌入方式

这个路径被保留下来，是因为“嵌入 MDP client”本身仍然是一个重要模式，即使文档结构已经迁移到了 `SDKs` 和 `Apps`。

## 什么时候适合嵌入

当有价值的状态本来就存在于某个运行时内部时，最适合直接嵌入 MDP client，例如：

- 移动端应用进程
- 桌面应用进程
- 后端 worker
- IDE 或浏览器集成

## 运行时检查项

只要一个运行时具备以下能力，就可以嵌入 MDP client：

- 保持连接不断开
- 收发消息
- 关联 request ID
- 调用本地过程

典型例子：

- Android service 或 app 进程
- iOS app 进程
- Qt 或 C++ 桌面应用
- Python worker 或 daemon
- Rust、Go、Java 或 Node 后端

## 推荐起点

- JavaScript 运行时优先看 [JavaScript / 如何使用](/zh-Hans/sdk/javascript/usage)
- 浏览器打包集成优先看 [Chrome 插件](/zh-Hans/apps/chrome-extension)
- IDE 打包集成优先看 [VSCode 插件](/zh-Hans/apps/vscode-extension)
