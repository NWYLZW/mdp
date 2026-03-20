---
title: 嵌入方式
status: Draft
---

# 嵌入方式

只要一个运行时具备以下能力，就可以嵌入 MDP client：

- 保持连接不断开
- 收发消息
- 关联 request ID
- 调用本地过程

典型例子：

- Android service 或 app 进程
- iOS app 进程
- Qt 或 C++ 桌面应用
- Python worker 或 daemon
- Rust、Go、Java 或 Node 后端
