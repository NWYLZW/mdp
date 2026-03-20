---
title: 传输
status: MVP
---

# 传输

协议本身应该保持传输无关，但 MVP 当前采用 WebSocket。

这样第一版可以直接获得：

- 双向消息传递
- 请求关联
- 心跳支持
- 浏览器与原生环境的低门槛嵌入

后续可以继续增加其他 transport，而不需要重写 registry 或 router。
