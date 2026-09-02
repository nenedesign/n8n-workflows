# Claude to Slack MCP Connection Test

A minimal 2-node utility workflow for verifying that your Claude Code MCP server can successfully connect to and post messages in Slack. Run it once after configuring your MCP setup to confirm the integration is working before building anything on top of it.

## Who it's for

**Beginner** — Anyone setting up Claude Code with MCP (Model Context Protocol) server integrations who wants a fast, no-friction way to confirm the Slack connection is live.

## Nodes used

- **Manual Trigger** — starts the workflow on demand
- **Slack** — posts a test message to a specified channel

## Requirements

| Service | Credential | Notes |
|---------|-----------|-------|
| Slack | Slack Bot token | Bot must be invited to the target channel |

Set your channel ID in the Slack node: replace `YOUR_SLACK_CHANNEL_ID` with the ID of the channel you want to post to (right-click a channel in Slack → **Copy link** → the ID is the last segment).

## How to import

1. Download `workflow.json`
2. In n8n, go to **Workflows → Add workflow → Import from file**
3. Connect your Slack credential
4. Set your channel ID in the Slack node
5. Click **Test workflow** — a message should appear in your Slack channel

## Customization

- **Change the test message:** Edit the message text in the Slack node to whatever you want to confirm is working
- **Swap to a different service:** Replace the Slack node with any other MCP-connected service (Gmail, Notion, etc.) to test that connection instead

---

Built by [Neville Ko](https://www.linkedin.com/in/nevilleko/) · [fromus.ca/ai-builds](https://www.fromus.ca/ai-builds)
