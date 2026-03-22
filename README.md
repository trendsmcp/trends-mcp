# Trends MCP

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![MCP](https://img.shields.io/badge/MCP-compatible-blue)](https://modelcontextprotocol.io)
[![Works with Claude](https://img.shields.io/badge/Claude-supported-orange)](https://trendsmcp.ai/mcp-server-for-claude)
[![Works with Cursor](https://img.shields.io/badge/Cursor-supported-purple)](https://trendsmcp.ai/mcp-server-for-cursor)

> **Give your AI live trend data across Google, YouTube, TikTok, Reddit, Amazon,
> Wikipedia, News, Web Traffic, App Downloads, Steam, npm, and more.**
> One MCP connection. Free API key. No scraping. Works with any MCP-compatible AI.

**[trendsmcp.ai](https://trendsmcp.ai)** &nbsp;|&nbsp;
[Data Sources](https://trendsmcp.ai/data-sources) &nbsp;|&nbsp;
[Use Cases](https://trendsmcp.ai/use-cases) &nbsp;|&nbsp;
[Install guides](#install-by-ai-client)

---

## Why Trends MCP

| Problem | Trends MCP solution |
|---------|-------------------|
| AI has a training cutoff -- it doesn't know what's trending today | Live data from 12+ sources, queried at request time |
| Managing TikTok, Reddit, YouTube APIs separately is painful | One MCP endpoint, all platforms, consistent schema |
| pytrends scrapes Google and breaks constantly | Managed pipeline with retries, no scraping |
| Trend data comes back as charts you have to read manually | Structured JSON your AI reasons over directly |
| Managing separate API keys for TikTok, Reddit, YouTube | One Trends MCP key covers all 12+ sources |
| Expensive enterprise tools just for trend signals | Free tier available, no dashboard, no per-seat pricing |

---

## Quick install

### 1. Get a free API key

Go to **[trendsmcp.ai](https://trendsmcp.ai)**, enter your email, and get your free key instantly.
100 requests/day, no credit card required.

### 2. Add to your AI client

[**+ Add to Cursor (one click)**](cursor://anysphere.cursor-deeplink/mcp/install?name=trends-mcp&config=eyJ1cmwiOiJodHRwczovL2FwaS50cmVuZHNtY3AuYWkvdjEvbWNwIiwidHJhbnNwb3J0IjoiaHR0cCJ9)

Or paste the config manually (replace `YOUR_API_KEY` with the key from your email):

**Cursor / Windsurf / Cline** &nbsp; (`~/.cursor/mcp.json` or equivalent)
```json
{
  "mcpServers": {
    "trends-mcp": {
      "url": "https://api.trendsmcp.ai/mcp",
      "transport": "http",
      "headers": { "Authorization": "Bearer YOUR_API_KEY" }
    }
  }
}
```

**VS Code / GitHub Copilot** &nbsp; (`.vscode/mcp.json`)
```json
{
  "servers": {
    "trends-mcp": {
      "type": "http",
      "url": "https://api.trendsmcp.ai/mcp",
      "headers": { "Authorization": "Bearer YOUR_API_KEY" }
    }
  }
}
```

**Claude Desktop** &nbsp; (`claude_desktop_config.json`)
```json
{
  "mcpServers": {
    "trends-mcp": {
      "url": "https://api.trendsmcp.ai/mcp",
      "transport": "http",
      "headers": { "Authorization": "Bearer YOUR_API_KEY" }
    }
  }
}
```

**Claude.ai** (browser) &nbsp; Settings → Connectors → Add custom connector:
```
https://api.trendsmcp.ai/mcp
```

---

## Available tools

| Tool | What it does | Example |
|------|-------------|---------|
| `get_trends` | Time-series for a keyword on one source | `get_trends(keyword='AI agents', source='google search', data_mode='weekly')` |
| `get_growth` | Cross-source growth % over multiple periods | `get_growth(keyword='vibe coding', source='all', percent_growth=['1M','3M','1Y'])` |
| `get_top_trends` | What is trending right now | `get_top_trends(source='tiktok', limit=20)` |
| `get_ranked_trends` | Top trends ranked by volume | `get_ranked_trends(source='reddit', limit=10)` |

---

## Example: ask your AI

After connecting, try these prompts in Claude, Cursor, or any MCP client:

```
What is the trend momentum for 'AI agents' across Google, TikTok, and Reddit over the past 3 months?
```
```
Which npm packages in the MCP ecosystem are growing fastest right now?
```
```
Compare search interest for 'Claude vs ChatGPT vs Gemini' on Google over the past year.
```
```
What are the top 20 trending topics on TikTok right now?
```
```
Is consumer interest in 'electric vehicles' growing or declining on Amazon and YouTube?
```

---

## Data sources

| Source | Full docs |
|--------|-----------|
| [Google Trends data for AI assistants](https://trendsmcp.ai/google-trends) | Query live Google Trends data from any AI assistant via MCP. Get real-time trending topics... |
| [YouTube trend data for AI assistants](https://trendsmcp.ai/youtube-trends) | Query YouTube search volume trends from any AI assistant via MCP. Track rising video topic... |
| [TikTok trend data for AI assistants](https://trendsmcp.ai/tiktok-trends) | Query live TikTok hashtag trend data from any AI assistant via MCP. Track viral hashtags, ... |
| [Reddit discussion trend data for AI](https://trendsmcp.ai/reddit-trends) | Query Reddit discussion volume trends from any AI assistant via MCP. Track community inter... |
| [Amazon search trend data for AI assistants](https://trendsmcp.ai/amazon-search-trends) | Query Amazon product search volume trends from any AI via MCP. Track consumer product dema... |
| [Wikipedia page view trend data for AI](https://trendsmcp.ai/wikipedia-trends) | Query Wikipedia page view trends from any AI assistant via MCP. Track information-seeking ... |
| [News sentiment and volume data for AI](https://trendsmcp.ai/news-sentiment-data) | Query news sentiment and volume data from any AI assistant via MCP. Positive/negative sent... |
| [Web traffic trend data for AI assistants](https://trendsmcp.ai/web-traffic-data) | Query website traffic trend data from any AI assistant via MCP. Track site visit trends, d... |
| [App download trend data for AI assistants](https://trendsmcp.ai/app-download-trends) | Query app download trend data from any AI assistant via MCP. Track mobile app growth, inst... |
| [Steam player trend data for AI assistants](https://trendsmcp.ai/steam-trends) | Query live Steam concurrent player data from any AI via MCP. Track game momentum, player c... |
| [npm package trend data for AI assistants](https://trendsmcp.ai/npm-trends) | Query live npm package download data from any AI via MCP. Track JavaScript library adoptio... |
| [LinkedIn topic trend data for AI assistants](https://trendsmcp.ai/linkedin-trends) | Query LinkedIn topic trends from any AI assistant via MCP. Track professional interest in ... |
| [Twitter / X trend signals for AI assistants](https://trendsmcp.ai/twitter-trends) | Query Twitter/X trend signals from any AI assistant via MCP. Track real-time social conver... |
| [Baidu search trends for AI assistants](https://trendsmcp.ai/baidu-trends) | Query Baidu search trends from any AI assistant via MCP. Track keyword interest in China, ... |
| [GitHub and developer trends for AI assistants](https://trendsmcp.ai/github-trends) | Track GitHub trending repositories and npm package adoption via MCP. Developer trend data ... |
| [Spotify and audio trend data for AI assistants](https://trendsmcp.ai/spotify-trends) | Query Spotify-related trend data from any AI assistant via MCP. Track music genre momentum... |
| [ChatGPT and AI tool adoption trends](https://trendsmcp.ai/chatgpt-trends) | Track ChatGPT, AI tool, and AI model adoption trends via MCP. Monitor search interest, Red... |
| [Google Shopping trend data for AI assistants](https://trendsmcp.ai/google-shopping-trends) | Query Google Shopping search trends from any AI via MCP. Track product purchase intent, ri... |
| [Google News trend data for AI assistants](https://trendsmcp.ai/google-news-trends) | Query Google News search trends from any AI assistant via MCP. Track news topic volume, br... |
| [Google Images trend data for AI assistants](https://trendsmcp.ai/google-images-trends) | Query Google Images search trend data from any AI via MCP. Track visual search volume, ris... |

---

## Install by AI client

| Client | Step-by-step guide |
|--------|--------------------|
| Trends MCP for Claude | [https://trendsmcp.ai/mcp-server-for-claude](https://trendsmcp.ai/mcp-server-for-claude) |
| Trends MCP for Cursor | [https://trendsmcp.ai/mcp-server-for-cursor](https://trendsmcp.ai/mcp-server-for-cursor) |
| Trends MCP for VS Code and GitHub Copilot | [https://trendsmcp.ai/mcp-server-for-vs-code](https://trendsmcp.ai/mcp-server-for-vs-code) |
| Trends MCP for Windsurf | [https://trendsmcp.ai/mcp-server-for-windsurf](https://trendsmcp.ai/mcp-server-for-windsurf) |
| Trends MCP for GitHub Copilot | [https://trendsmcp.ai/mcp-server-for-github-copilot](https://trendsmcp.ai/mcp-server-for-github-copilot) |
| Trends MCP for Cline | [https://trendsmcp.ai/mcp-server-for-cline](https://trendsmcp.ai/mcp-server-for-cline) |
| Trends MCP for ChatGPT | [https://trendsmcp.ai/mcp-server-for-chatgpt](https://trendsmcp.ai/mcp-server-for-chatgpt) |
| Trends MCP for Raycast | [https://trendsmcp.ai/mcp-server-for-raycast](https://trendsmcp.ai/mcp-server-for-raycast) |
| Trends MCP for OpenAI | [https://trendsmcp.ai/mcp-server-for-openai](https://trendsmcp.ai/mcp-server-for-openai) |

---

## Use cases

| Use case | Page |
|----------|------|
| AI-powered market research with live trend data | [https://trendsmcp.ai/market-research](https://trendsmcp.ai/market-research) |
| AI investment research with live alternative data | [https://trendsmcp.ai/investment-research](https://trendsmcp.ai/investment-research) |
| AI-powered competitor tracking with live signals | [https://trendsmcp.ai/competitor-tracking](https://trendsmcp.ai/competitor-tracking) |
| AI-powered brand monitoring with live signals | [https://trendsmcp.ai/brand-monitoring](https://trendsmcp.ai/brand-monitoring) |
| AI-powered SEO keyword research with live search trends | [https://trendsmcp.ai/seo-keyword-research](https://trendsmcp.ai/seo-keyword-research) |
| AI-powered content strategy with live trend data | [https://trendsmcp.ai/content-strategy](https://trendsmcp.ai/content-strategy) |
| AI-powered social listening via MCP | [https://trendsmcp.ai/social-listening-ai](https://trendsmcp.ai/social-listening-ai) |
| Trend forecasting with AI | [https://trendsmcp.ai/trend-forecasting](https://trendsmcp.ai/trend-forecasting) |
| AI-powered e-commerce product research with live demand data | [https://trendsmcp.ai/ecommerce-product-research](https://trendsmcp.ai/ecommerce-product-research) |
| Market research for startups with AI | [https://trendsmcp.ai/startup-market-research](https://trendsmcp.ai/startup-market-research) |
| Product launch research with AI | [https://trendsmcp.ai/product-launch-research](https://trendsmcp.ai/product-launch-research) |
| Influencer and creator trend research with AI | [https://trendsmcp.ai/influencer-trend-research](https://trendsmcp.ai/influencer-trend-research) |
| Trending topics tool for journalists | [https://trendsmcp.ai/journalist-trend-tool](https://trendsmcp.ai/journalist-trend-tool) |
| Consumer insights with AI via live trend data | [https://trendsmcp.ai/consumer-insights-ai](https://trendsmcp.ai/consumer-insights-ai) |
| Trend data for product managers | [https://trendsmcp.ai/product-manager-trend-data](https://trendsmcp.ai/product-manager-trend-data) |
| Viral trend detection for AI agents | [https://trendsmcp.ai/viral-trend-detection](https://trendsmcp.ai/viral-trend-detection) |
| Developer ecosystem trends for AI agents | [https://trendsmcp.ai/developer-ecosystem-trends](https://trendsmcp.ai/developer-ecosystem-trends) |

---

## Comparisons and alternatives

| Comparison | Page |
|------------|------|
| Google Trends API for AI agents | [https://trendsmcp.ai/google-trends-api](https://trendsmcp.ai/google-trends-api) |
| A modern pytrends alternative for AI agents | [https://trendsmcp.ai/pytrends-alternative](https://trendsmcp.ai/pytrends-alternative) |
| The Google Trends alternative built for AI | [https://trendsmcp.ai/google-trends-alternative](https://trendsmcp.ai/google-trends-alternative) |
| An Exploding Topics alternative for AI agents | [https://trendsmcp.ai/exploding-topics-alternative](https://trendsmcp.ai/exploding-topics-alternative) |
| A Glimpse alternative for AI agents | [https://trendsmcp.ai/glimpse-alternative](https://trendsmcp.ai/glimpse-alternative) |
| Semrush alternative for AI assistants | [https://trendsmcp.ai/semrush-alternative](https://trendsmcp.ai/semrush-alternative) |
| Ahrefs alternative for trend research | [https://trendsmcp.ai/ahrefs-alternative](https://trendsmcp.ai/ahrefs-alternative) |
| SimilarWeb alternative for AI assistants | [https://trendsmcp.ai/similarweb-alternative](https://trendsmcp.ai/similarweb-alternative) |
| Brandwatch alternative for AI assistants | [https://trendsmcp.ai/brandwatch-alternative](https://trendsmcp.ai/brandwatch-alternative) |
| BuzzSumo alternative for AI assistants | [https://trendsmcp.ai/buzzsumo-alternative](https://trendsmcp.ai/buzzsumo-alternative) |
| SparkToro alternative for AI assistants | [https://trendsmcp.ai/sparktoro-alternative](https://trendsmcp.ai/sparktoro-alternative) |

---

## License

MIT &copy; [Trends MCP](https://trendsmcp.ai)