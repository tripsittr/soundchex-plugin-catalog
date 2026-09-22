# SoundChex Official Plugin Catalog

The curated list of plugins for [SoundChex](https://github.com/tripsittr/SoundChex).

`manifest.json` is a repository the SoundChex admin can add under **Plugins →
Browse plugins**. Point SoundChex at the raw URL:

```
https://raw.githubusercontent.com/tripsittr/soundchex-plugin-catalog/main/manifest.json
```

## How it works

Each entry lists a plugin and its versions. A version's `sourceUrl` is a ZIP the
server downloads and installs; here it is each plugin's GitHub release archive.
SoundChex installs the newest version compatible with the running server, then
the operator enables it.

## Adding your own plugin

You do **not** have to be in this catalog. Host your own `manifest.json` at any
URL and users add that URL as a repository. To propose a plugin for the official
catalog, open a pull request adding it here — it is reviewed before merge.

## Format

```json
[
  {
    "id": "vendor.plugin-id",
    "name": "Plugin Name",
    "description": "...",
    "author": "...",
    "versions": [
      { "version": "1.0.0", "sourceUrl": "https://…/v1.0.0.zip", "targetAbi": "0.1.0", "requiresPhp": "8.2" }
    ]
  }
]
```

Versions are newest-first. `targetAbi` is the minimum SoundChex version.
