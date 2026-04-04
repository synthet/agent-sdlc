> **Claude Code:** Same intent as Cursor `/plan`. When customizing, keep in sync with `.cursor/commands/plan.md`.

# /plan — Implementation plan

Use after a spec exists (or for small tasks, a verbal agreement). Prefer **plan mode** or explicit user approval before large edits.

## Inputs

- Approved spec or tight task description.
- Relevant files the user pointed at.

## Output

1. **Goal** — What “done” means.
2. **Files / areas to touch** — Paths or components.
3. **Approach** — Steps in order; call out risky changes.
4. **Contracts (when applicable)** — If the **contracts** spec layer applies (tools, APIs, structured I/O), link or list paths to schema stubs or code-owned artifacts (see `templates/tool-contract-stub.md`).
5. **Tests** — What to run or add (map to AGENTS.md commands). For agents, separate **offline eval** from **prod observability** when relevant.
6. **Rollback / flags** — If feature-flagged or migratory. Note: markdown specs and plans support repeatable **human** review; they do **not** by themselves guarantee deterministic **runtime** replay of models or live tools.

## Done when

- Another developer could execute the plan without guessing.
- Test plan matches project conventions.

## Note

If the user has not approved implementation, **do not** apply code changes until they confirm.

## Agent / runtime boundary

Editor-kit work (rules, commands, markdown specs) is **not** a substitute for orchestration or eval runners. If the plan touches **runtime** agents, name where graphs, tool schemas, policy hooks, and eval jobs live—see `.cursor/skills/agent-runtime-handoff/SKILL.md`.
