---
name: threat-intelligence-enrichment
description: Enrich threat intelligence from CVEs, IOCs, malware names, threat actors, vendor advisories, security incidents, exploit reports, vulnerability disclosures, breach news, and mitigation guidance. Use when the user asks to investigate a CVE, enrich indicators, summarize vendor advisories, assess exploit status, collect mitigations, or produce a source-grounded security brief.
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

# Threat Intelligence Enrichment

## Workflow

Use search and extract to enrich security entities with authoritative and recent evidence; use map or crawl for known vendor portals or advisory collections. Keep this skill focused on query construction, source priority, verification, and security synthesis; execution mechanics should come from companion endpoint skills.

Treat the guidance below as base guidance; adapt it to the user's request when appropriate.

- Identify the input type: CVE, IOC, malware/tool, threat actor, vendor/product, advisory URL, incident, or campaign.
- Break the task into short subqueries under 400 characters: identifier, affected product, exploit status, vendor advisory, patches, mitigations, exploitation in the wild, and recent reporting.
- Search first, using exact-match style queries for CVEs, hashes, domains, IPs, advisory IDs, and malware names.
- Filter sources before extraction. Prioritize NVD/CVE records, vendor advisories, CISA/agency alerts, security research blogs, reputable incident reports, and official patch notes.
- Extract selected pages that can support exploit status, impact, affected versions, mitigations, timeline, or confidence.
- Use site navigation for vendor advisory portals or documentation sites when the relevant page is hard to find.
- Collect scoped advisory, changelog, release note, or documentation sections only when the user needs broad coverage.

## Research Budget

- Start with a small focused search set covering the identifier, vendor advisory, exploit status, and mitigation or patch evidence.
- Extract only the strongest authoritative sources before drafting.
- Add more searches only for named gaps, such as missing affected versions, missing patch notes, or unclear exploitation status.
- Do not use map unless a known vendor portal or documentation site has a specific advisory or release note to locate.
- Do not use crawl unless the user asks for coverage across many related advisories or docs pages.

## Capability Guidance

- Use search for CVEs, IOCs, advisories, exploit status, affected versions, mitigations, and recent incident reporting.
- Use extract on selected vendor advisories, CVE records, agency alerts, patch notes, and security research pages.
- Use map when a vendor portal or documentation site is known but the specific advisory is hard to locate.
- Use crawl for advisory/doc sets only when the user asks for coverage across many related pages.
- Use research only for threat landscape reports or multi-campaign summaries.

## Query And Source Guidance

- Use exact identifiers in queries: CVE IDs, advisory IDs, product/version names, hashes, domains, IPs, malware names, and actor aliases.
- Prioritize vendor advisories, NVD/CVE records, CISA or national agency alerts, CERT/CC, official patch notes, and reputable security research.
- Treat social posts, exploit-db style references, and secondary news as supporting evidence unless confirmed by authoritative sources.
- Separate "exploited in the wild", "public PoC", "theoretical exploitability", and "patched" as different statuses.
- Report failed or inaccessible sources when they affect vendor advisories, CVE records, affected-version evidence, or mitigation guidance.

## Output Template

Use this markdown structure and label uncertainty:

```markdown
# Threat Intelligence Brief: <entity>

## Summary
- Current status:
- Confidence:
- Most important source:

## Entity Details
- Type:
- Aliases/identifiers:
- Related products or systems:

## Impact And Exposure
- Affected products/versions:
- Exploit status:
- Evidence quality:

## Mitigation And Detection
- Patches or mitigations:
- Detection or hunting notes:
- Recommended checks:

## Timeline
- <date>: <event> ([source](URL))

## Sources And Gaps
- Sources:
- Gaps or unresolved claims:
```

Do not overstate attribution, exploitation, or compromise evidence. Label speculation and unverified claims.
