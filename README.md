# Tauri Plugin Persisted Scope
![Test](https://github.com/tauri-apps/tauri-plugin-persisted-scope/workflows/Test/badge.svg)

This plugin provides a Tauri Plugin that saves the filesystem and asset scopes and restores it when the app is reopened.

## Installation
There are three general methods of installation that we can recommend.
1. Pull sources directly from Github using git tags / revision hashes (most secure, good for developement, shown below)
2. Git submodule install this repo in your tauri project and then use `file` protocol to ingest the source
3. Use crates.io and npm (easiest, and requires you to trust that our publishing pipeline worked)

For more details and usage see [the vanilla demo](examples/vanilla/src-tauri/src/main.rs).
Please note, below in the dependencies you can also lock to a revision/tag in the `Cargo.toml`.

`src-tauri/Cargo.toml`
```yaml
[dependencies.tauri]
git = "https://github.com/tauri-apps/tauri/"
branch = "next"
features = ["api-all"]

[dependencies.tauri-plugin-persisted-scope]
git = "https://github.com/tauri-apps/tauri-plugin-persisted-scope"
tag = "tauri-plugin-persisted-scope-v0.1.0"
#branch = "main"
```

Use in `src-tauri/src/main.rs`:
```rust
fn main() {
    tauri::Builder::default()
        .plugin(tauri_plugin_persisted_scope::init())
        .run();
}
```

# License
MIT / Apache-2.0
