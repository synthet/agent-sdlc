# Spec: Example — add a new slash command to the kit

## Summary

Add a documented example spec so contributors and consumers see how `specs/` is used inside `agent-sdlc` itself. This is a **documentation and structure** change only.

## Stakeholders

- Maintainers of `agent-sdlc`
- Teams copying the kit into application repositories

## User stories

- As a maintainer, I want a concrete spec example so I can mirror the same pattern for real features.
- As an adopter, I want to see how spec-driven workflow maps to a repo that is mostly markdown and config.

## Non-goals

- Adding runtime code, npm packages, or automated eval pipelines.
- Changing consumer merge steps without updating INSTALL.md.

## Acceptance criteria

- When a contributor opens `specs/README.md`, they see how specs relate to `/spec`, `/plan`, and templates.
- When a contributor reads this file, they see filled sections matching [templates/spec-feature.md](../templates/spec-feature.md).
- When INSTALL references spec layout, it remains accurate (no broken relative links from `specs/`).

## Open questions

- Whether to add `markdownlint` or CI in a follow-up spec.

## References

- Issues: (none)
- Design: [INSTALL.md](../INSTALL.md), [templates/spec-feature.md](../templates/spec-feature.md)
