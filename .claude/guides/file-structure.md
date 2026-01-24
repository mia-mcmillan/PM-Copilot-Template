---
title: File Structure and Organization Guide
version: 1.1
last-updated: 2026-01-24
---

# File Structure and Organization Guide

This guide explains the 6-phase file organization system and conventions for organizing product management work in PM Copilot.

## Overview

PM Copilot uses a **6-phase workflow** that mirrors the product management lifecycle:

```
1-collect/     → Data collection (first-hand and second-hand sources)
2-analyze/     → Insights and pattern recognition
3-strategize/  → Strategy formation (opportunities, vision, themes, roadmap, OKRs)
4-experiment/  → Validation and testing
5-execute/     → Execution and project tracking
6-assess/      → Learning and metrics (loops back to Phase 1)
```

Each phase builds on the previous, with continuous feedback loops.

---

## Phase 1: Collect (Data Collection)

**Purpose**: Gather all source material (first-hand and second-hand) before analysis.

### Primary Sources (First-hand)

Direct, original evidence collected directly from the source:

```
1-collect/
├── primary/
│   ├── gong-calls/              # Sales call recordings/transcripts
│   ├── customer-interviews/     # Direct customer conversations
│   ├── user-research/           # User testing sessions, observations
│   ├── jpd/                     # Jira Product Discovery issues, feedback
│   ├── slack/                   # Customer conversations, support threads
│   ├── pendo/                   # Product analytics, feature usage, NPS
│   ├── analytics/               # Other product data
│   ├── support-tickets/         # Customer support interactions
│   └── surveys/                 # Direct customer feedback surveys
```

**Why these are first-hand:**
- **Gong**: Direct recordings of customer/prospect conversations
- **Customer interviews**: Your own conversations with users
- **User research**: Direct observation of user behavior
- **JPD**: Original customer problems, votes, and comments
- **Slack**: Unfiltered customer and team conversations
- **Pendo**: Actual usage behavior from your product
- **Support tickets**: Direct customer problems and feedback

**Characteristics:**
- Direct access to original data
- You control the questions and methodology
- Can verify quality yourself
- Highest reliability for decision-making

### Secondary Sources (Second-hand)

Interpretations, analyses, or summaries created by others:

```
1-collect/
└── secondary/
    ├── analyst-reports/         # Gartner, Forrester, IDC reports
    ├── market-research/         # Purchased research studies
    ├── competitor-analyses/     # Case studies, teardowns by others
    ├── industry-reports/        # State of the industry reports
    └── academic-research/       # Published studies and papers
```

**Why distinguish them:**
- Different reliability/trust levels
- Need to cite appropriately
- Should triangulate with first-hand sources
- Helps you recognize when you're over-indexing on others' interpretations

**Best practice**: Tag second-hand sources in frontmatter and always note in `2-analyze/` which insights come from them so you know what needs first-hand validation.

### Alternative Organization Options

**Option 1: Subfolder Structure** (Recommended)
```
1-collect/
├── primary/
└── secondary/
```

**Option 2: Naming Convention**
```
1-collect/
├── [primary] Customer Interview - Acme Corp.md
├── [primary] Gong Call - Q4 Enterprise Deal.md
├── [secondary] Gartner MQ - Wellness Platforms 2026.md
└── [secondary] Forrester Report - Remote Work Trends.md
```

**Option 3: Frontmatter Metadata**
```yaml
---
source-type: primary
source: gong
date: 2026-01-15
---
```

or

```yaml
---
source-type: secondary
source: Gartner
date: 2026-01-15
reliability: medium
---
```

### Naming Conventions for Collection Files

**Customer Interviews:**
```
YYYY-MM-DD - [Company] - [Role] - [Topic].md
Example: 2026-01-15 - Acme Corp - HR Director - JTBD.md
```

**Gong Calls:**
```
YYYY-MM-DD - Gong - [Company] - [Call Type].md
Example: 2026-01-10 - Gong - DataCorp - Demo Call.md
```

**Analytics/Pendo:**
```
YYYY-MM-DD - [Source] - [Report Type].md
Example: 2026-01-15 - Pendo - Feature Adoption Report Q4.md
```

**Analyst Reports:**
```
YYYY-MM - [Publisher] - [Report Title].md
Example: 2026-01 - Gartner - Magic Quadrant Wellness Platforms.md
```

---

## Phase 2: Analyze (Insights and Patterns)

**Purpose**: Transform raw data into insights, patterns, and synthesized understanding.

```
2-analyze/
├── insights/          # Individual insights from single sources
├── patterns/          # Cross-source pattern recognition
├── jtbd/             # Jobs-to-be-Done analysis
├── competitive/      # Competitive positioning analysis
└── themes/           # Strategic themes emerging from data
```

**Key distinction**: Files in `2-analyze/` are **your primary analytical work**, not second-hand sources. You're working directly with raw data from Phase 1.

**Naming Conventions:**

**Insights:**
```
[Insight Type] - [Source] - [Topic].md
Example: JTBD - HR Director - Remote Team Engagement.md
```

**Patterns:**
```
[Pattern Name] - Pattern.md
Example: Engagement Drop-off - Pattern.md
```

**Best Practice**: Always link back to source material in Phase 1:
```markdown
## Evidence

**Sources:**
- [[2026-01-15 - Acme Corp - HR Director - JTBD]]
- [[2026-01-10 - Pendo - Feature Adoption Report Q4]]
- [[2026-01-12 - Gong - DataCorp - Demo Call]]
```

---

## Phase 3: Strategize (Strategy Formation)

**Purpose**: Convert insights into strategic direction.

```
3-strategize/
├── opportunities/     # Opportunity definitions with RICE scores
├── strategy/         # Product vision, strategic themes, roadmaps
├── okrs/            # Objectives and Key Results
└── positioning/      # Market positioning documents
```

**Naming Conventions:**

**Opportunities:**
```
OPP-[Number] - [Opportunity Name].md
Example: OPP-101 - Team Fitness Challenges.md
```

**Roadmaps:**
```
YYYY-QQ - Roadmap.md
Example: 2026-Q1 - Roadmap.md
```

**OKRs:**
```
YYYY-[Quarter/Half/Year] - OKRs.md
Example: 2026-H1 - OKRs.md
```

---

## Phase 4: Experiment (Validation)

**Purpose**: Test and validate strategic hypotheses before full build.

```
4-experiment/
├── prototypes/       # Design prototypes, MVPs
├── experiments/      # A/B tests, pilots
└── validation/       # Customer validation results
```

**Naming Conventions:**

**Experiments:**
```
EXP-[Number] - [Hypothesis].md
Example: EXP-001 - Team Chat Drives Engagement.md
```

**Prototypes:**
```
PROTO-[Number] - [Feature Name].md
Example: PROTO-001 - Team Challenge Flow.md
```

---

## Phase 5: Execute (Project Tracking)

**Purpose**: Track execution with kanban boards, decisions, and progress.

```
5-execute/
├── projects/         # Kanban boards for active projects
├── decisions/        # Architecture Decision Records (ADRs)
└── sprints/         # Sprint planning and retrospectives
```

**Naming Conventions:**

**Kanban Boards:**
```
[Quarter] [Project Name] - Kanban.md
Example: Q4 2025 Team Challenges - Kanban.md
```

**Decision Records:**
```
DR-[Number] - [Decision Title].md
Example: DR-001 - Use WebSockets for Real-time Updates.md
```

---

## Phase 6: Assess (Learning and Metrics)

**Purpose**: Measure outcomes and capture learnings (feeds back to Phase 1).

```
6-assess/
├── metrics/          # Product metrics, dashboards
├── reviews/          # Weekly/monthly reviews
└── learnings/        # Post-mortems, retrospectives
```

**Naming Conventions:**

**Weekly Reviews:**
```
Weekly Review - YYYY-MM-DD.md
Example: Weekly Review - 2026-01-15.md
```

**Post-mortems:**
```
Postmortem - [Project Name] - YYYY-MM-DD.md
Example: Postmortem - Team Challenges Launch - 2026-01-30.md
```

---

## Cross-Cutting Concerns

### Templates Directory

**Templates**: All templates are bundled within their respective skill folders (`.claude/skills/*/template.md`).

### Infrastructure Directory

```
.claude/
├── modes/            # 6 coaching modes
├── coaching/         # 4 coaching patterns
├── skills/           # 13 PM skills (commands)
├── agents/           # 9 specialized agents
├── workflows/        # Phase transition guidance
└── guides/           # Documentation (this file)
```

**Do not modify** unless customizing the framework itself.

---

## File Linking Conventions

Use Obsidian-style wiki links for internal references:

**Link to file:**
```markdown
[[File Name]]
```

**Link with custom text:**
```markdown
[[File Name|Display Text]]
```

**Embed file:**
```markdown
![[File Name]]
```

**Link to heading:**
```markdown
[[File Name#Heading]]
```

**Examples:**
```markdown
This pattern is based on [[2026-01-15 - Acme Corp - HR Director - JTBD|our interview with Sarah Martinez]].

See the full analysis: [[JTBD - HR Director - Remote Team Engagement]]

Related opportunity: [[OPP-101 - Team Fitness Challenges]]
```

---

## Frontmatter Conventions

Every file should include YAML frontmatter for metadata:

### Standard Fields

```yaml
---
title: [Descriptive Title]
date: YYYY-MM-DD
author: [Your Name]
status: draft|in-review|approved|archived
phase: 1-collect|2-analyze|3-strategize|4-experiment|5-execute|6-assess
---
```

### Source-Specific Fields

**Collection files:**
```yaml
---
source-type: primary|secondary
source: gong|pendo|jpd|slack|customer-interview|analyst-report|etc
reliability: high|medium|low  # (for secondary sources)
date-collected: YYYY-MM-DD
---
```

**Analysis files:**
```yaml
---
insight-type: pattern|jtbd|competitive|theme
confidence: high|medium|low
evidence-sources: 3  # number of sources
validated: true|false
---
```

**Strategy files:**
```yaml
---
strategic-theme: [Theme Name]
owner: [PM Name]
reviewer: [Reviewer Name]
priority: now|next|later
---
```

### Extended Frontmatter Schema

See [`.claude/guides/frontmatter-conventions.md`](./frontmatter-conventions.md) for complete schema.

---

## Team Collaboration

For multi-PM workspaces:

**File Ownership:**
```yaml
---
owner: jane-doe
status: in-progress
---
```

**Review Workflows:**
```yaml
---
status: in-review
reviewer: john-smith
review-deadline: 2026-01-30
---
```

**Handoffs:**
```yaml
---
previous-owner: jane-doe
current-owner: john-smith
handoff-date: 2026-01-15
handoff-notes: "Continuing validation phase"
---
```

See [`.claude/guides/team-collaboration.md`](./team-collaboration.md) for complete guidelines.

---

## Best Practices

### 1. Start with Phase 1
Always collect source material before analyzing. Don't skip to conclusions.

### 2. Link Liberally
Connect insights to source material. Use `[[wiki links]]` extensively.

### 3. Tag Source Types
Always distinguish primary vs secondary sources in frontmatter.

### 4. Maintain Traceability
Every insight in Phase 2 should link back to sources in Phase 1.
Every opportunity in Phase 3 should link back to insights in Phase 2.

### 5. Use Consistent Naming
Follow naming conventions for easy sorting and finding.

### 6. Archive, Don't Delete
Move outdated files to `_archive/` subfolder rather than deleting.

### 7. Regular Reviews
Use Phase 6 (Assess) to review and clean up files regularly.

---

## Migration from Other Systems

### From Notion
1. Export as Markdown
2. Add frontmatter to each file
3. Convert Notion links to `[[wiki links]]`
4. Organize into phase folders

### From Confluence
1. Use Confluence markdown export
2. Add YAML frontmatter
3. Convert page links to file links
4. Organize by phase

### From Linear/Jira
1. Export issues as CSV
2. Convert to markdown files
3. Place in appropriate phase folder
4. Link to source tickets in frontmatter

---

## Examples

### Complete File Flow

**1. Customer interview** (`1-collect/primary/customer-interviews/`):
```
2026-01-15 - Acme Corp - HR Director - JTBD.md
```

**2. JTBD analysis** (`2-analyze/insights/`):
```
JTBD - HR Director - Remote Team Engagement.md
↳ Links to: [[2026-01-15 - Acme Corp - HR Director - JTBD]]
```

**3. Pattern synthesis** (`2-analyze/patterns/`):
```
Engagement Drop-off - Pattern.md
↳ Links to multiple sources in Phase 1
↳ Links to multiple insights in Phase 2
```

**4. Opportunity definition** (`3-strategize/opportunities/`):
```
OPP-101 - Team Fitness Challenges.md
↳ Links to: [[Engagement Drop-off - Pattern]]
```

**5. Roadmap prioritization** (`3-strategize/strategy/`):
```
2026-Q1 - Roadmap.md
↳ Links to: [[OPP-101 - Team Fitness Challenges]]
```

**6. Project execution** (`5-execute/projects/`):
```
Q1 2026 Team Challenges - Kanban.md
↳ Links to: [[OPP-101 - Team Fitness Challenges]]
```

**7. Weekly review** (`6-assess/reviews/`):
```
Weekly Review - 2026-01-20.md
↳ Links to: [[Q1 2026 Team Challenges - Kanban]]
```

This creates a **complete evidence chain** from raw data to shipped feature.

---

## Customization

### Adapt for Your Product

**Keep:**
- Phase structure (1-6)
- Primary/secondary source distinction
- Linking conventions
- Frontmatter schema

**Customize:**
- Subfolder names within each phase
- Naming conventions (if needed for your team)
- Frontmatter fields (add domain-specific fields)
- Templates (customize for your workflow)

### Adapt for Your Domain

**Engineering Leadership:**
```
1-collect/primary/tech-debt/
1-collect/primary/incident-reports/
2-analyze/architectural-patterns/
3-strategize/technical-roadmap/
```

**Design:**
```
1-collect/primary/user-testing/
1-collect/primary/design-critiques/
2-analyze/usability-patterns/
3-strategize/design-system/
```

The structure is domain-agnostic—adapt folders and templates for your needs.

---

## Troubleshooting

### Problem: Too many files in Phase 1
**Solution**: Create more specific subfolders, archive old data to `_archive/`

### Problem: Can't find related files
**Solution**: Use frontmatter tags, Obsidian graph view, or grep for `[[links]]`

### Problem: Links break when renaming files
**Solution**: Use Obsidian's "Update internal links" feature or find-and-replace

### Problem: Confusion between primary and secondary sources
**Solution**: Use consistent frontmatter `source-type` field, consider subfolder separation

---

## Summary

**The 6-phase structure creates an evidence chain:**
1. **Collect** sources (primary preferred, secondary tagged)
2. **Analyze** to extract insights (link to sources)
3. **Strategize** to define direction (link to insights)
4. **Experiment** to validate (link to strategy)
5. **Execute** to build (link to validation)
6. **Assess** to learn (loop back to collect)

**Key principles:**
- **Traceability**: Every decision links back to evidence
- **Source quality**: Distinguish first-hand from second-hand
- **Consistent structure**: Easy to navigate and automate
- **Team-ready**: Ownership, review, and handoff workflows

Follow these conventions and your product workspace becomes a strategic thinking tool, not just a file system.
