# Technical Tool Planning Docs

This repository contains long-running technical planning docs for upcoming software tools.

## Run Locally

Install dependencies:

```bash
uv sync
```

Start the docs server:

```bash
uv run mkdocs serve
```

Then open `http://127.0.0.1:8000`.

## Structure

- `docs/tools/` - individual tool plans
- `docs/architecture/` - shared architecture and decisions
- `docs/research/` - research notes
- `docs/operations/` - deployment and maintenance planning
