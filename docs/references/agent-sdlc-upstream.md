# Upstream documentation index (agent-sdlc)

Pinned starting points for **Cursor**, **Claude Code**, **MCP**, and **GitHub Spec Kit**. Use these to verify product behavior; this kit does not mirror full upstream docs.

| Retrieved | Tool | Primary URL | Kit-relevant focus |
|-----------|------|-------------|-------------------|
| 2026-04-04 | **Cursor** — Project Rules | https://cursor.com/docs/context/rules | Scoped rules (`.mdc`), how agents consume repo context |
| 2026-04-04 | **Cursor** — Slash commands | https://cursor.com/docs/agent/chat/commands | Custom `/` commands under `.cursor/commands/` |
| 2026-04-04 | **Cursor** — Agent Skills | https://cursor.com/docs/context/skills | Project skills under `.cursor/skills/` |
| 2026-04-04 | **Claude Code** — Slash commands | https://code.claude.com/docs/en/slash-commands | Custom commands under `.claude/commands/` |
| 2026-04-04 | **Claude Code** — Hooks | https://code.claude.com/docs/en/hooks-guide | Hook events, matchers, safety; pair with [INSTALL.md](../../INSTALL.md) |
| 2026-04-04 | **Model Context Protocol (MCP)** | https://modelcontextprotocol.io/ | Protocol overview; consumer apps connect MCP servers to agents |
| 2026-04-04 | **GitHub Spec Kit** | https://github.com/github/spec-kit | Spec-first coding workflow (constitution / specs / plans / tasks); analog to this kit’s SDLC layer |

## Workflow analog (Spec Kit vs agent-sdlc)

**GitHub Spec Kit** (upstream) commonly flows: constitution → specify → clarify → plan → tasks → implement. This kit’s **markdown commands** are an **editor-side analog**, not a compatible fork: `/constitution`, `/spec`, `/clarify`, `/plan`, `/tasks`, `/implement`, plus `/eval` for consumer eval rubrics. There is no Spec Kit CLI or codegen in this repository—see [INSTALL.md](../../INSTALL.md) and [specs/README.md](../../specs/README.md).

## Related in-repo docs

- [docs/research-synthesis-and-inventory.md](../research-synthesis-and-inventory.md) — synthesis from local research inputs and mapping to kit areas.
- [docs/CONTRIBUTING.md](../CONTRIBUTING.md) — mirror rule for `.cursor/commands` ↔ `.claude/commands`.

## Maintenance

When refreshing links, update the **Retrieved** column and adjust URLs if upstream paths change. Prefer official domains over third-party summaries.
