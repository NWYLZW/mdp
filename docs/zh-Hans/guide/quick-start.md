---
title: 快速开始
status: MVP
---

# 快速开始

从零到一跑通最短路径是：

1. 构建整个 workspace。
2. 启动 TypeScript MDP server。
3. 启动一个 client 进程。
4. 注册一个 tool、prompt、skill 和 resource。
5. 连接一个 MCP host，并调用 bridge tools。

```bash
pnpm install
pnpm build
node packages/server/dist/cli.js --port 7070
```

如果先走浏览器路径，可以直接加载生成好的 bundle：

```html
<script src="/assets/modeldriveprotocol-client.global.js"></script>
```

然后创建并注册一个 client：

```html
<script>
  const client = MDP.createMdpClient({
    serverUrl: "ws://127.0.0.1:7070",
    client: {
      id: "browser-01",
      name: "Browser Client"
    }
  });

  await client.connect();
  client.register();
</script>
```

MVP 当前仍然建议这条路径：

1. 启动 TypeScript MDP server。
2. 启动一个 client 进程。
3. 注册一个 tool、prompt、skill 和 resource。
4. 连接一个 MCP host，并调用 bridge tools。

第一版使用 WebSocket 传输和内存 registry。这样可以先把协议形状跑通，同时保持实现足够简单。
