---
title: Embedding
status: Draft
---

# Embedding

This path is kept because embedding remains a useful runtime pattern even after the docs IA moved to `SDKs` and `Apps`.

## When embedding is the right choice

Embed an MDP client when you need capabilities to stay inside a runtime that already owns the useful state:

- a mobile app process
- a desktop app process
- a backend worker
- an IDE or browser integration

## Runtime checklist

MDP clients can be embedded in any runtime that can:

- keep a connection open
- send and receive messages
- correlate request IDs
- call local procedures

Examples:

- Android service or app process
- iOS app process
- Qt or C++ desktop application
- Python worker or daemon
- Rust, Go, Java, or Node backend

## Start points

- For JavaScript runtimes, start with [JavaScript Usage](/sdk/javascript/usage).
- For browser packaging, start with [Chrome Extension](/apps/chrome-extension).
- For IDE packaging, start with [VSCode Extension](/apps/vscode-extension).
