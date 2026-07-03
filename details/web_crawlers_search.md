# Web Crawlers & Real-Time Search Engines

LLMs integrated with search engines and crawlers navigate the live web to fetch documents, keeping the model context up to date with continuous real-world changes.

## Navigation flow

```mermaid
graph TD
    Query[Dynamic User Request] --> Search[API Search query]
    Search --> Links[Get Organic Results list]
    Links --> Scraping[Fetch Page HTML]
    Scraping --> Markdown[Convert HTML to semantic markdown]
    Markdown --> LLMContext[Inject into LLM Prompt]
```

## Features
- **Temporal Alignment:** Avoids limitations caused by model knowledge cutoff.
- **Fact Verification:** Cross-references assertions against online directories.
