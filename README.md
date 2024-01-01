# Yaak API client

A desktop and web API development client with request collections, importers, authentication plugins and template functions.

## Architecture and stack

`apps/` contains the client UI; `packages/` holds shared TypeScript UI and runtime packages; `crates-tauri/` supplies desktop integration; Rust crates implement models, networking, synchronization and server functionality; `plugins/` supplies request importers and authentication.

## Requirements

Node from `.node-version`, npm, Rust/Cargo and Tauri platform build prerequisites. Native build dependencies vary by OS.

## Installation and local development

The root manifest defines the bootstrap and client entry points:

```sh
npm run init
npm start
```

`init` installs dependencies and runs bootstrap tasks, which can download vendor tools. Review those scripts before running on a restricted network.

## Configuration

Application credentials are configured in the client and authentication plugins; do not commit exported collections containing tokens. Native bundle configuration lives in `crates-tauri/`.

## Testing

`npm test` runs available workspace tests. `npm run lint:workspaces` checks workspaces. Rust tests require Cargo and platform dependencies; select a crate with `cargo test -p <crate-name>` using its manifest name.

## Deployment and integrations

`npm run client:bundle` builds the desktop client; `npm run web:build` builds the web variant. These are different targets with different runtime requirements. Request importer and authentication packages provide integration examples.

## Source provenance and license

This repository imports source from [mountain-loop/yaak](https://github.com/mountain-loop/yaak). Original product functionality belongs to its upstream contributors. The local history begins with a November 2026 source snapshot; it does not retain upstream development history or prove the exact upstream revision. GitHub reports the upstream repository was created on 2023-02-16; that is repository-origin evidence, not the date of this contribution. Existing year folders are retained as local organization.

Preserve `LICENSE` and existing third-party notices when redistributing. Missing root license text was recovered from the upstream repository during this maintenance pass; existing license files were preserved.

## Validation status

Setup and test commands above were checked against this checkout’s manifests, scripts and entry points. Full dependency installation, application builds and integration tests were not performed in this maintenance pass. The npm workspace dependencies, Rust toolchain and platform-specific Tauri build prerequisites were not provisioned. These instructions identify the supported workflow without claiming a successful product build.

See [source provenance](SOURCE_PROVENANCE.md) for pinned upstream license retrieval evidence and redistribution limitations.
