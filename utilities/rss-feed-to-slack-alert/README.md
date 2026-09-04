# RSS Feed to Slack Alert

Monitor any RSS feed and get a Slack notification whenever a new article matches your keyword.

## What it does

Polls an RSS feed every hour. When a new item's title or content contains your keyword, it posts the article title and link to your Slack channel. Non-matching articles are silently skipped.

## Who it's for

**Beginner** — Marketers, researchers, and developers who want to track topics across news feeds, blogs, or podcasts without manually checking them.

## Nodes used

- RSS Feed Trigger
- If
- Slack

## Requirements

- Any publicly accessible RSS feed URL
- Slack workspace with a Bot OAuth token
- n8n instance (self-hosted or cloud)

## How to import

1. Download `workflow.json`
2. Open n8n and go to **Workflows → Import from file**
3. Select the downloaded file

## Setup

1. Open "Poll RSS Feed" and set your RSS feed URL
2. Open "Matches Keyword?" and replace `YOUR_KEYWORD` in the rightValue field with your keyword
3. Connect your Slack Bot credential
4. Set your Slack channel ID in "Post Article to Slack"
5. Activate the workflow

## Customization

- Monitor multiple feeds by duplicating the RSS trigger and merging outputs before the IF node
- Add OR conditions to match any of several keywords
- Change the poll interval in the trigger node (every hour, every day, etc.)

---

Built by Neville Ko
