---
layout: home

hero:
  name: "MDP"
  text: "Model Drive Protocol"
  tagline: "The ultimate solution for connecting models with everything."
  actions:
    - theme: brand
      text: "Quick Start"
      link: /guide/quick-start
    - theme: alt
      text: "JavaScript SDK"
      link: /sdk/javascript/quick-start
    - theme: alt
      text: "Playground"
      link: /playground/

features:
  - title: "One Bridge Surface"
    details: "Hosts integrate with one stable MCP bridge instead of regenerating MCP tools whenever clients connect or disconnect."
  - title: "Runtime-Owned Capabilities"
    details: "Clients remain the source of truth for tools, prompts, skills, and resources. The server indexes and routes, but does not own business logic."
  - title: "Ready for Real Runtimes"
    details: "Use the JavaScript SDK for custom runtimes, or start from the packaged Chrome and VSCode integrations already included in the repo."
---

## What this is

MDP is a language-neutral protocol for exposing internal procedures to AI. It is designed for environments where the procedure lives inside a runtime, device, or process that should not be rebuilt as a standalone service.

## Pick A Path

- Use [Quick Start](/guide/quick-start) if you want the shortest path from zero to a working client plus MCP bridge.
- Use [Server / Tools](/server/tools) and [Server / APIs](/server/api) if you already understand the model and need exact tool or transport formats.
- Use [JavaScript SDK / Quick Start](/sdk/javascript/quick-start) if you want to embed MDP into a browser page, local process, or custom runtime.
- Use [Chrome Extension](/apps/chrome-extension) or [VSCode Extension](/apps/vscode-extension) if you want a packaged runtime integration instead of wiring the SDK from scratch.
- Use [Playground](/playground/) if you want a docs-native surface for trying connections and inspecting capability behavior.

## Typical Flow

1. Start the MDP server CLI and configure it in your MCP tool.
2. Connect one or more MDP clients over websocket or HTTP loop.
3. Register tools, prompts, skills, and resources from those runtimes.
4. Let your agent discover and call them through the fixed bridge tools.

## Good Fits

- Browser or extension capabilities that should stay inside the user session.
- IDE or editor integrations that need local workspace context.
- App-local or device-local operations that should not be rewritten as standalone services.
- Local agent or backend workflows that need MCP reachability without adding another per-runtime MCP server.
