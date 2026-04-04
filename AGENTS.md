# Agent charter (template)

Copy this file into a **consumer** repository root and fill in the placeholders. Coding agents (Cursor, Claude Code, Copilot, etc.) should treat this as the **source of truth** for how to work in that repo.

## Project

- **Name:**
- **Purpose (one paragraph):**

## Stack

- **Languages:**
- **Package manager / runtime:** (e.g. npm, pnpm, uv, pip, .NET)
- **Primary frameworks:**

## Commands

Document the **canonical** commands agents must use (adjust to your project):

| Action | Command |
|--------|---------|
| Install deps | |
| Lint | |
| Typecheck | |
| Unit tests | |
| Integration / E2E | |
| Build | |

## Layout

- **Source:** (e.g. `src/`, `apps/`, `lib/`)
- **Tests:** (e.g. `tests/`, `__tests__/`)
- **Specs / ADRs:** (e.g. `docs/specs/`, `specs/`)

## Boundaries

- **Do not** change without explicit instruction: (e.g. public API, DB migrations, legal copy)
- **Secrets:** never commit; use env / secret manager named: 

## SDLC expectations

- Prefer **small, reviewable** changes; match existing style and patterns.
- Run **lint and tests** before declaring work done (use commands above).
- For non-trivial work: produce a short **spec or plan** before large refactors.
- Use slash commands from **agent-sdlc** (`/spec`, `/plan`, `/implement`, etc.) when helpful.

## Links

- Contributing: 
- CI: 
- Issue tracker: 
