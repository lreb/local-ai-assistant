# Development

## Suggested Stack
Python 3.12+, Ollama, Qwen3, Pydantic, SQLite, pytest. Add libraries only when a requirement justifies them.

## Suggested Source Layout
```
src/
  agent/
  orchestration/
  llm/
  tools/
  context/
  memory/
  security/
  observability/
  config/
```

## Dependency Management
Use a reproducible dependency definition, pin important production dependencies, review transitive dependencies, and keep the set small.

## Configuration
Separate configuration from source. Never commit secrets. Validate configuration at startup.

## Implementation Order
1. Configuration and domain types
2. Ollama provider abstraction
3. Bounded orchestrator loop
4. Tool registry and validation
5. Permission engine
6. Read-only filesystem/Git tools
7. Context retrieval
8. SQLite memory
9. Structured logging/metrics
10. CLI
11. Tests and hardening before additional write/execution tools
