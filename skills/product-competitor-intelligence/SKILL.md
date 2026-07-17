---
name: product-competitor-intelligence
description: Research competitor products, SKUs, pricing, packaging, positioning, feature comparisons, product catalogs, category pages, retailer listings, marketplace data, and market intelligence. Use when the user asks for competitor SKU discovery, product data enrichment, pricing/spec extraction, product comparison, market intelligence, or crawl/map-driven product research.
license: MIT
metadata:
  author: tavily
  version: "0.1.0"
  homepage: https://www.tavily.com
  source: https://github.com/tavily-ai/use-case-skills
inputs:
  - name: TAVILY_API_KEY
    description: Tavily API key for endpoint requests.
    required: true
---

# Product Competitor Intelligence

## Workflow

Use search and extract for product, pricing, SKU, feature, and competitor intelligence; use map or crawl for known catalogs and large competitor sites. Keep this skill focused on query construction, site navigation, source filtering, and synthesis; execution mechanics should come from companion endpoint skills.

Treat the guidance below as base guidance; adapt it to the user's request when appropriate.

- Clarify the category, competitors, geography, target customer, price band, feature set, and desired output format.
- Split broad questions into short subqueries under 400 characters: competitors, product category, pricing, alternatives, reviews, SKUs, specs, marketplaces, and recent launches.
- Search for relevant competitors, product pages, category pages, retailer listings, pricing pages, reviews, docs, and official sources.
- Filter by relevance score, domain trust, page type, and freshness before extracting.
- Extract only selected pages that can support the requested comparison, table, or brief.
- Use site mapping before broad collection on known competitor, retailer, manufacturer, marketplace, docs, or catalog domains.
- Collect multiple pages only after choosing relevant path patterns and a tight scope.

## Research Budget

- Start with a small focused search set covering competitors, category, pricing, features/specs, reviews, or launches.
- Extract only the strongest product, pricing, catalog, marketplace, docs, or review pages before drafting.
- Add more searches only for named gaps, such as missing pricing, missing SKU evidence, or missing official competitor pages.
- Do not use map unless a known competitor, retailer, manufacturer, marketplace, docs, or catalog domain needs URL discovery.
- Do not use crawl until map has identified a narrow product, pricing, category, docs, or catalog section.

## Capability Guidance

- Use search for competitor discovery, pricing checks, feature comparisons, product claims, reviews, and launch signals.
- Use extract on selected product, pricing, docs, catalog, marketplace, review, or changelog pages.
- Use map when the domain is known but the relevant product, pricing, changelog, docs, category, or catalog pages are hard to find.
- Use crawl for SKU/catalog discovery only after narrowing to relevant sections.
- Use research only when the user asks for a market report rather than product-level evidence.

## Query And Source Guidance

- Include product category, buyer segment, geography, price band, SKU/model terms, competitor names, and feature terms in separate subqueries.
- Prioritize official product pages, pricing pages, docs, catalogs, retailer listings, marketplaces, review sites, customer stories, changelogs, and credible launch coverage.
- For known sites, look for paths such as products, pricing, category, collections, docs, blog, changelog, customers, or case studies.
- Avoid irrelevant paths such as login, cart, checkout, account, admin, tag archives, and unrelated content.
- Dedupe near-identical product pages, regional variants, and syndicated listings before synthesis.
- Report failed or inaccessible sources when they affect pricing, specs, availability, or competitor coverage.

## Output Template

Use this markdown structure and adapt columns to the user's request:

```markdown
# Product And Competitor Intelligence: <category/company>

## Scope
- Category:
- Geography:
- Competitors covered:
- Source coverage limits:

## Product Comparison
| Product/SKU | Company | Category | Pricing/availability | Key features/specs | Positioning | Source |
| --- | --- | --- | --- | --- | --- | --- |

## Competitor Notes
### <Competitor>
- Positioning:
- Product/pricing evidence:
- Strengths:
- Gaps or uncertainty:

## Market Signals
- Launches or changes:
- Review/customer signals:
- Distribution or channel signals:

## Follow-Up Searches
- <query idea>
```

Keep each claim tied to a source. Mark pricing, availability, or specs as unavailable when they are not visible.
