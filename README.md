# MCP Leaderboard - Hex Dashboard

A Hex-compatible Jupyter notebook for tracking adoption metrics of Payment, Commerce, and Crypto MCP (Model Context Protocol) servers.

## Data Quality Note

The original [mcp-leaderboard](https://github.com/csmoove530/mcp-leaderboard) registry contains several incorrect package names and non-existent GitHub repositories. This notebook uses a **verified registry** with only packages/repos that actually exist.

### Verified vs Original Registry

| Original Entry | Issue | Correction |
|---------------|-------|------------|
| `@anthropic/paypal-mcp` | Does not exist on npm | Use `@paypal/agent-toolkit` |
| `stripe/stripe-mcp` | GitHub repo does not exist | Removed (npm package works) |
| `stripe/agent-toolkit` | GitHub repo does not exist | Removed |
| `Shopify/dev-mcp` | GitHub repo does not exist | Removed (npm package works) |
| `square/square-mcp` | GitHub repo does not exist | Removed entirely |
| `coinbase/cdp-mcp` | GitHub repo does not exist | Removed entirely |
| `near-mcp` (npm) | Does not exist on npm | GitHub only |
| `coingecko-mcp` | Does not exist on npm | Removed entirely |
| `armor-crypto-mcp` | Does not exist on npm | Removed entirely |
| `hive-crypto-mcp` | Does not exist on npm | Removed entirely |

### Working Data Sources (as of 2026-02-23)

**npm packages that work:**
- `@stripe/mcp` - 36,525 weekly downloads
- `@paypal/agent-toolkit` - 594 weekly downloads
- `@shopify/dev-mcp` - 4,770 weekly downloads
- `shopify-mcp` - 197 weekly downloads
- `shopify-mcp-server` - 78 weekly downloads
- `@wolfielabs/shopify-storefront-mcp-server` - 3 weekly downloads
- `x402-mcp` - 513 weekly downloads
- `mcpay` - 69 weekly downloads

**GitHub repos that work:**
- `paypal/agent-toolkit` - 179 stars
- `GeLi2001/shopify-mcp` - 132 stars
- `microchipgnu/MCPay` - 82 stars
- `nearai/near-mcp` - 25 stars
- `amir-bengherbi/shopify-mcp-server` - 16 stars

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
- Top MCPs by downloads (horizontal bar)
- GitHub Stars vs Downloads (scatter plot)
- Week-over-Week growth leaders (bar chart)
- 7-day download trends (sparklines)
- Category distribution (donut chart)

## Adding Interactivity in Hex

Create a dropdown input parameter named `selected_category` with options:
- `all`
- `payments`
- `commerce`
- `crypto`

Then add this filter after data loading:

```python
if selected_category != 'all':
    df_mcps = df_mcps[df_mcps['category'] == selected_category]
```

## License

Based on [mcp-leaderboard](https://github.com/csmoove530/mcp-leaderboard) by csmoove530.
