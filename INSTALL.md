# Installing agent-sdlc in another project

This kit is designed to be **copied or merged** into a consumer repository. It is **not** a runtime dependency.

## Prerequisites

- **Cursor:** project rules read from `.cursor/rules/`, commands from `.cursor/commands/`, skills from `.cursor/skills/`.
- **Claude Code:** commands from `.claude/commands/`, settings from `.claude/settings.json` (use the example as a starting point).

## Adoption levels

### 1. Drop-in copy (recommended for first use)

1. Copy `.cursor/` and (if you use Claude Code) `.claude/` from this repo into your project root.
2. Copy `templates/` if you want GitHub/issue templates; wire `.github/pull_request_template.md` manually or symlink.
3. Merge [AGENTS.md](AGENTS.md) into your existing `AGENTS.md` (or create one): fill **Commands**, **Layout**, and **Boundaries**.
4. Open the project in Cursor and type `/` in chat to confirm commands appear.

**Merge checklist**

- [ ] Adjust `.cursor/rules/implementation.mdc` **globs** to match your source tree (`src/`, `app/`, etc.).
- [ ] Set real lint/test/build commands in `AGENTS.md`.
- [ ] Remove `.claude/` if you only use Cursor.
- [ ] Do **not** enable `hooks.json` until you read the Hooks section below.

### 2. Submodule or subtree (advanced)

- **Submodule:** add this repo as `vendor/agent-sdlc` and symlink or script-copy `.cursor` and `.claude` into the root. Pros: pin versions by commit. Cons: submodule friction for collaborators.
- **Subtree:** `git subtree add` a tagged release into a path, then copy folders out or script sync.

Document your chosen sync approach in the consumer repo’s `CONTRIBUTING.md`.

### 3. Cherry-pick

- Copy only `.cursor/rules/sdlc-core.mdc` + selected commands.
- Skip Claude folders entirely if unused.

## Cursor vs Claude Code paths

| Feature | Cursor | Claude Code |
|---------|--------|-------------|
| Slash commands | `.cursor/commands/*.md` | `.claude/commands/*.md` |
| Persistent rules | `.cursor/rules/*.mdc` | Use `CLAUDE.md` / project docs + command bodies |
| Hooks | `.cursor/hooks.json` (see example) | `.claude/settings.json` → `hooks` |

Command **bodies** are intentionally parallel in both trees. Each `.claude/commands/*.md` file notes its Cursor twin — **edit both** when you customize workflows so Cursor and Claude Code stay aligned.

## Hooks

### Cursor

1. Copy `hooks.json.example` to `hooks.json` **only** after editing script paths and testing.
2. Hooks are **beta**; behavior may change between Cursor versions.
3. Prefer **no-op or fast** scripts on Windows; avoid bash-only assumptions unless your team standardizes on Git Bash/WSL.

### Claude Code

1. Copy `.claude/settings.json.example` to `.claude/settings.json`.
2. Replace placeholder hook commands with tools that exist on your machine.
3. See official docs for event names and matchers: https://code.claude.com/docs/en/hooks-guide

## Skills

Project skills live under `.cursor/skills/<name>/SKILL.md`. Personal skills can stay in `~/.cursor/skills/`; this kit’s skills are **repo-local** so they version with the consumer project.

## Updating

Re-copy from a **tagged release** of `agent-sdlc` and diff against your customizations. Keep a short `docs/AGENT_SDLC.md` in the consumer repo noting local overrides.

## Support

Issues and improvements: `git@github.com:synthet/agent-sdlc.git`
