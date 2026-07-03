# Dynamic Structural Data Stores (SQL / Vector Databases)

This capability covers connecting models directly to data structures such as relational SQL engines and Vector Indexes to retrieve dynamic, structured, or semantic information.

## Access Flow

```mermaid
graph TD
    Query[User Semantic Query] --> Database{Type?}
    Database -->|Relational| TextToSQL[Generate SQL Query]
    Database -->|Vector| Embedding[Generate Search Vector]
    TextToSQL --> SQLEngine[Execute on PostgreSQL/MySQL]
    Embedding --> Index[Semantic Cosine Search]
    SQLEngine --> Result[Inject Data Records]
    Index --> Result
    Result --> Final[Formulate Context-Augmented Response]
```

## Significance
- **Real-Time Data Integration:** Bypasses parametric memory limitations.
- **Structured Operations:** Allows filter, join, and retrieval constraints.
