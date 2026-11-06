# Testing

## Strategy
Prioritize unit tests, then integration tests, then bounded agent scenario tests.

## Security Tests
Path traversal, symlink escape where relevant, unauthorized tools, invalid schemas, dangerous arguments, prompt injection, access outside allowed roots, secret redaction, and deny-by-default behavior.

## Orchestration Tests
Normal completion, one/multiple tool calls, tool failure, malformed request, timeout, cancellation, iteration limit, repeated-call detection, and approval-required flow.

## Ollama Adapter Tests
Service unavailable, model unavailable, timeout, invalid/malformed responses, and context-size handling.

## Model-Independent Testing
Mock the LLM provider for most orchestration tests. Security and permission logic must not depend on model quality.
