---
name: roadmap-plan
description: Create strategic product roadmap translating strategy into executable Now/Next/Later plans with clear priorities and sequencing
---

You are creating or updating a strategic product roadmap that translates strategy into executable plans.

## Your Task

Develop a comprehensive roadmap plan aligned with strategic themes:

1. **Gather Strategic Context**:
   - Current strategic themes from `/strategy/`
   - Pattern analyses and strategic synthesis
   - Prioritized opportunities from `/opportunities/`
   - SWOT and competitive analyses
   - Current OKRs and success metrics

2. **Define Roadmap Scope**:
   - Time horizon (3/6/12 months or quarterly)
   - Product area(s) covered
   - Resource capacity available
   - Strategic vs tactical balance

3. **Organize Into Roadmap Themes**:
   - Map opportunities to strategic themes
   - Group related initiatives
   - Sequence based on dependencies
   - Balance quick wins with long-term bets
   - Consider build/buy/partner options

4. **Create Roadmap Document**: Generate in `/strategy/` with:
   ```markdown
   # [Period] - Product Roadmap

   **Planning Period**: [Date Range]
   **Last Updated**: [Date]
   **Owner**: [PM Name]
   **Status**: [Draft/Approved/In Progress]

   ## Roadmap Vision
   [Where we're taking the product and why]

   ## Strategic Alignment
   This roadmap advances the following strategic themes:
   1. [[Strategic Theme 1]] - [How this roadmap supports it]
   2. [[Strategic Theme 2]] - [How this roadmap supports it]

   ## Success Metrics
   - [Key metrics this roadmap aims to move]
   - [Target values or improvement goals]

   ## Roadmap Structure

   ### Now (Current Quarter/0-3 months)
   **Focus**: [What we're optimizing for this period]
   **Capacity Allocation**: [Team allocation across themes]

   #### Initiative 1: [Initiative Name]
   **Strategic Theme**: [[Theme Name]]
   **Problem**: [Customer problem being solved]
   **Solution**: [High-level solution approach]
   **Success Metrics**: [How we measure success]
   **Effort**: [T-shirt size or story points]
   **Dependencies**: [Technical or organizational dependencies]
   **JPD Links**: [Link to opportunities]
   **Status**: [Not Started/In Progress/Completed]

   #### [Additional NOW initiatives...]

   ### Next (Next Quarter/3-6 months)
   **Focus**: [Strategic focus for this horizon]

   #### Initiative: [Name]
   [Same structure as NOW items]

   ### Later (6-12 months)
   **Focus**: [Long-term strategic focus]

   #### Initiative: [Name]
   [Same structure, but with more uncertainty noted]

   ### Under Consideration
   [Ideas being explored but not yet committed]

   #### Opportunity: [Name]
   **Why Interesting**: [Strategic value]
   **Open Questions**: [What we need to learn]
   **Decision Date**: [When we'll decide]

   ## Cross-Initiative Dependencies
   [Map dependencies between initiatives]

   ## Resource Allocation
   | Theme | Now | Next | Later | Total |
   |-------|-----|------|-------|-------|
   | [Theme 1] | 40% | 30% | 20% | 30% |
   | [Theme 2] | 30% | 40% | 30% | 33% |

   ## Risks & Mitigations
   | Risk | Impact | Likelihood | Mitigation |
   |------|---------|------------|------------|
   | [Risk] | H/M/L | H/M/L | [How to address] |

   ## What's Not On the Roadmap
   [Important to call out what we're NOT doing and why]

   ## Roadmap Assumptions
   - [Key assumptions underlying this plan]
   - [What would cause us to re-plan]

   ## Stakeholder Communication
   **Internal Review**: [Date and participants]
   **Executive Approval**: [Date and status]
   **Team Communication**: [How and when shared]
   **Customer Preview**: [If applicable]

   ## Review & Update Cadence
   [How often we review and update this roadmap]
   ```

5. **Create Supporting Artifacts**:
   - Timeline visualization (suggest format)
   - Theme-based view for stakeholders
   - Jira epic creation checklist
   - Roadmap presentation deck outline

6. **Link to Execution**:
   - Map initiatives to OKRs
   - Connect to JPD opportunities
   - Link to Jira epics (if created)
   - Reference supporting analyses

## Output

Present:
- Roadmap summary (Now/Next/Later highlights)
- Strategic alignment validation
- Resource allocation breakdown
- File path to roadmap document
- Recommended next steps for execution
