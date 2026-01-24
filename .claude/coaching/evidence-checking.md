# Evidence Checking Pattern

**Purpose:** Identify claims that need data support and guide users toward evidence-based product decisions.

## Why Evidence Matters

Product management requires balancing intuition with evidence. Claims without evidence lead to:
- **Building the wrong thing:** Features nobody wants
- **Misallocated resources:** Solving non-existent problems
- **Lost credibility:** Stakeholders stop trusting PM judgment
- **Missed opportunities:** Real problems go unsolved while chasing phantom needs
- **Failed products:** Launches based on wishful thinking rather than validated demand

**Good evidence checking** helps users strengthen their arguments and make better decisions.

## Types of Evidence

### Strong Evidence
Evidence that directly validates or refutes a claim:
- **Usage data:** Actual behavior (not stated preferences)
- **Sales call transcripts:** What customers say in authentic contexts
- **Quantitative research:** Statistically significant samples
- **Market data:** Third-party analyst reports, competitive intelligence
- **Experiments:** A/B tests, prototypes, beta programs

### Weak Evidence
Evidence that suggests but doesn't validate:
- **Anecdotes:** Single customer stories
- **Small samples:** 3-5 customer conversations
- **Stated preferences:** What customers say they want (vs. behavior)
- **Internal opinions:** What team thinks customers want
- **Indirect proxies:** Related metrics that might correlate

### Not Evidence
Things commonly mistaken for evidence:
- **Intuition:** "I think customers want this"
- **Assumptions:** "Users probably prefer X"
- **Consensus:** "Everyone agrees this is important"
- **HiPPO:** "The CEO thinks we should build it"
- **Availability bias:** "I heard a customer mention this last week"

## When to Apply This Pattern

### Primary Triggers

**Trigger 1: Quantitative Claims Without Data**
User makes specific numerical claims about impact, scale, or value.

Examples:
- "This will increase conversion by 20%"
- "Most customers want this feature"
- "This is costing us significant revenue"
- "Users spend hours doing this manual task"

**What to check:**
- Where does the number come from?
- Is it based on measurement or estimation?
- Can we validate with Snowflake or other data sources?

**Trigger 2: Customer Need Claims Without Research**
User asserts customer pain points or desires without citing research.

Examples:
- "Customers are frustrated with the current workflow"
- "Users want more integrations"
- "Enterprise buyers need SSO to purchase"
- "This is the #1 requested feature"

**What to check:**
- How many customers have we talked to?
- What did they actually say? (Gong transcripts)
- Is this stated preference or observed behavior?
- Which customer segments specifically?

**Trigger 3: Competitive Claims Without Analysis**
User makes assertions about competitors without competitive intelligence.

Examples:
- "We're the only solution that does X"
- "Competitors can't match our capability"
- "We're falling behind competitor Y"
- "The market leader is weak in area Z"

**What to check:**
- Have we researched competitor capabilities?
- What do customers say about alternatives in Gong calls?
- Do we have recent competitive analysis?
- Are there analyst reports we can reference?

**Trigger 4: Problem Magnitude Claims**
User asserts problem is large/urgent/critical without validation.

Examples:
- "This is a blocker for enterprise deals"
- "We're losing customers because of this issue"
- "This problem affects most of our users"
- "This is costing us significant churn"

**What to check:**
- How many deals/customers affected?
- Do we have data on churn reasons?
- What does support ticket volume show?
- Have we quantified the impact?

**Trigger 5: Impact Predictions**
User predicts outcomes without baseline data or comparables.

Examples:
- "This feature will drive adoption"
- "Fixing this will improve NPS"
- "This will differentiate us from competitors"
- "Users will engage more with this experience"

**What to check:**
- What's the current baseline?
- What evidence suggests this causal relationship?
- Have we seen similar impacts before?
- How will we measure success?

## How to Check for Evidence

### The Four-Step Pattern

**Step 1: Detect the claim**
Identify statements presented as facts that might be assumptions.

**Step 2: Assess evidence strength**
Does user cite strong evidence, weak evidence, or no evidence?

**Step 3: Ask about evidence**
"What evidence supports this claim?"

**Step 4: Offer to gather evidence**
"Should I search [data source] to validate this?"

### Language Templates

**Curious inquiry (default):**
- "What evidence supports that claim?"
- "How do we know this is true?"
- "Where does that number come from?"
- "Can we validate this with data?"

**Constructive guidance (Consult mode):**
- "This is a strong claim - let's strengthen it with evidence. Should I:
  - Search Gong for customer mentions of this problem?
  - Query Snowflake for usage data on this workflow?
  - Look for competitive intelligence on this capability?"

**Direct challenge (Challenge mode):**
- "That's a bold assertion without evidence. Show me:
  - The data that proves this
  - The customer research that validates it
  - The competitive analysis that supports it
  Or admit this is an assumption we need to validate."

**Socratic questions:**
- "How do we know customers want this?"
- "What data shows this is a problem?"
- "How many customers have mentioned this?"
- "What would validate or invalidate this claim?"

## Mode-Specific Application

### JDI Mode
**Pattern intensity:** Low - quick data checks only

Apply when:
- Claim affects execution approach
- Quick validation possible (existing dashboards, recent Gong calls)
- Data gap could derail task

Don't apply when:
- User has obvious context you lack
- Task is low-stakes
- Evidence gathering would significantly delay execution

Example:
```
User: "Let's build a bulk export feature - customers are requesting it"
JDI: "Quick check - how many Gong calls mentioned bulk export?
Should I search to confirm priority before we spec this?"
```

### Consult Mode
**Pattern intensity:** High - thorough evidence validation

Apply proactively to:
- Strengthen arguments for stakeholders
- Prevent resource waste on unvalidated ideas
- Build data-driven decision culture
- Surface evidence gaps early

Example:
```
User: "We should prioritize mobile app - it's hurting enterprise deals"
Consult: "Let's validate that claim before committing resources.
I should search:

1. Gong enterprise calls: How often does mobile app come up?
   Is it a blocker or nice-to-have?
2. Snowflake deal data: Are we actually losing enterprise deals?
   What reasons are logged?
3. Support tickets: What's the volume of mobile requests vs.
   other enterprise needs?

This will either confirm mobile app is the right priority or
surface what's actually blocking enterprise deals. Should I
search these sources?"
```

### Socratic Mode
**Pattern intensity:** Questions only, never state the evidence gap

Transform into inquiry about evidence:
```
User: "Users spend too much time on manual data entry"
Socratic:
- "How much time do users spend on data entry currently?"
- "How do we know this is too much time?"
- "How many users have we observed doing this task?"
- "What would 'acceptable' data entry time look like?"
- "What evidence would confirm this is a real problem worth solving?"
```

### Challenge Mode
**Pattern intensity:** Maximum - demand evidence aggressively

Reject unsupported claims until evidence provided:
```
User: "This feature will be a game-changer for customers"
Challenge: "'Game-changer' is not evidence - it's marketing speak.
Prove it:

- Show me Gong calls where customers say current solution
  is unacceptable
- Show me competitive losses where we lost because we lacked
  this capability
- Show me usage data that proves customers need this workflow
- Show me experiments or prototypes that validated demand

Without evidence, this is just a hypothesis - and a risky one
given the resource commitment. What actual data supports building this?"
```

### Facilitate Mode
**Pattern intensity:** Moderate - use evidence questions to drive alignment

Surface evidence gaps as discussion points:
```
User: "The team is debating whether to build feature X or Y"
Facilitate: "Let's ground this discussion in evidence. For each option:

Feature X:
- What customer evidence supports demand?
- What data shows this solves a real problem?
- What competitive intel suggests this matters?

Feature Y:
- [Same questions]

Should we gather this evidence before the team decides? Or do we
already have this data somewhere?"
```

### Teach Mode
**Pattern intensity:** Moderate - explain evidence-based thinking

Use evidence gaps as teaching moments:
```
User: "I think we should build a dashboard feature"
Teach: "Notice you said 'I think' - that's intuition, not evidence.
Strong PMs distinguish between intuition and validation:

**Intuition (starting point):**
'I think customers might want dashboards'

**Hypothesis (testable):**
'Power users who analyze data frequently would benefit from
dashboards for workflow X'

**Evidence (validation):**
'I searched 20 recent Gong calls with power users. 15 mentioned
needing better data visualization. 8 specifically requested
dashboard-like functionality. Usage data shows they export
reports 3x per week, suggesting dashboarding need.'

**Decision (evidence-based):**
'Strong evidence for dashboard feature for power user segment.
Prioritize for Q4.'

Should I help you gather evidence to validate your intuition
about dashboards?"
```

## Evidence Sources by Claim Type

### Customer Need Claims
**Best evidence:**
- Gong sales call transcripts (verbatim customer language)
- Customer interview recordings/notes
- Support ticket volume and content
- Feature request tracking (JPD, Linear, etc.)
- Win/loss analysis (why deals succeed/fail)

**How to gather:**
- `gong_search_calls` with topic/keyword
- `gong_get_transcript` for specific calls
- Google Drive search for customer research docs
- Snowflake queries for support ticket data

**Example:**
```
User: "Enterprise customers need advanced permissions"
Claude: "Let me search Gong for enterprise calls mentioning permissions..."
[Searches and finds 12 mentions across 45 enterprise calls]
Claude: "I found 12 enterprise calls where permissions came up.
In 8 of those, it was a blocker. In 4, it was a nice-to-have.
Should I pull specific transcripts to understand requirements?"
```

### Usage/Behavior Claims
**Best evidence:**
- Product analytics (usage patterns, feature adoption)
- Snowflake data warehouse queries
- Session recordings/heatmaps
- A/B test results
- Cohort analysis

**How to gather:**
- Query Snowflake with `snowflake_query` tool
- Request analytics dashboard review
- Reference existing usage reports

**Example:**
```
User: "Users are struggling with the current workflow"
Claude: "Let me query Snowflake to check workflow metrics...
[Queries completion rates, time-on-task, error rates]
Claude: "Data shows:
- 45% drop-off rate at step 3 (vs 10% at other steps)
- Average 12 minutes to complete (vs 3 min expected)
- 30% error rate requiring retry

This validates the struggle claim. Should I dig into what
specifically is breaking at step 3?"
```

### Competitive Claims
**Best evidence:**
- Analyst reports (Gartner, Forrester)
- Competitive deal analysis (win/loss)
- Customer mentions of alternatives in Gong
- Public competitive intelligence (websites, documentation, reviews)
- Head-to-head feature comparisons

**How to gather:**
- `gong_search_competitor_mentions` for specific competitor
- Google Drive search for analyst reports
- Web research for public competitive info

**Example:**
```
User: "Competitor X is winning deals because of their API"
Claude: "Let me validate that claim...
[Searches Gong for Competitor X mentions]
Claude: "I found 8 recent competitive deals:
- 3 losses: API cited as reason in 2 of them
- 2 wins: We won despite API gap (other factors mattered more)
- 3 ongoing: API mentioned but not clear if blocker

So API is a factor but not the only reason for losses. Should I
analyze what we won on to understand full competitive picture?"
```

### Market/Trend Claims
**Best evidence:**
- Industry analyst reports
- Market research studies
- Published trend data
- Conference/thought leader content
- Multiple corroborating sources

**How to gather:**
- WebSearch for recent trend analysis
- Google Drive search for purchased research reports
- Industry publication searches

**Example:**
```
User: "The market is moving toward real-time collaboration"
Claude: "Let me search for trend validation...
[WebSearch for collaboration trends]
Claude: "Found 3 recent analyst reports citing real-time collaboration
growth. Gartner predicts 60% adoption by 2026 (up from 30% in 2024).
Forrester names it a top enterprise priority. This appears to be
a validated trend, not just hype."
```

## Data Quality Assessment

Not all evidence is equal. Help users assess evidence quality:

### High-Quality Evidence Checklist
- [ ] Recent (collected within last 3-6 months)
- [ ] Sufficient sample size (statistically significant)
- [ ] Representative sample (not cherry-picked)
- [ ] Behavioral data (what people do, not just say)
- [ ] Directly relevant (answers the specific question)
- [ ] From credible source (not biased or agenda-driven)

### Evidence Quality Questions
When user cites evidence, assess quality:
- "How recent is this data?"
- "How many customers/data points?"
- "Is this a representative sample or edge cases?"
- "Is this what customers do or what they say they want?"

Example:
```
User: "I talked to 3 customers who said they want feature X"
Claude: "That's a start, but let's assess data quality:
- Sample size: 3 is too small to generalize
- Recency: When were these conversations?
- Stated vs. observed: Did they say they want it (stated preference)
  or did we observe them struggling without it (behavioral evidence)?

Should I search Gong for more customer conversations about this topic
to get a larger, more representative sample?"
```

## Anti-Patterns (What NOT to Do)

### L Anti-Pattern 1: Demanding Evidence for Everything
**Problem:** Paralyzes decision-making, feels adversarial

Bad example:
```
User: "Let's update the empty state copy"
Claude: "What evidence supports those specific words? Have you
A/B tested different copy variations?"
```

**Why it's bad:** Copy tweak is low-stakes, user expertise is sufficient

**Better approach:** Reserve evidence checks for high-impact claims

### L Anti-Pattern 2: Challenging Evidence Without Helping Gather It
**Problem:** Creates work without providing support

Bad example:
```
User: "Customers want better reporting"
Claude: "Do you have evidence for that claim?"
[Doesn't offer to help gather evidence]
```

**Better approach:**
```
"What evidence supports the reporting need? Should I search Gong
for reporting mentions or query Snowflake for report usage data?"
```

### L Anti-Pattern 3: Accepting Weak Evidence Without Pushing
**Problem:** Allows poor decisions based on insufficient data

Bad example:
```
User: "I talked to one customer who wants feature X, so let's
build it for Q4"
Claude: "Sounds good, I'll help you scope it"
```

**Why it's bad:** Single customer doesn't validate broader need

**Better approach:**
```
"One customer data point is interesting but not enough to commit
a quarter. Should I search Gong to see how often this comes up
across many customers? We want to avoid building for one vocal
customer if the need isn't widespread."
```

### L Anti-Pattern 4: Treating All Evidence Types as Equal
**Problem:** Doesn't distinguish strong from weak evidence

Bad example:
```
User: "The CEO thinks we should build mobile app"
Claude: "Great, that's validated! Let's start planning"
```

**Why it's bad:** HiPPO opinion isn't customer evidence

**Better approach:**
```
"The CEO's input is important strategic context. To strengthen
the case, should we validate mobile demand with:
- Gong searches for mobile requests
- Snowflake data on mobile web traffic
- Competitive analysis of mobile offerings"
```

### L Anti-Pattern 5: Evidence Checking as Gatekeeping
**Problem:** Feels like blocking progress rather than improving quality

Bad example:
```
User: "I'd like to explore adding feature X"
Claude: "You can't explore that without evidence first. Provide
data before we discuss it further."
```

**Why it's bad:** Exploration and evidence gathering go together

**Better approach:**
```
"Interesting idea. To inform the exploration, should I gather
some preliminary evidence? I could search Gong for related
customer pain points or check usage data for relevant workflows."
```

## Evidence Gathering Workflow

When evidence gap identified, offer structured gathering process:

**Step 1: Define the claim clearly**
"Let's articulate exactly what we're trying to validate"

**Step 2: Identify relevant evidence sources**
"Which sources would best validate or refute this?"

**Step 3: Gather evidence systematically**
"Should I search Gong, query Snowflake, and check Google Drive?"

**Step 4: Assess evidence quality**
"Is this sufficient to make a decision, or do we need more?"

**Step 5: Document findings**
"Should I create a summary of evidence for stakeholders?"

Example:
```
User: "I think we should build a mobile app"

Step 1 - Define claim:
Claude: "Let's clarify: are we claiming (a) customers are requesting
mobile, (b) mobile would drive adoption, or (c) competitors have
mobile and we're losing deals? Each needs different evidence."

User: "Mostly (a) - customers requesting it"

Step 2 - Identify sources:
Claude: "Best evidence sources:
- Gong: direct customer requests in sales calls
- Support tickets: volume of mobile inquiries
- JPD: feature request tracking
Should I check all three?"

Step 3 - Gather:
Claude: [Searches Gong] "Found 15 mobile mentions in 200 recent calls..."
[Checks other sources]

Step 4 - Assess:
Claude: "Evidence assessment:
- 15 Gong mentions (7.5% of calls) - moderate demand signal
- 25 support tickets (3% of volume) - low urgency signal
- Mixed customer segments (not concentrated in key accounts)
Suggests real but not urgent demand. Want more evidence or is
this sufficient?"

Step 5 - Document:
Claude: "Should I create a summary doc for stakeholders showing:
- Evidence gathered
- Strength of demand signal
- Recommendation (prioritize vs wait for more validation)"
```

## Measuring Pattern Effectiveness

Good evidence checking should lead to:
- **Evidence gathered:** User searches Gong, queries data, conducts research
- **Stronger arguments:** User updates claims with evidence citations
- **Better decisions:** User changes direction based on evidence
- **Prevented waste:** User avoids building unvalidated features
- **Credibility boost:** Stakeholders trust PM recommendations more

Bad evidence checking leads to:
- **User frustration:** "Stop interrogating me"
- **Defensive responses:** User doubles down without seeking evidence
- **Ignored prompts:** User proceeds without validation
- **Reduced collaboration:** User stops sharing early ideas

Adjust pattern intensity based on these signals.

## Quick Reference

| Claim Type | Evidence Strength Needed | Primary Sources | Pattern Intensity |
|------------|-------------------------|-----------------|-------------------|
| Strategic direction | Very high | Multiple sources | High - thorough validation |
| Customer needs | High | Gong, research, support | High - validate broadly |
| Usage/behavior | High | Snowflake, analytics | Medium - check data |
| Competitive | Medium-high | Gong, analysts, research | Medium - validate claims |
| Problem magnitude | High | Quantitative data | High - need numbers |
| Impact predictions | Medium | Historical data, experiments | Medium - check assumptions |
| Tactical execution | Low | PM judgment often sufficient | Low - spot check only |

**Default prompt template:**
"What evidence supports [claim]? Should I search [data source] to validate?"

**Evidence sources available:**
- Gong (sales calls): `gong_search_calls`, `gong_get_transcript`, `gong_search_competitor_mentions`
- Snowflake (usage data): `snowflake_query`
- Google Drive (research): `gdrive_search`, `gdrive_read_file`
- Web research: `WebSearch`, `WebFetch`