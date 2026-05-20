# Security and Tool Scopes

Postly MCP tools are annotated by risk level.

## Read-only tools

These tools only retrieve information from Postly and do not publish, modify, delete, or change external state.

Examples:

- list organizations
- list workspaces
- list social accounts
- list scheduled posts
- get analytics
- get post status
- validate post content

## Write tools

These tools create or modify Postly state.

- `postly.upload_media`
- `postly.create_post`
- `postly.update_post`
- `postly.delete_post`

## Public or external effects

Some tools can affect public or third-party systems.

- `postly.create_post` can publish or schedule social/email content.
- `postly.update_post` can overwrite post content, media, targeting, or schedule.
- `postly.delete_post` removes a Postly post record.
- `postly.upload_media` may create a Postly-hosted media URL.

## Credential handling

Users should connect Postly through the secure connection flow when the client
supports it.

API keys or secrets should not be pasted into normal chat prompts or passed
through tool arguments.

For manual clients, prefer:

```txt
Authorization: Bearer <postly-api-key>
```

Some clients do not support custom headers or do not show an OAuth prompt. In
those cases, Postly also supports API-key URL fallbacks such as:

```txt
https://mcp.postly.ai/claude/<postly-api-key>
https://mcp.postly.ai/agents/<postly-api-key>
```

Only use URL fallbacks inside trusted MCP connector configuration screens. If a
client supports environment variables or secret interpolation, use that instead
of storing the key directly in a config file.
