---
name: sales-account-intelligence
description: Build sales-ready account intelligence for companies, prospects, customers, partners, and target buyers. Use when the user asks for sales prep, account brief, meeting prep, buyer research, expansion signals, customer intelligence, trigger events, executive context, outreach angles, or market/account context for GTM teams.
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

# Sales Account Intelligence

## Workflow

Use search and extract to produce fast, useful sales account context with cited sources; use map or crawl only when a known company site needs scoped navigation. Keep this skill focused on research planning, query construction, source selection, and sales-ready synthesis; execution mechanics should come from companion endpoint skills.

Treat the guidance below as base guidance; adapt it to the user's request when appropriate.

- Define the account, audience, sales motion, geography, and meeting or outreach goal.
- Split research into short subqueries under 400 characters: company overview, recent news, products, customers, leadership, funding/financials, hiring, partnerships, pain points, and relevant initiatives.
- Use search for discovery, then filter by source quality before extracting.
- Extract the strongest sources: official website, newsroom, product pages, customer stories, investor/press pages, credible news, job postings, and relevant executive profiles.
- Use site navigation when the company site is large and useful pages are hard to find.
- Collect scoped site sections only when the user needs broad coverage of customers, case studies, news, products, solutions, or careers.

## Research Budget

- Start with a small focused search set: account overview, recent triggers, product/initiative context, and buyer/pain-point evidence.
- Extract only the strongest sources before drafting the brief.
- Add more searches only for named gaps that block the brief, such as missing trigger events or missing official product context.
- Do not use map until search finds the company domain and there is a specific buried page type to locate.
- Do not use crawl for first-pass account prep unless the user explicitly asks for a site scan.

## Capability Guidance

- Use search for most account briefs, meeting prep, outreach research, and trigger-event checks.
- Use extract on selected official pages, newsroom posts, customer stories, credible news, job postings, and executive profiles.
- Use map when the company domain is known but important pages are buried.
- Use crawl for account site scans only after narrowing to sections that support the sales goal.
- Use research only when the user asks for a deep strategic account report.

## Query And Source Guidance

- Include company name, aliases, product names, executive names, industry terms, geography, and the sales motion in separate subqueries.
- For trigger events, use explicit recency language and search for funding, hiring, partnerships, launches, expansion, regulation, incidents, and leadership changes.
- Prioritize official company pages, newsroom posts, customer stories, product pages, investor or press pages, credible news, job postings, and relevant executive profiles.
- Treat LinkedIn-style profile snippets, unsourced lists, and old syndicated pages as lower confidence.
- Report failed or inaccessible sources when they affect trigger events, official pages, customer evidence, or buyer context.

## Output Template

Use this markdown structure and keep it practical:

```markdown
# Account Brief: <company>

## Account Snapshot
- What they do:
- Size/market/geography:
- Relevant products or business lines:

## Trigger Events
- <event>: <why it matters> ([source](URL))

## Business Priorities And Likely Pain Points
- Priority:
- Evidence:
- Sales relevance:

## Buyer And Executive Context
- Person/team:
- Relevant context:
- Confidence:

## Outreach Angles
- Angle:
- Supporting evidence:
- Discovery question:

## Source Gaps
- <missing or uncertain item>
```

Keep claims practical. Do not invent budget, intent, internal priorities, or buyer names when sources do not support them.
