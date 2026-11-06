# Performance

## Target
Windows 11, 16 GB RAM, Ollama, `qwen3:4b`.

## Main Constraints
Memory pressure, inference latency, context length, and excessive tool output.

## Optimization Order
1. Reduce context size.
2. Avoid duplicate prompt content.
3. Reduce unnecessary LLM calls.
4. Bound and summarize tool output.
5. Cache safe deterministic results.
6. Stream user-visible responses when useful.
7. Avoid repository-wide loading.

## Measure
Prompt/context size, response size, time to first token, total inference latency, tool latency, iterations per task, peak memory use, cache hit rate, and failure/timeout rates.

Do not optimize without measurements.
