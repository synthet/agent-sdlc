---
name: agent-runtime-handoff
description: Clarify what lives in the agent-sdlc editor kit vs what belongs in the application runtime (orchestration, eval, observability, MCP servers).
---

# Agent runtime handoff

## When to use

- User is **adopting agent-sdlc** and asks what to install beyond rules/commands.
- Work spans **specs in-repo** and **production agent code** (graphs, tools, evals, traces).
- Risk of conflating **SDLC markdown** with **executable agent frameworks**.

## Kit vs runtime (short)

| Stays in agent-sdlc (copy/merge) | Lives in the consumer application repo |
|----------------------------------|----------------------------------------|
| `.cursor/rules`, `.cursor/commands`, `.cursor/skills` | Orchestration code (e.g. LangGraph, Agents SDK, vendor frameworks) |
| `.claude/commands` mirror | Tool implementations, JSON Schema, API clients |
| `templates/`, root `AGENTS.md` charter | Policy middleware, guardrails, allowlists |
| `specs/` for human intent and acceptance criteria | Eval datasets, graders, CI eval jobs, online monitors |
| | Observability (OpenTelemetry, LangSmith, Langfuse, etc.) |
| | **MCP servers** as processes the app or IDE attaches to |

This kit **documents** boundaries in [docs/research-synthesis-and-inventory.md](../../../docs/research-synthesis-and-inventory.md) and vocabulary in `.cursor/rules/spec-layers-and-boundaries.mdc`.

## Upstream pointers

- [docs/references/agent-sdlc-upstream.md](../../../docs/references/agent-sdlc-upstream.md) — Cursor, Claude Code, MCP, GitHub Spec Kit.

## Guidance for handoff text

When closing a spec or plan, add a **one-paragraph** note: where runtime code, evals, and telemetry will live, and that rollback is revert PRs / config—not a migration. Avoid prescribing vendor choices unless the user asked.
