# Architecture Decision Records

## ADR-001 Local-First AI
Status: Accepted

Use local inference by default through Ollama for privacy, offline capability, and predictable inference cost.

## ADR-002 Initial Model
Status: Accepted

Use `qwen3:4b` initially because it provides a practical capability/resource balance for the target 16 GB development laptop. Keep the model configurable.

## ADR-003 Python Orchestration
Status: Accepted

Implement the first orchestration layer in Python because its ecosystem is strong for local LLM integration, validation, RAG, data processing, and automation.

## ADR-004 Controlled Tool Architecture
Status: Accepted

Do not expose unrestricted OS access to the LLM. Expose narrow, typed, validated capabilities through registered tools.

## ADR-005 SQLite Initially
Status: Accepted

Use SQLite for durable local metadata and memory until scale or concurrency requirements demonstrate the need for another database.
