# Kuro MCP connector

Connect your AI assistant to [Kuro](https://meetkuro.com/), an AI picture studio for images, video clips, voice-overs, music and editable storyboard films.

This repository contains public connection configuration and setup documentation for the hosted Kuro MCP server. It does not contain Kuro's backend implementation.

## Connect

- Endpoint: `https://api.meetkuro.com/mcp`
- Transport: Streamable HTTP
- Authentication: OAuth 2.1, dynamic client registration and PKCE S256
- Account: [Create or sign in to a Kuro account](https://app.meetkuro.com/sign-in)

### Claude Code

```sh
claude mcp add --transport http kuro https://api.meetkuro.com/mcp
```

Open `/mcp` in Claude Code and authenticate Kuro through the browser.

### Other MCP clients

Add the endpoint above as a remote HTTP server, then complete OAuth. The `.mcp.json` in this repository contains the connection declaration. No embedded credential or local server process is needed.

### Claude Code plugin

```sh
/plugin marketplace add Quentin967/kuro-mcp
/plugin install kuro@kuro
```

The connector plugin provides the hosted MCP connection. Kuro's separately distributed creative skills are not bundled here.

## What agents can do

Browse models and reusable recipes, quote generation costs, create images and clips, generate voice-overs and music, retrieve saved work, and edit, render and export storyboard films. Connected tools act within the signed-in Kuro account.

Generation uses the account's existing entitlements. Kuro has a free tier, paid plans and bring-your-own-provider-key generation; see [pricing](https://meetkuro.com/pricing/). Creating media can consume credits. Quote the requested work and obtain authorization before charged generation. Social publication requires the user's explicit approval.

## Documentation and support

- [Connection guide](https://meetkuro.com/agents/)
- [Agent orientation and tool reference](https://meetkuro.com/agents.md)
- [llms.txt](https://meetkuro.com/llms.txt)
- [Terms](https://meetkuro.com/terms/)
- [Privacy](https://meetkuro.com/privacy/)
- Support: hello@meetkuro.com

## License

The connection configuration and documentation in this repository are MIT licensed. The hosted Kuro service is governed by its own [Terms](https://meetkuro.com/terms/); this repository does not license the service implementation.
