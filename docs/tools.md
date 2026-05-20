# Postly MCP Tools

Tool names may appear in two forms depending on the client.

Standard endpoints such as `/sse` expose dotted names:

```txt
postly.list_workspaces
```

Claude-safe and agent-safe endpoints such as `/claude`, `/gemini`, `/windsurf`,
`/openclaw`, and `/agents` expose underscore names:

```txt
postly_list_workspaces
```

The tools are the same. Only the names change to satisfy stricter client
validators.

## Workspace and account discovery

- `postly.list_organizations`
- `postly.list_workspaces`
- `postly.list_social_accounts`
- `postly.resolve_publishing_targets`

## Validation and schemas

- `postly.get_channel_schema`
- `postly.validate_post`

## Publishing and media

- `postly.upload_media`
- `postly.create_post`
- `postly.update_post`
- `postly.delete_post`

## Scheduling and activity

- `postly.list_scheduled_posts`
- `postly.get_publishing_activity`
- `postly.list_posts`
- `postly.get_post`
- `postly.get_post_status`

## Analytics

- `postly.list_analytics_sources`
- `postly.get_account_analytics`
- `postly.get_post_analytics`
