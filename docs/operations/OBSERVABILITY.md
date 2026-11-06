# Observability

## Purpose
Make agent behavior operationally understandable without recording sensitive content unnecessarily.

## Structured Logs
Capture request ID, operation, model name, duration, tool name, authorization outcome, success/failure, agent iteration, and sanitized error category.

## Never Log
Passwords, API keys, tokens, private keys, authentication cookies, full environment variables, or unredacted sensitive tool payloads.

## Initial Metrics
- `agent_requests_total`
- `agent_failures_total`
- `agent_iterations`
- `llm_latency_ms`
- `tool_latency_ms`
- `tool_failures_total`
- `tool_denials_total`
- `approval_requests_total`

Use debug diagnostics only in development and continue secret redaction there.
