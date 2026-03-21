---
title: Native Client
status: Draft
---

# Native Client

This path is kept for compatibility with older links. The current docs structure prefers runtime-specific entry points under `Apps` plus the generic embedding guidance.

## Preferred entry points

- [Embedding](/client/embedding)
- [VSCode Extension](/apps/vscode-extension)
- [JetBrains Plugin](/apps/jetbrains-plugin)

## What this page refers to

A native client can expose internal app APIs without turning them into remote public services.

Good fits:

- Android view and service methods
- iOS app state and actions
- Qt slots or facade methods

The server only sees the protocol metadata and routed invocation result.
