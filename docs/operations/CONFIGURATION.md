# Configuration

## Example
```env
OLLAMA_HOST=http://localhost:11434
OLLAMA_MODEL=qwen3:4b
AGENT_MAX_ITERATIONS=10
LOG_LEVEL=INFO
DATABASE_PATH=./data/assistant.db
```

## Principles
Centralize and type configuration. Validate it on startup. Use safe defaults. Keep secrets out of source and ordinary configuration files committed to Git.

## Recommended Additional Controls
Configure allowed project roots, tool timeouts, maximum file size/read size, maximum tool output size, approval policy, and network-enabled/disabled state.
