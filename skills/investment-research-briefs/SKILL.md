---
name: investment-research-briefs
description: Create concise investment research briefs, company memos, sector snapshots, portfolio monitoring updates, earnings/news summaries, risk and catalyst briefs, and market thesis support. Use when the user asks for an investor-focused brief on a company, sector, public/private market, comparable set, or portfolio theme.
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

# Investment Research Briefs

## Workflow

Use search and extract for quick investor briefs and source checks, research for full investment memos, and map or crawl only for large known source collections. Keep this skill focused on research design, source selection, verification, and synthesis; execution mechanics should come from companion endpoint skills.

Treat the guidance below as base guidance; adapt it to the user's request when appropriate.

- Define the target, investor lens, geography, timeframe, asset type, and desired depth.
- For quick briefs, split into short subqueries under 400 characters: business overview, market position, financial/operating signals, recent developments, competitors, risks, catalysts, and valuation/comps if requested.
- Prefer filings, investor relations pages, earnings materials, company pages, regulators, exchanges, reputable financial media, and market sources.
- For deeper memos, provide a clear research goal, known context, constraints, target market, and desired output shape.
- Verify specific metrics, quotes, management claims, filings, and high-impact assertions against original or authoritative sources.
- Separate sourced facts, inferred interpretation, and open diligence questions.

## Research Budget

- Start with a small focused search set covering business context, recent developments, financial/operating signals, and risks/catalysts.
- Extract only the strongest sources before drafting a concise brief.
- Add more searches only for named gaps, such as missing filing evidence, missing earnings context, or missing competitor context.
- Do not use map unless a known investor-relations, filing, transcript, or presentation library has buried pages.
- Do not use research unless the user asks for a full memo, sector landscape, or multi-source thesis.

## Capability Guidance

- Use search for fast discovery across companies, sectors, filings, news, competitors, and market context.
- Use extract to verify metrics, quotes, filings, management claims, transcripts, and other high-impact assertions.
- Use research for full investment memos, sector landscapes, or multi-source thesis work.
- Use map or crawl only for large investor-relations, filing, transcript, or presentation libraries.

## Query And Source Guidance

- Use company legal name, ticker, product names, segment names, geography, competitor names, and reporting period in queries.
- For public companies, prioritize original filings, earnings calls, investor presentations, regulator pages, and exchange notices.
- For private companies, triangulate from company pages, funding announcements, customer stories, hiring, product documentation, and credible press.
- For recent developments, make the timeframe explicit in the query.
- For competitor or sector work, build separate subqueries for category, demand drivers, pricing, regulation, customer adoption, and risks.
- Include known assumptions or prior context in broad research requests to avoid rediscovering what is already known.
- Report failed or unavailable sources when they affect filings, transcripts, IR pages, market data, or cited claims.

## Output Template

Use this markdown structure and adapt sections to the user's mandate:

```markdown
# Investment Brief: <company/sector/theme>

## Executive Summary
<concise bullets with the main investor-relevant takeaways>

## Business And Market Context
- Business model:
- Customers/segments:
- Market position:
- Competitors:

## Recent Developments
- <dated development with source>

## Signals
- Financial or operating signals:
- Product, customer, hiring, or partnership signals:
- Regulatory or macro signals:

## Risks
- <risk>: <evidence and uncertainty>

## Catalysts And Watch Items
- <catalyst/watch item>: <why it matters>

## Open Diligence Questions
- <question>

## Sources
- [Source title](URL) - <what it supports>
```

Do not provide personalized financial advice. State when source coverage is thin, stale, or incomplete.
