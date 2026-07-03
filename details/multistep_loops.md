# Multi-Step Autonomous Loops (Agentic Tool Use)

Agentic tool use leverages multi-step loops where the LLM evaluates the result of intermediate actions and iteratively updates its planning trace to execute consecutive operations.

## Loop Lifecycle

```mermaid
graph TD
    Goal[Set Goal] --> Plan[Formulate Plan]
    Plan --> Exec[Execute Next Step / Tool]
    Exec --> Observation[Capture Environment State]
    Observation --> Critique{Goal Achieved?}
    Critique -->|No - Error/Partial| Plan
    Critique -->|Yes| Finish[Return Output]
```

## Features
- **Adaptive Execution:** Handles unforeseen failures or edge cases dynamically.
- **State Maintenance:** Requires context tracking to hold intermediate states.
