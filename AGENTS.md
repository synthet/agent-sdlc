# AGENTS.md

## Maintainer charter (this repository: agent-sdlc)

Coding agents should read this section first when working **inside** `agent-sdlc`. The consumer template below is for repositories that **adopt** this kit.

### Project

- **Name:** agent-sdlc
- **Purpose:** Reusable spec-driven SDLC artifacts for Cursor and Claude Code: rules, slash commands, optional hooks, project skills, and templates. Consumer repos copy or merge these files per [INSTALL.md](INSTALL.md).

### Stack

- **Languages:** Markdown; rule front matter in `.mdc` files
- **Package manager / runtime:** None (this repo is not an application)
- **Primary frameworks:** N/A

### Commands

There is no in-repo lint or test runner yet. Before claiming work complete, follow [docs/CONTRIBUTING.md](docs/CONTRIBUTING.md) and verify mirrored `.cursor/commands` ↔ `.claude/commands` edits when applicable.

| Action | Command |
|--------|---------|
| Install deps | N/A |
| Lint | N/A (add tooling in a dedicated change if needed) |
| Typecheck | N/A |
| Unit tests | N/A |
| Integration / E2E | N/A |
| Build | N/A |

### Layout

- **Source:** `.cursor/`, `.claude/`, `templates/`, `docs/`, `specs/`, `.github/`
- **Tests:** N/A
- **Specs / ADRs:** `specs/` (see [specs/README.md](specs/README.md))

### Boundaries

- **Do not** change without explicit instruction: licensing file ([LICENSE](LICENSE)), documented upstream remote in [README.md](README.md)
- **Secrets:** never commit; use env / secret manager named: N/A for this repo

### SDLC expectations

- Prefer **small, reviewable** changes; match existing style and patterns.
- For non-trivial kit changes, use a short spec under `specs/` and slash commands (`/spec`, `/plan`, `/implement`, etc.) when helpful.

### Links

- Contributing: [docs/CONTRIBUTING.md](docs/CONTRIBUTING.md)
- CI: none in-tree
- Issue tracker: upstream repository listed in [README.md](README.md)

---

## Agent charter (template)

Copy the following into a **consumer** repository root and fill in the placeholders. Coding agents (Cursor, Claude Code, Copilot, etc.) should treat that file as the **source of truth** for how to work in that repo.

### Project

- **Name:**
- **Purpose (one paragraph):**

### Stack

- **Languages:**
- **Package manager / runtime:** (e.g. npm, pnpm, uv, pip, .NET)
- **Primary frameworks:**

### Commands

Document the **canonical** commands agents must use (adjust to your project):

| Action | Command |
|--------|---------|
| Install deps | |
| Lint | |
| Typecheck | |
| Unit tests | |
| Integration / E2E | |
| Build | |

### Layout

- **Source:** (e.g. `src/`, `apps/`, `lib/`)
- **Tests:** (e.g. `tests/`, `__tests__/`)
- **Specs / ADRs:** (e.g. `docs/specs/`, `specs/`)

### Boundaries

- **Do not** change without explicit instruction: (e.g. public API, DB migrations, legal copy)
- **Secrets:** never commit; use env / secret manager named:

### SDLC expectations

- Prefer **small, reviewable** changes; match existing style and patterns.
- Run **lint and tests** before declaring work done (use commands above).
- For non-trivial work: produce a short **spec or plan** before large refactors.
- Use slash commands from **agent-sdlc** (`/spec`, `/plan`, `/implement`, etc.) when helpful.

### Links

- Contributing:
- CI:
- Issue tracker:
