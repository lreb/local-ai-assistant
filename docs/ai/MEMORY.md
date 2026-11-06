# Memory

## Principle
Session context and durable memory are different. Do not persist everything.

## Session Memory
Current project, current task, selected resources, and recent tool results.

## Durable Memory
Only explicitly useful cross-session information such as configured projects, preferences, allowed directories, and assistant configuration.

## Storage
Initial durable store: SQLite.

## Sensitive Information
Do not store passwords, API tokens, private keys, authentication cookies, or equivalent secrets in ordinary assistant memory.

## Controls
Durable memory must be inspectable, attributable to its source where practical, and deletable by the user.
