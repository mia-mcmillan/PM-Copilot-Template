# Phase Transitions & Quality Gates

**Purpose:** Define entry/exit criteria for moving between workflow phases.

## The 6-Phase Workflow

```
1-collect/     ’  2-analyze/      ’  3-strategize/
Data gathering    Insights          Strategy & roadmap

        “                ‘

6-assess/        5-execute/        4-experiment/
Learn & iterate   Build & ship      Validate & test
```

**Continuous cycle:** Learnings from Phase 6 feed back to Phase 1.

## Phase 1: Collect ’ Phase 2: Analyze

### Exit Criteria (Collect)
-  Multi-source data collected (Gong, Snowflake, customer research)
-  Coverage across key customer segments
-  Data is recent and relevant
-  Sufficient volume for pattern recognition

### Entry Criteria (Analyze)
- Raw data available in `1-collect/`
- Clear questions to answer through analysis
- Time allocated for synthesis

### Quality Gate Questions
- Do we have enough data to find patterns?
- Are we missing critical data sources?
- Is the data recent enough to be actionable?

### Red Flags (Don't Proceed)
- L Only single-source data
- L Data is stale (>6 months old for most contexts)
- L Missing key customer segments
- L Too small sample size

---

## Phase 2: Analyze ’ Phase 3: Strategize

### Exit Criteria (Analyze)
-  Patterns validated across multiple sources
-  Customer insights documented with JTBD
-  Strategic themes emerging from patterns
-  Competitive position understood

### Entry Criteria (Strategize)
- Insights and patterns documented in `2-analyze/`
- Clear understanding of customer needs
- Competitive landscape mapped

### Quality Gate Questions
- Do patterns appear in multiple data sources?
- Do we understand the "why" behind customer behavior?
- Are insights specific enough to drive strategy?

### Red Flags (Don't Proceed)
- L Patterns based on single source
- L Conflicting insights not reconciled
- L Unclear customer needs or JTBD
- L No competitive differentiation identified

---

## Phase 3: Strategize ’ Phase 4: Experiment

### Exit Criteria (Strategize)
-  Opportunities documented and scored
-  Strategic themes defined
-  Roadmap priorities set
-  Success metrics identified
-  Key assumptions mapped

### Entry Criteria (Experiment)
- Prioritized opportunity selected
- Clear hypothesis to validate
- Success criteria defined
- Validation approach planned

### Quality Gate Questions
- Is this opportunity validated with customer evidence?
- What assumptions need testing before full build?
- Do we have a clear go/no-go decision framework?

### Red Flags (Don't Proceed)
- L Opportunity lacks customer evidence
- L No clear hypothesis to test
- L Success metrics undefined
- L Skipping validation for "obvious" ideas (rarely obvious)

### Special Case: Skip to Execute
**When:** Maintenance work, bug fixes, small iterations
**Criteria:** Low risk, well-understood problem, no validation needed

---

## Phase 4: Experiment ’ Phase 5: Execute

### Exit Criteria (Experiment)
-  Prototype tested with target customers
-  Key assumptions validated (or invalidated and pivoted)
-  Technical feasibility confirmed
-  Go decision made with stakeholder alignment
-  Success metrics baselined

### Entry Criteria (Execute)
- Validation results documented in `4-experiment/`
- Go decision approved
- Project plan defined
- Engineering resources allocated

### Quality Gate Questions
- Did validation results support the hypothesis?
- Are we confident this solves the customer problem?
- Do we have technical feasibility confirmation?
- Is there exec/stakeholder alignment?

### Red Flags (Don't Proceed)
- L Validation failed (customers didn't adopt prototype)
- L Technical feasibility concerns unresolved
- L Stakeholders not aligned
- L Success metrics can't be measured

### Loop Back to Strategize
**When:** Validation invalidated the opportunity
**Action:** Re-prioritize, pivot approach, or kill opportunity

---

## Phase 5: Execute ’ Phase 6: Assess

### Exit Criteria (Execute)
-  Feature released to production
-  Rollout complete (or at target %)
-  Initial health metrics stable
-  Instrumentation in place
-  Enough time elapsed to measure impact (typically 2-4 weeks minimum)

### Entry Criteria (Assess)
- Feature live in production
- Metrics flowing
- Customers actively using (or enough time for adoption)

### Quality Gate Questions
- Is the feature stable and performing as expected?
- Can we measure the success criteria we defined?
- Has enough time passed to see meaningful data?

### Red Flags (Don't Proceed)
- L Feature is unstable or buggy
- L Metrics not instrumented
- L Too early to measure outcomes (wait longer)
- L Adoption hasn't started yet

---

## Phase 6: Assess ’ Phase 1: Collect (Loop)

### Exit Criteria (Assess)
-  Success criteria evaluated (met or not met)
-  Outcome report documented
-  Key learnings captured
-  Next iteration identified (if needed)

### Entry Criteria (Collect - New Cycle)
- Learnings documented in `6-assess/learning/`
- New questions identified
- Iteration or new opportunity prioritized

### Quality Gate Questions
- Did we achieve the intended outcome?
- What did we learn about customers?
- What should we do next based on results?

### Decisions After Assessment
- **Success:** Document patterns, scale solution, move to next opportunity
- **Partial success:** Plan iterations, return to Experiment phase
- **Failure:** Document why, kill or pivot, capture learnings

### Loop Back Options
- **To Collect:** New customer signals, new market dynamics
- **To Analyze:** Pattern updates based on outcomes
- **To Strategize:** Strategy refinement based on learnings
- **To Experiment:** Test new iteration or pivot

---

## Quality Gate Enforcement

### How Gates Work

**Claude's role during transitions:**
1. Detect when user is moving between phases
2. Ask: "Have we met the exit criteria?"
3. Surface red flags if present
4. Recommend: proceed, loop back, or acknowledge risks

**User's decision:**
-  **Proceed:** Gate passed, confident moving forward
-   **Proceed with risks:** Acknowledge gaps, move forward anyway
- L **Loop back:** Return to previous phase to fill gaps

### Gate Intensity by Mode

**JDI Mode:** Light gate checks, trust user judgment
**Consult Mode:** Thorough gate checks, raise concerns proactively
**Challenge Mode:** Strict gates, demand evidence before proceeding

### When to Override Gates

**Good reasons to proceed despite red flags:**
- Speed is more important than perfection
- Learning by doing is more valuable
- Cost of delay outweighs validation risk
- Iterative approach planned (fail fast, learn)

**Bad reasons to override:**
- Impatience
- Pressure to ship without validation
- Ignoring clear failure signals
- "We already built it, might as well ship"

---

## Non-Linear Flow

The workflow is **NOT strictly linear**. Common loops:

### Collect ÷ Analyze
- New data changes patterns
- Patterns reveal data gaps

### Analyze ÷ Strategize
- Strategy unclear without more analysis
- New strategy surfaces analytical gaps

### Strategize ÷ Experiment
- Validation fails, re-strategize
- New opportunity emerges from experiment

### Experiment ÷ Execute
- Pilot fails, run new experiment
- Production issues require re-validation

### Execute ÷ Assess
- Measure outcomes, identify next iteration
- Assessment reveals need for immediate fixes

### Assess ÷ Collect (Primary Loop)
- Learnings drive new data collection
- Outcomes validate or invalidate strategy
- **This is the continuous discovery cycle**

---

## Example: Full Workflow

```
Phase 1 (Collect):
Gather Gong calls, Snowflake usage data, customer interviews on "data access"
 Gate: 25 Gong calls, usage data from 100 customers, 8 interviews

Phase 2 (Analyze):
Pattern emerges: "Data bottleneck - analysts wait days for queries"
 Gate: Pattern in 18/25 Gong calls, validated by usage data

Phase 3 (Strategize):
Opportunity: "Self-Service Query Builder"
Priority: High strategic alignment, high customer impact
 Gate: Clear JTBD, customer evidence strong, exec aligned

Phase 4 (Experiment):
Build prototype query builder, test with 3 customers
Result: 2/3 succeeded, 1 struggled (needs SQL knowledge)
 Gate: Validated with modification (add query templates)

Phase 5 (Execute):
Build production version with templates, release to 20% of users
Health: Stable after 1 week, expanding rollout
 Gate: Released, stable, instrumented

Phase 6 (Assess):
After 6 weeks: 60% reduction in analyst tickets (target: 80%)
Learning: Templates helped, but need in-app education
Decision: Partial success - iterate with guidance

Loop back to Phase 4 (Experiment):
Test in-app tutorial with next cohort of users
```

---

## Quick Reference

| Transition | Key Question | Most Common Red Flag |
|------------|-------------|---------------------|
| **Collect ’ Analyze** | Enough data to find patterns? | Single-source data only |
| **Analyze ’ Strategize** | Patterns validated across sources? | Conflicting insights unreconciled |
| **Strategize ’ Experiment** | Key assumptions identified? | Skipping validation for "obvious" ideas |
| **Experiment ’ Execute** | Validation confirmed hypothesis? | Failed validation ignored |
| **Execute ’ Assess** | Feature stable & measurable? | Metrics not instrumented |
| **Assess ’ Collect** | Learnings captured? | No retrospective or learning captured |

---

## Version History

- **V1.0 (Week 4):** Initial phase transitions for 6-phase model
- **Future:** Expand with detailed examples and mode-specific guidance