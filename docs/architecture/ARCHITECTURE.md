# Architecture

## Style
Use a modular layered architecture with explicit boundaries.

## Components
### Interface
Initial interface: CLI. Future options may include a local REST API or local web UI.

### Agent
Owns session lifecycle and coordinates orchestration.

### Orchestrator
Runs the bounded agent loop, invokes the model, interprets tool requests, dispatches approved tools, and returns results.

### LLM Provider
Abstracts model communication. Initial implementation: Ollama. Core application logic must not depend directly on Ollama-specific APIs.

### Tool Registry
Registers tool schemas and implementations and validates tool selection.

### Authorization
Determines whether a validated request can execute and whether user approval is required.

### Context Service
Retrieves the minimum relevant project information for the current task.

### Memory
Stores explicitly durable state. Initial implementation: SQLite.

### Observability
Captures request IDs, model/tool latency, context size, iterations, errors, and outcomes.

## Dependency Direction
Interface -> Agent -> Orchestrator -> application abstractions -> infrastructure adapters.

Tools and LLM providers implement application interfaces; core logic must not import operating-system implementation details.
