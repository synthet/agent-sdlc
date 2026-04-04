# Spec: Research-driven enrichment of agent-sdlc

## Summary

Use **local deep-research exports** (spec-driven agent frameworks landscape) plus **authoritative product and protocol documentation** (Cursor, Claude Code, MCP, GitHub Spec Kit, selected agent SDK docs) to extract actionable patterns—contracts, workflow gates, policy hooks, evaluation loops, and observability—and **map them into this kit** as rules, slash commands, skills, templates, and adoption notes. The kit stays a **markdown-and-config** artifact; runtime frameworks (LangGraph, Agents SDK, and so on) are referenced for consumer repos, not shipped as code here.

## Stakeholders

- **Maintainers** of `agent-sdlc` who curate rules, commands, and install docs.
- **Consumer teams** adopting the kit who want SDLC guidance aligned with modern agent-engineering practice.
- **Coding agents** (Cursor, Claude Code, Copilot) that consume rules and commands daily.

## User stories

- As a **maintainer**, I want research and upstream docs distilled into **checkable kit changes** so improvements are traceable and reviewable.
- As an **adopter**, I want **clear boundaries** between “editor/SDLC kit” and “runtime agent stack” so I know what to copy vs what to install separately.
- As an **agent user**, I want **consistent vocabulary** (spec layers, eval hooks, policy) across rules and commands so `/spec` and `/plan` align with how production agents are built.
- As a **contributor**, I want a **short bibliography** (URLs + optional local snapshots) so claims about external tools are verifiable without re-running deep research.

## Non-goals

- Adding application runtime, package manifests, LangGraph/LangSmith/OpenAI SDK code, or CI eval runners to this repository.
- Vendoring full third-party documentation trees or scraping entire doc sites.
- Replacing upstream product docs; we **link** and optionally keep **small excerpts** under fair use / license where explicitly allowed.
- Committing local deep-research markdown if the project policy keeps it gitignored; synthesis and citations can still live in this spec and in tracked `docs/` snippets written for the kit.
- Changing [LICENSE](LICENSE) or the documented upstream remote in [README.md](../README.md) without explicit maintainer instruction.

## Acceptance criteria

- **Document inventory:** When implementation starts, there is a written list of **inputs** (in-repo paths + external URLs) and **outputs** (which kit areas each input may change).
- **Research synthesis:** When the local reports `docs/deep-research-report-3.md` and `docs/deep-research-report-4.md` are present, the implementation notes summarize **at least**: (a) multi-layer “spec” model (contracts, workflow, policy, test/eval, ops/observability), (b) composable stack vs single-framework view, (c) deterministic replay caveats—**without** copying large tables verbatim into the kit.
- **Upstream alignment:** When “download tools” is executed, at least **one** of: pinned doc URLs in References, or a small tracked `docs/references/` index (if added in implementation), lists **Cursor** (rules/commands/skills), **Claude Code** (commands/hooks), **MCP** (protocol or official overview), and **GitHub Spec Kit**—each with retrieval date and primary URL.
- **Kit deltas (concrete):** A follow-up implementation PR proposes **specific** edits to: `.cursor/rules/` and/or `.claude`-side guidance, **and/or** new/updated slash commands, **and/or** `templates/`, **and/or** [INSTALL.md](../INSTALL.md) / [README.md](../README.md) / [AGENTS.md](../AGENTS.md)—each change tied to a bullet in the synthesis (no drive-by refactors).
- **Mirror rule:** When any `.cursor/commands/*.md` body changes, the mirrored `.claude/commands/*.md` twin is updated per [docs/CONTRIBUTING.md](../docs/CONTRIBUTING.md).
- **Reviewability:** Another developer can execute the plan without guessing tool versions or secret steps; rollback is “revert the PR” (no migrations).

## Open questions

- Should ignored deep-research files remain **local-only**, or should a **redacted, kit-owned** summary be committed under `docs/` for all contributors?
- Do we add **markdownlint** or a link-check script in a **separate** spec, or only manual CONTRIBUTING checks for this effort?
- (Follow-up) Optional **rule** mapping spec layers to concrete consumer repo folder conventions—still unscoped.

## References

- Local inputs (when present): `docs/deep-research-report-3.md`, `docs/deep-research-report-4.md` (themes: SDD for agents, framework scorecards, lifecycle diagrams).
- In-repo: [specs/README.md](./README.md), [templates/spec-feature.md](../templates/spec-feature.md), [INSTALL.md](../INSTALL.md), [AGENTS.md](../AGENTS.md), `.cursor/commands/`, `.claude/commands/`, `.cursor/rules/`.
- External (to verify during implementation; URLs are starting points, not pinned yet): Cursor documentation (Project Rules, Commands, Agent Skills), Claude Code documentation (slash commands, hooks), [Model Context Protocol](https://modelcontextprotocol.io/) specification/overview, [GitHub Spec Kit](https://github.com/github/spec-kit) README and workflow docs, vendor agent SDK docs as needed for cross-links only.

---

# Implementation plan (for `/plan`)

## Goal

**Done** means: inputs are cataloged and summarized, authoritative sources are fetched or linked, and a **single reviewable PR** (or sequenced small PRs) updates the kit with deliberate improvements—each change traceable to the synthesis. No claim of “complete” without CONTRIBUTING validation (Cursor ↔ Claude command mirrors when touched).

## Files / areas to touch

| Area | Likely edits |
|------|----------------|
| `specs/` | This file refined after review; optional follow-up spec for `/eval` or tooling only. |
| `docs/` | Optional `docs/references/agent-sdlc-upstream.md` (URL index) or short “runtime vs kit” note—only if maintainers want it tracked. |
| `.cursor/rules/` | Optional new or extended `.mdc` for vocabulary (spec layers) and boundaries (kit vs runtime). |
| `.cursor/commands/` + `.claude/commands/` | Optional new command(s) or tweaks to `/spec`, `/plan`, `/implement` prompts to mention eval/policy layers when relevant. |
| `.cursor/skills/` | Optional skill for “hand off to runtime stack” pointers. |
| `templates/` | Optional template for eval rubrics or “tool JSON Schema stub.” |
| `INSTALL.md` / `README.md` / `AGENTS.md` | Short cross-links if new workflows or folders appear. |

## Approach

1. **Inventory** — List all analysis inputs (local reports, in-repo kit files). Note which are gitignored and how teammates obtain them.
2. **Fetch / record** — For each external “tool” or doc set: open official pages (or use approved fetch in maintainer environment), record **title, URL, date retrieved**, and **1–3 kit-relevant takeaways** each. Do not bulk-download; prefer an index file in-repo if summaries are committed.
3. **Synthesize** — Extract non-duplicate themes from reports 3 and 4 (they overlap): contract specs, workflow specs, policy, eval, observability; composable stacks; Spec Kit as coding-workflow analog.
4. **Gap analysis** — For each theme, map to current kit: rules, commands, templates, INSTALL. Mark **gaps** (missing guidance) vs **out of scope** (runtime).
5. **Design changes** — Pick the smallest set of high-impact edits (prefer one new command OR one rule OR one template, not all at once unless trivial).
6. **Implement** — Apply edits; mirror `.cursor/commands` ↔ `.claude/commands`; update INSTALL/README only if user-visible paths change.
7. **Handoff note** — Add a short “For application repos” paragraph: where AGENTS.md, specs, and runtime (e.g. LangSmith, OTel) live—without implementing runtime.

**Risky changes:** Broad rewrites of every rule file (hard to review); adding hooks documentation that conflicts with [INSTALL.md](../INSTALL.md) hooks warnings—any hook-related text must stay conservative and link to upstream safety guidance.

## Tests

Per [AGENTS.md](../AGENTS.md): no in-repo test runner. **Before claiming done:**

- Manually verify **mirrored** command files if any `.cursor/commands/*.md` or `.claude/commands/*.md` was edited (diff bodies or twin pointers).
- If INSTALL/README change: follow links from `specs/` and INSTALL locally (relative paths).
- Optional: `git grep` for broken twin references (“Cursor twin”) if new commands added.

## Rollback / flags

- All changes are **version-controlled markdown/config**; rollback is `git revert` on the implementing PR.
- No feature flags or environment variables.
- If `docs/references/` is added and later unwanted, remove the folder and references in one revert.

---

## Implementation status (2026-04-04)

Delivered artifacts tied to this spec:

| Artifact | Path |
|----------|------|
| Document inventory + research synthesis | [docs/research-synthesis-and-inventory.md](../docs/research-synthesis-and-inventory.md) |
| Upstream URL index (retrieval dates) | [docs/references/agent-sdlc-upstream.md](../docs/references/agent-sdlc-upstream.md) |
| Spec layers + kit/runtime rule | `.cursor/rules/spec-layers-and-boundaries.mdc` |
| Runtime handoff skill | `.cursor/skills/agent-runtime-handoff/SKILL.md` |
| Eval rubric template (consumer repo) | [templates/eval-rubric.md](../templates/eval-rubric.md) |
| Command alignment (mirrored) | `.cursor/commands/spec.md`, `plan.md`, `implement.md` ↔ `.claude/commands/*` |
| Adoption / charter links | [INSTALL.md](../INSTALL.md), [README.md](../README.md), [AGENTS.md](../AGENTS.md), [docs/CONTRIBUTING.md](../docs/CONTRIBUTING.md) |
| Spec Kit–style commands (mirrored) | `.cursor/commands/constitution.md`, `clarify.md`, `tasks.md`, `eval.md` ↔ `.claude/commands/*` |
| Constitution / tasks / contract templates | [templates/constitution.md](../templates/constitution.md), [templates/tasks-breakdown.md](../templates/tasks-breakdown.md), [templates/tool-contract-stub.md](../templates/tool-contract-stub.md) |
| Eval rubric + spec template extensions | [templates/eval-rubric.md](../templates/eval-rubric.md), [templates/spec-feature.md](../templates/spec-feature.md); `/plan` replay caveat |
| Upstream workflow analog | [docs/references/agent-sdlc-upstream.md](../docs/references/agent-sdlc-upstream.md) — Spec Kit vs agent-sdlc |

Open questions in this spec remain for maintainers (ignored deep-research files, markdownlint) unless addressed in a follow-up spec.
