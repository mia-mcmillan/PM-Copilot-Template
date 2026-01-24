# Primary Sources (First-hand)

Direct, original evidence collected directly from the source.

## Current Folders

- **customer-interviews/** - Direct customer conversations and JTBD interviews

## Recommended Subfolders

Create these folders as needed when collecting data:

- **gong-calls/** - Sales call recordings/transcripts from Gong
- **user-research/** - User testing sessions, observations, research studies
- **jpd/** - Jira Product Discovery issues, customer feedback, votes
- **slack/** - Customer conversations, support threads, team discussions
- **pendo/** - Product analytics, feature usage, NPS surveys
- **analytics/** - Other product data and analytics exports
- **support-tickets/** - Customer support interactions and tickets
- **surveys/** - Direct customer feedback surveys

## Why Primary Sources?

Primary sources give you:
- **Direct access** to original data
- **Control** over questions and methodology
- **Highest reliability** for decision-making
- **Ability to verify** quality yourself

## Naming Conventions

### Customer Interviews
```
YYYY-MM-DD - [Company] - [Role] - [Topic].md
Example: 2026-01-15 - Acme Corp - HR Director - JTBD.md
```

### Gong Calls
```
YYYY-MM-DD - Gong - [Company] - [Call Type].md
Example: 2026-01-10 - Gong - DataCorp - Demo Call.md
```

### Analytics/Pendo
```
YYYY-MM-DD - [Source] - [Report Type].md
Example: 2026-01-15 - Pendo - Feature Adoption Report Q4.md
```

## Frontmatter

Tag all primary sources with:

```yaml
---
source-type: primary
source: gong|pendo|jpd|slack|customer-interview|user-research|analytics|support-ticket
date-collected: YYYY-MM-DD
---
```

See [`.claude/guides/frontmatter-conventions.md`](../../.claude/guides/frontmatter-conventions.md) for complete schema.