# Postly MCP

Official MCP server for Postly — the AI social media scheduler for ChatGPT and AI agents.

Postly helps you create, schedule, publish, and manage social media and email campaigns directly from ChatGPT. Connect your accounts, upload media, draft content, schedule campaigns, monitor publishing activity, and track analytics from one workflow.

---

## Demo

Watch the official ChatGPT MCP demo:

[![Watch Demo](https://img.youtube.com/vi/2wyovmoUEhU/maxresdefault.jpg)](https://www.youtube.com/watch?v=2wyovmoUEhU)

Video:
https://www.youtube.com/watch?v=2wyovmoUEhU

---

## Features

- AI-powered social media publishing
- Multi-platform publishing workflows
- Post scheduling and campaign automation
- Media upload and attachment support
- Publishing activity tracking
- Workspace and organization management
- Social account discovery
- Analytics and performance reporting
- MCP integration for ChatGPT, Claude, Cursor, and AI agents

---

## What You Can Do

### Workspace & Organization Management

- List Postly organizations
- List Postly workspaces
- Discover connected publishing targets
- View connected social and email accounts

### Publishing Workflows

- Create social posts
- Schedule future posts
- Update existing posts
- Delete draft or scheduled posts
- Validate posts before publishing
- Upload and attach media

### Analytics & Monitoring

- Check scheduled publishing queues
- Monitor publishing activity
- Fetch post analytics
- Fetch account analytics
- Track publishing status and delivery

---

## Supported Platforms

Postly supports social and communication workflows across connected channels including:

- LinkedIn
- Instagram
- Facebook
- X / Twitter
- Telegram
- Email & newsletters
- Additional supported Postly channels

---

## Supported MCP Actions

### Read-Only Actions

These tools only retrieve data and do not modify external systems or publish content.

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
- Resolve publishing targets
- Get channel schema

### Write Actions

These tools create or modify Postly state.

- Upload media
- Create posts
- Update posts
- Delete posts

Some write actions may publish content publicly or send messages through connected providers. Postly validates content and may require confirmation before sensitive actions.

---

## Example Prompts

### Workspace Discovery

```txt
Show me my Postly organizations and workspaces.
```

```txt
List my connected Telegram and LinkedIn accounts.
```

### Publishing

```txt
Publish this to my Telegram channel:

Launch update: our new scheduler is live.
```

```txt
Schedule this for tomorrow at 9 AM on my LinkedIn page:

Our launch webinar starts soon.
```

```txt
Create an Instagram launch post with a cheerful image and publish it.
```

### Scheduling & Monitoring

```txt
How many posts do I have lined up for tomorrow?
```

```txt
Show me today's publishing activity.
```

```txt
Check the status of my latest scheduled Postly post.
```

### Analytics

```txt
What analytics are available for my Instagram account this month?
```

```txt
Show me analytics for my latest LinkedIn campaign.
```

---

## Security & Permissions

Postly MCP separates tools into read-only and write-enabled actions.

### Read-Only Tools

Read-only tools:

- Never publish content
- Never modify external systems
- Never delete posts or schedules
- Only retrieve accessible workspace data

### Write Tools

Write-enabled tools may:

- Publish content publicly
- Schedule campaigns
- Upload media
- Update post content
- Delete posts

Sensitive or destructive actions should always be confirmed before execution.

---

## Credential Handling

Users should authenticate using the secure Postly connection flow.

Never paste API keys or credentials directly into prompts.

---

## Documentation

- [ChatGPT MCP Demo](docs/chatgpt-mcp-demo.md)
- [Available Tools](docs/tools.md)
- [Security & Scopes](docs/security-and-scopes.md)

---

## MCP Use Cases

Postly MCP can be used for:

- AI-powered social media automation
- Marketing campaign management
- Content scheduling workflows
- Cross-platform publishing
- AI agent integrations
- Analytics reporting
- Creator workflows
- Team publishing operations

---

## Roadmap

- [ ] Expanded analytics support
- [ ] Additional social channels
- [ ] AI campaign planning workflows
- [ ] Team collaboration features
- [ ] Enhanced media workflows
- [ ] Public npm package
- [ ] Hosted MCP endpoint
- [ ] OAuth improvements

---

## Status

This is the official public MCP repository for Postly.

Actively under development.

---

## License

MIT
