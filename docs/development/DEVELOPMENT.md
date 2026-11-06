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
2. Ollama provider abstraction (local models)
3. Agent/orchestrator loop
4. Tool registry
5. Permission engine
6. list_files
7. read_file
8. search_files
9. git_status
10. git_diff
11. Context retrieval
12. SQLite memory
13. Structured logging
14. CLI
15. Additional tools
16. Tests and hardening 
