# YachtSummary MCP

Public connection pack for the hosted YachtSummary Broker Copilot MCP.

This repository contains client configuration and broker-safe guidance. It does not contain the private YachtSummary server source, customer data, API keys, or broker tokens.

## Who can use it

Anyone with:

- a YachtSummary account
- an MCP client that supports remote HTTP servers and OAuth, such as Codex or another compatible client

Access is broker-scoped: YachtSummary decides which leads, workflows, and actions each signed-in user may access.

## Fastest setup in Codex

1. Clone or open this repository in Codex.
2. Approve or enable **YachtSummary Broker Copilot** if Codex prompts you.
3. Sign into YachtSummary through the OAuth page.
4. Start with:

~~~text
Use YachtSummary and show me my available workflows.
~~~

Then try:

~~~text
Use YachtSummary and tell me which leads I should work first today. Do not send messages or place bids.
~~~

~~~text
Use YachtSummary to draft my next touch for lead <lead id>. Do not send it.
~~~

## Connect another MCP client

Hosted endpoint:

~~~text
https://mcp.yachtsummary.com/mcp
~~~

Generic configuration:

~~~json
{
  "mcpServers": {
    "yachtsummary": {
      "type": "http",
      "url": "https://mcp.yachtsummary.com/mcp"
    }
  }
}
~~~

Use OAuth when the client supports it. The server publishes OAuth discovery metadata and requests these scopes:

- ys.read
- ys.procedures

Do not put YachtSummary credentials or broker tokens in this repository. If a technical MCP client does not support OAuth, follow that client's secure header/secret storage flow and obtain a broker-scoped token from the YachtSummary AI Connector page.

## ChatGPT

When the YachtSummary app is available in your ChatGPT workspace, use:

~~~text
ChatGPT → Apps → YachtSummary → Connect → sign into YachtSummary
~~~

A public GitHub repository does not by itself publish a ChatGPT app. ChatGPT availability still depends on the YachtSummary app's workspace or marketplace rollout.

## Safety

- Reads and drafts can run directly within the signed-in broker's scope.
- Email, SMS, notes, bids, ownership changes, auctions, notifications, and other record changes require the relevant YachtSummary permission and confirmation flow.
- Nothing is sent merely because a draft was generated.
- Never paste FS Mirror keys, raw API keys, customer exports, or live response dumps into issues or commits.
- If sample data appears, the YachtSummary login or broker scope may not be connected yet.

## Useful links

- [Service status](https://mcp.yachtsummary.com/status)
- [YachtSummary](https://yachtsummary.com/)
- [Privacy](https://mcp.yachtsummary.com/privacy)
- [Terms](https://mcp.yachtsummary.com/terms)
- [Support](https://mcp.yachtsummary.com/support)

## License

The public client configuration and documentation in this repository are MIT licensed. YachtSummary names, branding, hosted services, and customer data are not transferred by that license.
