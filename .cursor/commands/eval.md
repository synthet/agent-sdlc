# /eval — Eval rubric for agent or LLM behavior

Use when you need **checkable** criteria for how an agent or LLM-backed feature should behave. Fills a rubric for **consumer** eval runners—this kit does not execute evals.

## Inputs

- Feature or scenario name; related **spec** or issue link.
- Whether behavior is **offline** (CI/batch), **online** (prod traces), or both.

## Output

Produce sections aligned with `templates/eval-rubric.md`:

1. **Feature / scenario** and related spec.
2. **Scope of layers** — contracts, workflow, policy, ops (checkboxes).
3. **Offline vs online** — what this rubric targets; regression / spot-check notes.
4. **Policy / red-team style cases** — deny paths and edge prompts if relevant.
5. **Criteria table** — ID, criterion, pass condition, optional weight.
6. **Dataset / fixtures** — inputs, golden references if any.
7. **Judge / automation** — human, LLM-as-judge, programmatic; link to **AGENTS.md** or CI job.
8. **Non-goals** and **rollback** (how to skip without blocking unrelated CI).

## Done when

- Each criterion is **checkable** without interpreting product intent.

## References

- Template: `templates/eval-rubric.md`
- Vocabulary: `.cursor/rules/spec-layers-and-boundaries.mdc`
