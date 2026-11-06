# Tools

## Contract
Each tool defines name, purpose, typed input schema, structured output schema, permission level, timeout, and implementation.

## Initial Tool Set
- `list_files` SAFE: list files under allowed roots.
- `read_file` SAFE: read authorized text files with size limits.
- `search_files` SAFE: search approved project files.
- `git_status` SAFE: inspect repository state.
- `git_diff` SAFE: inspect uncommitted changes.
- `run_tests` CAUTION: execute preconfigured test commands.
- `write_file` CAUTION: write inside approved roots with safeguards.
- `execute_command` RESTRICTED: do not expose unrestricted command execution initially.

## Validation
Every tool validates its arguments independently of the model. Resolve and verify paths. Enforce size, timeout, and output limits.

## Structured Output
Prefer `{ "success": true, "data": {}, "error": null }` over raw terminal output.

## Design Rule
Prefer purpose-built tools over generic shell access.
