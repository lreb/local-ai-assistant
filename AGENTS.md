# AGENTS.md

## Purpose
This repository implements a local AI-assisted software development and orchestration assistant.

Priorities: local execution, user control, security, deterministic tool execution, maintainability, performance, minimal dependencies, and clear separation of responsibilities.

Default runtime: Ollama. Initial model: qwen3:4b. Do not assume cloud AI services are available.

## Source of Truth
1. AGENTS.md
2. docs/PRODUCT.md
3. docs/REQUIREMENTS.md
4. docs/architecture/
5. docs/security/
6. docs/ai/
7. docs/tools/
8. docs/development/
9. docs/operations/

Do not duplicate rules. If documents conflict, follow the higher-priority source and report the inconsistency.

## Engineering Principles
- KISS and DRY.
- Apply SOLID where useful.
- Least privilege and secure-by-default behavior.
- Explicit behavior and input validation.
- Separation of concerns and dependency injection.
- Fail safely; avoid unnecessary abstractions and frameworks.

## Architecture Rules
User -> Agent -> Orchestrator -> LLM / Tools -> Resources.

The LLM can request registered tools but never directly execute operating-system operations. All actions pass through the tool layer.

## Security Rules
Never expose secrets in prompts, commit secrets, allow unrestricted filesystem/shell access, allow path traversal, automatically delete files or rewrite Git history, expose environment variables, or execute model-generated code without validation.

Sensitive operations require explicit approval.

## Tool Classification
SAFE: list/read/search approved files, git status/diff, inspect configuration.
CAUTION: create/modify files, run tests, git add, install packages.
RESTRICTED: delete files, arbitrary commands, git push/reset, credential changes, process termination, external systems.

Restricted actions require explicit user approval.

## Coding Rules
Use small modules, type hints, descriptive names, structured logging, explicit errors, dependency injection, configuration objects, and unit tests. Avoid global state, hard-coded paths/models/secrets, large multipurpose classes, and silent exceptions.

## AI Rules
Treat LLM output as untrusted input. The model may reason, classify, summarize, propose actions, and request approved tools. Tool arguments must be validated before execution.

## Agent Loop
User Request -> Build Context -> LLM -> Tool Request -> Validate -> Authorization -> Execute -> Tool Result -> LLM -> Final Response.

Use maximum iteration and timeout limits. Stop safely on repeated failures.

## Context Management
Do not load an entire repository by default. Use progressive retrieval: identify relevant information, search, retrieve small relevant sections, then send them to the model.

## Performance
Optimize context size first, then LLM-call count, tool-call count, model size, and disk operations.

## Testing
Cover validation, permissions, path restrictions, iteration limits, malformed model output, Ollama failures, timeouts, and tool failures.

## Change Discipline
Read relevant docs, identify security impact, make the smallest reasonable change, test it, and update documentation only when behavior or architecture changes.
