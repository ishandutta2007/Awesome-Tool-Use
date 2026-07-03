# Remote Code Execution (RCE) Prompt Injection Hazard

Autonomous execution models are vulnerable to indirect prompt injection: malicious payloads inside untrusted websites or data sources hijack the system prompt and execute actions (e.g. system commands, database drops).

## Attack Vector and Sandbox Mitigation

```mermaid
graph TD
    Attacker[Inject instructions on Webpage] -.-> Crawler[Agent Scrapes Webpage]
    Crawler --> LLMContext[LLM parses malicious code]
    LLMContext --> HijackedInstructions[LLM generates destructive tool arguments]
    HijackedInstructions --> SandboxedBoundary{Is Sandbox Isolation active?}
    SandboxedBoundary -->|Yes| Container[Execute safely inside ephemeral gVisor container]
    SandboxedBoundary -->|No| RCE[Critical System Compromise / Data Loss]
```

## Security Best Practices
- **Strict Sandboxing:** Run code execution models in ephemeral, rootless environments.
- **Human-in-the-Loop:** Require authorization for destructive changes (FS, database writes).
