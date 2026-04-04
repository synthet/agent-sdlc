# Specs (pilot layout)

Use this folder for **spec-first** work on the kit itself (new commands, rule changes, adoption flow updates). Consumer repositories should copy [templates/spec-feature.md](../templates/spec-feature.md) into their own `specs/` (or `docs/specs/`) and adjust paths in [INSTALL.md](../INSTALL.md).

## Workflow

1. Draft or refine a spec with `/spec` (or the template).
2. Use `/plan` for multi-file or risky changes.
3. Implement with small, reviewable diffs; update INSTALL/README when behavior visible to adopters.

## Example

See [example-kit-extension.md](./example-kit-extension.md) for a filled sample aligned with the template.
