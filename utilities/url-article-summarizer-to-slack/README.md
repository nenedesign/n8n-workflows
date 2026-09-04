# URL & Article Summarizer to Slack

Send any article URL to this webhook and get an AI-generated summary posted to your Slack channel in seconds.

## What it does

Receives a URL via webhook, fetches the page HTML, summarizes the content using OpenAI, and posts the result to Slack. The webhook also returns the summary as JSON for programmatic use.

## Who it's for

**Beginner–Intermediate** — Researchers, content teams, and developers who want to quickly digest articles without reading them in full.

## Nodes used

- Webhook
- Edit Fields (Set)
- HTTP Request
- OpenAI Chat Model
- AI Agent
- Slack
- Respond to Webhook

## Requirements

- OpenAI API key
- Slack workspace with a Bot OAuth token
- n8n instance (self-hosted or cloud)

## How to import

1. Download `workflow.json`
2. Open n8n and go to **Workflows → Import from file**
3. Select the downloaded file

## How to use

Activate the workflow and send a POST request to the webhook URL:

```bash
curl -X POST YOUR_WEBHOOK_URL \
  -H "Content-Type: application/json" \
  -d '{"url": "https://example.com/article"}'
```

## Customization

- Swap OpenAI for Anthropic or Gemini by replacing the Chat Model node
- Edit the system message in "Summarize Content" to change the summary length or tone
- Add a second Slack node to post to a different channel based on the URL domain

---

Built by Neville Ko
