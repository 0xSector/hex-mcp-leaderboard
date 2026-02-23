# MCP Leaderboard - Hex Dashboard

A Hex-compatible Jupyter notebook for tracking adoption metrics of Payment, Commerce, and Crypto MCP (Model Context Protocol) servers.

## Data Sources

- **npm Registry API** - Weekly download counts and 7-day trends
- **GitHub REST API** - Stars, forks, open issues, last commit date

## Metrics Tracked

| Metric | Source |
|--------|--------|
| Weekly Downloads | npm |
| Week-over-Week Change % | npm |
| 7-Day Download Trend | npm |
| GitHub Stars | GitHub |
| GitHub Forks | GitHub |
| Open Issues | GitHub |
| Last Commit Date | GitHub |

## MCPs Tracked

**Payments:** Stripe MCP, Stripe Agent Toolkit, PayPal MCP, Square MCP

**Commerce:** Shopify Dev MCP, Shopify MCP, Shopify Storefront MCP, Shopify MCP Server

**Crypto:** x402 MCP, MCPay, Armor Crypto MCP, CoinGecko MCP, Hive Intelligence, NEAR MCP, Coinbase CDP

## Import into Hex

1. Download `mcp_leaderboard.ipynb` from this repository
2. Go to [Hex](https://hex.tech) and log in
3. Click **Import** in the top navigation
4. Upload the `.ipynb` file
5. Run all cells

## Optional: Add GitHub Token

For higher API rate limits, add your GitHub token in the data fetching cell:

```python
headers['Authorization'] = 'token YOUR_GITHUB_TOKEN'
```

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

## Visualizations Included

- Summary metrics (total downloads, stars, avg growth)
- Leaderboard table ranked by downloads
- Downloads by category (bar chart)
- Top 10 MCPs by downloads (horizontal bar)
- GitHub Stars vs Downloads (scatter plot)
- Week-over-Week growth leaders (bar chart)
- 7-day download trends (sparklines)
- Category distribution (donut chart)

## License

Based on [mcp-leaderboard](https://github.com/csmoove530/mcp-leaderboard) by csmoove530.
