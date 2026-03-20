---
title: Transport
status: MVP
---

# Transport

The protocol stays transport-agnostic. The current reference implementation ships two MDP-side transports:

- `ws` / `wss` for direct bidirectional sessions
- `http` / `https` loop mode for runtimes that prefer request/response polling

Transport auth is independent from the message set. In the reference server it can arrive:

- directly in `Authorization`, `Cookie`, or `x-mdp-auth-*` headers
- through `POST /mdp/auth`, which issues an auth cookie that the browser can carry into a later `ws` / `wss` upgrade

Both transports preserve the same message model:

- `registerClient`
- `unregisterClient`
- `callClient`
- `callClientResult`
- `ping`
- `pong`

That means registry, routing, and MCP bridge logic stay unchanged when the transport changes.
