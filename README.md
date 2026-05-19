# Postly MCP

Official MCP server for Postly — the AI social media scheduler for ChatGPT and AI agents.

Postly helps you create, schedule, publish, and manage social media and email campaigns directly from ChatGPT. Connect your accounts, upload media, draft content, schedule campaigns, monitor publishing activity, and track analytics from one workflow.

## Demo

Watch the ChatGPT MCP demo:

https://www.youtube.com/watch?v=2wyovmoUEhU

## What you can do

- List Postly organizations and workspaces
- View connected social accounts and publishing targets
- Create, validate, schedule, update, and delete posts
- Upload or attach media
- Check scheduled posts
- Monitor publishing activity
- Fetch account and post analytics

## Supported actions

### Read-only actions

- List organizations
- List workspaces
- List social accounts
- List analytics sources
- Get account analytics
- Get post analytics
- List scheduled posts
- Get publishing activity
- List posts
- Get post details
- Get post status
- Validate posts

### Write actions

- Upload media
- Create posts
- Update posts
- Delete posts

Some write actions may publish content publicly or send messages through connected providers. Postly validates content and may require confirmation before sensitive actions.

## Example prompts

```txt
Show me my Postly organizations and workspaces.
Publish this to my Telegram channel: Launch update: our new scheduler is live.
Schedule this for tomorrow at 9 AM on my LinkedIn page: Our launch webinar starts soon.
How many posts do I have lined up for tomorrow?
What analytics are available for my Instagram account this month?
Check the status of my latest scheduled Postly post.

## Documentation

- [ChatGPT MCP Demo](docs/chatgpt-mcp-demo.md)
- [Available Tools](docs/tools.md)
- [Security & Scopes](docs/security-and-scopes.md)
