---
name: tavily-web
description: "Search and research the web with Tavily. Use for current information, source discovery, webpage extraction, site mapping, documentation crawling, comparisons, and comprehensive research with citations."
---

# Tavily Web Research

Use the Tavily MCP tools provided by this plugin to retrieve current, source-grounded web information.

## Choose the right tool

- `tavily_search`: Find relevant sources and current information on the web.
- `tavily_extract`: Read clean content from one or more known URLs.
- `tavily_map`: Discover relevant URLs and understand a website's structure.
- `tavily_crawl`: Retrieve content from multiple pages within a website.
- `tavily_research`: Produce comprehensive, multi-source research with citations.

## Workflow

1. Clarify the requested scope, freshness, geography, domains, and output format when they are ambiguous.
2. Use `tavily_search` for focused questions and source discovery.
3. Use `tavily_extract` when the user supplies URLs or when full page content is needed.
4. Use `tavily_map` before crawling a large or unfamiliar site when target pages are unclear.
5. Use `tavily_crawl` for documentation sections or other multi-page website tasks.
6. Use `tavily_research` for literature reviews, market analyses, detailed comparisons, and other broad synthesis tasks.
7. Synthesize the results rather than pasting raw tool output. Preserve source URLs and cite factual claims.

## Search guidance

- Write concise, specific search queries instead of long instructions.
- Split multi-part questions into distinct searches when that improves coverage.
- Use domain and date filters when the user specifies them.
- For relative dates such as “last week,” calculate and use exact dates from the current date.
- Prefer primary and authoritative sources for factual or technical claims.
- Cross-check consequential claims with more than one independent source.
- Distinguish sourced facts from your own analysis.

## Authentication and limits

The server is configured at `https://mcp.tavily.com/mcp`. If authentication is required, ask the user to complete the client's OAuth flow. Never request that the user paste an API key into chat.
