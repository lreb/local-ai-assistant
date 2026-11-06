# Requirements

## Functional
- FR-001: Communicate with a local Ollama instance.
- FR-002: Make the active model configurable; default `qwen3:4b`.
- FR-003: Support explicitly registered tool calling.
- FR-004: Read files only inside allowed roots.
- FR-005: Search repositories without loading the full repository into the model.
- FR-006: Require explicit approval for sensitive actions.
- FR-007: Create structured audit records for consequential tool operations.
- FR-008: Handle LLM, Ollama, validation, timeout, and tool failures safely.

## Non-Functional
### Security
Apply least privilege and deny by default.
### Performance
Minimize model context and redundant LLM/tool calls.
### Privacy
Keep local data local unless external communication is explicitly authorized.
### Maintainability
Separate business logic, AI orchestration, and tool/infrastructure execution.
### Testability
Tools and orchestration must be independently testable without a live model when possible.
