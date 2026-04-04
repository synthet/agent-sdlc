# Research synthesis and document inventory

This file satisfies the **document inventory** and **research synthesis** goals from [specs/research-driven-framework-enrichment.md](../specs/research-driven-framework-enrichment.md). It is maintained for **traceability**; it does not replace upstream product documentation (see [references/agent-sdlc-upstream.md](./references/agent-sdlc-upstream.md)).

## 1. Document inventory

### Inputs

| Input | Location / access | Role |
|--------|-------------------|------|
| Deep research export (themes: SDD for agents, scorecards, lifecycle) | `docs/deep-research-report-3.md` | **Local.** Listed in [.gitignore](../.gitignore); obtain from maintainer or internal export if missing. |
| Deep research export (overlap with report 3) | `docs/deep-research-report-4.md` | **Local.** Same as above. |
| Kit spec for this effort | [specs/research-driven-framework-enrichment.md](../specs/research-driven-framework-enrichment.md) | Acceptance criteria and implementation plan. |
| Specs layout | [specs/README.md](../specs/README.md), [templates/spec-feature.md](../templates/spec-feature.md) | Pilot layout for consumer repos. |
| Adoption docs | [INSTALL.md](../INSTALL.md), [AGENTS.md](../AGENTS.md), [README.md](../README.md) | Boundaries and copy/merge flow. |
| Commands (Cursor + Claude) | `.cursor/commands/`, `.claude/commands/` | Rituals: `/constitution`, `/spec`, `/clarify`, `/plan`, `/tasks`, `/eval`, `/implement`, etc. |
| Rules | `.cursor/rules/*.mdc` | Scoped guardrails. |
| Upstream URL index | [docs/references/agent-sdlc-upstream.md](./references/agent-sdlc-upstream.md) | Verifiable pointers to Cursor, Claude Code, MCP, Spec Kit. |

### Outputs (kit areas each input may change)

| Output area | Typical changes driven by research + upstream alignment |
|-------------|---------------------------------------------------------|
| `docs/` | This file, references index, CONTRIBUTING cross-links. |
| `.cursor/rules/` | Vocabulary and kit-vs-runtime boundaries ([spec-layers-and-boundaries.mdc](../.cursor/rules/spec-layers-and-boundaries.mdc)). |
| `.cursor/commands/` + `.claude/commands/` | Aligned wording for spec layers, eval/policy reminders (mirror both sides). |
| `.cursor/skills/` | Pointer skills (e.g. runtime handoff) without shipping runtime code. |
| `templates/` | Eval rubric, constitution, task breakdown, tool-contract stubs, spec-feature adjuncts for consumer repos. |
| `specs/` | Specs describing kit evolution (e.g. this enrichment spec). |

## 2. Research synthesis (reports 3 & 4)

Summarized **without** copying large comparison tables verbatim.

### (a) Multi-layer “spec” model

Production agent engineering treats intent as **layered, checkable artifacts**, not only prose prompts:

1. **Contracts** — Tool and I/O contracts (e.g. JSON Schema for functions, structured outputs / typed models).
2. **Workflow** — Explicit control flow (graphs, steps, pipelines, checkpoints) instead of implicit ad hoc loops.
3. **Policy** — Safety and governance (guardrails, middleware, filters, allow/deny) applied around model and tool calls.
4. **Test / eval** — What “good” means: datasets, rubrics, graders, regression suites, red-team cases; often **offline** (CI) and **online** (production traces).
5. **Ops / observability** — Traces, telemetry, auditability, and feedback from runs back into specs and evals.

**Mapping to this kit:** `specs/` and `/spec` focus on the **human-authored SDLC spec** (problem, criteria, non-goals). Consumer **application** repos still own contracts, workflow code, policy middleware, eval harnesses, and observability **outside** this markdown-and-config kit. The [agent-runtime-handoff](../.cursor/skills/agent-runtime-handoff/SKILL.md) skill states that split explicitly.

### (b) Composable stack vs single framework

Strong **spec-driven** practice is usually a **composition** of orchestration, evaluation, observability, and sometimes outer workflow engines—not a single monolith. Teams mix graph runtimes, eval products, policy libraries, and scheduling/orchestration (e.g. data/workflow tools) as needed.

**Mapping to this kit:** [agent-sdlc](https://github.com/synthet/agent-sdlc) is the **editor and SDLC** layer (rules, commands, templates). It **references** runtime stacks in docs and skills; it does **not** ship LangGraph, Agents SDK, LangSmith, etc.

### (c) Deterministic replay caveats

**True deterministic replay** of full agent runs is hard: LLM sampling and live tool side effects introduce variability. Common patterns:

- **Checkpointed workflow state** can resume control flow and support debugging (“time travel”), but **re-executing** nodes may still call models/tools again with different outcomes unless outputs are recorded or cached.
- **Durable / event-sourced** outer engines treat non-deterministic steps as **recorded activities** when strict replay is required.

**Mapping to this kit:** Do not promise deterministic agent replay from specs alone. In plans and acceptance criteria, distinguish **repeatable human review** (specs, checklists) from **runtime replay** (consumer-owned infrastructure).

## 3. GitHub Spec Kit (analog)

**Spec Kit** targets **AI-assisted coding** workflows (constitution, specs, plans, tasks). It is a useful **workflow analog** for this kit’s spec-first rituals, not a substitute for **runtime** agent orchestration. Cross-link: [GitHub Spec Kit](https://github.com/github/spec-kit) in [agent-sdlc-upstream.md](./references/agent-sdlc-upstream.md).

## 4. Rollback

All artifacts are version-controlled markdown. Revert the implementing PR to roll back.
