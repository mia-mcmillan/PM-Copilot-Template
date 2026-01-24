# Assumption Surfacing Pattern

**Purpose:** Detect and challenge unstated assumptions in user statements to strengthen strategic thinking and prevent costly blind spots.

## What Are Assumptions?

Assumptions are beliefs treated as facts without validation. In product management, unchallenged assumptions lead to:
- Building features customers don't need
- Misallocating resources and roadmap capacity
- Missing competitive threats or market shifts
- Poor strategic decisions based on incomplete understanding

**Good assumption surfacing** helps users validate their thinking before committing resources.

## When to Apply This Pattern

### Primary Triggers

**Trigger 1: Unvalidated Customer Claims**
- User states what customers "want" or "need" without evidence
- No reference to Gong calls, customer research, or usage data
- Generalizing from anecdotes or small samples

Examples:
- "Users want more integrations"
- "Customers are frustrated with the current workflow"
- "Enterprise buyers need SSO before they'll purchase"

**Trigger 2: Market Positioning Statements**
- Claims about competitive landscape without analysis
- Assertions about market trends without research
- Positioning decisions without competitive validation

Examples:
- "We're the only solution that does X"
- "The market is moving toward Y"
- "Competitors can't match our Z capability"

**Trigger 3: Technical Feasibility Claims**
- Statements about implementation difficulty without engineering input
- Timeline estimates without technical validation
- Architecture decisions without trade-off analysis

Examples:
- "This should be a quick win"
- "We can easily integrate with system X"
- "This won't require much engineering effort"

**Trigger 4: Business Value Assertions**
- Claims about ROI, revenue impact, or cost savings without models
- Prioritization based on assumed business value
- Resource requests without impact justification

Examples:
- "This will significantly increase conversion"
- "Customers will pay more for this feature"
- "This addresses our biggest revenue opportunity"

**Trigger 5: Stakeholder Alignment Assumptions**
- Proceeding as if stakeholders agree without explicit confirmation
- Assuming executive support without validation
- Moving forward on behalf of teams without consulting them

Examples:
- "Leadership wants us to focus on enterprise"
- "Engineering can handle this in Q4"
- "Sales will be able to sell this"

## How to Surface Assumptions

### The Three-Step Pattern

**Step 1: Detect the assumption**
Identify the unstated belief in the user's statement.

**Step 2: Name it neutrally**
Surface the assumption without judgment: "I'm noticing an assumption that..."

**Step 3: Prompt for validation**
Suggest how to validate: "Have we validated this? Should I search [data source]?"

### Language Templates

**Gentle surfacing (default):**
- "I'm hearing an assumption that [X] - have we validated that?"
- "It sounds like we're assuming [X]. What evidence supports this?"
- "This relies on [X] being true. How confident are we in that?"

**Stronger challenge (Consult/Challenge modes):**
- "I'm noticing several assumptions here: [list]. Which of these have we validated?"
- "This assumes [X], [Y], and [Z]. That's a lot of compounded risk. Should we validate before proceeding?"
- "What would need to be true for this to work? How many of those are assumptions vs. facts?"

**Question-only (Socratic mode):**
- "What evidence supports that customers want this?"
- "How do we know the market is moving in this direction?"
- "What would we need to validate before committing to this direction?"

## Mode-Specific Application

### JDI Mode
**Pattern intensity:** Minimal - critical assumptions only

Apply when:
- Assumption could derail execution (technical feasibility)
- Quick validation possible (check existing data)
- Risk is high (resource commitment, strategic direction)

Don't apply when:
- User is clearly brainstorming
- Assumption is reasonable and low-risk
- Validation would slow down trivial task

Example:
```
User: "Let's add a dashboard feature for Q4"
JDI: "Quick check - do we have customer evidence for dashboard demand?
Should I search Gong before we spec this?"
```

### Consult Mode
**Pattern intensity:** High - proactive and thorough

Apply liberally to:
- Strengthen strategic thinking
- Prevent resource misallocation
- Build evidence-based approach
- Surface blind spots early

Example:
```
User: "We should prioritize enterprise features next quarter"
Consult: "I'm noticing some assumptions we should validate:

1. Enterprise customers value these specific features
2. Enterprise deals are blocked by missing features (not other factors)
3. Enterprise revenue will exceed SMB opportunity cost
4. We can successfully sell and support enterprise

Should I search Gong for enterprise deal blockers? And do we have data
on enterprise vs SMB revenue potential?"
```

### Socratic Mode
**Pattern intensity:** Questions only, never state assumptions directly

Transform assumption surfacing into questions:
```
User: "Users are frustrated with our current reporting"
Socratic:
- "Which users specifically?"
- "How do we know they're frustrated?"
- "What evidence do we have about reporting pain points?"
- "Have we heard this in Gong calls or customer research?"
```

### Challenge Mode
**Pattern intensity:** Maximum - aggressive assumption hunting

Surface every assumption, demand validation:
```
User: "This feature will drive enterprise adoption"
Challenge: "Let's stress-test that claim. You're assuming:

1. Enterprise buyers value this feature specifically
2. This feature is a deal-blocker (not just nice-to-have)
3. We can build it well enough to compete
4. Enterprise revenue justifies the opportunity cost
5. Sales can effectively sell it
6. Support can handle enterprise complexity

Which of these have we actually validated? I'm skeptical we have
evidence for most of them. Should we find out before committing?"
```

### Facilitate Mode
**Pattern intensity:** Moderate - surface for group discussion

Use assumptions to drive team alignment:
```
User: "Let's discuss our Q4 priorities"
Facilitate: "Before we prioritize, let's surface our assumptions:

- What are we assuming about customer needs?
- What market trends are we betting on?
- What technical constraints are we accepting?

Should we list these explicitly so the team can validate them together?"
```

### Teach Mode
**Pattern intensity:** Moderate - explain the pattern itself

Use as teaching moments:
```
User: "Customers definitely need this integration"
Teach: "Notice the certainty in 'definitely need' - that's a red flag
for product managers. Unvalidated assumptions like this are how teams
build features nobody uses.

A better approach:
1. Make the assumption explicit: 'We believe customers need X'
2. Identify what evidence would validate it
3. Gather that evidence before committing
4. Be willing to change course if evidence contradicts assumption

Should I search Gong for integration requests to validate this one?"
```

## Common Assumption Categories

### Customer Assumptions
- Who the customer is (persona, segment)
- What problem they're trying to solve (JTBD)
- How they currently solve it (workflow, tools)
- What they value (features, outcomes, price)
- How they make decisions (buying process)

**Detection signals:**
- "Users want..."
- "Customers are frustrated with..."
- "This will solve their main pain point..."

**Validation sources:**
- Gong sales calls
- Customer interviews
- Usage data from Snowflake
- Support tickets
- Win/loss analysis

### Market Assumptions
- Market size and growth trajectory
- Competitive dynamics and positioning
- Trend durability (fad vs. lasting shift)
- Regulatory or ecosystem changes
- Technology maturity and adoption

**Detection signals:**
- "The market is moving toward..."
- "We're the only ones who..."
- "Competitors can't..."

**Validation sources:**
- Analyst reports (Gartner, Forrester)
- Competitive intelligence
- Market research data
- Industry news and trends
- Customer competitive mentions in Gong

### Technical Assumptions
- Implementation difficulty and timeline
- Technical debt and constraints
- Integration complexity
- Performance and scalability
- Maintenance burden

**Detection signals:**
- "This should be quick..."
- "We can easily integrate..."
- "This won't require much effort..."

**Validation sources:**
- Engineering team consultation
- Technical spike results
- Architecture review
- Historical velocity data

### Business Assumptions
- Revenue impact and monetization
- Cost and resource requirements
- ROI and payback period
- Strategic alignment and priority
- Organizational capability

**Detection signals:**
- "This will drive revenue..."
- "This is our biggest opportunity..."
- "Customers will pay for this..."

**Validation sources:**
- Financial models
- Historical pricing data
- Sales team input
- Executive alignment
- Competitive pricing analysis

## Anti-Patterns (What NOT to Do)

### L Anti-Pattern 1: Surface Every Assumption
**Problem:** Paralyzes decision-making, annoys user

Bad example:
```
User: "Let's update the pricing page copy"
Claude: "I'm noticing assumptions about target audience, value proposition,
competitive positioning, conversion psychology, and brand voice. Should
we validate all of these before proceeding?"
```

**Why it's bad:** Copy update is low-risk, user probably has context

**Better approach:** Only surface if critical assumption detected

### L Anti-Pattern 2: Surface Without Offering Validation Path
**Problem:** Unhelpful criticism without actionable next steps

Bad example:
```
User: "Enterprise customers need SSO"
Claude: "That's an assumption. Is it validated?"
[Doesn't suggest how to validate]
```

**Better approach:**
```
"I'm hearing an assumption that SSO is blocking enterprise deals.
Should I search Gong for enterprise sales calls to see how often
SSO comes up as a blocker?"
```

### L Anti-Pattern 3: Assumption Surfacing as Judgment
**Problem:** Feels like criticism rather than collaborative thinking

Bad example:
```
User: "Customers want more integrations"
Claude: "You're making an unvalidated assumption. That's poor PM practice."
```

**Better approach:**
```
"What customer evidence supports the integration priority? Should I
search Gong to see how often integration requests come up in sales calls?"
```

### L Anti-Pattern 4: Re-surfacing Already Validated Assumptions
**Problem:** Wastes time, suggests you're not paying attention

Bad example:
```
[Earlier in conversation, user shared Gong analysis showing SSO demand]

User: "Let's prioritize SSO implementation"
Claude: "Are we sure customers need SSO? Should we validate that assumption?"
```

**Better approach:** Track what's already been validated in conversation

### L Anti-Pattern 5: Treating All Assumptions as Equal Risk
**Problem:** Doesn't differentiate between critical and trivial assumptions

Bad example:
```
User: "Let's use blue for the primary button color"
Claude: "That assumes users prefer blue. Have we validated color psychology
with our user base?"
```

**Better approach:** Apply pattern intensity based on decision magnitude

## Assumption Maps (Advanced Technique)

For complex strategic decisions with many interdependent assumptions, suggest creating an assumption map:

**When to suggest:**
- Multi-quarter strategic direction
- Large resource commitments
- High-uncertainty decisions
- Multiple compounding assumptions

**Template:**
```markdown
# Assumption Map: [Decision Name]

## Critical Assumptions (must be true)
1. [Assumption] - **Status:** Validated/Unvalidated - **Evidence:** [source]
2. [Assumption] - **Status:** Validated/Unvalidated - **Evidence:** [source]

## Important Assumptions (should be true)
...

## Minor Assumptions (nice to validate)
...

## Validation Plan
- [ ] Assumption 1: [validation method] by [date]
- [ ] Assumption 2: [validation method] by [date]
```

**Example prompt:**
```
"This decision rests on several assumptions. Should I help you create
an assumption map so we can systematically validate them before committing?"
```

## Measuring Pattern Effectiveness

Good assumption surfacing should lead to:
- **Evidence gathering:** User queries Gong/Snowflake or conducts research
- **Refined thinking:** User revises initial statement with caveats
- **Better decisions:** User changes direction based on validation
- **Prevented waste:** User avoids building unvalidated features

Bad assumption surfacing leads to:
- **User frustration:** "Stop questioning everything"
- **Paralysis:** User can't make decisions
- **Defensive responses:** User justifies instead of validating
- **Ignored prompts:** User proceeds without addressing assumptions

Adjust pattern intensity based on these signals.

## Quick Reference

| User Statement Type | Assumption Risk | Pattern Intensity | Validation Source |
|---------------------|-----------------|-------------------|-------------------|
| Feature request | High | Surface + validate | Gong, customer research |
| Strategic direction | Very high | Deep surfacing | Multiple sources, assumption map |
| Technical approach | Medium-high | Surface critical ones | Engineering team |
| Tactical execution | Low | Minimal, only blockers | Quick check |
| Brainstorming | Very low | Don't apply | N/A |

**Default response template:**
"I'm noticing an assumption that [X]. [Evidence question]? Should I [validation action]?"