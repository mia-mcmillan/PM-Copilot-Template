# Secondary Sources (Second-hand)

Interpretations, analyses, or summaries created by others.

## Recommended Subfolders

Create these folders as needed when collecting research:

- **analyst-reports/** - Gartner, Forrester, IDC market reports
- **market-research/** - Purchased research studies and surveys
- **competitor-analyses/** - Case studies, teardowns, analyses by others
- **industry-reports/** - State of the industry reports and trends
- **academic-research/** - Published studies and academic papers

## Why Distinguish Secondary Sources?

Secondary sources:
- Add a **layer of interpretation** (someone else's analysis)
- Have **different reliability** levels (need to assess credibility)
- Should be **triangulated** with first-hand sources
- Help you recognize when you're **over-indexing** on others' interpretations

## When to Use Secondary Sources

Use secondary sources for:
- **Broad market context** and trends
- **Competitive intelligence** when you can't get direct data
- **Industry benchmarks** and standards
- **Academic validation** of frameworks and approaches

**Best practice**: Always validate key insights from secondary sources with your own primary research.

## Naming Conventions

### Analyst Reports
```
YYYY-MM - [Publisher] - [Report Title].md
Example: 2026-01 - Gartner - Magic Quadrant Wellness Platforms.md
```

### Market Research
```
YYYY-MM - [Publisher] - [Study Title].md
Example: 2026-01 - Forrester - Remote Work Trends Study.md
```

### Competitor Analyses
```
YYYY-MM - [Topic] - Competitor Analysis.md
Example: 2026-01 - Team Engagement Features - Competitor Analysis.md
```

## Frontmatter

Tag all secondary sources with:

```yaml
---
source-type: secondary
source: analyst-report|market-research|competitor-analysis|industry-report|academic-research
reliability: high|medium|low
publisher: [Publisher Name]
publication-date: YYYY-MM
---
```

### Reliability Levels

- **high**: Trusted source, rigorous methodology (Gartner, Forrester, academic journals)
- **medium**: Decent source, some methodology concerns (industry blogs, startup reports)
- **low**: Questionable source, treat as directional only (unverified analyses, opinion pieces)

## In Analysis (Phase 2)

When creating insights in `2-analyze/`, always note which insights come from secondary sources so you know what needs first-hand validation:

```markdown
## Evidence

**Primary sources:**
- [[Customer Interview - Acme Corp]]
- [[Pendo - Feature Adoption Report]]

**Secondary sources:**
- [[Gartner MQ - Wellness Platforms]] (reliability: high)

**Status**: Partially validated - need 2 more customer interviews to confirm pattern
```

See [`.claude/guides/frontmatter-conventions.md`](../../.claude/guides/frontmatter-conventions.md) for complete schema.
