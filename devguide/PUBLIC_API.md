# Client Public API

## Status

**Proposed minimal SDK surface.** The client mirrors remote service contracts and does not expose local scientific execution.

## Main object

```python
from molsys_ai_client import MolSysAIClient

client = MolSysAIClient.from_profile("uibcdf")
```

Candidate methods:

- `health()`
- `capabilities()`
- `generate(...)`
- `stream_generate(...)`
- `query_knowledge(...)`
- `ask_documentation(...)`
- `get_symbol(...)`
- `get_recipes(...)`

Exact names remain provisional.

## Return types

Methods return typed Python models that preserve server request IDs, API version, model or corpus identity, citations, usage, warnings and structured errors.

## Sync and async

The SDK should provide coherent synchronous and asynchronous APIs without duplicating schemas. Streaming uses typed events rather than raw text lines.

## Errors

Expose stable exception categories for configuration, authentication, authorization, quota, validation, incompatibility, timeout, transport failure, service overload and server failure. Exceptions redact tokens and retain safe trace identifiers.

## Non-goals

No MolSysSuite imports, session ownership, command planning, viewer control, project memory or local tool execution.