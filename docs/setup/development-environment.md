# Development Environment Setup

Use this guide to configure your local machine for Project SENTINEL development.

## Tooling Checklist

- Install Python 3.11 or later
- Install [uv](https://github.com/astral-sh/uv) for workspace and dependency management
- Install Docker Desktop
- Install kubectl
- Install AWS CLI v2
- Install Git and configure SSH access to GitHub

## Install Python Runtime

1. Verify the Python version:
   ```bash
   python --version
   ```
2. If your Python version is older than 3.11, install a new interpreter and set it as the default.

## Install uv

1. Install uv using the official script:
   ```bash
   curl -LsSf https://astral.sh/uv/install.sh | sh
   ```
2. On Windows PowerShell, run:
   ```powershell
   iwr https://astral.sh/uv/install.ps1 -UseBasicParsing | iex
   ```
3. Confirm the installation:
   ```bash
   uv --version
   ```

## Configure Docker and Kubernetes

1. Start Docker Desktop and ensure it runs without errors.
2. Verify that Docker works:
   ```bash
   docker run hello-world
   ```
3. Install kubectl and confirm the version:
   ```bash
   kubectl version --client
   ```

## Configure AWS Access

1. Install AWS CLI v2 and confirm the version:
   ```bash
   aws --version
   ```
2. Configure AWS credentials with least-privilege IAM roles dedicated to the hackathon account:
   ```bash
   aws configure --profile sentinel
   ```
3. Export the profile when you work on the project:
   ```bash
   set AWS_PROFILE=sentinel
   ```

## Bootstrap the Workspace

1. Clone the repository:
   ```bash
   git clone <repo-url>
   cd agenticai
   ```
2. Create a Python virtual environment managed by uv:
   ```bash
   uv sync --extra dev
   ```
3. Run quality gates to ensure your setup works:
   ```bash
   uv run ruff check .
   uv run pytest
   ```

## Optional Enhancements

- Install [`pre-commit`](https://pre-commit.com/) and configure hooks once the linting stack stabilizes.
- Install [`direnv`](https://direnv.net/) to manage environment variables per directory.
- Configure IDE integrations for Ruff, mypy, and pytest.
