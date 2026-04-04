# Eval rubric (stub)

Use in **consumer application** repositories to define how agent behavior is scored. This template is **not** executed by agent-sdlc; wire it to your eval runner (CI, platform dashboards, or offline scripts).

## Feature or scenario

- **Name:**
- **Related spec / issue:**

## Scope of layers

- [ ] **Contracts** — Tool args/results and structured outputs validated
- [ ] **Workflow** — Expected steps or graph paths
- [ ] **Policy** — Safety / deny cases covered
- [ ] **Ops** — Trace or log fields present for debugging

## Offline vs online

- **Offline (CI / batch):** fixed datasets, mocks, golden outputs; runs in pipelines or local scripts.
- **Online (production traces):** sampling, dashboards, alerts on live traffic—**not** a substitute for offline regression unless explicitly designed.

State what this rubric targets:

- [ ] Offline
- [ ] Online
- [ ] Both (explain split below)

**Notes:**

## Regression and spot-checks

- **Regression suite:** (what must stay green when merging)
- **Spot-checks:** (manual or ad hoc runs before release)
- **Frequency:** (every PR / nightly / on-demand)

## Policy / red-team style cases

- **Deny or refusal cases:** (inputs that must not produce harmful or non-compliant outputs)
- **Adversarial or edge prompts:** (optional; link to dataset or playbook)

## Criteria (checkable)

| ID | Criterion | Pass condition | Weight (optional) |
|----|-----------|----------------|-------------------|
| E1 | | | |
| E2 | | | |

## Dataset / fixtures

- **Inputs:** (prompts, user messages, tool mocks)
- **Golden or reference:** (if any; rubric-only is OK for LLM judges)

## Judge / automation

- **Human rubric only** / **LLM-as-judge** / **Programmatic checks** (pick one or combine)
- **Command or job:** (link to AGENTS.md or CI workflow name)
- **Judge prompt or rubric file:** (if using an LLM grader; avoid committing secrets)

## Non-goals

- What this eval explicitly does **not** cover

## Rollback

- How to disable or skip this eval without blocking unrelated CI
