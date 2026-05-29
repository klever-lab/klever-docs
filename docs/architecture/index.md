# Architecture

## API-First Tools

The API is the main product. We build it by hand and treat it as the single source of truth.

Everything users touch, the command-line tool and the web app, sits on top of that API. We can lean on LLMs to help build those parts from the API and its docs.

## Cloud Compatibility Layer

The suite should work like an opinionated compatibility layer over cloud providers.

The tools should make cloud primitives easier to combine while still letting advanced users reach the raw provider options when needed. Presets can exist, but they should not be the only interface.
