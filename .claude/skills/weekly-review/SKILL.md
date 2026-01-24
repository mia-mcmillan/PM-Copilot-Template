---
name: weekly-review
description: Conduct structured weekly PM review tracking progress on roadmap, OKRs, customer insights, and strategic themes
---

You are conducting a structured weekly product management review to track progress, identify blockers, and plan ahead.

## Your Task

Create a comprehensive weekly review covering strategy, execution, and insights:

1. **Review Timeframe**: Current week (default) or specified week

2. **Gather Key Information**:
   - Progress on roadmap initiatives
   - OKR progress and metrics
   - New customer insights or feedback
   - Competitive intelligence updates
   - Pattern changes or emerging themes
   - Team capacity and velocity
   - Blockers and risks

3. **Review Structure**: Analyze across key dimensions:

   **Strategic Progress**:
   - How did this week advance strategic themes?
   - Any changes to strategic context?
   - New patterns or insights requiring strategy adjustment?

   **Execution Progress**:
   - Roadmap initiative status updates
   - Completed work and shipped features
   - Work in progress and blockers
   - Velocity vs plan

   **Customer & Market Intelligence**:
   - New customer feedback themes
   - Competitive moves observed
   - Win/loss learnings
   - Usage metrics or adoption trends

   **Metrics & OKRs**:
   - Key metrics movement
   - OKR progress tracking
   - Leading indicator trends

   **Risks & Issues**:
   - Blockers identified
   - Risks materialized or new risks
   - Mitigation actions needed

4. **Create Weekly Review Document**: Generate in `/reviews/` with:
   ```markdown
   # Weekly Review - [Week of Date]

   **Week**: [Start Date] - [End Date]
   **Reviewer**: [PM Name]
   **Status**: ⚠️ At Risk | ✅ On Track | 🚀 Ahead

   ## Week in Summary
   [2-3 sentence executive summary of the week]

   ### Key Wins 🎉
   - [Major accomplishment]
   - [Feature shipped]
   - [Important learning]

   ### Key Challenges ⚠️
   - [Blocker or issue]
   - [Risk that materialized]

   ### Key Decisions Made 🎯
   - [Important product decision]
   - [Strategic choice]

   ## Strategic Progress

   ### Theme 1: [Strategic Theme Name]
   **Status**: [On Track/At Risk/Behind]
   **Progress**: [What advanced this theme this week]
   **Next Week**: [Planned work on this theme]

   [Repeat for each active theme]

   ## Roadmap Initiative Updates

   ### [Initiative Name]
   **Status**: 🟢 On Track | 🟡 At Risk | 🔴 Blocked
   **Progress This Week**: [What was completed]
   **Blockers**: [None or list blockers]
   **Next Week**: [Planned work]
   **ETA Change**: [Any timeline changes]

   [Repeat for each active initiative]

   ## OKR Progress

   ### Objective: [OKR Name]

   #### KR1: [Key Result]
   **Target**: [Target value]
   **Current**: [Current value] ([X%] of target)
   **Progress**: 🟢 On Track | 🟡 At Risk | 🔴 Behind
   **This Week**: [Progress made]
   **Trend**: ⬆️ Improving | ➡️ Flat | ⬇️ Declining

   [Repeat for each KR and Objective]

   ## Customer & Market Intelligence

   ### New Customer Insights
   - [Key customer feedback theme]
   - [Important customer interaction]
   - [Support trend or escalation]

   ### Competitive Intelligence
   - [Competitive move observed]
   - [Win/loss learning]
   - [Market development]

   ### Emerging Patterns
   - [New pattern detected requiring attention]

   ## Key Metrics Dashboard

   | Metric | Last Week | This Week | Change | Target | Status |
   |--------|-----------|-----------|--------|--------|--------|
   | [Metric 1] | [Value] | [Value] | [+/-X%] | [Target] | [🟢/🟡/🔴] |
   | [Metric 2] | [Value] | [Value] | [+/-X%] | [Target] | [🟢/🟡/🔴] |

   ## Risks & Issues

   ### Active Risks
   | Risk | Impact | Likelihood | Status | Mitigation |
   |------|---------|------------|--------|------------|
   | [Risk] | H/M/L | H/M/L | [Status] | [Action] |

   ### Blockers
   1. **[Blocker]**: [Description and impact]
      - **Owner**: [Who's responsible to unblock]
      - **Action**: [What needs to happen]
      - **ETA**: [When this will be resolved]

   ## Team Health & Capacity
   **Velocity**: [Story points or initiatives completed]
   **Capacity Next Week**: [Team availability]
   **Morale**: [Any concerns or wins to note]

   ## Decisions Needed
   1. **[Decision]**: [Context and options]
      - **Deadline**: [When decision is needed]
      - **Stakeholders**: [Who needs to decide]

   ## Action Items for Next Week

   ### Strategic Actions
   - [ ] [Action item with owner and due date]

   ### Tactical Actions
   - [ ] [Action item with owner and due date]

   ### Follow-ups Required
   - [ ] [Follow-up with owner]

   ## Focus for Next Week
   **Top Priority**: [Single most important thing]
   **Key Initiatives**: [2-3 key focuses]
   **Risk Areas**: [What to watch closely]

   ## Learning & Reflections
   **What Went Well**: [Process or approach that worked]
   **What to Improve**: [Process or approach to adjust]
   **Experiments to Try**: [New approach to test]

   ## Stakeholder Communication Needed
   - [ ] [Stakeholder] - [What to communicate]
   - [ ] [Team] - [What to share]

   ---

   **Next Review**: [Date]
   **Previous Review**: [[Link to last week's review]]
   ```

5. **Generate Insights**:
   - Velocity trends over past 4 weeks
   - OKR trajectory analysis
   - Pattern changes requiring strategic attention
   - Recommendations for next week's focus

## Output

Present:
- Week in brief (wins/challenges/decisions)
- Status of strategic themes and initiatives
- Critical blockers or risks
- File path to weekly review document
- Top priorities for next week
