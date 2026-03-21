# AGENTS.md

This file is for agents working on the VSCode extension app under `apps/vscode-extension`.

## Purpose

This app runs an MDP client inside the VSCode extension host and exposes workspace, editor, prompt, skill, and resource capabilities.

The extension is intentionally split by responsibility. Do not treat `extension.ts` or capability registration as catch-all files.

## Read This App In This Order

1. [README.md](./README.md)
2. [src/extension.ts](./src/extension.ts)
3. [src/extension-controller.ts](./src/extension-controller.ts)
4. [src/extension-client.ts](./src/extension-client.ts)
5. [src/extension-ui.ts](./src/extension-ui.ts)
6. [src/capabilities/index.ts](./src/capabilities/index.ts)
7. [src/capabilities/shared.ts](./src/capabilities/shared.ts)
8. [src/capabilities/workspace-tools.ts](./src/capabilities/workspace-tools.ts)
9. [src/capabilities/review.ts](./src/capabilities/review.ts)
10. [src/capabilities/resources.ts](./src/capabilities/resources.ts)
11. [src/config.ts](./src/config.ts)
12. [src/model.ts](./src/model.ts)
13. [test/capabilities.test.ts](./test/capabilities.test.ts)

## Module Boundaries

Keep these boundaries intact:

- `src/extension.ts`
  activation and VSCode subscription wiring only
- `src/extension-controller.ts`
  connection lifecycle, reconnect behavior, and controller state
- `src/extension-client.ts`
  MDP client construction and client identity metadata
- `src/extension-ui.ts`
  status bar text, tooltip content, and human-readable status messages
- `src/capabilities/index.ts`
  top-level capability registration only
- `src/capabilities/shared.ts`
  reusable snapshot, diagnostics, and argument parsing helpers
- `src/capabilities/workspace-tools.ts`
  workspace/file/search/command tools
- `src/capabilities/review.ts`
  prompt and skill registration
- `src/capabilities/resources.ts`
  resource registration

If you add a new VSCode capability, place it in the closest focused module. Do not append unrelated helpers to a large file because it is already imported.

## Change Strategy

When editing this app:

1. preserve the current capability names and payload shapes unless the feature explicitly requires a protocol change
2. prefer extracting helpers before adding branches to an already-large module
3. update capability tests when tool behavior changes
4. update `README.md` and docs pages when exposed capabilities or local workflow change

## Validation

Use the app-scoped commands first:

```bash
pnpm --filter @modeldriveprotocol/vscode-extension typecheck
pnpm --filter @modeldriveprotocol/vscode-extension test
pnpm --filter @modeldriveprotocol/vscode-extension build
pnpm --filter @modeldriveprotocol/vscode-extension package:vsix
```

When docs are touched, also run:

```bash
pnpm docs:build
```

Remove generated `dist/**` artifacts from this app after validation if they are not part of the requested change.

## Release Notes

- `.github/workflows/vscode-extension-ci.yml`
  builds, tests, and uploads a VSIX artifact for this app
- `.github/workflows/vscode-extension-release.yml`
  runs on `vscode-extension-v*` tags and publishes the VSIX to the VS Code Marketplace
- `VSCODE_EXTENSION_PUBLISHER`
  repository variable used to stamp the release manifest with the real publisher id
- `VSCE_PAT`
  Marketplace token secret used by `vsce publish`
