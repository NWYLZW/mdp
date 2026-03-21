---
layout: home

hero:
  name: "MDP"
  text: "模型驱动协议"
  tagline: "模型与万物建立连接的终极方案"
  actions:
    - theme: brand
      text: "快速使用"
      link: /zh-Hans/guide/quick-start
    - theme: alt
      text: "JavaScript SDK"
      link: /zh-Hans/sdk/javascript/quick-start
    - theme: alt
      text: "Playground"
      link: /zh-Hans/playground/

features:
  - title: "统一 Bridge Surface"
    details: "Host 侧只需要接入一套稳定的 MCP bridge，不需要随着 client 上下线不断重建 MCP tools。"
  - title: "能力归运行时所有"
    details: "tools、prompts、skills、resources 都由 client 注册。server 负责索引和路由，不持有业务逻辑。"
  - title: "可直接落地到真实运行时"
    details: "你可以用 JavaScript SDK 接入自定义运行时，也可以直接从仓库里已有的 Chrome 和 VSCode 集成开始。"
---

## 这是什么

MDP 是一个面向 AI 的语言无关协议，用来暴露运行时内部的过程调用。它适合那些能力本来就存在于某个运行时、设备或进程内，不适合被重写成独立服务的场景。

## 先选一条入口

- 如果你想先用最短路径跑通链路，从 [快速使用](/zh-Hans/guide/quick-start) 开始。
- 如果你已经知道 MDP 要做什么，只想看精确的接口和工具格式，直接看 [Server / Tools](/zh-Hans/server/tools) 和 [Server / APIs](/zh-Hans/server/api)。
- 如果你要把 MDP 接进浏览器页面、本地进程或自定义运行时，优先看 [JavaScript SDK / 简易上手](/zh-Hans/sdk/javascript/quick-start)。
- 如果你不想从零接 SDK，而是想直接从现成集成开始，优先看 [Chrome 插件](/zh-Hans/apps/chrome-extension) 和 [VSCode 插件](/zh-Hans/apps/vscode-extension)。
- 如果你想在文档站里直接试连接和看行为，使用 [Playground](/zh-Hans/playground/)。

## 典型链路

1. 启动 MDP server CLI，并把它配置进你的 MCP 工具。
2. 让一个或多个 MDP client 通过 websocket 或 HTTP loop 连上来。
3. 从这些运行时里注册 tools、prompts、skills、resources。
4. 让 Agent 通过固定的 bridge tools 去发现并调用它们。

## 适合的场景

- 能力存在于浏览器页面或扩展里，必须留在用户会话内。
- 能力依赖 IDE、本地工作区或编辑器状态。
- 能力属于应用本地、设备本地或进程本地，不适合拆成独立服务。
- 你希望本地 agent 或后端流程可被 MCP 访问，但又不想为每个运行时单独做一个 MCP server。
