# MolSys-AI Client Development Guide

> **Design status**
>
> This repository is intentionally narrow. Some earlier ideas about profiles, tokens and endpoint configuration are remembered but still require verification against project history.

## Mission

`molsys-ai-client` is the typed transport SDK for remote MolSys-AI services.

It provides endpoint configuration, authentication handling, typed models, streaming, retries, timeouts, compatibility negotiation and clear transport errors.

It must not contain the scientific agent, MolSysSuite execution logic, molecular session state, viewer control, planning or tool orchestration. Those responsibilities belong to `molsys-ai`.

## Documents

- [ARCHITECTURE.md](ARCHITECTURE.md): package boundary and candidate profile model.
- [PUBLIC_API.md](PUBLIC_API.md): minimal synchronous, asynchronous and streaming SDK surface.
- [CONFIGURATION.md](CONFIGURATION.md): precedence, named profiles and secure credential resolution.
- [COMPATIBILITY.md](COMPATIBILITY.md): schema ownership and client-server version negotiation.
- [ROADMAP.md](ROADMAP.md): minimal implementation path.

## Strategic note

This repository should remain small until an independently versioned SDK is demonstrably useful. The first implementation may initially be consumed only by `molsys-ai` and documentation front ends.
