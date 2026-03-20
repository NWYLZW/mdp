---
title: API
status: Draft
---

# API

服务端 API 应该保持收敛：

- register client
- unregister client
- 列出 client registry
- 查询 capability indexes
- 路由 `callClient`

内部实现可以拆成 registry、capability index 和 invocation router，但对外 surface 应保持稳定。
