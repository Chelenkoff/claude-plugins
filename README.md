# claude-plugins

A personal Claude Code plugin marketplace.

## Add this marketplace

```bash
/plugin marketplace add Chelenkoff/claude-plugins
```

## Available plugins

| Plugin | What it does |
|---|---|
| [`cpp-poco-class-gen`](https://github.com/Chelenkoff/cpp-poco-class-gen) | Generates a C++11 getter/setter class (`.h` + `.cpp`) from a class name and a list of `name:type` members — e.g. `Person name:string age:int`. Members are named `m_<prefix><PascalCase>` (`m_sName`, `m_nAge`, `m_fScore`, `m_bActive`, `m_pOwner`, ...); scalars/pointers pass by value, everything else by `const&`. See that repo's own README for the full naming table and examples. |

## Install a plugin from here

```bash
/plugin install cpp-poco-class-gen@chelenkoff-plugins
```

(`chelenkoff-plugins` is this marketplace's internal name, set in `.claude-plugin/marketplace.json` —
that's what goes after the `@`, not the repo name.)

## Adding a new plugin to this marketplace

1. Publish the plugin as its own repo (with `.claude-plugin/plugin.json` at its root).
2. Add an entry to `.claude-plugin/marketplace.json`:
   ```json
   {
     "name": "<plugin-name>",
     "source": { "source": "github", "repo": "Chelenkoff/<plugin-repo>" },
     "description": "<one line>"
   }
   ```
3. Add a row to the table above.
4. Commit and push — anyone who's already added this marketplace picks up the new plugin on their next
   `/plugin marketplace update` (or by re-adding).
