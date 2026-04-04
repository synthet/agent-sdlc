# /tasks — Break a plan into executable tasks

Use after an approved **plan**. Produces an ordered, checkable task list (workflow analog to task breakdown in spec-first kits).

## Inputs

- Approved **plan** (path or pasted).
- **AGENTS.md** for verification commands (lint, test, build).

## Output

1. **Links** — Spec and plan references.
2. **Task table** — ID, task, owner (optional), dependencies, **verification** (command or checklist row).
3. **Kit vs runtime** — If work spans editor markdown and application agents, state who owns graphs, tool schemas, policy, eval jobs, telemetry (see `.cursor/skills/agent-runtime-handoff/SKILL.md`).
4. **Assumptions** — Include: editor specs support repeatable **human** review; they do **not** alone guarantee deterministic **runtime** replay of LLMs or live tools.

## Done when

- Tasks are **ordered** so blocked work is obvious; each task has a clear **done** definition.

## Optional

- Save to `specs/tasks-<slug>.md` or `tasks.md` using `templates/tasks-breakdown.md`.
