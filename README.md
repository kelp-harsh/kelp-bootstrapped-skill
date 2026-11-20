# Kelp for Claude (alpha)

A plugin marketplace with one plugin, `kelp-alpha`: the **Kelp-alpha** connector (Kelp's alpha test
environment) and a small bootstrap skill that has Claude fetch Kelp's base skill through that connector
before its first Kelp tool call. The guidance itself is published by Kelp and served to signed-in
users; nothing in this repository describes Kelp's tools or data.

## Install

1. In Claude, open Settings → Plugins → Add plugins → GitHub and add this repository. Turn on
   **Sync automatically**.
2. Install `kelp-alpha`. Every member signs in to Kelp with their own account the first time the
   Kelp-alpha connector is used.
3. Make sure the Kelp host named in `kelp/.mcp.json` is on the workspace's sandbox network allow
   list.

In Claude Code:

```
/plugin install kelp-alpha --marketplace kelp-harsh/kelp-bootstrapped-skill
```

A version bump merged to `main` reaches every member on its own. Renaming the plugin (from `kelp`
in 1.3.0 to `kelp-alpha` in 1.4.0) installs it as a new plugin: uninstall the old `kelp` plugin so
two copies of the same connector are not loaded side by side.
