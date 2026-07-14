# Postly MCP

Official MCP server for Postly, the AI social media scheduler for ChatGPT and AI agents.

Postly helps you create, schedule, publish, and manage social media and email campaigns directly from ChatGPT and other MCP-compatible clients. Connect your accounts, attach media, schedule campaigns, monitor publishing activity, and track analytics from one workflow.

---

## Demo

### How to Connect Postly MCP to ChatGPT

[![How to Connect Postly MCP to ChatGPT](https://img.youtube.com/vi/pqVyBYYhdZw/maxresdefault.jpg)](https://www.youtube.com/watch?v=pqVyBYYhdZw)

Video:  
https://www.youtube.com/watch?v=pqVyBYYhdZw

### Publish to LinkedIn with ChatGPT and Postly MCP

[![Publish to LinkedIn with ChatGPT + Postly MCP](https://img.youtube.com/vi/i084A-fpcNo/maxresdefault.jpg)](https://www.youtube.com/watch?v=i084A-fpcNo)

Video:  
https://www.youtube.com/watch?v=i084A-fpcNo

---

## Features

- AI-powered social media publishing
- Multi-platform publishing workflows
- Immediate and scheduled publishing
- Campaign automation
- Flexible media ingestion
- Publishing activity and status tracking
- Workspace and organization management
- Connected account discovery
- Analytics and performance reporting
- MCP integration for ChatGPT, Claude, Gemini CLI, Windsurf, OpenClaw, OpenRouter-compatible gateways, and other MCP clients

---

## What You Can Do

### Workspace and Organization Management

- List Postly organizations
- List Postly workspaces
- Discover connected publishing targets
- View connected social and email accounts

### Publishing Workflows

- Create social media and email posts
- Publish immediately
- Schedule future posts
- Update draft or scheduled posts
- Delete draft or scheduled posts
- Validate posts before publishing
- Apply platform-specific publishing settings
- Attach generated, hosted, local, or in-memory media

### Analytics and Monitoring

- Check scheduled publishing queues
- Monitor publishing activity
- Fetch post analytics
- Fetch account analytics
- Track publishing status and delivery

---

## Supported Platforms

Postly MCP uses the Postly API as the middleware for all publishing workflows. There is no separate REST-only platform integration.

Supported connected channels include:

- Facebook
- Instagram
- LinkedIn
- TikTok
- X / Twitter
- YouTube
- Telegram
- Pinterest
- Threads
- Bluesky
- Google Business Profile
- Email and newsletter platforms
- Other channels supported by Postly

Platform-specific settings can be passed through the Postly API, including TikTok options such as AI-generated content disclosure and sharing to the feed.

API documentation:  
https://docs.postly.ai

---

## Media Handling

Postly accepts media in the formats your application, agent, CMS, automation pipeline, or AI generation tool already produces.

### Binary File Upload

Upload files directly from:

- Local disk
- Browser upload flows
- Backend services
- AI clients that can provide the generated file

Postly stores the uploaded asset and makes it available for publishing.

### Public Media URL

Provide a publicly accessible HTTPS media URL from:

- A CDN
- CMS
- DAM
- Cloud storage
- AI image or video generation service
- Other publicly accessible media hosts

Postly fetches and stores the media when the post is created or scheduled, not when the scheduled publishing time arrives.

Once the scheduling request has completed successfully, the original media URL does not need to remain available until publication.

### Base64 or Data URL

Send media already held in memory as Base64 or a data URL.

This is useful when your application or agent already has the media content and you do not want to create a separate public hosting step.

### Inline Media Import

Media can be imported, stored, and attached during post creation or post updates.

This keeps the workflow compact by allowing media ingestion and the post operation to happen within the same publishing flow.

### Supported Workflows

These media options are suitable for:

- AI-generated images and videos
- Browser and server-side uploads
- CMS and DAM integrations
- CDN-hosted assets
- Local media workflows
- Automated publishing pipelines
- Media already held in application memory

Always confirm that the post creation or scheduling request succeeded before allowing a temporary source URL to expire.

API Access supports media uploads of up to 10 GB, subject to the supported limit of the destination platform.

Media upload limits:  
https://postly.ai/resources/media-upload-limits

---

## Publishing Limits

MCP requests use the same Postly API and publishing infrastructure. There is no separate MCP publishing allowance.

Publishing is governed by Postly's daily limits for each destination platform.

Daily post limits:  
https://postly.ai/legal/daily-post-limits

---

## Supported MCP Actions

### Read-Only Actions

These tools retrieve data without publishing content or modifying Postly state.

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

These tools create or modify Postly data.

- Upload and import media
- Create posts
- Update posts
- Delete posts

Some write actions may publish content publicly or send messages through connected providers. Postly validates content and may require confirmation before sensitive actions.

---

## Quick Start

1. Create a Postly API key.
2. Choose the MCP endpoint for your AI client.
3. Connect using OAuth, an `Authorization` header, or the API-key URL fallback.
4. Ask the client to list your Postly organizations, workspaces, and connected accounts.
5. Create, schedule, or publish your first post.

### Get a Postly API Key

In Postly, open:

```txt
API & MCP -> API Access -> Create API key
````

Keep your API key private. Do not paste it into normal chat messages.

Only enter it into:

* A Postly connector authorization screen
* A trusted local MCP client configuration
* A secure environment variable

### Which URL Should I Use?

| Client                            | Recommended URL                                 | Authentication                           |
| --------------------------------- | ----------------------------------------------- | ---------------------------------------- |
| ChatGPT custom app / official app | `https://mcp.postly.ai/sse`                     | OAuth page requests your Postly API key  |
| Claude web custom connector       | `https://mcp.postly.ai/claude`                  | OAuth page requests your Postly API key  |
| Claude manual fallback            | `https://mcp.postly.ai/claude/<postly-api-key>` | API key in URL                           |
| Gemini CLI                        | `https://mcp.postly.ai/gemini`                  | `Authorization: Bearer <postly-api-key>` |
| Windsurf                          | `https://mcp.postly.ai/windsurf`                | `Authorization: Bearer <postly-api-key>` |
| OpenClaw                          | `https://mcp.postly.ai/openclaw`                | `Authorization: Bearer <postly-api-key>` |
| OpenRouter / multi-model gateways | `https://mcp.postly.ai/openrouter`              | `Authorization: Bearer <postly-api-key>` |
| Generic MCP clients               | `https://mcp.postly.ai/agents`                  | `Authorization: Bearer <postly-api-key>` |

Use the header-based method when your client supports custom headers. Use the API-key URL fallback only when the client cannot send custom headers or does not provide an OAuth prompt.

Full setup instructions are available in [Manual Connections](docs/manual-connections.md).

---

## Example Prompts

### Workspace Discovery

```txt
Show me my Postly organizations and workspaces.
```

```txt
List all my connected social media and email accounts.
```

### Publishing

```txt
Publish this update to my Telegram channel:

Our new scheduler is now live.
```

```txt
Schedule this for tomorrow at 9 AM on my LinkedIn page:

Our launch webinar starts soon.
```

```txt
Create an Instagram launch post with a cheerful image and publish it.
```

```txt
Schedule this public MP4 URL on my TikTok account for Friday at 3 PM:

https://example.com/video.mp4

Mark the video as AI-generated and share it to the feed.
```

```txt
Upload this generated video file and schedule it on Facebook and Instagram for tomorrow at 10 AM.
```

### Scheduling and Monitoring

```txt
How many posts do I have scheduled for tomorrow?
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

## Security and Permissions

Postly MCP separates tools into read-only and write-enabled actions.

### Read-Only Tools

Read-only tools:

* Never publish content
* Never modify external systems
* Never delete posts or schedules
* Only retrieve accessible workspace data

### Write Tools

Write-enabled tools may:

* Publish content publicly
* Schedule campaigns
* Upload, fetch, or import media
* Update post content
* Delete posts

Sensitive or destructive actions should be confirmed before execution.

---

## Credential Handling

Use the secure Postly connection flow whenever it is available.

For manual MCP clients, use an `Authorization` header or the documented API-key URL fallback.

Never paste API keys or credentials directly into normal prompts.

---

## Documentation

* Postly API documentation: [https://docs.postly.ai](https://docs.postly.ai)
* Daily post limits: [https://postly.ai/legal/daily-post-limits](https://postly.ai/legal/daily-post-limits)
* Media upload limits: [https://postly.ai/resources/media-upload-limits](https://postly.ai/resources/media-upload-limits)
* [ChatGPT MCP Demo](docs/chatgpt-mcp-demo.md)
* [Manual Connections](docs/manual-connections.md)
* [Available Tools](docs/tools.md)
* [Security and Scopes](docs/security-and-scopes.md)

---

## MCP Use Cases

Postly MCP can be used for:

* AI-powered social media automation
* Autonomous publishing workflows
* Marketing campaign management
* Content scheduling
* Cross-platform publishing
* Public media URL publishing
* Binary media uploads
* Base64 and data URL media ingestion
* CMS, DAM, and CDN integrations
* AI agent integrations
* Analytics reporting
* Creator workflows
* Team publishing operations

---

## Roadmap

* [ ] Expanded analytics support
* [ ] Additional social channels
* [ ] AI campaign planning workflows
* [ ] Team collaboration features
* [ ] Enhanced media workflows
* [ ] Public npm package
* [ ] OAuth improvements

---

## Status

This is the official public MCP repository for Postly.

Actively under development.

---

## License

MIT

```
