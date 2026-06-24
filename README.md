# mitchell-ee-claude-plugins

A [Claude Code plugin marketplace](https://code.claude.com/docs/en/plugin-marketplaces) — a catalog of plugins maintained by Mike Mitchell for Equal Experts.

This repo contains **no plugin code**. It is purely a catalog: `.claude-plugin/marketplace.json` points at each plugin's own GitHub repository. When you install a plugin, Claude Code fetches it directly from its source repo.

## Install a plugin

Add this marketplace once:

```
/plugin marketplace add mitchell-ee/mitchell-ee-claude-plugins
```

Then install any plugin from it:

```
/plugin install <plugin-name>@mitchell-ee-claude-plugins
```

## Plugins in this catalog

| Plugin | Description | Source |
| --- | --- | --- |
| `vcw` | Visual Collaboration with AI — skills and agents for LLM-assisted, human-led visual collaboration in product management (opportunity trees, assumption maps, story maps, prototypes). | [mitchell-ee/visual-collab-workflow](https://github.com/mitchell-ee/visual-collab-workflow) |

Install `vcw`:

```
/plugin marketplace add mitchell-ee/mitchell-ee-claude-plugins
/plugin install vcw@mitchell-ee-claude-plugins
```

## Adding a new plugin to the catalog

1. Create or publish the plugin in its **own** GitHub repo (with a valid `.claude-plugin/plugin.json`).
2. Add an entry to the `plugins` array in `.claude-plugin/marketplace.json`, pointing at that repo:

   ```json
   {
     "name": "my-plugin",
     "source": { "source": "github", "repo": "mitchell-ee/my-plugin-repo" },
     "description": "What it does."
   }
   ```
3. Commit and push. Users re-run `/plugin marketplace update mitchell-ee-claude-plugins` to pick up the change.
