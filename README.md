# Project SENTINEL

Project SENTINEL is an autonomous enterprise risk and intelligence platform built for the NVIDIA Agentic AI Hackathon. This repository is structured as a Python-first monorepo that houses agents, services, shared libraries, and infrastructure as independent packages coordinated through a unified workspace.

## Repository Layout

- `agents/` – Agent implementations (supervisor, ingestion, analysis, etc.)
- `services/` – Long-running services and APIs that expose SENTINEL capabilities
- `shared/` – Shared utilities, schemas, and common business logic
- `infrastructure/` – Infrastructure-as-code, deployment manifests, and automation scripts
- `docs/` – Project documentation, setup guides, and architecture references
- `.github/workflows/` – Continuous integration workflows

Each package follows a `pyproject.toml` + `src/` layout so that it can be versioned and released independently when the platform matures.

## Monorepo Tooling

The workspace is managed with [`uv`](https://github.com/astral-sh/uv), which provides fast dependency resolution and native monorepo support. The root `pyproject.toml` declares workspace members corresponding to the packages listed above.

### Prerequisites

Install the core tooling locally before working on the project:

```bash
# Install uv (Linux/macOS)
curl -LsSf https://astral.sh/uv/install.sh | sh

# Install uv (Windows PowerShell)
powershell -ExecutionPolicy Bypass -c "iwr https://astral.sh/uv/install.ps1 -UseBasicParsing | iex"

# Ensure Docker Desktop, kubectl, and AWS CLI are present
```

Configure Python 3.11+ and validate the toolchain:

```bash
uv python install 3.11
uv --version
python --version
```

### Bootstrap the Workspace

```bash
# Resolve and install shared dependencies across the workspace
uv sync --extra dev

# Run static analysis and the test suite
uv run ruff check .
uv run pytest
```
