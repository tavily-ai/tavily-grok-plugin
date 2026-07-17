# Tavily Plugin for Grok Build

Search the web, extract webpage content, map and crawl websites, and run deep research directly from Grok Build with [Tavily](https://www.tavily.com).

Tavily is a search and research platform built for AI agents. This plugin connects Grok Build to Tavily's hosted MCP server and includes skills for general web research, developer workflows, competitive intelligence, investment research, sales intelligence, scientific research, threat intelligence, and vendor screening.

## Installation

In Grok Build, open `/plugin`, search for **Tavily**, and install the plugin.

On first connection, Grok opens Tavily's authorization flow in the browser. Sign in to connect your Tavily account!

## Tools

| Tool | What it does |
|---|---|
| `tavily_search` | Search the web for current, relevant sources with domain and date filters |
| `tavily_extract` | Extract clean, structured content from one or more webpages |
| `tavily_map` | Discover URLs and understand a website's structure |
| `tavily_crawl` | Crawl multiple pages and retrieve their content |
| `tavily_research` | Produce comprehensive multi-source research with citations |

## Skills

### Search and research

| Skill | What it does |
|---|---|
| `tavily-web` | Coordinates Tavily tools for search, extraction, mapping, crawling, and research |
| `tavily-best-practices` | Helps developers build production-ready Tavily integrations |

### Specialized research

| Skill | What it does |
|---|---|
| `academic-scientific-research` | Finds, screens, and synthesizes academic papers and scientific literature |
| `investment-research-briefs` | Creates company, sector, portfolio, and investment research briefs |
| `product-competitor-intelligence` | Compares products, pricing, positioning, features, and competitors |
| `sales-account-intelligence` | Builds sales-ready company, prospect, and buyer intelligence |
| `threat-intelligence-enrichment` | Enriches CVEs, IOCs, malware, threat actors, and security incidents |
| `vendor-risk-kyc-screening` | Screens companies and executives for vendor risk and KYC concerns |

## Example prompts

```text
Search for the latest changes to the Model Context Protocol and cite the primary sources.
```

```text
Map the Tavily documentation and find every page related to authentication.
```

```text
Research the leading agent observability platforms and compare their capabilities with citations.
```

```text
Create a competitor intelligence brief for three AI search providers.
```

```text
Find recent papers on retrieval-augmented generation and summarize the strongest evidence.
```

## Authentication and security

The plugin connects only to Tavily's hosted MCP endpoint at `https://mcp.tavily.com/mcp`. Authentication is handled through the MCP authorization flow.

## Resources

- [Tavily](https://www.tavily.com)
- [Documentation](https://docs.tavily.com)
- [MCP documentation](https://docs.tavily.com/documentation/mcp)
- [Tavily Remote MCP](https://github.com/tavily-ai/tavily-remote-mcp)

## License

MIT
