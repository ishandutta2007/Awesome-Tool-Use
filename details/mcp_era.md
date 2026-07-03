# Model Context Protocol (MCP) Era (~2025–Present)

The **Model Context Protocol (MCP)** is an open standard that decouples models and tool-using clients from the servers hosting actual tools. It introduces a unified, secure client-server paradigm.

## System Architecture

```mermaid
graph LR
    subgraph Client App
        LLMClient[LLM Client / Agent Application]
    end
    subgraph MCP Server Hub
        DatabaseServer[MCP Database Server]
        APIServer[MCP Web API Server]
        FileSystemServer[MCP Local FS Server]
    end
    LLMClient <-->|Model Context Protocol JSON-RPC| DatabaseServer
    LLMClient <-->|Model Context Protocol JSON-RPC| APIServer
    LLMClient <-->|Model Context Protocol JSON-RPC| FileSystemServer
```

## Core Protocol Features
- **Dynamic Tool Discovery:** Clients can list available tools dynamically upon server initialization.
- **Resource Management:** Read-only data resources (files, tables) can be browsed standardly.
- **Unified Security:** Authorization and sandboxing policies are decoupled from the client.
