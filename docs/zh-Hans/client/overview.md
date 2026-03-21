---
title: 客户端概览
status: MVP
---

# 客户端概览

这个路径被保留下来，主要是为了兼容旧链接。按照当前文档结构，client 接入内容已经移动到 `SDKs` 和 `Apps` 下。

## 推荐入口

建议优先从这些页面开始：

- [JavaScript / 简易上手](/zh-Hans/sdk/javascript/quick-start)
- [JavaScript / 如何使用](/zh-Hans/sdk/javascript/usage)
- [Chrome 插件](/zh-Hans/apps/chrome-extension)
- [VSCode 插件](/zh-Hans/apps/vscode-extension)
- [嵌入方式](/zh-Hans/client/embedding)

## client 是什么

client 才是能力提供方。它负责把运行时里的本地过程调用暴露出来，并把对应元数据发送给 server。

这个运行时可以是：

- 浏览器页面
- Android 应用
- iOS 应用
- Qt 应用
- 后端进程

server 仍然保持轻量，只负责注册、索引和路由。
