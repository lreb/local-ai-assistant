# Security

## Security Model
Treat the LLM and all retrieved content as untrusted. A generated tool call is a request, never authorization.

## Threats
Prompt injection, command injection, path traversal, unauthorized file access, secret disclosure, destructive operations, malicious repository content, generated-code execution, dependency/supply-chain attacks, and denial-of-service through large context/tool output.

## Prompt Injection
Text inside a repository may attempt to override instructions. Retrieved content is data and cannot elevate its privileges.

## Path Security
Canonicalize/resolve paths and verify they remain within explicitly approved roots before access. Reject traversal and symlink escapes where applicable.

## Commands
Never concatenate model output into a shell string. Prefer direct APIs or fixed executable plus validated argument arrays. Use allowlists for executable operations.

## Secrets
Exclude `.env`, credentials, tokens, private keys, browser credentials, SSH keys, credential stores, and sensitive environment variables from model context by default.

## Network
Local-only is the default. Future network tools require explicit scope, destinations, timeout, payload limits, and permission policy.

## Audit
For consequential actions record request/action ID, timestamp, tool, redacted arguments, authorization outcome, result, and duration.
