# Knowledge Plugin for Claude

**Your second brain, inside Claude.** Learn from articles, research topics, organize what you know, and let Claude remember it all — across every conversation.

## What it does

Seven skills that turn Claude into a knowledge management system:

| Skill | What it does |
|-------|-------------|
| `/kb-learn` | Learn from articles, research topics, fix errors in your KB |
| `/kb-find` | Look up what you already know (read-only, token-efficient) |
| `/kb-compact` | Clean up — split oversized notes, unify terminology, fix indexes |
| `/kb-mint` | Convert KB topics into skills, package as plugins |
| `/kb-view` | Browse your KB in a local web viewer with search and graph |
| `/kb-monitor` | Track what you read most, surface skill candidates |
| `/kb-bootstrap` | First-time setup — run once per project |

## Install

### From marketplace

```bash
# Add the marketplace
/plugin marketplace add farzadshbfn/knowledge-plugin

# Install the plugin
/plugin install kb@farzadshbfn
```

### Standalone

```bash
claude --plugin-dir /path/to/knowledge-plugin
```

### First run

After installing, run `/kb-bootstrap` in your project. It creates the config and directory structure for your knowledge base.

## How it works

You build a personal knowledge base in markdown. The plugin manages it:

- **Learn something** — `/kb-learn article <url>` extracts claims, compares against your KB, and adds what's new
- **Research a topic** — `/kb-learn topic "distributed consensus"` searches the web, assesses your current knowledge level, and fills the gaps
- **Fix an error** — `/kb-learn fix "actually X works like Y"` finds and corrects mistakes
- **Find what you know** — `/kb-find "how does X work"` progressively loads just enough context (not your whole KB)
- **Keep it clean** — `/kb-compact` reorganizes as your KB grows

Everything stays in markdown files you own. No lock-in, no external services.

## Multi-KB support

Run multiple knowledge bases in one project:

```json
// .claude/knowledge-base/config.json
{
  "kb_roots": [
    { "name": "core", "path": "./knowledge" },
    { "name": "ios", "path": "./ios/knowledge" }
  ]
}
```

Cross-reference with `@kb-name/path` links.

## Want the skills without the plugin?

If you prefer KB-backed skills (symlinked from your own knowledge base) instead of a plugin install, check out [knowledge-skills](https://github.com/farzadshbfn/knowledge-skills) for the source skill structure.

## License

MIT
