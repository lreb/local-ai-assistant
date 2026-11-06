# Context Management

## Objective
Provide the smallest high-quality context necessary for an accurate result.

## Progressive Retrieval
Request -> classify intent -> identify needed evidence -> search -> retrieve relevant sections -> build context -> invoke model.

## Do Not Automatically Send
Entire repositories, all conversation history, every Markdown file, binary files, generated directories, dependency directories, secrets, or unrelated logs.

## Default Exclusions
`.git/`, `node_modules/`, `bin/`, `obj/`, `dist/`, `build/`, `coverage/`, `.venv/`, `__pycache__/`.

## Priority
1. Current user request
2. Relevant code/data/tool evidence
3. Relevant project documentation
4. Needed session context

## Efficiency
Remove duplicates, generated content, irrelevant logs, repeated instructions, and unrelated documentation. Cache deterministic retrieval where safe and useful.
