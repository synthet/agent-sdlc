# Contributing to agent-sdlc

This repository is a **documentation and config kit** (Cursor rules, slash commands, Claude mirror, templates). There is no application runtime, package manifest, or CI workflow in-tree yet.

## Validation before a PR

- **Consistency:** If you change a Cursor command under `.cursor/commands/`, update the mirrored file under `.claude/commands/` (each file notes its twin).
- **INSTALL / README:** If adoption steps or paths change, update [INSTALL.md](../INSTALL.md) and [README.md](../README.md).
- **Specs:** Non-trivial behavior or workflow changes should have a short spec under `specs/` (see [specs/README.md](../specs/README.md)).
- **Secrets:** Do not commit credentials, tokens, or real `.env` content.
- **Research / upstream claims:** Prefer citations via [docs/references/agent-sdlc-upstream.md](references/agent-sdlc-upstream.md); broader synthesis lives in [docs/research-synthesis-and-inventory.md](research-synthesis-and-inventory.md). Local deep-research exports under `docs/deep-research-report-*.md` may be gitignored per [.gitignore](../.gitignore).

## Optional tooling

Teams can add `markdownlint`, `prettier`, or other checks later; if you do, document the canonical commands in the root [AGENTS.md](../AGENTS.md) table for agents and humans.
