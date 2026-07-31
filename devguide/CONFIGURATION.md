# Client Configuration

## Sources and precedence

Configuration may come from explicit constructor arguments, environment variables, a selected named profile and package defaults, in that order. Effective configuration should be inspectable with secrets redacted.

## Profile scope

A client profile contains connection defaults only:

- endpoint,
- API version preference,
- model defaults,
- timeout and retry policy,
- TLS and proxy configuration,
- credential reference.

It does not contain molecular project state, conversation memory or hidden scientific personalization.

## Candidate location

A possible user configuration location is:

```text
~/.config/molsys-ai/config.toml
```

The path and format remain provisional pending repository archaeology and platform review.

## Credential resolution

Profiles reference credentials through environment variables, OS keyrings or protected files. Raw token values should not be serialized when configuration is displayed, logged or copied.

## Environment variables

Environment variables should support CI, containers and clusters without requiring interactive profile setup. Names must be documented and stable once released.

## Validation

Configuration is validated before network calls. Invalid endpoints, unsupported API versions, missing credentials and contradictory settings produce local typed errors.

## Separation from core profiles

`molsys-ai` may define execution and user-preference profiles. The client only consumes the connection portion needed to contact remote services.