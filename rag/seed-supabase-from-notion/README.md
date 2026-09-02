# Seed a Supabase AI Knowledge Base from Notion with Ollama Embeddings

Automatically ingests pages from a Notion database into a Supabase vector store using locally-run Ollama embeddings. Once seeded, the knowledge base is ready for use with any n8n RAG or agentic workflow.

## Who it's for

**Intermediate** — Teams and individuals who want to turn a Notion workspace into a queryable AI knowledge base without sending data to external embedding APIs.

## Nodes used

- **Notion** — reads pages from a specified database
- **Ollama Embeddings** — generates vector embeddings locally (no cloud API required)
- **Supabase Vector Store** — inserts embedded documents into a Postgres vector table
- **Character Text Splitter** — chunks long documents before embedding

## Requirements

| Service | Credential | Notes |
|---------|-----------|-------|
| Notion | Notion API key | Create an internal integration at notion.so/my-integrations |
| Supabase | Supabase API key | Free tier sufficient |
| Ollama | None | Must be running locally; default model: `nomic-embed-text` |

**Supabase table required:** Run the SQL setup in your Supabase SQL editor before activating. The schema is included in the sticky note on the canvas.

## How to import

1. Download `workflow.json`
2. In n8n, go to **Workflows → Add workflow → Import from file**
3. Connect your Notion, Supabase credentials and confirm Ollama is running at `http://localhost:11434`

## Customization

- **Swap the embedding model:** Open the Ollama Embeddings node and change the model name (e.g. `mxbai-embed-large`)
- **Filter Notion pages:** Add a filter in the Notion node to ingest only specific database views or tags
- **Multiple databases:** Duplicate the workflow and point each copy at a different Notion database to build separate knowledge bases

---

Built by [Neville Ko](https://www.linkedin.com/in/nevilleko/) · [fromus.ca/ai-builds](https://www.fromus.ca/ai-builds)
