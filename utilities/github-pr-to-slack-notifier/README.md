# GitHub PR to Slack Notifier

Get a Slack notification every time a pull request is opened, merged, or closed in your GitHub repository.

## What it does

Listens for GitHub pull request events and posts a formatted message to Slack with the PR title, status (opened/merged/closed), author, and a direct link. Automatically distinguishes merged PRs from closed-without-merging ones.

## Who it's for

**Beginner** — Engineering teams who want PR activity surfaced in Slack without switching to GitHub constantly.

## Nodes used

- GitHub Trigger
- Edit Fields (Set)
- Slack

## Requirements

- GitHub Personal Access Token or OAuth app with `repo` scope
- Slack workspace with a Bot OAuth token
- n8n instance (self-hosted or cloud) with a public URL for the GitHub webhook

## How to import

1. Download `workflow.json`
2. Open n8n and go to **Workflows → Import from file**
3. Select the downloaded file

## Setup

1. Connect your GitHub credential to "On Pull Request Event"
2. Set your repository owner and name in the trigger node
3. Connect your Slack Bot credential
4. Set your Slack channel ID in "Post PR Notification"
5. Activate the workflow — n8n registers the webhook with GitHub automatically

## Customization

- Add more GitHub events (issues, push, releases) by editing the events list in the trigger
- Filter by PR action (opened only, merged only) using an IF node before the Slack node
- Post to different Slack channels based on the repository using a Switch node

---

Built by Neville Ko
