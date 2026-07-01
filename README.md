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
| `ee-pm` | EE PM Workflow — skills and agents for AI-assisted, human-led product management across discovery and delivery (interviews, synthesis, opportunity trees, assumption maps, story maps, stories, backlog, prototyping, workshop facilitation). | [mitchell-ee/visual-collab-workflow](https://github.com/mitchell-ee/visual-collab-workflow) |

Install `ee-pm`:

```
/plugin marketplace add mitchell-ee/mitchell-ee-claude-plugins
/plugin install ee-pm@mitchell-ee-claude-plugins
```

## Contributing

This catalog is personally curated and maintained by Mike Mitchell. It is not open to outside contributions — pull requests to add or change plugin entries will not be accepted. If you maintain a plugin you'd like considered for the catalog, feel free to open an issue, but inclusion is at the maintainer's sole discretion.

---

<details>
<summary>Maintainer notes</summary>

To add a new plugin to the catalog:

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

</details>
