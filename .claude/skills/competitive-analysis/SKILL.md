---
name: competitive-analysis
description: Conduct in-depth competitive positioning and market analysis with battlecards and strategic positioning recommendations
---

You are conducting an in-depth competitive positioning and market analysis.

## Your Task

Create comprehensive competitive analysis for specified competitor or market landscape:

1. **Identify Analysis Scope**:
   - Specific competitor deep-dive OR
   - Overall competitive landscape assessment
   - Market segment(s) to analyze
   - Time period for analysis

2. **Gather Competitive Intelligence**:
   - Gong call mentions of competitors
   - Win/loss analysis data
   - Customer feedback comparing to competitors
   - Market research on competitive positioning
   - Competitor product capabilities and roadmap signals
   - Pricing and packaging analysis

3. **Analyze Competitive Dimensions**:
   - **Product Capabilities**: Feature comparison, UX quality, performance
   - **Market Position**: Market share, brand strength, customer loyalty
   - **Go-to-Market**: Sales approach, pricing, partnerships, marketing
   - **Customer Satisfaction**: NPS, reviews, retention metrics
   - **Strategic Direction**: Roadmap signals, M&A activity, focus areas
   - **Strengths/Weaknesses**: What they do well/poorly

4. **Create Competitive Analysis Document**: Generate in `/analyses/` with:
   ```markdown
   # [Competitor/Market] - Competitive Analysis

   **Date**: [Date]
   **Scope**: [Competitor name or market segment]
   **Sources**: [Intelligence sources used]

   ## Executive Summary
   [Key competitive insights and strategic implications]

   ## Market Overview
   **Market Size**: [TAM/SAM/SOM if available]
   **Growth Rate**: [Market growth trends]
   **Key Players**: [Major competitors and market share]
   **Market Dynamics**: [Trends reshaping the market]

   ## Competitor Profile: [Competitor Name]

   ### Company Overview
   - **Founded**: [Year]
   - **Size**: [Revenue, employees, funding]
   - **Ownership**: [Public/Private, investors]

   ### Product Capabilities
   | Capability | Competitor | Us | Winner | Notes |
   |------------|------------|-----|---------|-------|
   | [Feature 1] | [Rating] | [Rating] | [Who] | [Details] |

   ### Positioning Analysis
   **Target Market**: [Their ICP vs ours]
   **Value Proposition**: [Their messaging and positioning]
   **Differentiation**: [What makes them unique]

   ### Pricing & Packaging
   **Pricing Model**: [How they charge]
   **Price Points**: [Actual pricing if known]
   **Packaging**: [Tiers and features]
   **Comparison**: [vs our pricing]

   ### Sales & Marketing Approach
   **Sales Motion**: [PLG/Sales-led/Hybrid]
   **Marketing Focus**: [Channels and messaging]
   **Partnerships**: [Key partnerships]

   ### Strengths & Weaknesses
   **Strengths**:
   - [Strength with evidence]

   **Weaknesses**:
   - [Weakness with evidence]

   ### Customer Sentiment
   **Win Themes**: [Why customers choose them]
   **Loss Themes**: [Why customers choose us instead]
   **Customer Complaints**: [Common pain points from reviews]

   ### Strategic Direction
   **Recent Moves**: [Product launches, acquisitions, etc.]
   **Roadmap Signals**: [Where they're investing]
   **Threats to Us**: [How they're targeting our position]

   ## Competitive Positioning Map
   [2x2 or other visualization showing market positioning]

   ## Our Competitive Advantages
   1. [Advantage with supporting evidence]

   ## Competitive Vulnerabilities
   1. [Gap or weakness vs competitors]

   ## Win/Loss Analysis
   **Win Rate vs [Competitor]**: [Percentage if known]
   **Common Win Reasons**: [Why we beat them]
   **Common Loss Reasons**: [Why we lose to them]

   ## Strategic Implications
   ### Defensive Moves
   [How to protect our position]

   ### Offensive Opportunities
   [How to exploit their weaknesses]

   ### Positioning Strategy
   [How to position against this competitor]

   ## Recommended Actions
   1. [Prioritized competitive responses]

   ## Monitoring Plan
   [How to track competitive moves going forward]
   ```

5. **Link to Strategy**: Connect competitive insights to:
   - Product differentiation strategy
   - Roadmap priorities to maintain/build advantage
   - Sales positioning and battlecards

## Output

Present:
- Key competitive insights
- Our positioning vs competitor(s)
- Critical vulnerabilities to address
- File path to competitive analysis document
- Recommended strategic responses
