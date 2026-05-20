# ChatGPT MCP Demo

Demo video:

https://www.youtube.com/watch?v=2wyovmoUEhU

## Demo flow

The demo shows how Postly can be used from ChatGPT to:

1. Discover available workspaces and connected accounts
2. Resolve publishing targets
3. Validate post content
4. Create or schedule posts
5. Check publishing activity
6. Review analytics

## Connecting ChatGPT

During the ChatGPT connection flow, Postly asks for a Postly API key and then
gives ChatGPT a scoped MCP token.

For internal testing with ChatGPT Developer Mode, create a custom app with this
MCP server URL:

```txt
https://mcp.postly.ai/sse
```

Choose OAuth authentication. When the Postly authorization page opens, paste
your Postly API key.

Do not paste the API key into a normal ChatGPT prompt.

See [Manual Connections](manual-connections.md) for Claude, Gemini CLI,
Windsurf, OpenClaw, and generic MCP client setup.
