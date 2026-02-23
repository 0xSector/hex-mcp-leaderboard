# MCP Leaderboard - Hex Dashboard

A Hex-compatible Jupyter notebook for tracking adoption metrics of MCP (Model Context Protocol) servers from reputable companies.

## Overview

Tracks **22 verified MCP packages** across **6 categories** from major tech companies.

## Categories & Companies

| Category | Companies | Top Package |
|----------|-----------|-------------|
| **Core** | Anthropic, MCP Foundation, Prefect | @modelcontextprotocol/sdk (16M/wk) |
| **DevTools** | Microsoft, GitHub, Upstash, Figma, Browserbase, Sentry | @playwright/mcp (1.4M/wk) |
| **Cloud** | Cloudflare | @cloudflare/mcp-server-cloudflare |
| **Payments** | Stripe, PayPal | @stripe/mcp (36K/wk) |
| **Commerce** | Shopify | @shopify/dev-mcp (4.7K/wk) |
| **Crypto** | x402, MCPay, NEAR | x402-mcp |

## Verified Data Sources (as of 2026-02-23)

### High-Volume npm Packages
| Package | Weekly Downloads |
|---------|-----------------|
| `@modelcontextprotocol/sdk` | 16,124,713 |
| `@anthropic-ai/claude-code` | 6,515,721 |
| `@anthropic-ai/sdk` | 5,595,592 |
| `@playwright/mcp` | 1,433,368 |
| `@upstash/context7-mcp` | 213,334 |
| `fastmcp` | 139,915 |
| `@stripe/mcp` | 36,525 |
| `mcp-use` | 18,652 |

### Top GitHub Repos (by stars)
| Repo | Stars |
|------|-------|
| `upstash/context7` | 46,624 |
| `microsoft/playwright-mcp` | 27,558 |
| `github/github-mcp-server` | 27,181 |
| `PrefectHQ/fastmcp` | 23,081 |
| `GLips/Figma-Context-MCP` | 13,209 |
| `mcp-use/mcp-use` | 9,264 |
| `cloudflare/mcp-server-cloudflare` | 3,448 |
| `browserbase/mcp-server-browserbase` | 3,147 |

## Import into Hex

1. Download `mcp_leaderboard.ipynb` from this repository
2. Go to [Hex](https://hex.tech) and log in
3. Click **Import** in the top navigation
4. Upload the `.ipynb` file
5. Run all cells

## Optional: Add GitHub Token

For higher API rate limits (60/hr -> 5000/hr), uncomment and add your token in the data fetching cell:

```python
headers['Authorization'] = 'token YOUR_GITHUB_TOKEN'
```

## Visualizations Included

- Summary metrics (total downloads, stars, avg growth)
- Leaderboard table ranked by downloads
- Downloads by category (bar chart)
- Top 10 MCPs by downloads (horizontal bar)
- GitHub Stars vs Downloads (scatter plot)
- Week-over-Week growth leaders (bar chart)
- 7-day download trends (sparklines)
- Category distribution (donut chart)

## Adding Interactivity in Hex

Create a dropdown input parameter named `selected_category` with options:
- `all`
- `core`
- `devtools`
- `cloud`
- `payments`
- `commerce`
- `crypto`

Then add this filter after data loading:

```python
if selected_category != 'all':
    df_mcps = df_mcps[df_mcps['category'] == selected_category]
```

## Data Quality

All packages and repos have been manually verified to exist. The original [mcp-leaderboard](https://github.com/csmoove530/mcp-leaderboard) contained several non-existent packages which have been removed or corrected.

## License

Based on [mcp-leaderboard](https://github.com/csmoove530/mcp-leaderboard) by csmoove530.
