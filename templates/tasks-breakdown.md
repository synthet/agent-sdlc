# Tasks: <title or slug>

Derived from an approved **plan**. Use after `/tasks`; convention: `specs/tasks-<slug>.md` or `tasks.md` in the consumer repo.

## Links

- **Spec:**
- **Plan:**

## Task list

| ID | Task | Owner | Depends on | Verification |
|----|------|-------|------------|--------------|
| T1 | | | | |
| T2 | | | | |

## Kit vs runtime (if applicable)

| Item | Owner (editor / app / infra) |
|------|-------------------------------|
| Rules, markdown specs | |
| Tool schemas, graphs, eval jobs | |

## Assumptions and replay

- **Editor specs and checklists** support repeatable **human** review; they do **not** guarantee deterministic **runtime** replay of LLM or live tool calls. Strict replay needs recorded outputs or other consumer-owned infrastructure.

## Rollback

- How to abandon or reorder this task list without blocking the rest of the branch
