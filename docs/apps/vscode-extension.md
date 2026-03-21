---
title: VSCode Extension
status: Draft
---

# VSCode Extension

VSCode is a good MDP host runtime when the capability depends on workspace state, editor selection, diagnostics, or extension-owned commands.

## Good capability shapes

Typical examples include:

- reading the active file or selection as a resource
- exposing extension commands as tools
- packaging review or refactor flows as skills

## Recommended topology

Run the MDP client inside the extension host process and expose capabilities from the extension boundary, not from a separate remote service.

That keeps:

- editor state local
- capability metadata explicit
- MCP integration stable through the MDP server

## Current repo status

This repository now includes a dedicated VSCode extension app under `apps/vscode-extension`.

The app runs the MDP client inside the extension host and currently exposes:

- `vscode.getWorkspaceContext`
- `vscode.findWorkspaceFiles`
- `vscode.readWorkspaceFile`
- `vscode.searchWorkspaceText`
- `vscode.getDiagnostics`
- `vscode.executeCommand` with an allowlist
- `vscode.reviewSelection` as a prompt
- `vscode.reviewActiveEditor` as a skill
- active document, selection, and workspace folder resources

Use it as the default starting point when you want a VSCode runtime to register capabilities with the MDP server.

## Configuration

The extension contributes `mdp.*` settings for the main integration points:

- `mdp.serverUrl`
- `mdp.autoConnect`
- `mdp.autoReconnect`
- `mdp.reconnectDelayMs`
- `mdp.clientId`
- `mdp.clientName`
- `mdp.authToken`
- `mdp.allowedCommands`
- `mdp.findFilesMaxResults`
- `mdp.textSearchMaxResults`
- `mdp.resourceTextLimit`
- `mdp.diagnosticResultLimit`

## Build

Build the extension with:

```bash
pnpm --filter @modeldriveprotocol/vscode-extension build
```

The extension entry point is emitted to `apps/vscode-extension/dist/extension.js`.

- [JavaScript Quick Start](/sdk/javascript/quick-start)
- [MCP Definitions](/sdk/javascript/mcp-definitions)
- [Skills Definitions](/sdk/javascript/skills-definitions)
