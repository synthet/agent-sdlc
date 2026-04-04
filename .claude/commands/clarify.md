> **Claude Code:** Same intent as Cursor `/clarify`. When customizing, keep in sync with `.cursor/commands/clarify.md`.

# /clarify — Resolve spec ambiguities

Use when a **spec** exists but acceptance criteria, scope, or edge cases are still fuzzy. Produces decisions you can paste back into the spec (workflow analog to a “clarify” pass in spec-first kits).

## Inputs

- Path to a spec file **or** the spec pasted in the thread.
- Any **constitution** or principles doc if the repo has one.

## Output

1. **Ambiguities** — Numbered list of unclear or conflicting points (quote spec lines if helpful).
2. **Proposed decisions** — Recommended resolution per item (default assumption if the user stays silent).
3. **Spec edits** — Concrete bullets to add, change, or remove: acceptance criteria, non-goals, open questions.
4. **Residual risks** — What remains unknown or needs a human owner.

## Done when

- Another reader could implement or plan from the spec **without** guessing the ambiguous parts.

## Optional

- For **agent or LLM** features, map clarifications to **spec layers** (contracts, workflow, policy, eval, ops) per `.cursor/rules/spec-layers-and-boundaries.mdc`.
