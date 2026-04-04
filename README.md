# agent-sdlc

Reusable **spec-driven SDLC** artifacts for **Cursor** and **Claude Code**: rules, slash commands, optional hooks, and project skills. Consumer repos copy or merge these files and maintain a root **`AGENTS.md`** charter.

## Contents

| Path | Purpose |
|------|---------|
| [AGENTS.md](AGENTS.md) | Template charter for any repo |
| [INSTALL.md](INSTALL.md) | How to adopt this kit in another project |
| [docs/CONTRIBUTING.md](docs/CONTRIBUTING.md) | Maintainer notes for this repo |
| [docs/references/agent-sdlc-upstream.md](docs/references/agent-sdlc-upstream.md) | Pinned upstream doc index (Cursor, Claude Code, MCP, Spec Kit) |
| [docs/research-synthesis-and-inventory.md](docs/research-synthesis-and-inventory.md) | Research synthesis and document inventory |
| [specs/](specs/) | Spec-first examples and layout for kit work |
| `.cursor/rules/` | Cursor Rules (`.mdc`) — guardrails and scoped guidance |
| `.cursor/commands/` | Cursor slash commands (`/constitution`, `/spec`, `/clarify`, `/plan`, `/tasks`, `/eval`, `/implement`, …) |
| `.cursor/skills/` | Project-local Agent Skills |
| `.cursor/hooks.json.example` | Optional Cursor hooks (beta); copy with care |
| `.claude/commands/` | Claude Code slash commands (mirrors Cursor) |
| `.claude/settings.json.example` | Claude Code hooks/settings template |
| `templates/` | PR template, issue/spec skeletons (copy into `.github/` or `specs/` as needed) |

## Philosophy

- **Rules** constrain (short, scoped).
- **Commands** orchestrate repeatable rituals.
- **Skills** teach deeper procedures when relevant.
- **Hooks** automate only what is fast, safe, and tested on your OS.

Avoid duplicating the same text in rules, skills, and commands; link to **AGENTS.md** instead.

## Cursor hooks (beta)

Cursor hooks are experimental and **OS-specific**. See [INSTALL.md](INSTALL.md) before enabling.

1. Copy [`.cursor/hooks.json.example`](.cursor/hooks.json.example) to `.cursor/hooks.json`.
2. Replace the placeholder `command` with a **fast**, non-interactive script (test on Windows/macOS/Linux as needed).
3. Available hook names depend on your Cursor version; check current docs under **Hooks** on [cursor.com/docs](https://cursor.com/docs).

If unsure, **skip hooks** until you need them.

## Claude Code

Place `.claude/` in the repo root. Custom slash commands live in `.claude/commands/`. Hook shape is documented in [Claude Code hooks](https://code.claude.com/docs/en/hooks-guide); adapt `settings.json.example` for your environment.

## License

MIT — see [LICENSE](LICENSE).

## Remote

Upstream: `git@github.com:synthet/agent-sdlc.git`

After creating the GitHub repo and configuring SSH (or HTTPS), publish with:

```bash
git push -u origin main
```

If `git remote` is missing: `git remote add origin git@github.com:synthet/agent-sdlc.git`
