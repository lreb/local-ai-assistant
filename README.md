# Local AI Assistant

A private, local AI-assisted software development and orchestration platform.

## Goals
- Understand software projects and documentation.
- Analyze and search source code.
- Execute approved development tools.
- Assist troubleshooting and repetitive engineering workflows.
- Keep data local by default.

## Initial Stack
- Runtime: Ollama
- Model: qwen3:4b
- Agent: Python
- Storage: SQLite
- Configuration: environment variables plus configuration files

## Architecture
User -> Agent -> Orchestrator -> Ollama/Qwen3 + controlled tools -> Local resources.

See `docs/architecture/ARCHITECTURE.md`.

## Security
The LLM receives no direct operating-system privileges. Capabilities are exposed through registered, validated, permission-controlled tools. See `docs/security/SECURITY.md`.

## Start Here
Read `AGENTS.md`, then `docs/PRODUCT.md` and `docs/REQUIREMENTS.md` before implementation.
