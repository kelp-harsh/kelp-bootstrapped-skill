# Kelp for Claude

A plugin marketplace with one plugin, `kelp`: the Kelp connector and a small bootstrap skill that has
Claude fetch Kelp's base skill through the connector before its first Kelp tool call. The guidance itself
is published by Kelp and served to signed-in users; nothing in this repository describes Kelp's
tools or data.

## Install

1. In Claude, open Settings → Plugins → Add plugins → GitHub and add this repository. Turn on
   **Sync automatically**.
2. Install `kelp`. Every member signs in to Kelp with their own account the first time the
   connector is used.
3. Make sure the Kelp host named in `kelp/.mcp.json` is on the workspace's sandbox network allow
   list.

A version bump merged to `main` reaches every member on its own.
