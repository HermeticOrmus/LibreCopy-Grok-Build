# libre-copy-grok

The Grok-native LibreCopy plugin. It carries the skills melted for Grok Build, and only those:

| Skill | Job | Melted from (pack plugin) |
|-------|-----|---------------------------|
| `docs-critique` | Daily critique loop for one page: honesty, first success, runnable examples, severity | `documentation-testing` + `content-strategy` |
| `api-docs` | API narrative: auth, first success, the error they will hit | `api-documentation` |
| `style-guide` | Ten-rule voice; em dashes optional (Diego voice) | `style-guides` |

Install:

```bash
grok plugin marketplace add HermeticOrmus/LibreCopy-Grok-Build
grok plugin install libre-copy-grok@libre-copy-grok --trust
```

The six stub skills are not in this plugin. They live in [stubs/](../../stubs/), and each names the pack plugin that holds the real depth (or says honestly that none covers it one to one). The same marketplace installs those pack plugins.

Manifest: [.grok-plugin/plugin.json](./.grok-plugin/plugin.json). Honest inventory: [docs/DEPTH_MATRIX.md](../../docs/DEPTH_MATRIX.md). The v0 bundle stub this plugin replaces is kept at [stubs/librecopy-core/](../../stubs/librecopy-core/).
