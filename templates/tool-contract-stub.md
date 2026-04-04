# Tool contract: <tool_name>

**SDLC stub** for a single tool or function the agent may call. **Authoritative** schema and validation live in **application** code (and your OpenAPI / JSON Schema artifacts); keep this doc in sync when behavior changes.

## Summary

- **Purpose:**
- **Related spec / issue:**

## Invocation

- **Name** (as exposed to the model):
- **Idempotency:** safe to retry? side effects?

## Arguments (JSON Schema sketch)

```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "type": "object",
  "properties": {},
  "required": []
}
```

## Result (JSON Schema sketch)

```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "type": "object",
  "properties": {}
}
```

## Errors

- **Codes / shapes:** (e.g. validation vs upstream API failure)
- **What the agent should do:** retry, escalate, user message

## Policy / safety notes

- PII, destructive actions, rate limits—pointer to policy layer in app

## Tests / eval

- Link to rubric rows or programmatic checks that assert this contract

## References

- Source file(s):
- OpenAPI / schema file(s):
