# MolSys-AI Client Development Guide

> **Design status**
>
> This repository is intentionally narrow. Some earlier ideas about profiles, tokens and endpoint configuration are remembered but still require verification against project history.

## Mission

`molsys-ai-client` is the typed transport SDK for remote MolSys-AI services.

It should provide:

- endpoint configuration,
- authentication handling,
- typed request and response models,
- streaming support,
- retries, timeouts and clear transport errors,
- compatibility negotiation with server APIs.

It must not contain:

- the scientific agent,
- MolSysSuite execution logic,
- molecular session state,
- viewer control,
- planning or tool orchestration.

Those responsibilities belong to `molsys-ai`.

## Documents

- [ARCHITECTURE.md](ARCHITECTURE.md): package boundaries and profile model.
- [ROADMAP.md](ROADMAP.md): minimal implementation path.

## Strategic note

This repository should remain small until an independently versioned SDK is demonstrably useful. The first implementation may initially be consumed only by `molsys-ai` and documentation front ends.
