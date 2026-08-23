# Architecture

## API-First Tools

The API is the core of our infrastructure — it runs as its own hardened server and is the single source of truth. We build it by hand.

The web app and CLI we provide are just clients on top of that API. Since the API is the real interface, you're welcome to vibe-code your own client against it.

## Cloud Compatibility Layer

The suite should work like an opinionated compatibility layer over cloud providers.

The tools should make cloud primitives easier to combine while still letting advanced users reach the raw provider options when needed. Presets can exist, but they should not be the only interface.
