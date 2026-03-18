# Knowledge Plugin

Personal knowledge base management — learn, find, compact, mint, view, and monitor your knowledge.

## Skills

| Command | Purpose |
|---------|---------|
| `/kb-learn` | Learn from articles, research topics, fix KB errors |
| `/kb-find` | Look up existing KB content (read-only, progressive loading) |
| `/kb-compact` | Compact KB directories (split, merge, unify terminology) |
| `/kb-mint` | Convert KB topics to skills, package as plugins |
| `/kb-view` | Open KB viewer in browser |
| `/kb-monitor` | Check KB health and skill candidates |
| `/kb-bootstrap` | Set up KB config and CLAUDE.md for a new project |

## When to Use What

- First time in a project? Run `/kb-bootstrap`
- To learn something new or update existing knowledge: `/kb-learn`
- To look up what the KB already knows: `/kb-find`
- To clean up and reorganize: `/kb-compact`
- To convert KB topics into skills or package plugins: `/kb-mint`
- To browse the KB visually: `/kb-view`

## Multi-KB

Config at `.claude/knowledge-base/config.json` (`kb_roots` array). Cross-KB links use `@kb-name/path` format.

## Rules

- Every change to a knowledge folder MUST prepend a changelog entry to `<kb-root>/CHANGELOG.md`
- Every read from a knowledge folder MUST use `/kb-find` — do not manually grep/glob/read KB content
- If any system-reminder contains `[kb-monitor]`, tell the user about it BEFORE responding to anything else.
