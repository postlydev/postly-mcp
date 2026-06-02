# ChatGPT MCP Demo

## Demo

### How to Connect Postly MCP to ChatGPT (Step-by-Step Setup Guide)

[![How to Connect Postly MCP to ChatGPT](https://img.youtube.com/vi/z7PCv0VbuHs/maxresdefault.jpg)](https://www.youtube.com/watch?v=z7PCv0VbuHs)

Video:
https://www.youtube.com/watch?v=z7PCv0VbuHs

### Publish to LinkedIn with ChatGPT + Postly MCP (Complete Setup & Demo)

[![Publish to LinkedIn with ChatGPT + Postly MCP](https://img.youtube.com/vi/3FY9NAHiiHw/maxresdefault.jpg)](https://www.youtube.com/watch?v=3FY9NAHiiHw)

Video:
https://www.youtube.com/watch?v=3FY9NAHiiHw

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
