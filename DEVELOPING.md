# Developing

This guide is for contributors and maintainers working on the repository itself.

## Local Workflow

Install dependencies and use the repo-level commands from the project root:

```bash
pnpm install
pnpm test:unit
pnpm build
pnpm test
pnpm docs:build
```

These commands match the validation flow described in [AGENTS.md](./AGENTS.md).

## Release Workflow

Package publishing is handled by GitHub Actions plus Changesets.

1. Run `pnpm changeset` for any change that should ship in `@modeldriveprotocol/*`.
2. Commit the generated `.changeset/*.md` file together with the code change.
3. Merge the pull request into `main`.
4. On the release commit, run `pnpm version-packages` and commit the version and changelog updates.
5. Create and push a release tag that points at that versioned commit, for example `v0.1.1`.
6. The `Release` workflow runs only for matching tag pushes and publishes any unpublished package versions to npm.

Useful commands:

```bash
pnpm changeset
pnpm version-packages
pnpm publish:packages
pnpm release
```

- `pnpm changeset` creates a release note for the affected packages.
- `pnpm version-packages` applies all pending changesets locally.
- `pnpm publish:packages` publishes versions that are not yet on npm.
- `pnpm release` builds and then publishes, which is useful for dry runs against a private registry.

## GitHub Actions

- [`.github/workflows/ci.yml`](./.github/workflows/ci.yml) runs build, tests, and docs validation on pull requests and pushes to `main`.
- [`.github/workflows/release.yml`](./.github/workflows/release.yml) runs only when a `v*` tag is pushed and publishes the unpublished package versions from that tagged commit.

## Maintainer Setup

Before the first publish:

1. Create an npm automation token with publish access to the `@modeldriveprotocol` scope.
2. Add the token to the GitHub repository as `NPM_TOKEN`.
3. Protect `main` so only reviewed, green builds can be merged.

The package manifests are configured for public scoped publishing and npm provenance, so the release workflow publishes public packages and emits provenance attestations.
