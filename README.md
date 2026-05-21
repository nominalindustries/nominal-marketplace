# nominal-marketplace

The Claude plugin catalog for Nominal Industries. It lists the Nominal plugins so they can be installed and updated through the Claude plugin marketplace rather than by downloading zips.

## Plugins

- **spicypowers** - the spicy-brain operating layer: communication style, brain-dump intake, status translation, transitions, thread archetypes, tracking artifacts. No code required.
- **nominalpowers** - the engineering layer: the lead-thread workflow, subagent dispatch, external-validator discipline, staged TDD, and the Nominal Tauri scaffold.

## Adding this marketplace

Add it as a Git source in the Claude client's plugin settings, pointing at this repository. Once added, both plugins can be installed from it, and updates flow through `/plugin update` instead of a fresh download.

## A note on the plugin sources

Each plugin lives in its own repository. The `source` entries in `.claude-plugin/marketplace.json` are full git URLs for that reason. The catalog and the plugins version independently: a plugin can be updated in its own repo without touching this catalog, and this catalog can add or remove plugins without touching them.

## Maintaining the catalog

To add a plugin: add an entry to the `plugins` array in `.claude-plugin/marketplace.json` with its `name`, `description`, full git URL `source`, and `category`. To remove one: delete its entry. Bump the catalog `version` when the list changes.
