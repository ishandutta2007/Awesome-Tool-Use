# Closed-Loop Self-Correction / Sandboxed Compilation

This variant automates code or tool parameter execution by running them in a compiler sandboxed loop and analyzing compiler error diagnostics to recursively self-correct bugs.

## Debugging Loop

```mermaid
graph TD
    Code[Generate Code Block] --> SandboxedCompiler[Run in Sandbox]
    SandboxedCompiler --> Result{Succeeded?}
    Result -->|Yes| Output[Capture Result]
    Result -->|No - Crash/Error| StackTrace[Extract Stack Trace / Diagnostic Logs]
    StackTrace --> Feedback[Feed Error Message back to LLM]
    Feedback --> Code
```

## Significance
- **Autonomy:** Eliminates human debugging interventions.
- **Reliability:** Ensures compiler verification before final output submission.
