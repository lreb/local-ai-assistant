# Data Flow

## Normal Request
1. User submits a request.
2. Input is validated.
3. Context service retrieves relevant information.
4. Orchestrator constructs model input.
5. Ollama runs the configured model.
6. Model returns either a final response or tool request.
7. Tool name and arguments are validated.
8. Authorization and approval policies are evaluated.
9. Approved tool executes with a timeout.
10. Sanitized structured result returns to the orchestrator.
11. Result is supplied to the model if another reasoning step is required.
12. Agent returns the final response.

## Trust Boundary
LLM output is untrusted. It must pass through schema validation and authorization before causing side effects.

Never bypass: LLM -> Validator -> Authorization -> Tool -> Resource.
