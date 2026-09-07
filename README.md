# n8n Workflow Templates

> AI Product Manager, Builder and Strategist: 20 years shipping 0-to-1 products, now building production-grade AI automation with n8n.

I'm Neville Ko, currently Head of Product & Experience at [Distinct AI](https://www.distinctplugins.io/) and an [official n8n creator](https://n8n.io/creators/nene/) with published templates on the n8n marketplace. This repo contains workflow templates I've built across agentic RAG, AI agents, and developer utilities, designed to be imported directly into n8n and adapted for real use cases.

**Links:** [Portfolio](https://www.fromus.ca/ai-builds) · [LinkedIn](https://www.linkedin.com/in/nevilleko/) · [n8n Marketplace](https://n8n.io/creators/)

---

## Workflows

| Workflow | Category | Level | Description |
|----------|----------|-------|-------------|
| [Seed a Supabase AI knowledge base from Notion](./rag/seed-supabase-from-notion/) | RAG | Intermediate | Ingest Notion pages into a Supabase vector store using local Ollama embeddings |
| [Multi-KB agentic RAG assistant](./rag/multi-kb-agentic-rag-assistant/) | RAG | Advanced | AI agent that queries multiple knowledge bases and returns grounded answers with source citations (published on n8n marketplace) |
| [Autonomous customer support agent](./ai-agents/autonomous-customer-support-agent/) | AI Agents | Advanced | 50-node production agent: multi-KB RAG, web search fallback, confidence-gated escalation, PII scrubbing, audit logging |
| [Slack Gemini Agent](./ai-agents/slack-gemini-agent/) | AI Agents | Intermediate | Gemini-powered Slack bot with live tools: weather, news, stock quotes, Wikipedia, and calculations |
| [Gmail AI Triage](./ai-agents/gmail-ai-triage/) | AI Agents | Intermediate | AI agent that classifies unread emails and applies labels or marks as read (runs on local Ollama) |
| [AI Daily Briefing Bot](./utilities/ai-daily-briefing-bot/) | Utilities | Beginner | Fetches top stories from 3 RSS feeds, summarizes with Ollama, and posts a morning briefing to Slack |
| [Claude to Slack MCP Connection Test](./utilities/claude-to-slack-mcp-test/) | Utilities | Beginner | 2-node utility to verify your Claude Code MCP connection to Slack is working |
| [URL and Article Summarizer to Slack](./utilities/url-article-summarizer-to-slack/) | Utilities | Beginner | POST any URL and get an AI-generated article summary posted to Slack |
| [API Health Monitor](./utilities/api-health-monitor/) | Utilities | Beginner | Monitor a list of HTTP endpoints on a schedule and alert Slack when one goes down |
| [RSS Feed to Slack Alert](./utilities/rss-feed-to-slack-alert/) | Utilities | Beginner | Poll an RSS feed and post matching articles to Slack when your keyword appears |
| [GitHub PR to Slack Notifier](./utilities/github-pr-to-slack-notifier/) | Utilities | Beginner | Post a Slack notification when a GitHub pull request is opened, merged, or closed |
| [AI Webhook Classifier](./utilities/ai-webhook-classifier/) | Utilities | Intermediate | POST any text and get back a structured JSON classification: category, priority, confidence, summary |

---

## How to Import Any Workflow

1. Download the `workflow.json` from any workflow folder
2. In n8n, go to **Workflows → Add workflow → Import from file**
3. Connect your credentials in the n8n UI
4. Read the workflow's `README.md` for setup details and required services

---

## What These Workflows Demonstrate

- **Agentic RAG:** multi-knowledge base routing with confidence-gated escalation
- **Production security:** API key auth, rate limiting, deduplication, PII scrubbing
- **Async webhook architecture:** 202 Accepted pattern with multi-channel delivery (Slack, email, HTTP callback)
- **Local-first AI:** Ollama for LLM inference and embeddings; no cloud API required
- **Vector embeddings and semantic search:** Supabase pgvector with nomic-embed-text
- **Human-in-the-loop escalation:** business-hours routing and off-hours queuing

---

## Also Built: AI Governance for Regulated Industries

Working implementations of all 10 OWASP LLM risks for financial services, insurance, and legal tech. Includes n8n workflows, system prompt library, and governance checklists mapped to SEC/FINRA, OSFI E-23, SOC 2, and PCI-DSS v4.0.

[View the ai-governance-owasp10 repo](https://github.com/nenedesign/ai-governance-owasp10) · [View the ai-governance-pci-dss repo](https://github.com/nenedesign/ai-governance-pci-dss) · [View the ai-governance-soc2 repo](https://github.com/nenedesign/ai-governance-soc2)

---

## Research Focus

Applied research and hands-on builds at [fromus.ca/ai-builds](https://www.fromus.ca/ai-builds):

- **Multi-Agent Orchestration:** modality-agnostic, agent-to-agent workflows focused on security and privacy
- **Privacy-First Local AI:** on-device open-weight models designed to secure sensitive financial and healthcare data
- **Context and Memory Management:** hybrid memory retrieval for context-aware user personalization
- **Hybrid Inference Routing:** optimizing token efficiency, latency, and cost across cloud and local environments

---

## Stack

**Automation and Agents:** `n8n` · `Claude Code` · `MCP Servers` · `LangChain` · `Google ADK`

**Inference and Models:** `Ollama` · `Docker` · `OpenRouter` · `Claude API` · `Gemini API` · `Perplexity API`

**Data and Storage:** `Supabase` · `Postgres` · `Notion` · `Obsidian` · `Open WebUI`

**Prototyping:** `Figma` · `Lovable` · `Cursor` · `VS Code`

---

*All workflows are free of personal credentials and account-specific data. Placeholder values are clearly labeled (e.g. `YOUR_SLACK_CHANNEL_ID`). MIT licensed; use and adapt freely.*
