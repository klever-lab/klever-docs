# Architecture

## API-First Architecture

The API server functions as the central execution layer and authoritative source of state for all tools.

The web application and command-line interfaces operate strictly as clients over this API. External clients can integrate directly against the same endpoints.

## Cloud Abstraction Layer

The suite operates as an abstraction layer across supported cloud providers.

The architecture provides composable interfaces for cloud primitives while preserving direct access to underlying provider configurations alongside default presets.
