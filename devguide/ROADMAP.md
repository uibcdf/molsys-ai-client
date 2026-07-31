# Client Roadmap

## Phase 0 — Verify recovered requirements

- Search repository history for profile, token, endpoint and configuration ideas.
- Mark each recovered requirement as confirmed, revised or discarded.

## Phase 1 — Minimal typed transport

- Define client configuration.
- Implement health and capabilities calls.
- Implement non-streaming inference and knowledge queries.
- Add typed exceptions, timeouts and tests.

## Phase 2 — Profiles and authentication

- Add named endpoint profiles only after requirements are verified.
- Integrate secure token resolution.
- Ensure logs and exceptions redact credentials.

## Phase 3 — Streaming and compatibility

- Add streaming responses and events.
- Add API-version and capability negotiation.
- Test against supported server versions.

## Phase 4 — Packaging

- Publish only when the SDK has a clear independent consumer and stable API.
- Keep dependencies minimal and avoid importing MolSysSuite.
