---
title: Frontmatter Conventions and Schema
version: 1.1
last-updated: 2026-01-24
---

# Frontmatter Conventions and Schema

This guide documents the YAML frontmatter schema used across PM Copilot files for metadata, collaboration, and automation.

## Overview

Every markdown file should include YAML frontmatter at the top:

```yaml
---
key: value
another-key: another value
---
```

Frontmatter enables:
- **Collaboration**: Track ownership, status, reviews
- **Organization**: Filter and query files by metadata
- **Automation**: Scripts and tools can parse metadata
- **Context**: Claude understands file purpose and status

---

## Universal Fields (All Files)

Use these fields in every file:

```yaml
---
title: Descriptive Title Here
date: YYYY-MM-DD
author: Your Name
status: draft|in-review|approved|archived
phase: 1-collect|2-analyze|3-strategize|4-experiment|5-execute|6-assess
---
```

### Field Definitions

| Field | Type | Required | Description | Example |
|-------|------|----------|-------------|---------|
| `title` | string | Yes | Human-readable title | `Customer Interview - Acme Corp` |
| `date` | date | Yes | File creation or last major update | `2026-01-24` |
| `author` | string | Yes | Primary author | `Jane Doe` |
| `status` | enum | Yes | Current workflow status | `draft`, `in-review`, `approved`, `archived` |
| `phase` | enum | Yes | Which phase this file belongs to | `1-collect`, `2-analyze`, `3-strategize`, `4-experiment`, `5-execute`, `6-assess` |

### Status Values

- **`draft`**: Work in progress, not ready for review
- **`in-review`**: Ready for feedback, awaiting review
- **`approved`**: Reviewed and approved, ready to use
- **`archived`**: No longer active, kept for reference

---

## Phase-Specific Fields

### Phase 1: Collect

Files in `1-collect/` should include source-specific metadata:

```yaml
---
# Universal fields
title: Customer Interview - Acme Corp - HR Director
date: 2026-01-15
author: Jane Doe
status: approved
phase: 1-collect

# Collection-specific fields
source-type: primary
source: customer-interview
date-collected: 2026-01-15
participants: ["Jane Doe", "Sarah Martinez"]
company: Acme Corp
role: HR Director
---
```

#### Primary Sources

```yaml
---
source-type: primary
source: gong|pendo|jpd|slack|customer-interview|user-research|analytics|support-ticket
---
```

**Source options:**
- `gong` - Sales call recordings/transcripts
- `pendo` - Product analytics, feature usage
- `jpd` - Jira Product Discovery issues
- `slack` - Customer/team conversations
- `customer-interview` - Direct customer interviews
- `user-research` - User testing sessions
- `analytics` - Product analytics data
- `support-ticket` - Customer support interactions
- `survey` - Customer feedback surveys

#### Secondary Sources

```yaml
---
source-type: secondary
source: analyst-report|market-research|competitor-analysis|industry-report|academic-research
reliability: high|medium|low
publisher: Gartner
publication-date: 2026-01
---
```

**Reliability levels:**
- `high` - Trusted source, rigorous methodology
- `medium` - Decent source, some methodology concerns
- `low` - Questionable source, treat as directional only

#### Complete Example (Primary Source)

```yaml
---
title: Gong Call - DataCorp - Q4 Enterprise Demo
date: 2026-01-10
author: Jane Doe
status: approved
phase: 1-collect
source-type: primary
source: gong
date-collected: 2026-01-10
participants: ["John Sales", "DataCorp CTO", "DataCorp PM"]
company: DataCorp
call-type: demo
duration-minutes: 45
recording-url: https://app.gong.io/call?id=123456
tags: ["enterprise", "analytics-feature", "competitive-mention"]
---
```

#### Complete Example (Secondary Source)

```yaml
---
title: Gartner Magic Quadrant - Wellness Platforms 2026
date: 2026-01-20
author: Jane Doe
status: approved
phase: 1-collect
source-type: secondary
source: analyst-report
reliability: high
publisher: Gartner
publication-date: 2026-01
report-url: https://www.gartner.com/doc/123456
tags: ["competitive-intelligence", "market-positioning"]
---
```

### Phase 2: Analyze

Files in `2-analyze/` should include analysis-specific metadata:

```yaml
---
# Universal fields
title: JTBD - HR Director - Remote Team Engagement
date: 2026-01-16
author: Jane Doe
status: approved
phase: 2-analyze

# Analysis-specific fields
insight-type: jtbd
confidence: high
evidence-sources: 3
validated: true
strategic-theme: Employee Engagement
---
```

#### Insight Types

- `jtbd` - Jobs-to-be-Done analysis
- `pattern` - Cross-source pattern recognition
- `competitive` - Competitive positioning analysis
- `theme` - Strategic theme identification
- `user-journey` - User journey mapping
- `synthesis` - Multi-source insight synthesis

#### Confidence Levels

- `high` - 3+ sources, consistent evidence, validated
- `medium` - 2 sources, mostly consistent, some validation
- `low` - 1 source or inconsistent evidence, unvalidated

#### Complete Example

```yaml
---
title: Engagement Drop-off - Pattern
date: 2026-01-18
author: Jane Doe
status: approved
phase: 2-analyze
insight-type: pattern
confidence: high
evidence-sources: 5
validated: true
strategic-theme: Employee Engagement
evidence-links:
  - "[[2026-01-15 - Acme Corp - HR Director - JTBD]]"
  - "[[2026-01-10 - Pendo - Feature Adoption Report Q4]]"
  - "[[2026-01-12 - Gong - DataCorp - Demo Call]]"
  - "[[2026-01-08 - Slack - Customer Success Thread]]"
  - "[[2026-01-05 - Support Ticket Analysis]]"
tags: ["engagement", "retention", "onboarding"]
---
```

### Phase 3: Strategize

Files in `3-strategize/` should include strategy-specific metadata:

```yaml
---
# Universal fields
title: OPP-101 - Team Fitness Challenges
date: 2026-01-20
author: Jane Doe
status: approved
phase: 3-strategize

# Strategy-specific fields
opportunity-id: OPP-101
strategic-theme: Employee Engagement
priority: now
rice-score: 22500
reach: 5000
impact: 9
confidence: 5
effort: 10
owner: Jane Doe
reviewer: John Smith
target-quarter: 2026-Q1
---
```

#### Priority Levels

- `now` - Current quarter, top priority
- `next` - Next 2-3 quarters
- `later` - Future consideration, 6+ months out
- `ice-box` - Good idea, not prioritized yet
- `rejected` - Decided not to pursue (with reasoning)

#### Complete Example (Opportunity)

```yaml
---
title: OPP-101 - Team Fitness Challenges
date: 2026-01-20
author: Jane Doe
status: approved
phase: 3-strategize
opportunity-id: OPP-101
strategic-theme: Employee Engagement
priority: now
rice-score: 22500
reach: 5000
impact: 9
confidence: 5
effort: 10
owner: Jane Doe
reviewer: John Smith
reviewed-date: 2026-01-22
target-quarter: 2026-Q1
jpd-link: https://company.atlassian.net/jira/software/projects/JPD/ideas/view/123
related-patterns:
  - "[[Engagement Drop-off - Pattern]]"
tags: ["team-engagement", "gamification", "retention"]
---
```

#### Complete Example (Roadmap)

```yaml
---
title: 2026-Q1 Roadmap
date: 2026-01-22
author: Jane Doe
status: in-review
phase: 3-strategize
roadmap-period: 2026-Q1
strategic-themes: ["Employee Engagement", "Enterprise Scale"]
owner: Jane Doe
reviewer: Sarah VP-Product
review-deadline: 2026-01-31
last-updated: 2026-01-24
tags: ["roadmap", "q1-2026"]
---
```

#### Complete Example (OKRs)

```yaml
---
title: 2026-H1 OKRs
date: 2026-01-25
author: Jane Doe
status: draft
phase: 3-strategize
okr-period: 2026-H1
owner: Jane Doe
reviewer: Sarah VP-Product
review-deadline: 2026-02-01
strategic-alignment: "[[2026 Product Vision]]"
tags: ["okrs", "h1-2026"]
---
```

### Phase 4: Experiment

Files in `4-experiment/` should include experiment-specific metadata:

```yaml
---
# Universal fields
title: EXP-001 - Team Chat Drives Engagement
date: 2026-02-01
author: Jane Doe
status: in-progress
phase: 4-experiment

# Experiment-specific fields
experiment-id: EXP-001
hypothesis: Team chat increases engagement by 30%
method: A/B test
start-date: 2026-02-05
end-date: 2026-02-19
sample-size: 500
related-opportunity: "[[OPP-101 - Team Fitness Challenges]]"
tags: ["validation", "team-chat", "engagement"]
---
```

#### Complete Example

```yaml
---
title: EXP-001 - Team Chat Drives Engagement Hypothesis
date: 2026-02-01
author: Jane Doe
status: in-progress
phase: 4-experiment
experiment-id: EXP-001
hypothesis: "Adding team chat to challenges increases weekly active users by 30%"
method: A/B test
start-date: 2026-02-05
end-date: 2026-02-19
sample-size: 500
control-group: 250
treatment-group: 250
success-criteria: "30% increase in WAU, 95% confidence"
related-opportunity: "[[OPP-101 - Team Fitness Challenges]]"
results-status: pending
tags: ["validation", "team-chat", "engagement"]
---
```

### Phase 5: Execute

Files in `5-execute/` should include execution-specific metadata:

```yaml
---
# Universal fields
title: Q1 2026 Team Challenges - Kanban
date: 2026-02-01
author: Jane Doe
status: in-progress
phase: 5-execute

# Execution-specific fields
kanban-plugin: board
project-id: PROJ-101
related-opportunity: "[[OPP-101 - Team Fitness Challenges]]"
start-date: 2026-02-01
target-launch: 2026-03-31
team: ["Jane Doe", "John Dev", "Sarah Designer"]
epic-link: https://company.atlassian.net/browse/EPIC-123
tags: ["project", "team-challenges", "q1-2026"]
---
```

#### Complete Example (Kanban)

```yaml
---
title: Q1 2026 Team Challenges MVP - Kanban
date: 2026-02-01
author: Jane Doe
status: in-progress
phase: 5-execute
kanban-plugin: board
project-id: PROJ-101
related-opportunity: "[[OPP-101 - Team Fitness Challenges]]"
start-date: 2026-02-01
target-launch: 2026-03-31
actual-launch: null
team:
  pm: Jane Doe
  eng-lead: John Dev
  design-lead: Sarah Designer
  engineers: ["John Dev", "Alice Eng", "Bob Eng"]
epic-link: https://company.atlassian.net/browse/EPIC-123
sprint: Sprint 23
tags: ["project", "team-challenges", "q1-2026", "mvp"]
---
```

#### Complete Example (Decision Record)

```yaml
---
title: DR-001 - Use WebSockets for Real-time Updates
date: 2026-02-10
author: John Dev
status: approved
phase: 5-execute
decision-id: DR-001
decision-type: architectural
context: "[[Q1 2026 Team Challenges - Kanban]]"
decision-maker: John Dev
approver: Jane Doe (PM)
approved-date: 2026-02-11
alternatives-considered: ["polling", "server-sent events", "WebSockets"]
decision: WebSockets
rationale: "Real-time is critical for engagement, WebSockets best for bidirectional"
consequences: "Increased infra complexity, better UX"
tags: ["architecture", "real-time", "websockets"]
---
```

### Phase 6: Assess

Files in `6-assess/` should include assessment-specific metadata:

```yaml
---
# Universal fields
title: Weekly Review - 2026-02-15
date: 2026-02-15
author: Jane Doe
status: approved
phase: 6-assess

# Assessment-specific fields
review-type: weekly
review-period: 2026-W07
owner: Jane Doe
attendees: ["Jane Doe", "John Dev", "Sarah Designer"]
related-projects:
  - "[[Q1 2026 Team Challenges - Kanban]]"
tags: ["weekly-review", "q1-2026"]
---
```

#### Complete Example (Weekly Review)

```yaml
---
title: Weekly Review - 2026-02-15
date: 2026-02-15
author: Jane Doe
status: approved
phase: 6-assess
review-type: weekly
review-period: 2026-W07
owner: Jane Doe
attendees: ["Jane Doe", "John Dev", "Sarah Designer", "Alice Eng"]
related-projects:
  - "[[Q1 2026 Team Challenges - Kanban]]"
key-metrics:
  velocity: 23
  burn-down: on-track
  blockers: 1
tags: ["weekly-review", "q1-2026"]
---
```

#### Complete Example (Post-mortem)

```yaml
---
title: Postmortem - Team Challenges Launch
date: 2026-04-05
author: Jane Doe
status: approved
phase: 6-assess
review-type: postmortem
project: "[[Q1 2026 Team Challenges - Kanban]]"
launch-date: 2026-03-31
owner: Jane Doe
attendees: ["Jane Doe", "John Dev", "Sarah Designer", "Product Team"]
outcome: success
success-metrics:
  engagement-increase: 35%
  adoption-rate: 68%
  nps-delta: +12
tags: ["postmortem", "team-challenges", "q1-2026"]
---
```

---

## Team Collaboration Fields

For multi-PM workspaces, add collaboration fields:

```yaml
---
# Ownership
owner: jane-doe
previous-owner: john-smith  # (for handoffs)

# Review workflow
reviewer: sarah-vp-product
review-deadline: 2026-02-01
reviewed-date: 2026-01-30

# Handoffs
handoff-date: 2026-01-15
handoff-notes: "Continuing validation phase, experiments in flight"

# Notifications
notify: ["jane-doe", "john-smith"]
---
```

See [team-collaboration.md](./team-collaboration.md) for complete guidelines.

---

## Tags

Use tags for cross-cutting themes and easy filtering:

```yaml
---
tags: ["engagement", "retention", "enterprise", "gamification"]
---
```

**Common tag categories:**
- **Features**: `team-challenges`, `ai-coaching`, `analytics-dashboard`
- **Themes**: `engagement`, `retention`, `onboarding`, `enterprise-scale`
- **Customer segments**: `enterprise`, `smb`, `consumer`
- **Methodologies**: `jtbd`, `competitive`, `swot`, `rice`
- **Status**: `validated`, `high-confidence`, `needs-validation`
- **Time periods**: `q1-2026`, `h1-2026`, `2026`

---

## Optional Fields

### URLs and Links

```yaml
---
jpd-link: https://company.atlassian.net/jira/software/projects/JPD/ideas/view/123
jira-epic: https://company.atlassian.net/browse/EPIC-123
figma-link: https://figma.com/file/abc123
recording-url: https://app.gong.io/call?id=123456
---
```

### Multi-value Fields

```yaml
---
participants: ["Jane Doe", "John Smith", "Sarah Designer"]
evidence-links:
  - "[[Source 1]]"
  - "[[Source 2]]"
  - "[[Source 3]]"
strategic-themes: ["Engagement", "Retention"]
---
```

### Custom Domain Fields

Add domain-specific fields as needed:

```yaml
---
# Healthcare-specific
hipaa-compliant: true
patient-facing: false

# Financial services
regulatory-approval: required
compliance-review: pending

# B2B SaaS
enterprise-ready: true
sso-required: true
---
```

---

## Validation

### Required Field Checker

Use this regex to validate required fields are present:

```regex
^---\n.*title:.*\n.*date:.*\n.*author:.*\n.*status:.*\n.*phase:.*\n.*---$
```

### Status Transition Rules

Valid status transitions:
- `draft` → `in-review`
- `in-review` → `approved` or `draft` (if revision needed)
- `approved` → `archived` (when no longer active)
- `archived` → (no transitions, permanent archive)

### Date Format

Always use ISO 8601 format: `YYYY-MM-DD`
- Correct: `2026-01-24`
- Incorrect: `01/24/2026`, `24-Jan-2026`, `Jan 24 2026`

---

## Automation and Queries

### Obsidian Dataview Queries

**Find all draft documents:**
```dataview
TABLE author, date
FROM ""
WHERE status = "draft"
SORT date DESC
```

**Find high-priority opportunities:**
```dataview
TABLE priority, rice-score, strategic-theme
FROM "3-strategize/opportunities"
WHERE priority = "now"
SORT rice-score DESC
```

**Find files by owner:**
```dataview
TABLE status, phase, date
FROM ""
WHERE owner = "jane-doe"
SORT date DESC
```

**Find unvalidated insights:**
```dataview
TABLE confidence, evidence-sources
FROM "2-analyze"
WHERE validated = false
SORT confidence ASC
```

### Command-line Queries (grep/ripgrep)

**Find all files in review:**
```bash
rg "status: in-review" --files-with-matches
```

**Find files by strategic theme:**
```bash
rg "strategic-theme: Employee Engagement" --files-with-matches
```

**Find files needing review this week:**
```bash
rg "review-deadline: 2026-02-" --files-with-matches
```

---

## Best Practices

### 1. Always Include Required Fields
Never skip `title`, `date`, `author`, `status`, or `phase`.

### 2. Use Consistent Values
Stick to defined enum values for `status`, `phase`, `priority`, etc.

### 3. Update Dates When Editing
Change `date` field when making significant updates.

### 4. Link to Related Files
Use `related-opportunity`, `evidence-links`, etc. to maintain traceability.

### 5. Tag Thoughtfully
Use consistent tag names. Avoid tag explosion (prefer 3-7 tags per file).

### 6. Add Context for Future Self
Use `notes`, `rationale`, or `context` fields to explain non-obvious decisions.

### 7. Archive, Don't Delete
Change `status: archived` rather than deleting files.

---

## Examples by File Type

### Customer Interview

```yaml
---
title: Customer Interview - Acme Corp - HR Director - JTBD
date: 2026-01-15
author: Jane Doe
status: approved
phase: 1-collect
source-type: primary
source: customer-interview
date-collected: 2026-01-15
participants: ["Jane Doe", "Sarah Martinez"]
company: Acme Corp
role: HR Director
interview-type: JTBD
duration-minutes: 45
recording-url: https://zoom.us/rec/123456
tags: ["customer-interview", "jtbd", "hr-director", "engagement"]
---
```

### Pattern Analysis

```yaml
---
title: Engagement Drop-off - Pattern
date: 2026-01-18
author: Jane Doe
status: approved
phase: 2-analyze
insight-type: pattern
confidence: high
evidence-sources: 5
validated: true
strategic-theme: Employee Engagement
evidence-links:
  - "[[2026-01-15 - Acme Corp - HR Director - JTBD]]"
  - "[[2026-01-10 - Pendo - Feature Adoption Report Q4]]"
tags: ["pattern", "engagement", "retention"]
---
```

### Opportunity

```yaml
---
title: OPP-101 - Team Fitness Challenges
date: 2026-01-20
author: Jane Doe
status: approved
phase: 3-strategize
opportunity-id: OPP-101
strategic-theme: Employee Engagement
priority: now
rice-score: 22500
owner: Jane Doe
target-quarter: 2026-Q1
tags: ["opportunity", "team-challenges", "high-priority"]
---
```

### Kanban Board

```yaml
---
title: Q1 2026 Team Challenges - Kanban
date: 2026-02-01
author: Jane Doe
status: in-progress
phase: 5-execute
kanban-plugin: board
project-id: PROJ-101
related-opportunity: "[[OPP-101 - Team Fitness Challenges]]"
target-launch: 2026-03-31
tags: ["project", "kanban", "q1-2026"]
---
```

### Weekly Review

```yaml
---
title: Weekly Review - 2026-02-15
date: 2026-02-15
author: Jane Doe
status: approved
phase: 6-assess
review-type: weekly
review-period: 2026-W07
owner: Jane Doe
tags: ["weekly-review", "q1-2026"]
---
```

---

## Migration Guide

### Adding Frontmatter to Existing Files

1. Open file in editor
2. Add `---` at the very top
3. Add required fields
4. Add phase-specific fields
5. Add `---` to close frontmatter
6. Save file

**Before:**
```markdown
# Customer Interview - Acme Corp

Sarah Martinez, HR Director at Acme Corp...
```

**After:**
```markdown
---
title: Customer Interview - Acme Corp - HR Director
date: 2026-01-15
author: Jane Doe
status: approved
phase: 1-collect
source-type: primary
source: customer-interview
---

# Customer Interview - Acme Corp

Sarah Martinez, HR Director at Acme Corp...
```

### Bulk Migration Script

Use this bash script to add basic frontmatter to all files:

```bash
#!/bin/bash
# add-frontmatter.sh

for file in $(find . -name "*.md" -type f); do
  # Check if file already has frontmatter
  if ! head -n 1 "$file" | grep -q "^---$"; then
    # Get filename without extension
    filename=$(basename "$file" .md)

    # Add basic frontmatter
    cat > "$file.tmp" <<EOF
---
title: $filename
date: $(date +%Y-%m-%d)
author: Your Name
status: draft
phase: 1-collect
---

$(cat "$file")
EOF

    mv "$file.tmp" "$file"
    echo "Added frontmatter to: $file"
  fi
done
```

---

## Summary

**Frontmatter enables:**
- **Traceability**: Link files across phases
- **Collaboration**: Track ownership and reviews
- **Organization**: Filter and query by metadata
- **Automation**: Scripts and tools can parse metadata
- **Context**: Claude understands file purpose and status

**Key principles:**
- Always include required fields
- Use consistent enum values
- Link to related files
- Tag thoughtfully
- Update dates when editing

Follow these conventions and your files become queryable, traceable, and collaboration-ready.
