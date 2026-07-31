# Compatibility Strategy

## Contract ownership

Remote API schemas are owned by `molsys-ai-server` and represented in `molsys-ai-client`. The local scientific command protocol is owned by `molsys-ai` and is a separate contract.

The client should preferably generate or validate transport models from the server's published OpenAPI/schema artifacts while retaining a stable ergonomic Python API.

## Negotiation

At startup or first use, the client may query server capabilities and determine:

- supported API major and minor versions,
- available service groups,
- streaming support,
- model roles,
- knowledge projects and corpus versions,
- authentication requirements.

## Version rules

- Matching major versions are required unless an explicit compatibility adapter exists.
- Additive optional fields should not break older clients.
- Unknown event types are preserved or surfaced safely rather than silently discarded.
- Removed or semantically changed fields require a new major API version.

## Testing matrix

Maintain tests for the current client against all supported server releases and the current server against supported client releases. Include streaming, errors, capability negotiation and credential redaction.

## Failure behavior

Incompatible clients fail early with actionable version information. They must not guess request formats or silently downgrade security behavior.