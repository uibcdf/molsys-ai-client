# MolSys-AI Client Development Guide

## Mission

`molsys-ai-client` is the typed transport SDK for remote MolSys-AI services.

It provides endpoint configuration, authentication handling, typed models, streaming, retries, timeouts, compatibility negotiation and clear transport errors.

It must not contain the scientific/specialist agent, MolSysSuite execution logic, molecular session state, viewer control, planning or tool orchestration. Those responsibilities belong to [molsys-ai-agent](https://github.com/uibcdf/molsys-ai-agent).

## Documents

- [ARCHITECTURE.md](ARCHITECTURE.md)
- [PUBLIC_API.md](PUBLIC_API.md)
- [CONFIGURATION.md](CONFIGURATION.md)
- [COMPATIBILITY.md](COMPATIBILITY.md)
- [ROADMAP.md](ROADMAP.md)

## Relationship to legacy server code

Transport/configuration/authentication concepts currently present under legacy `molsys-ai-server/client/cli` should migrate here only after classification and compatibility tests. Agent planning/execution code belongs to `molsys-ai-agent`, not this SDK.

## Strategic note

This repository should remain small and dependency-light. In particular, it should remain usable without MolSysSuite installed.
