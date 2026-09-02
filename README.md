# n8n Workflow Templates

> AI Product Manager, Builder & Strategist — 20 years shipping 0-to-1 products, now building production-grade AI automation with n8n.

I'm Neville Ko, currently Head of Product & Experience at [Distinct AI](https://www.distinct.ai/) and an [official n8n creator](https://n8n.io/creators/](https://n8n.io/workflows/18427-seed-a-supabase-ai-knowledge-base-from-notion-with-ollama-embeddings/) with a published template on the n8n marketplace (more templates pending n8n approval). This repo contains workflow templates I've built across agentic RAG, AI agents, and developer utilities — designed to be imported directly into n8n and adapted for real use cases.

**Links:** [Portfolio](https://www.fromus.ca/ai-builds) · [LinkedIn](https://www.linkedin.com/in/nevilleko/) · [n8n Marketplace](https://n8n.io/creators/)

---

## Workflows

| Workflow | Category | Level | Description |
|----------|----------|-------|-------------|
| [Seed a Supabase AI knowledge base from Notion](./rag/seed-supabase-from-notion/) | RAG | Intermediate | Ingest Notion pages into a Supabase vector store using local Ollama embeddings |
| [Multi-KB agentic RAG assistant](./rag/multi-kb-agentic-rag-assistant/) | RAG | Advanced | AI agent that queries multiple knowledge bases and returns grounded answers with source citations — published on n8n marketplace |
| [Autonomous customer support agent](./ai-agents/autonomous-customer-support-agent/) | AI Agents | Advanced | 50-node production agent: multi-KB RAG, web search fallback, confidence-gated escalation, PII scrubbing, audit logging |
| [Slack Gemini Agent](./ai-agents/slack-gemini-agent/) | AI Agents | Intermediate | Gemini-powered Slack bot with live tools: weather, news, stock quotes, Wikipedia, and calculations |
| [Claude to Slack MCP Connection Test](./utilities/claude-to-slack-mcp-test/) | Utilities | Beginner | 2-node utility to verify your Claude Code MCP → Slack connection is working |

---

## How to Import Any Workflow

1. Download the `workflow.json` from any workflow folder
2. In n8n, go to **Workflows → Add workflow → Import from file**
3. Connect your credentials in the n8n UI
4. Read the workflow's `README.md` for setup details and required services

---

## What These Workflows Demonstrate

- **Agentic RAG** — multi-knowledge base routing with confidence-gated escalation
- **Production security** — API key auth, rate limiting, deduplication, PII scrubbing
- **Async webhook architecture** — 202 Accepted pattern with multi-channel delivery (Slack, email, HTTP callback)
- **Local-first AI** — Ollama for LLM inference and embeddings; no cloud API required
- **Vector embeddings and semantic search** — Supabase pgvector with nomic-embed-text
- **Human-in-the-loop escalation** — business-hours routing and off-hours queuing

---

## Research Focus

Applied research and hands-on builds at [fromus.ca/ai-builds](https://www.fromus.ca/ai-builds):

- **Multi-Agent Orchestration** — modality-agnostic, agent-to-agent workflows focused on security and privacy
- **Privacy-First Local AI** — on-device open-weight models designed to secure sensitive financial and healthcare data
- **Context & Memory Management** — hybrid memory retrieval for context-aware user personalization
- **Hybrid Inference Routing** — optimizing token efficiency, latency, and cost across cloud and local environments

---

## What I'm Building Next — AI Governance Framework

The next series of builds targets governance-aware AI systems for regulated industries (financial services, healthcare). Each workflow will be mapped to a real regulatory framework:

| Pillar | Regulatory Anchor | Technical Approach |
|--------|------------------|--------------------|
| **Alignment** | SEC/FINRA, OSFI E-23, OWASP LLM Top 10 | System prompt enforcement, PreToolUse validation hooks, non-custodial mock testing |
| **Control** | ISO 27001 Least Privilege | Tool permission allowlists, ephemeral Devcontainers, no production DB writes |
| **Visibility** | SOC 2 Type II, non-repudiation tracing | OTel audit logs, AI proxy (LiteLLM/Portkey), prompt hashes, SSO identity |
| **Security** | PCI-DSS v4.0, SOC 2 PII | PreToolUse DLP hooks, local file blocklists, Anthropic Zero Data Retention |
| **Societal & Legal** | SOC 2, software supply chain | Pre-commit secret scanning (gitleaks), mandatory HITL PR signing, CI/CD static analysis |

---

## Stack

**Automation & Agents:** `n8n` · `Claude Code` · `MCP Servers` · `LangChain` · `Google ADK`

**Inference & Models:** `Ollama` · `Docker` · `OpenRouter` · `Claude API` · `Gemini API` · `Perplexity API`

**Data & Storage:** `Supabase` · `Postgres` · `Notion` · `Obsidian` · `Open WebUI`

**Prototyping:** `Figma` · `Lovable` · `Cursor` · `VS Code`

---

*All workflows are free of personal credentials and account-specific data. Placeholder values are clearly labeled (e.g. `YOUR_SLACK_CHANNEL_ID`). MIT licensed — use and adapt freely.*
