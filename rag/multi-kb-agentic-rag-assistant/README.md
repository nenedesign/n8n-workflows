# Multi-Knowledge Base Agentic RAG Assistant with n8n, Supabase and Ollama

A production-ready agentic RAG assistant that queries multiple Supabase vector stores simultaneously and routes answers through an AI agent. The agent autonomously selects which knowledge base to search based on the query, returns a grounded answer with source citations, and falls back gracefully when no relevant content is found.

Also published on the [n8n marketplace](https://n8n.io/creators/).

## Who it's for

**Advanced** — Developers and teams building internal AI assistants that need to query across multiple knowledge domains (e.g. product docs, HR policies, technical references) from a single chat interface.

## Nodes used

- **Chat Trigger** — built-in n8n chat interface for testing
- **AI Agent** — orchestrates tool selection and response generation
- **Ollama Chat Model** — local LLM inference (no cloud API required)
- **Ollama Embeddings** — local embedding generation
- **Supabase Vector Store** (×3) — one per knowledge base, configured as agent tools
- **Postgres Chat Memory** — persists conversation history across sessions
- **Window Buffer Memory** — maintains short-term context window

## Requirements

| Service | Credential | Notes |
|---------|-----------|-------|
| Supabase | Supabase API key | 3 separate vector tables required |
| Postgres | Postgres connection | For chat memory (can reuse Supabase Postgres) |
| Ollama | None | Must be running locally; models: `qwen2.5:7b` + `nomic-embed-text` |

**Supabase tables required:** Three vector store tables (Primary, Secondary, Reference KB). SQL schema is included in the canvas sticky notes.

## How to import

1. Download `workflow.json`
2. In n8n, go to **Workflows → Add workflow → Import from file**
3. Connect Supabase, Postgres credentials and confirm Ollama is running at `http://localhost:11434`
4. Seed each knowledge base using the companion seeding workflow

## Customization

- **Swap the LLM:** Replace the Ollama Chat Model node with an OpenAI, Anthropic, or Gemini node — no other changes needed
- **Add a knowledge base:** Duplicate any Supabase Vector Store tool node and connect it to the agent's Tool input
- **Change the trigger:** Replace the Chat Trigger with a Webhook, Slack Trigger, or Gmail Trigger for production deployment

---

Built by [Neville Ko](https://www.linkedin.com/in/nevilleko/) · [fromus.ca/ai-builds](https://www.fromus.ca/ai-builds)
