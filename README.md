# AI Agent Methodologies

> Real-world debugging & engineering lessons from production failures.

[简体中文](./README.zh.md)

## What is this

A collection of debugging and engineering methodologies designed for AI coding assistants (Claude Code, Cursor, Hermes Agent, etc.). Each methodology includes:

- **Principle** — core idea
- **Checklist** — actionable steps
- **Anti-pattern** — real failure case
- **When to use** — applicable scenarios

## Methodologies

| Methodology | Core Idea | Source |
|-------------|-----------|--------|
| [Constraint-First Debugging](./skills/constraint-first-debugging/) | Verify platform/API constraints before writing code | WeChat voice bubble failure |

## Install

### Claude Code

Drop `CLAUDE.md` into your project root:

```bash
curl -o CLAUDE.md https://raw.githubusercontent.com/ryan-flow/ai-agent-methodologies/main/CLAUDE.md
```

### Hermes Agent

```bash
hermes skill install ryan-flow/ai-agent-methodologies
```

### Cursor

Copy `.cursor/rules/methodologies.mdc` to your project's `.cursor/rules/` directory.

### Manual

Each methodology under `skills/` is a standalone Markdown file — copy it anywhere.

## Contributing

Hit a new bug? PRs welcome! Format:

1. Create a new directory under `skills/`
2. Include `SKILL.md` (Hermes format) and `METHODOLOGY.md` (universal format)
3. Add an entry to the methodology table in README

## License

MIT
