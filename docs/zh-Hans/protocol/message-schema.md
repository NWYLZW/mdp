---
title: 消息模型
status: MVP
---

# 消息模型

MDP transport 当前需要支持一组很小的消息集合：

- `registerClient`
- `unregisterClient`
- `callClient`
- `callClientResult`
- `ping`
- `pong`

`callClient` 应该包含：

- `requestId`
- `clientId`
- `kind`
- `name` 或 `uri`
- `args`

返回结果应包含：

- `ok`
- `data`
- `error`

```json
{
  "type": "callClient",
  "requestId": "req-123",
  "clientId": "browser-01",
  "kind": "tool",
  "name": "searchDom",
  "args": {
    "query": "MCP"
  }
}
```
