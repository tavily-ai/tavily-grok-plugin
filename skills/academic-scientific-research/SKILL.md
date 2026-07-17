---
name: academic-scientific-research
description: Find, screen, and synthesize academic papers, scientific literature, technical reports, preprints, clinical or biomedical publications, and evidence around a research question. Use when the user asks to find papers, summarize literature, compare methods, identify seminal or recent work, extract claims from studies, or build a source-grounded academic/scientific evidence brief.
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

# Academic Scientific Research

## Workflow

Use search to discover scholarly sources, extract to verify source content, map or crawl for known scholarly sites and collections, and research for full literature-review synthesis. Keep this skill focused on research planning, source selection, extraction targets, and evidence synthesis; execution mechanics should come from companion endpoint skills.

Treat the guidance below as base guidance; adapt it to the user's request when appropriate.

- Translate the user's question into search terms, synonyms, key entities, and likely source domains.
- Break broad questions into short subqueries under 400 characters: core concept, synonyms, method names, target population or data, benchmark or dataset, author/lab, and year range.
- Prefer scholarly and official sources when available: preprint servers, PubMed/NIH pages, journals, conference proceedings, professional societies, standards bodies, and official technical reports.
- Extract from the strongest selected pages after screening titles, snippets, source type, recency, and relevance.
- Reserve broad research synthesis for full literature reviews, research landscapes, or multi-method comparisons.
- Distinguish primary studies, review papers, preprints, editorials, guidelines, standards, and news coverage.

## Research Budget

- Start with a small focused search set covering the main concept, synonyms, methods, and source type.
- Extract only the strongest scholarly sources before drafting the evidence brief.
- Add more searches only for named gaps, such as missing review papers, missing recent work, or missing primary studies.
- Do not use map unless a known lab, journal, conference, repository, or documentation site has buried pages.
- Do not use crawl unless the user needs broad collection from a known proceedings, publication list, or docs section.

## Capability Guidance

- Use search first when the user needs papers, methods, benchmarks, authors, institutions, or recent work.
- Use extract when comparing a small set of papers, reading abstracts, or verifying study claims.
- Use map only when a known lab, journal, conference, repository, or documentation site has useful but hard-to-find pages.
- Use crawl only when the user needs many pages from a known source, such as proceedings, a lab publication list, or a technical docs section.
- Use research only when the user explicitly needs a full literature review or research landscape.

## Query And Source Guidance

- Pair formal terms with common synonyms and acronyms.
- Include population, dataset, benchmark, organism, intervention, model, metric, or method terms when relevant.
- For recent literature, include explicit year ranges or recency language in the query.
- Prefer primary literature for claims, review papers for landscape summaries, and guidelines/standards for practice recommendations.
- Deduplicate preprints and final publications; cite the final version when available.
- Treat abstracts, papers, supplemental pages, tables, and official repositories as separate evidence surfaces.
- Report failed or inaccessible sources when they affect key papers, guidelines, datasets, or primary evidence.

## Output Template

Use this markdown structure and adapt sections to the user's scope:

```markdown
# Evidence Brief: <topic>

## Research Question
<brief framing of the question>

## Search Strategy
- Concepts searched:
- Source types prioritized:
- Inclusion logic:
- Exclusions or limitations:

## Key Sources
| Source | Type | Why it matters | URL |
| --- | --- | --- | --- |

## Findings
### <Theme>
- Claim:
- Evidence:
- Limitations:

### <Theme>
- Claim:
- Evidence:
- Limitations:

## Consensus And Disagreement
- Consensus:
- Disagreement:
- Evidence gaps:

## Follow-Up Queries
- <query idea>
```

For medical, clinical, or biomedical topics, be conservative: do not provide diagnosis or treatment advice, and prioritize primary literature, systematic reviews, guidelines, and official health sources.
