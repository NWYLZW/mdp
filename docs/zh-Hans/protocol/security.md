---
title: 安全
status: Draft
---

# 安全

MDP 应该默认假设 client 可能暴露敏感的本地状态。

基础关注点包括：

- client 身份认证
- server 授权
- capability 级别访问控制
- 在不泄露敏感信息的前提下记录请求日志
- timeout 与 disconnect 清理

MVP 可以先保持简单，但协议本身应该为更强的认证与策略层预留空间。
