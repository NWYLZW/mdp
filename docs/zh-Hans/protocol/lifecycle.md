---
title: 生命周期
status: MVP
---

# 生命周期

Client 生命周期：

1. connect
2. register
3. 暴露能力
4. 处理路由调用
5. heartbeat
6. unregister 或 disconnect

Server 生命周期：

1. 接收 transport 连接
2. 存储 client session
3. 索引 capabilities
4. 路由请求
5. 在 timeout 或 disconnect 时清理状态
