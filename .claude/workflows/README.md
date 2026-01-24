# Workflows

This directory contains workflow guidance for the 6-phase PM Copilot process.

## Purpose

Workflow files provide:
- Phase transition criteria (quality gates)
- When to move from one phase to next
- What "done" looks like for each phase
- How phases connect together

## Workflow Files

### 1. Phase Transitions
**File:** `phase-transitions.md` *(Week 4)*

**Purpose:** Define gates between phases

**Contains:**
- Entry criteria for each phase
- Exit criteria (quality gates)
- What to carry forward
- When to loop back
- Red flags that block transition

---

## The 6-Phase Workflow

```
1-collect/     →  2-analyze/      →  3-strategize/
Data gathering    Insights          Strategy & roadmap

        ↓                ↑

6-assess/      ←  5-execute/      ←  4-experiment/
Learn & iterate   Build & ship      Validate & test
```

**Continuous cycle:** Learnings from Phase 6 feed back to Phase 1 for ongoing discovery.

## Phase Overview

### Phase 0: Discover
**Purpose:** Market research and foundational learning

**Deliverables:**
- Market research
- Competitive deep dives
- Technology trend analysis
- Ecosystem mapping

**Gate to Phase 1:**
✅ Sufficient market context established
✅ Key trends and dynamics understood
✅ Competitive landscape mapped

---

### Phase 1: Collect
**Purpose:** Gather product-specific intelligence

**Deliverables:**
- Gong transcripts
- Customer feedback
- Usage data (Pendo, Snowflake)
- Salesforce data

**Gate to Phase 2:**
✅ Multi-source data collected
✅ Coverage across customer segments
✅ Recent data (within relevant timeframe)

---

### Phase 2: Analyze
**Purpose:** Synthesize insights and recognize patterns

**Deliverables:**
- JTBD analyses
- Customer insights
- Pattern recognition
- Strategic synthesis

**Gate to Phase 3:**
✅ Patterns validated across multiple sources
✅ Strategic themes emerging
✅ Customer needs understood
✅ Competitive position clear

---

### Phase 3: Assess
**Purpose:** Evaluate specific opportunities

**Deliverables:**
- Opportunity assessments
- Feasibility analysis
- Market sizing
- Hypothesis formation

**Gate to Phase 4:**
✅ Opportunities scored and prioritized
✅ Assumptions mapped
✅ Evidence supporting opportunities
✅ Clear winners identified

---

### Phase 4: Strategize
**Purpose:** Form strategy and roadmap

**Deliverables:**
- Product vision
- Strategic themes
- Roadmap (Now/Next/Later)
- OKRs
- Decision records

**Gate to Phase 5:**
✅ Strategy coherent and defensible
✅ Alignment with leadership
✅ Clear priorities set
✅ Success metrics defined

---

### Phase 5: Experiment
**Purpose:** Validate before full commitment

**Deliverables:**
- MVPs
- Pilots and betas
- A/B tests
- Prototypes
- Validation results

**Gate to Phase 6:**
✅ Hypothesis tested
✅ Validation criteria met
✅ Risks reduced
✅ Go/no-go decision made

---

### Phase 6: Execute
**Purpose:** Build and ship to production

**Deliverables:**
- Production features
- Metrics and dashboards
- Execution tracking
- Stakeholder updates

**Gate to Phase 7:**
✅ Feature shipped
✅ Instrumentation in place
✅ Initial data collected
✅ Stabilized in production

---

### Phase 7: Learn
**Purpose:** Measure outcomes and iterate

**Deliverables:**
- Retrospectives
- Outcome analysis (did we hit OKRs?)
- Decision reviews (were we right?)
- Lessons learned

**Gate back to Phase 0/1:**
✅ Outcomes measured
✅ Learnings captured
✅ Next iteration identified
✅ Insights feed back to discovery

---

## Phase Transition Gates

### What is a Quality Gate?

A checkpoint before moving to the next phase:
- Ensures minimum quality bar is met
- Identifies gaps or risks
- Prevents rushing ahead without foundation
- Forces explicit decisions

### How Gates Work

**Before transition, Claude asks:**
1. "Have we met the exit criteria for this phase?"
2. "What are the open questions or risks?"
3. "What should we carry forward?"
4. "Are we ready to proceed, or should we loop back?"

**User decides:**
- ✅ Proceed: Gate passed, move forward
- ⚠️ Proceed with risks: Acknowledge gaps, move forward
- ❌ Loop back: Return to previous phase, fill gaps

### Gate Enforcement Levels

**Strict (High-stakes decisions):**
- Strategy formation
- Resource commitments
- Major pivots

**Moderate (Most work):**
- Standard phase transitions
- Typical PM workflow

**Loose (Iterative work):**
- Learning cycles
- Continuous discovery

## Non-Linear Flow

**The workflow is NOT strictly linear:**

### Common Loops

**Discovery ⟷ Collection:**
- New market intel requires more data gathering
- Data reveals gaps in market understanding

**Analysis ⟷ Assessment:**
- Opportunity assessment reveals pattern gaps
- New patterns change opportunity scores

**Strategy ⟷ Assessment:**
- Strategy unclear, need more opportunity work
- New strategic direction surfaces new opportunities

**Experiment ⟷ Execute:**
- Experiment fails, back to experimentation
- Production learning leads to new experiments

**Learn ⟷ Discover:**
- Outcomes reveal new market dynamics
- Retrospectives identify research gaps

### When to Loop Back

**Loop back when:**
- Quality gate fails
- New information contradicts earlier work
- Assumptions proven wrong
- Stakes increase (need more rigor)
- Strategic pivot required

**Don't loop back when:**
- Perfect is the enemy of good enough
- Diminishing returns on more analysis
- Learning by doing is more valuable
- Speed matters more than certainty

## Using Workflows

### For Daily Work

**Start of session:**
"Which phase are we in?"
→ Claude loads appropriate guidance

**During transition:**
"Should we move to [next phase]?"
→ Claude checks gate criteria

**When stuck:**
"Are we in the right phase?"
→ Claude suggests where you should be

### For Strategic Planning

**Quarter planning:**
Review full cycle: Discover → Learn

**Initiative planning:**
Map initiative to phases, estimate effort

**Retrospectives:**
Which phases worked well? Which need improvement?

## Workflow Customization

### Adapt phases to your context

**Startup (fast):**
- Collapse Discover into Collect
- Quick gates, bias toward action
- Experiment before Strategy sometimes

**Enterprise (rigorous):**
- Extended Discover and Assess
- Strict gates with stakeholder alignment
- Formal decision records required

**Maintenance work:**
- Skip Discover and Assess
- Jump to Experiment or Execute
- Lightweight gates

## Performance Monitoring

Track for workflow:
- Are phase transitions clear?
- Do gates prevent problems?
- Is flow efficient or bureaucratic?
- Do users understand where they are?
- Are loops back happening appropriately?

## Troubleshooting

**Problem:** Don't know which phase I'm in
- Ask Claude: "What phase are we in?"
- Look at recent file locations
- Check against phase deliverables

**Problem:** Gates feel bureaucratic
- Adjust gate strictness level
- Focus on minimum viable quality
- Balance rigor with momentum

**Problem:** Constantly looping back
- May need better Discover/Collect work
- Quality bar might be too high
- Consider progressive disclosure (good enough, then iterate)

## Example: Full Cycle

```
Phase 0 (Discover): Market research shows self-service analytics trend
↓
Phase 1 (Collect): Gather Gong calls, usage data, customer feedback on data access
↓
Phase 2 (Analyze): Pattern emerges: Data bottleneck is top pain point
↓
Gate Check: Pattern validated? ✅ Yes, appears in 15+ Gong calls and usage data
↓
Phase 3 (Assess): Assess opportunity "Self-Service Query Builder"
- Market size: Enterprise segment, $X TAM
- Assumptions: Users can write SQL, IT wants self-service
- Priority: High strategic alignment, high customer impact
↓
Gate Check: Ready for strategy? ✅ Yes, strong evidence and clear priority
↓
Phase 4 (Strategize): Add to roadmap, set OKR "80% reduction in data team tickets"
↓
Gate Check: Ready to experiment? ✅ Yes, but need to validate SQL assumption
↓
Phase 5 (Experiment): Build MVP query builder, pilot with 3 customers
- Result: 2/3 customers succeeded, 1 struggled with SQL
- Learning: Need query templates for non-technical users
↓
Gate Check: Go to production? ⚠️ Proceed with modification (add templates)
↓
Phase 6 (Execute): Build production version with templates, ship to all customers
↓
Gate Check: Stabilized? ✅ Yes, 2 weeks in production, metrics flowing
↓
Phase 7 (Learn): Retrospective after 1 quarter
- Outcome: 65% reduction in tickets (target: 80%)
- Learning: Templates helped, but need more education
- Next iteration: Add in-app guidance
↓
Loop back to Phase 1: Collect more usage data on templates
```

## Version History

- **V1.0 (Week 1):** Framework established, README created
- **V1.0 (Week 4):** Phase transitions implemented
- **Future:** Workflows refined based on usage patterns
