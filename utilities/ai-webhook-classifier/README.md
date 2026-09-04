# AI Webhook Classifier

POST any text to this webhook and get back a structured JSON classification: category, priority, confidence score, and one-sentence summary.

## What it does

Receives a text payload via webhook, runs it through OpenAI using a structured output parser, and returns a clean JSON object. No regex or post-processing needed — the model returns valid JSON every time thanks to schema enforcement.

## Who it's for

**Intermediate** — Developers building support triage systems, content routers, or any pipeline that needs AI-powered categorization at the API boundary.

## Nodes used

- Webhook
- Edit Fields (Set)
- OpenAI Chat Model
- Structured Output Parser
- AI Agent
- Respond to Webhook

## Requirements

- OpenAI API key
- n8n instance (self-hosted or cloud)

## How to import

1. Download `workflow.json`
2. Open n8n and go to **Workflows → Import from file**
3. Select the downloaded file

## Setup

1. Connect your OpenAI credential to the OpenAI Chat Model node
2. Activate the workflow and note the webhook URL
3. POST a request to test it:

```bash
curl -X POST YOUR_WEBHOOK_URL \
  -H "Content-Type: application/json" \
  -d '{"text": "I cannot log in after resetting my password"}'
```

**Example response:**
```json
{
  "success": true,
  "text": "I cannot log in after resetting my password",
  "classification": {
    "category": "technical",
    "priority": "high",
    "confidence": 0.95,
    "summary": "User is locked out after a password reset"
  }
}
```

## Customization

- Edit the categories and priorities in the system message and JSON schema to match your use case
- Add a Slack or email node after "Classify Request" to route high-priority items automatically
- Swap OpenAI for Anthropic or Gemini by replacing the Chat Model node

---

Built by Neville Ko
