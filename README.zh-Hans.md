# Model Drive Protocol（模型驱动协议）

| [en-US](./README.md) | zh-Hans |
| --- | --- |

MDP 是一个围绕 MCP 构建的跨运行时能力注册与 RPC 桥接协议。

在这个仓库里，当前 MVP 包括：

- 一个 TypeScript 编写的 MDP server
- 一个使用 TypeScript 编写并产出 JavaScript 的 client SDK
- 一个多语言的 VitePress 文档站
- 一组固定的 MCP bridge tools，而不是为每个 client 动态生成 MCP tools

## MDP 解决什么问题

MDP 让任意运行时都可以通过一个桥接 server，把内部过程调用暴露给 AI。

这个运行时可以是：

- Web
- Android
- iOS
- Qt / C++
- Node.js
- Python / Go / Rust / Java
- 原生设备进程或本地 agent 进程

核心模型是：

- client 提供能力
- MDP server 维护注册与路由
- MDP server 向 MCP host 暴露 bridge tools

MVP 当前支持的能力类型：

- `tools`
- `prompts`
- `skills`
- `resources`

## 工作区结构

```text
packages/
  protocol/  共享的 MDP 消息与模型类型
  server/    TypeScript MDP server + MCP bridge
  client/    TypeScript client SDK，产出 JavaScript
docs/        VitePress 多语言文档站
scripts/     仓库工具脚本与 smoke test
```

## MCP Bridge Tools

MVP server 暴露固定的 MCP tools：

- `listClients`
- `callClients`
- `listTools`
- `callTools`
- `listPrompts`
- `getPrompt`
- `listSkills`
- `callSkills`
- `listResources`
- `readResource`

## 快速开始

安装依赖：

```bash
pnpm install
```

构建整个 workspace：

```bash
pnpm build
```

运行 smoke test：

```bash
pnpm test
```

本地启动文档站：

```bash
pnpm docs:dev
```

构建文档站：

```bash
pnpm docs:build
```

## 文档入口

协议和实现细节请查看文档站：

- [指南](./docs/zh-Hans/guide/introduction.md)
- [协议概览](./docs/zh-Hans/protocol/overview.md)
- [MCP Bridge](./docs/zh-Hans/protocol/mcp-bridge.md)
- [服务端 MVP 设计](./docs/zh-Hans/server/mvp-design.md)
- [JS 客户端](./docs/zh-Hans/client/js-client.md)
- [嵌入其他运行时](./docs/zh-Hans/client/embedding.md)

## MVP 状态

当前 MVP 范围：

- MDP 侧使用 WebSocket 传输
- 基于内存的 client registry
- client capability registration
- 从 MCP bridge tools 路由到已连接 client
- TypeScript client runtime，并产出 JavaScript
- 浏览器全局 bundle，位于 `packages/client/dist/modeldriveprotocol-client.global.js`

当前 MVP 不覆盖：

- 身份认证与权限策略
- 持久化 registry 存储
- 多节点路由
- 非 WebSocket 的 transports
- 除 JavaScript 优先 client 之外的原生 SDK
