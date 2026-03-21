---
title: Client Overview
status: MVP
---

# Client Overview

This path is kept for compatibility with older links. In the current docs structure, client integration content is organized under `SDKs` and `Apps`.

## Preferred entry points

Start here instead:

- [JavaScript Quick Start](/sdk/javascript/quick-start)
- [JavaScript Usage](/sdk/javascript/usage)
- [Chrome Extension](/apps/chrome-extension)
- [VSCode Extension](/apps/vscode-extension)
- [Embedding](/client/embedding)

## What a client is

The client is the capability provider. It exposes local procedures from a runtime and sends their metadata to the server.

That runtime can be:

- a browser page
- an Android app
- an iOS app
- a Qt app
- a backend process

The server remains thin. It stores descriptors, maintains registration state, and routes invocations.
