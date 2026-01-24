---
name: prioritize-opportunities
description: Apply multi-dimensional scoring framework (strategic alignment, customer impact, business value, effort) to prioritize opportunities and inform roadmap decisions
---

You are applying a multi-dimensional prioritization framework to score and rank product opportunities.

## Your Task

Score opportunities using strategic alignment, customer impact, and business value dimensions:

1. **Gather Opportunities**: Collect from:
   - JPD opportunities in `3-strategize/opportunities/`
   - Ideas from customer insights in `2-analyze/insights/`
   - Strategic initiatives from `2-analyze/strategic-analysis/`
   - Patterns from `2-analyze/patterns/`
   - Technical debt or infrastructure needs

   **Check for duplication**: Review existing opportunities before scoring to avoid duplicate work

2. **Apply Prioritization Framework**: Score each opportunity across:

   **Strategic Alignment (1-10)**:
   - Alignment with strategic themes (40%)
   - Competitive positioning impact (30%)
   - Long-term vision fit (30%)

   **Customer Impact (1-10)**:
   - Number of customers affected (30%)
   - Severity of pain point (30%)
   - Frequency of use (20%)
   - Customer segment value (20%)

   **Business Value (1-10)**:
   - Revenue impact (40%)
   - Retention/churn impact (30%)
   - Efficiency/cost savings (20%)
   - Market expansion potential (10%)

   **Effort (1-10)** [inverse - higher = more effort]:
   - Engineering complexity (40%)
   - Design requirements (20%)
   - Dependencies (20%)
   - Timeline (20%)

3. **Calculate Priority Scores**:
   ```
   Priority Score = (Strategic Alignment + Customer Impact + Business Value) / Effort

   Confidence = (Evidence Quality * Source Diversity) / 10
   ```

4. **Create Prioritization Document**: Generate in `/strategy/` with:
   ```markdown
   # [Period] - Opportunity Prioritization

   **Date**: [Date]
   **Opportunities Scored**: [Count]
   **Framework Version**: [Version/date]

   ## Prioritization Framework

   ### Scoring Dimensions
   **Strategic Alignment (1-10)**
   - 9-10: Core strategic theme, critical for vision
   - 7-8: Strong alignment with strategic themes
   - 5-6: Moderate alignment
   - 3-4: Weak alignment
   - 1-2: Off-strategy or tactical only

   **Customer Impact (1-10)**
   - 9-10: Critical pain for majority of customers
   - 7-8: Significant pain for large segment
   - 5-6: Moderate pain or niche impact
   - 3-4: Minor pain or small segment
   - 1-2: Nice-to-have

   **Business Value (1-10)**
   - 9-10: Major revenue/retention impact ($XM+)
   - 7-8: Significant business impact
   - 5-6: Moderate impact
   - 3-4: Minor impact
   - 1-2: Negligible business impact

   **Effort (1-10)** [inverse scoring]
   - 9-10: 6+ months, high complexity
   - 7-8: 3-6 months, significant work
   - 5-6: 1-3 months, moderate work
   - 3-4: 2-4 weeks, straightforward
   - 1-2: <2 weeks, minimal work

   ## Prioritized Opportunities

   ### Tier 1: Must Do (Score 15+)

   #### [Opportunity Name]
   **Priority Score**: [Score]
   **Confidence**: [High/Medium/Low]

   | Dimension | Score | Rationale |
   |-----------|-------|-----------|
   | Strategic Alignment | [1-10] | [Why this score] |
   | Customer Impact | [1-10] | [Evidence and reasoning] |
   | Business Value | [1-10] | [Expected impact] |
   | Effort | [1-10] | [Complexity assessment] |

   **Evidence**:
   - **Patterns Addressed**: [[Pattern Name - Pattern]] (primary problem this solves)
   - **JTBD Analyses**: [[JTBD analyses]] (customer evidence)
   - **Strategic Alignment**: [[Strategic Theme]] (strategic fit)
   - **Customer Feedback**: [[Feedback synthesis]] (voice of customer)
   - **Market Research**: [[Research doc]] (market validation)
   - **Competitive Analysis**: [[Competitive doc]] (competitive context)

   **JPD Link**: [Link if available]
   **Jira Epic**: [Link if created]

   **Recommendation**: [Do now/next/later]

   [Repeat for each Tier 1 opportunity]

   ### Tier 2: Should Do (Score 10-15)
   [Same structure]

   ### Tier 3: Could Do (Score 5-10)
   [Same structure]

   ### Not Prioritized (Score <5)
   [Brief list with reason for low priority]

   ## Prioritization Matrix

   ### Value vs Effort Matrix
   ```
   High Value │ [Opps] │ [Opps] │
   Low Effort │ [Opps] │ [Opps] │
              └─────────┴────────┘
              Low Value  High Value
   ```

   ## Theme-Based View

   ### Theme 1: [Strategic Theme Name]
   - [Opportunity] - Score: [X]
   - [Opportunity] - Score: [X]
   **Total Theme Investment**: [Estimated effort]

   ## Sequencing Recommendations

   ### Immediate Priorities (Do First)
   1. [Opportunity] - [Why first]

   ### Dependencies & Sequencing
   [Call out where one opportunity should precede another]

   ## Resource Allocation Implications
   - [How this prioritization affects team capacity]
   - [Trade-offs being made]
   - [Capacity gaps identified]

   ## Scoring Confidence & Assumptions
   **High Confidence**:
   - [Opportunities with strong evidence]

   **Medium Confidence**:
   - [Opportunities needing validation]

   **Low Confidence**:
   - [Opportunities requiring research]

   **Key Assumptions**:
   - [Assumptions underlying these scores]

   ## Recommended Actions
   1. [Next steps for top priorities]
   2. [Validation needed for medium-confidence items]
   3. [Research needed for low-confidence items]

   ## Review Schedule
   [When to re-score based on new information]
   ```

5. **Create Visualizations**: Suggest formats for:
   - Value vs Effort 2x2 matrix
   - Priority ranking list
   - Theme-based resource allocation
   - Timeline/roadmap view of prioritized items

## Output

Present:
- Top 5 prioritized opportunities with scores
- Key insights from prioritization exercise
- Resource allocation recommendations
- File path to prioritization document
- Suggested sequencing and next steps
