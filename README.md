# MolSys-AI Client

**MolSys-AI Client is the lightweight typed Python SDK for MolSys-AI remote services.**

It provides configuration, authentication, HTTP/streaming transport, typed request/response models, compatibility negotiation, retries/timeouts, and transport errors.

It deliberately does **not** own MolSysSuite execution, planning, molecular session state, viewer control, or scientific project memory.

## Relationship to the project

- [molsys-ai](https://github.com/uibcdf/molsys-ai) — umbrella/architecture.
- [molsys-ai-server](https://github.com/uibcdf/molsys-ai-server) — remote services consumed by this SDK.
- [molsys-ai-agent](https://github.com/uibcdf/molsys-ai-agent) — specialist agent that may use this SDK while operating MolSysSuite locally.

The client should remain usable without installing MolSysSuite.

See `devguide/` for the proposed API, configuration, compatibility, and roadmap.
