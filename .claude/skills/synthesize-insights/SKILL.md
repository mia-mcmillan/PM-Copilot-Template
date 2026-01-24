---
name: synthesize-insights
description: Create strategic synthesis combining multi-source insights (JPD, Gong, feedback, research) into coherent strategic understanding and themes
---

You are creating a strategic synthesis document that combines insights from multiple sources into coherent strategic understanding.

## Your Task

Create a comprehensive strategic synthesis for the specified time period (default: last 30 days):

1. **Gather Intelligence**: Review and analyze:
   - Recent pattern analyses from `2-analyze/patterns/`
   - Customer insights from `2-analyze/insights/`
   - Opportunity data from `3-strategize/opportunities/`
   - Market research from `1-collect/` and `2-analyze/insights/`
   - Existing strategic themes from `3-strategize/strategy/`

   **Check for existing syntheses**: Review `2-analyze/strategic-analysis/` to see if a similar synthesis exists that should be updated rather than creating new

2. **Identify Strategic Themes**: Look for:
   - Common strategic directions suggested by multiple patterns
   - Customer needs that align with business objectives
   - Market opportunities with competitive advantage potential
   - Technical capabilities needed across multiple opportunities
   - Resource allocation implications

3. **Synthesize Into Themes**: Group insights into 3-5 strategic themes:
   - Each theme should be supported by multiple data sources
   - Themes should be distinct but may have interdependencies
   - Include both offensive (growth) and defensive (retention) themes
   - Balance customer needs with business objectives

4. **Create Strategic Synthesis Document**: Generate file in `2-analyze/strategic-analysis/` with:

   **Use template**: Base on bundled `template.md` in this skill folder

   **Link to sources**: Ensure comprehensive linking to patterns, JTBD analyses, and opportunities
   ```markdown
   # [Period] - Strategic Synthesis

   **Period**: [Date Range]
   **Created**: [Date]
   **Sources Analyzed**: [Count and list of sources]

   ## Executive Summary
   [2-3 paragraph overview of key strategic insights]

   ## Strategic Themes Identified

   ### Theme 1: [Theme Name]
   **Priority**: [High/Medium/Low]
   **Type**: [Growth/Retention/Efficiency/Innovation]

   #### Supporting Evidence
   - [Pattern analysis reference]
   - [Customer insight reference]
   - [Market research reference]

   #### Customer Impact
   [Which segments benefit, how, and expected impact]

   #### Business Impact
   [Revenue/retention/efficiency implications]

   #### Resource Requirements
   [Engineering/design/PM effort estimate]

   #### Dependencies
   [Technical, organizational, or strategic dependencies]

   [Repeat for each theme]

   ## Cross-Theme Insights
   [Connections, conflicts, or synergies between themes]

   ## Recommended Strategic Actions
   1. [Prioritized action items]

   ## Strategic Risks
   [Risks of pursuing or not pursuing these themes]

   ## Next Steps
   [Specific follow-up actions needed]
   ```

5. **Link to Strategy Formation**: Suggest how these themes should influence:
   - Product vision updates
   - Roadmap priorities
   - OKR development
   - Resource allocation

## Output

Present:
- Summary of strategic themes identified
- Key insights that drove theme formation
- File path to strategic synthesis document
- Recommended next steps for strategy formation
