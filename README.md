<p align="center">
  <img src="https://index.asiavirtualsolutions.com/brand/avs-indexer-logo-icon-light.png" width="96" alt="AVS Indexer by Asia Virtual Solutions">
</p>

# AVS Indexer MCP Server

Submit backlinks and new pages for search engine indexing, straight from your AI assistant.

AVS Indexer is a URL indexing service for SEO. This hosted MCP server connects it to Claude, Claude Code, Cursor and
other MCP clients. You ask in plain words. The assistant checks the cost, submits your URLs and tracks the results.

> **Nothing to install.** AVS Indexer is a remote (hosted) MCP server. This repository holds the documentation only.

| | |
|---|---|
| **Server URL** | `https://index.asiavirtualsolutions.com/mcp` |
| **Transport** | Streamable HTTP |
| **Sign-in** | OAuth 2.1 (log in with your email and click Allow) or an API key |
| **Free trial** | 50 free credits for new accounts |
| **Website** | https://index.asiavirtualsolutions.com |

## What you can do

- **Submit up to 5,000 URLs at a time:** backlinks, new blog posts, product pages.
- **Choose the speed:** normal indexing (1 credit per URL) or instant indexing (10 credits per URL).
- **Skip dead links automatically:** every URL is checked before it is sent. Pages that return 404, carry noindex,
  are blocked by robots.txt or point their canonical elsewhere are skipped, and the credits go back to you.
- **Drip-feed:** spread a submission over 2 to 30 days so new links look natural. Stop it anytime and unsent
  credits are refunded.
- **Work in projects:** group submissions per client or website, and see what was sent, what was skipped and why.
- **Check your balance** and the cost of a submission before you spend anything.

## Tools

| Tool | What it does | Uses credits |
|---|---|---|
| `submit_urls` | Submit up to 5,000 URLs. Options: project name, normal or instant, drip-feed 2–30 days, URL check on or off | Yes |
| `estimate_cost` | Shows the cost of a submission and whether your balance covers it | No |
| `get_balance` | Shows your credit balance and price per URL | No |
| `list_batches` | Lists recent submissions with status, counts, refunds and drip-feed progress | No |
| `get_batch` | Shows one submission in detail, including skipped URLs and the reason | No |
| `stop_drip` | Stops a drip-feed and refunds the URLs that were not sent yet | No (refunds) |

## Quick start

1. **Create a free account** at https://index.asiavirtualsolutions.com. New accounts get **50 free credits**.
2. **Add the server** to your AI app (see below). Server URL:
   `https://index.asiavirtualsolutions.com/mcp`
3. **Sign in** when your app asks, and click **Allow**.
4. **Ask:** "What is my AVS Indexer balance?"

### Claude (claude.ai and Claude Desktop)

Settings → Connectors → **Add custom connector** → paste the server URL → **Connect** → log in → **Allow**.

### Claude Code

Sign in with your account (recommended):

```
claude mcp add --transport http avs-indexer https://index.asiavirtualsolutions.com/mcp
```

Then run `/mcp` in Claude Code and choose **Authenticate**.

Or use an API key from your dashboard:

```
claude mcp add --transport http avs-indexer https://index.asiavirtualsolutions.com/mcp --header "Authorization: Bearer YOUR_KEY"
```

### Cursor and other MCP clients (mcp.json)

```json
{
  "mcpServers": {
    "avs-indexer": {
      "url": "https://index.asiavirtualsolutions.com/mcp",
      "headers": { "Authorization": "Bearer YOUR_KEY" }
    }
  }
}
```

Clients that support OAuth can leave out the `headers` line and sign in instead.

## Sign-in and permissions

- **OAuth 2.1:** your app opens our sign-in page. Log in with your email and click **Allow**. No key to copy.
- **API key:** create one in your dashboard and send it as `Authorization: Bearer YOUR_KEY`.
- **Read-only access:** on the Allow screen, untick **Submit URLs**. The assistant can then check balances and
  results, but cannot spend credits.
- You can see and remove connected AI apps in your dashboard at any time.

## Example prompts

- "What is my AVS Indexer balance?"
- "Submit these URLs for normal indexing in the project Client A. Tell me the cost first."
- "Drip-feed these 300 backlinks over 10 days."
- "How is my last submission doing? Which URLs were skipped and why?"
- "Stop the drip-feed for batch 42."

## Credits and pricing

- Normal indexing: **1 credit per URL**. Instant indexing: **10 credits per URL**.
- Dead links found by the URL check are refunded automatically.
- Credits never expire.
- Credit packs: https://index.asiavirtualsolutions.com/#pricing

## Good to know

Search engines decide which pages they index. No service can force a page into the index. AVS Indexer gets your URLs
in front of search engines quickly, and the URL check skips dead pages so you don't pay for links that cannot be indexed.

## Links

- Website: https://index.asiavirtualsolutions.com
- Setup guide: https://index.asiavirtualsolutions.com/integrations#mcp
- Changelog: https://index.asiavirtualsolutions.com/changelog
- Publisher: [Asia Virtual Solutions](https://asiavirtualsolutions.com)
