# Client Architecture

## Boundary

The client translates Python calls into versioned requests to `molsys-ai-server` and translates server responses into typed Python objects. It should be usable without installing MolSysSuite.

```text
molsys-ai or another application
        │ typed Python API
        ▼
molsys-ai-client
├── configuration
├── authentication
├── HTTP and streaming transport
├── request/response schemas
└── compatibility and errors
        │
        ▼
molsys-ai-server
```

## Candidate API

```python
from molsys_ai_client import MolSysAIClient

client = MolSysAIClient.from_profile("uibcdf")
answer = client.ask(question, project="molsysviewer")
```

The exact API is provisional.

## Profiles

**Remembered — verify:** previous planning may have included tokenized user profiles.

A conservative design is to define a profile as named connection configuration:

```toml
[profiles.uibcdf]
endpoint = "https://api.uibcdf.org"
model = "default"
token_source = "keyring:molsys-ai/uibcdf"
```

Profiles may select endpoints and defaults. They must not contain scientific project state or encode a user's scientific expertise into hidden prompts.

## Authentication

- Tokens are opaque server credentials.
- Secret values should be resolved from environment variables, OS keyrings or protected files.
- Tokens must never appear in logs, exported workflows or repository configuration.
- Authentication mechanisms should remain replaceable.

## API groups

The likely remote service groups are:

- health and capabilities,
- model inference,
- knowledge query,
- documentation assistant,
- streaming events.

Scientific execution APIs are excluded by default because molecular data and tool execution belong locally in `molsys-ai`.
