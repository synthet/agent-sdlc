# Specs (pilot layout)

Use this folder for **spec-first** work on the kit itself (new commands, rule changes, adoption flow updates). Consumer repositories should copy [templates/spec-feature.md](../templates/spec-feature.md) into their own `specs/` (or `docs/specs/`) and adjust paths in [INSTALL.md](../INSTALL.md).

## Workflow

1. (Optional, program-level) Establish or refresh principles with `/constitution` using `templates/constitution.md`.
2. Draft or refine a spec with `/spec` (or `templates/spec-feature.md`).
3. If the spec is still ambiguous, run `/clarify` and merge decisions back into the spec.
4. Use `/plan` for multi-file or risky changes; when **contracts** matter, link tool/API stubs (`templates/tool-contract-stub.md`).
5. Break the approved plan into tasks with `/tasks` (save with `templates/tasks-breakdown.md` if helpful).
6. Implement with small, reviewable diffs; update INSTALL/README when behavior visible to adopters.
7. When agent or LLM **behavior quality** must be defined, use `/eval` with `templates/eval-rubric.md` (consumer-side runners only).

For **agent or LLM** features, use **spec layers** (contracts, workflow, policy, eval, ops) vocabulary from `.cursor/rules/spec-layers-and-boundaries.mdc` so criteria stay checkable.

## Example

See [example-kit-extension.md](./example-kit-extension.md) for a filled sample aligned with the template.
