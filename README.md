# Yaak API client

A desktop and web API development client with request collections, importers, authentication plugins and template functions.

## Architecture and stack

`apps/` contains the client UI; `packages/` holds shared TypeScript UI and runtime packages; `crates-tauri/` supplies desktop integration; Rust crates implement models, networking, synchronization and server functionality; `plugins/` supplies request importers and authentication.
