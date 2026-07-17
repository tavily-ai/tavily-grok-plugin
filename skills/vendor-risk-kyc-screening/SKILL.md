---
name: vendor-risk-kyc-screening
description: Screen vendors, merchants, suppliers, counterparties, companies, executives, and related entities for vendor risk, KYC, adverse media, sanctions, regulatory actions, litigation, recalls, supplier risk, cybersecurity incidents, and compliance concerns. Use when the user asks for vendor onboarding research, KYC screening, supplier due diligence, merchant case research, or a source-grounded risk brief.
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

# Vendor Risk KYC Screening

## Workflow

Use search and extract for source-grounded vendor, merchant, supplier, counterparty, and KYC research; use map or crawl only for known official directories or registries. Treat this as research support, not a final compliance determination. Execution mechanics should come from companion endpoint skills.

Treat the guidance below as base guidance; adapt it to the user's request when appropriate.

- Identify the entity, aliases, parent/subsidiaries, executives, jurisdictions, products, and risk categories.
- Break the screen into short subqueries under 400 characters for each alias and risk type: sanctions, enforcement, litigation, regulatory warning, recall, adverse media, cybersecurity incident, supplier risk, and jurisdiction.
- Use exact-match style queries for legal names, people, product names, and phrases that must appear verbatim.
- Search first, then filter by domain trust and source type before extracting. Prioritize official regulators, sanctions lists, court records, recall databases, company disclosures, and credible news.
- Extract selected sources that can support or rule out specific findings.
- Use site navigation only when a known regulator, registry, or company site needs URL discovery.
- Collect multiple pages only for scoped official directories, recalls/advisories, policy pages, or supplier/product pages.

## Research Budget

- Start with a small focused search set covering entity aliases, sanctions/regulatory risk, adverse media, and jurisdiction-specific risk.
- Extract only the strongest official or credible sources before drafting.
- Add more searches only for named gaps, such as missing alias coverage, missing jurisdiction coverage, or unresolved high-risk findings.
- Do not use map unless a known regulator, registry, sanctions portal, or company site has specific buried pages to locate.
- Do not use crawl unless the user asks for scoped collection from an official directory, registry, recalls page, or supplier/product section.

## Capability Guidance

- Use search for most vendor screening, KYC, adverse media, sanctions, enforcement, litigation, recall, and supplier-risk discovery.
- Use extract on selected official records, regulator pages, sanctions pages, court records, recall databases, company disclosures, and credible news.
- Use map for official registries, regulator sites, sanctions portals, or company domains with hard-to-find pages.
- Use crawl for directories or official record sets only after narrowing the paths and risk categories.
- Use research for full due diligence reports, then verify high-impact claims against original sources.

## Query And Source Guidance

- Query legal names, trade names, aliases, parent/subsidiary names, executives, product names, and jurisdiction terms separately.
- Combine entity terms with specific risk concepts: sanctions, enforcement action, consent order, lawsuit, fraud, recall, breach, warning letter, import alert, debarment, bankruptcy, and adverse media.
- Prioritize regulators, sanctions databases, court systems, recall databases, official registries, company disclosures, and credible news.
- Treat unsourced aggregators, copied press releases, and name-match-only hits as low confidence until corroborated.
- Report failed or inaccessible sources when they affect official registries, sanctions pages, or high-risk findings.

## Output Template

Use this markdown structure and avoid implying clearance:

```markdown
# Vendor / KYC Risk Brief: <entity>

## Scope
- Entity and aliases checked:
- Jurisdictions:
- Risk categories:
- Source coverage limits:

## Findings
### High
- Finding:
- Evidence:
- Confidence:

### Medium
- Finding:
- Evidence:
- Confidence:

### Low / Watch
- Finding:
- Evidence:
- Confidence:

## No Relevant Findings In Searched Sources
- <risk category or alias checked>

## Recommended Next Checks
- <next check>

## Sources
- [Source title](URL) - <what it supports>
```

Say "no relevant findings found in searched sources" instead of "cleared" unless the user supplied authoritative internal checks.
