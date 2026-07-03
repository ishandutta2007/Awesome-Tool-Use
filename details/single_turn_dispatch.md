# Single-Turn Function Dispatch

Single-turn function dispatch refers to situations where an LLM is expected to map a user request directly to a single execution signature and complete the action in one round-trip.

## Sequence Flow

```mermaid
sequenceDiagram
    participant User
    participant LLM
    participant API as External Tool API
    User->>LLM: Send query (e.g. "Get weather in NYC")
    LLM->>LLM: Identify matching tool schema & parameters
    LLM->>API: Dispatch payload (get_weather: {location: "NYC"})
    API-->>LLM: Return result (temp: 72F, status: sunny)
    LLM-->>User: Formulate final response
```

## Key Aspects
- **Low Latency:** Optimized for immediate action execution.
- **High Determinism:** Simple parameter matching with minimal agentic decision branches.
