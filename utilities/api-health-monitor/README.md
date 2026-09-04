# API Health Monitor

Monitor a list of HTTP endpoints on a schedule and get a Slack alert whenever one goes down.

## What it does

Runs every hour, pings each endpoint in your list, and sends a Slack message with the failing URL and error details if any request fails. Healthy endpoints produce no output.

## Who it's for

**Beginner** — Developers and ops teams who need simple uptime monitoring without a dedicated monitoring service.

## Nodes used

- Schedule Trigger
- Code
- HTTP Request
- If
- Slack

## Requirements

- Slack workspace with a Bot OAuth token
- n8n instance (self-hosted or cloud)

## How to import

1. Download `workflow.json`
2. Open n8n and go to **Workflows → Import from file**
3. Select the downloaded file

## Setup

1. Open the "Define Endpoints to Monitor" Code node and replace the placeholder names and URLs with your real endpoints
2. Connect your Slack Bot credential
3. Set your Slack channel ID in "Send Down Alert"
4. Activate the workflow

## Customization

- Change the check interval in "Run Health Checks Hourly" (every 5 minutes, every 15 minutes, etc.)
- Add more endpoints by adding more items to the Code node array
- Switch from GET to POST for endpoints that require a specific method

---

Built by Neville Ko
