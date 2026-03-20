---
layout: home

hero:
  name: "MDP"
  text: "模型驱动协议"
  tagline: "通过 client 注册与 MCP bridge tools，把运行时内部过程调用暴露给 AI 的协议。"
  actions:
    - theme: brand
      text: "阅读协议"
      link: /zh-Hans/guide/introduction
    - theme: alt
      text: "构建服务端"
      link: /zh-Hans/server/mvp-design

features:
  - title: "跨运行时"
    details: "Android、iOS、Qt、后端服务和浏览器运行时都可以通过同一套协议暴露能力。"
  - title: "Client 驱动"
    details: "能力由 client 注册，包括 tools、prompts、skills 和 resources。server 只负责索引和路由。"
  - title: "MCP bridge"
    details: "server 保持轻量，对上暴露稳定的 bridge tools，例如 listClients、callTools 和 readResource。"
---

## 这是什么

MDP 是一个面向 AI 的语言无关协议，用来暴露运行时内部的过程调用。它适合那些能力本来就存在于某个运行时、设备或进程内，不适合被重写成独立服务的场景。

## 从这里开始

- 阅读[介绍](/zh-Hans/guide/introduction)了解问题定义。
- 查看[架构](/zh-Hans/guide/architecture)理解 client / server 边界。
- 阅读[消息模型](/zh-Hans/protocol/message-schema)查看线上的消息格式。
- 参考[服务端 MVP](/zh-Hans/server/mvp-design)实现第一版可运行链路。
