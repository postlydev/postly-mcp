# Postly MCP

Official MCP server for Postly, the AI social media scheduler for ChatGPT and AI agents.

Postly helps you create, schedule, publish, and manage social media and email campaigns directly from ChatGPT. Connect your accounts, upload media, draft content, schedule campaigns, monitor publishing activity, and track analytics from one workflow.

---

## Demo

### How to Connect Postly MCP to ChatGPT (Step-by-Step Setup Guide)

[![How to Connect Postly MCP to ChatGPT](https://img.youtube.com/vi/pqVyBYYhdZw/maxresdefault.jpg)](https://www.youtube.com/watch?v=pqVyBYYhdZw)

Video:
https://www.youtube.com/watch?v=pqVyBYYhdZw

### Publish to LinkedIn with ChatGPT + Postly MCP (Complete Setup & Demo)

[![Publish to LinkedIn with ChatGPT + Postly MCP](https://img.youtube.com/vi/i084A-fpcNo/maxresdefault.jpg)](https://www.youtube.com/watch?v=i084A-fpcNo)

Video:
https://www.youtube.com/watch?v=i084A-fpcNo



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
- MCP integration for ChatGPT, Claude, Gemini CLI, Windsurf, OpenClaw,
  OpenRouter-compatible gateways, and other MCP clients

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
- Generate and publish media directly

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

## Quick Start

1. Create a Postly API key in Postly.
2. Choose the MCP endpoint for your AI client.
3. Connect the client using OAuth, an `Authorization` header, or the API-key URL fallback.
4. Ask the client to list your Postly workspaces before publishing.

### Get a Postly API Key

In Postly, open:

```txt
API & MCP -> API Access -> Create API key
```

Keep the key private. Do not paste it into normal chat messages. Only paste it
into a connector authorization screen, a trusted local client config, or an
environment variable.

### Which URL Should I Use?

| Client | Recommended URL | Auth method |
| --- | --- | --- |
| ChatGPT custom app / official app | `https://mcp.postly.ai/sse` | OAuth page asks for your Postly API key |
| Claude web custom connector | `https://mcp.postly.ai/claude` | OAuth page asks for your Postly API key |
| Claude manual fallback | `https://mcp.postly.ai/claude/<postly-api-key>` | API key in URL |
| Gemini CLI | `https://mcp.postly.ai/gemini` | `Authorization: Bearer <postly-api-key>` |
| Windsurf | `https://mcp.postly.ai/windsurf` | `Authorization: Bearer <postly-api-key>` |
| OpenClaw | `https://mcp.postly.ai/openclaw` | `Authorization: Bearer <postly-api-key>` |
| OpenRouter / multi-model gateways | `https://mcp.postly.ai/openrouter` | `Authorization: Bearer <postly-api-key>` |
| Generic MCP clients | `https://mcp.postly.ai/agents` | `Authorization: Bearer <postly-api-key>` |

Use the header form when your client supports custom headers. Use the URL
fallback only when a client cannot send custom headers or does not show an OAuth
prompt.

Full setup instructions are in [Manual Connections](docs/manual-connections.md).

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

Users should authenticate using the secure Postly connection flow where
available. For manual clients, use an `Authorization` header or the documented
API-key URL fallback.

Never paste API keys or credentials directly into normal prompts.

---

## Documentation

- [ChatGPT MCP Demo](docs/chatgpt-mcp-demo.md)
- [Manual Connections](docs/manual-connections.md)
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
- [ ] OAuth improvements

---

## Status

This is the official public MCP repository for Postly.

Actively under development.

---

## License

MIT
