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

Users should connect Postly through the secure connection flow.

API keys or secrets should not be pasted into normal chat prompts or passed through tool arguments.
