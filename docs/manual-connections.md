# Manual Connections

Use this guide when Postly is not available as a one-click app inside your AI
client yet, or when you are testing a custom MCP setup.

## Before You Start

You need a Postly API key.

In Postly, open:

```txt
API & MCP -> API Access -> Create API key
```

Copy the key once and keep it private. Do not paste it into ordinary chat
messages. Use it only in an authorization page, a trusted MCP client config, or
an environment variable.

## Endpoint Summary

| Client | URL |
| --- | --- |
| ChatGPT | `https://mcp.postly.ai/sse` |
| Claude | `https://mcp.postly.ai/claude` |
| Gemini CLI | `https://mcp.postly.ai/gemini` |
| Windsurf | `https://mcp.postly.ai/windsurf` |
| OpenClaw | `https://mcp.postly.ai/openclaw` |
| OpenRouter gateways | `https://mcp.postly.ai/openrouter` |
| Hermes | `https://mcp.postly.ai/hermes` |
| Cabinet | `https://mcp.postly.ai/cabinet` |
| NanoClaw | `https://mcp.postly.ai/nanoclaw` |
| Other MCP clients | `https://mcp.postly.ai/agents` |

The Claude, Gemini, Windsurf, OpenRouter, Hermes, Cabinet, OpenClaw, NanoClaw,
and generic agent endpoints expose Claude-safe tool names such as
`postly_list_workspaces` instead of dotted names like
`postly.list_workspaces`.

## ChatGPT

### App Flow

1. Open ChatGPT.
2. Go to Apps or Connectors.
3. Choose Postly.
4. Connect your Postly account.
5. Paste your Postly API key when Postly asks for it.

### Developer Mode / Custom App Testing

For internal testing:

1. Enable ChatGPT Developer Mode if your workspace supports it.
2. Create a custom app or MCP connector.
3. Use this MCP server URL:

```txt
https://mcp.postly.ai/sse
```

4. Choose OAuth authentication.
5. When Postly opens the authorization page, paste your Postly API key.
6. Finish the connection and start a new chat.

Try:

```txt
Show me my Postly organizations, workspaces, and publishing targets.
```

## Claude

Claude supports remote MCP custom connectors. Use the Claude endpoint:

```txt
https://mcp.postly.ai/claude
```

For individual Claude accounts:

1. Open Claude.
2. Go to Customize -> Connectors.
3. Click `+` or `Add custom connector`.
4. Name it `Postly`.
5. Paste the URL above.
6. Connect and paste your Postly API key on the Postly authorization page.
7. In a new chat, enable the Postly connector from the connector/tools menu.

For Claude Team or Enterprise workspaces, an owner may need to add the custom
connector first from Organization settings -> Connectors. Team members can then
connect it from Customize -> Connectors.

### Claude Manual Fallback

If Claude pulls the tools but never shows the Postly API-key authorization page,
use the API-key URL fallback:

```txt
https://mcp.postly.ai/claude/<postly-api-key>
```

Example shape:

```txt
https://mcp.postly.ai/claude/pk_live_xxxxxxxxxxxxxxxxx
```

Only use this fallback in a trusted Claude connector screen. Prefer the OAuth
URL whenever Claude shows the authorization flow.

## Gemini CLI

Gemini CLI supports remote MCP servers over HTTP and headers.

Recommended command:

```sh
gemini mcp add --scope user --transport http --header "Authorization: Bearer <postly-api-key>" postly https://mcp.postly.ai/gemini
```

Then verify:

```sh
gemini mcp list
```

Start Gemini CLI and ask:

```txt
Use Postly to list my workspaces and publishing targets.
```

### Important Scope Note

`--scope user` saves the server in your user Gemini config so it is available
from any folder.

If you intentionally use project scope, run the command from the actual project
folder, not your home folder:

```sh
gemini mcp add --scope project --transport http --header "Authorization: Bearer <postly-api-key>" postly https://mcp.postly.ai/gemini
```

If Gemini says no MCP servers are configured, run:

```sh
gemini mcp list
```

from the same scope/folder where you added the server, or add it again with
`--scope user`.

## Windsurf

Windsurf can connect to remote HTTP MCP servers from Cascade MCP settings.

Use this configuration:

```json
{
  "mcpServers": {
    "postly": {
      "serverUrl": "https://mcp.postly.ai/windsurf",
      "headers": {
        "Authorization": "Bearer <postly-api-key>"
      }
    }
  }
}
```

Windsurf also supports reading sensitive values from environment variables. If
you prefer that, set `POSTLY_API_KEY` locally and use:

```json
{
  "mcpServers": {
    "postly": {
      "serverUrl": "https://mcp.postly.ai/windsurf",
      "headers": {
        "Authorization": "Bearer ${env:POSTLY_API_KEY}"
      }
    }
  }
}
```

After saving, restart or refresh Cascade MCP tools and ask:

```txt
Use Postly to show my connected publishing targets.
```

## OpenClaw

OpenClaw stores outgoing MCP server definitions with `openclaw mcp set`.

Use:

```sh
openclaw mcp set postly '{"url":"https://mcp.postly.ai/openclaw","transport":"streamable-http","headers":{"Authorization":"Bearer <postly-api-key>"}}'
```

Check it:

```sh
openclaw mcp list
openclaw mcp show postly --json
```

OpenClaw stores the server definition. The runtime or adapter that OpenClaw
launches is responsible for connecting to it.

## OpenRouter and Multi-Model Gateways

Use this endpoint when a gateway supports remote MCP tools:

```txt
https://mcp.postly.ai/openrouter
```

Send:

```txt
Authorization: Bearer <postly-api-key>
```

If the gateway expects a JSON server definition, use this shape:

```json
{
  "name": "postly",
  "url": "https://mcp.postly.ai/openrouter",
  "transport": "streamable-http",
  "headers": {
    "Authorization": "Bearer <postly-api-key>"
  }
}
```

## Generic MCP Clients

For clients that support remote HTTP MCP servers:

```json
{
  "mcp": {
    "servers": {
      "postly": {
        "url": "https://mcp.postly.ai/agents",
        "transport": "streamable-http",
        "headers": {
          "Authorization": "Bearer <postly-api-key>"
        }
      }
    }
  }
}
```

If your client cannot send headers, use the path fallback:

```txt
https://mcp.postly.ai/agents/<postly-api-key>
```

Client-specific path fallbacks also work:

```txt
https://mcp.postly.ai/gemini/<postly-api-key>
https://mcp.postly.ai/windsurf/<postly-api-key>
https://mcp.postly.ai/openclaw/<postly-api-key>
https://mcp.postly.ai/openrouter/<postly-api-key>
https://mcp.postly.ai/hermes/<postly-api-key>
https://mcp.postly.ai/cabinet/<postly-api-key>
https://mcp.postly.ai/nanoclaw/<postly-api-key>
```

## First Prompts To Test

After connecting, test with read-only prompts first:

```txt
Show me my Postly organizations and workspaces.
```

```txt
List my connected publishing targets.
```

```txt
How many posts do I have scheduled for tomorrow?
```

Then test publishing:

```txt
Create a draft post in Postly for my Telegram test channel saying:
This is a Postly MCP test.
```

If you want to publish publicly, say so clearly and name the target:

```txt
Publish this to my Test Channel on Telegram:
This is a Postly MCP test.
```

## Troubleshooting

### The client connects but cannot see tools

Use the client-specific endpoint, not always `/sse`.

For Claude, use:

```txt
https://mcp.postly.ai/claude
```

For Gemini CLI, use:

```txt
https://mcp.postly.ai/gemini
```

### Gemini says no MCP servers are configured

You probably added the server in project scope from a different folder. Add it
with user scope:

```sh
gemini mcp add --scope user --transport http --header "Authorization: Bearer <postly-api-key>" postly https://mcp.postly.ai/gemini
```

### Claude does not ask for an API key

Use the fallback URL:

```txt
https://mcp.postly.ai/claude/<postly-api-key>
```

### The client rejects tool names

Use one of the non-dotted endpoints:

```txt
https://mcp.postly.ai/claude
https://mcp.postly.ai/gemini
https://mcp.postly.ai/windsurf
https://mcp.postly.ai/openclaw
https://mcp.postly.ai/agents
```

### Media upload fails

Ask the AI client to pass attached or generated files directly to Postly through
the create/update post action. Do not ask users to upload generated images to
another hosting service first unless the client cannot pass files to MCP tools.

## References

- ChatGPT Developer Mode: https://platform.openai.com/docs/developer-mode
- Claude custom connectors: https://support.claude.com/en/articles/11175166-get-started-with-custom-connectors-using-remote-mcp
- Gemini CLI MCP servers: https://google-gemini.github.io/gemini-cli/docs/tools/mcp-server.html
- Windsurf Cascade MCP: https://docs.windsurf.com/windsurf/cascade/mcp
- OpenClaw MCP: https://docs.openclaw.ai/fr/cli/mcp
