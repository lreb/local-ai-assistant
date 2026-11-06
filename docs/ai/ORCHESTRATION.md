# Orchestration

## Agent Loop
Default maximum iterations: 10, configurable.

1. Supply relevant context and approved tool definitions to the model.
2. Receive response.
3. If final answer, stop.
4. For each requested tool: validate name/schema, validate arguments, authorize, obtain approval if needed, execute with timeout, sanitize output, and append the result.
5. Repeat within limits.

## Stop Conditions
Final answer, iteration limit, rejected operation, approval required, timeout budget exceeded, cancellation, or unrecoverable failure.

## Reliability Controls
Every external operation needs a timeout. Detect repeated identical failed calls. Use bounded retries only for transient failures and never retry destructive actions blindly.

## Errors
Treat tool errors as structured data. Redact secrets and sensitive environment details before exposing errors to the model or logs.
