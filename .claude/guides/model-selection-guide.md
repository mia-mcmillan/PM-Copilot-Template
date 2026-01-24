# Model Selection Guide

**Version:** 1.0
**Last Updated:** 2026-01-24

Hybrid model strategy optimizing for quality on strategic work and cost on operational tasks.

## Quick Reference

| Task Type | Recommended Model | Rationale |
|-----------|------------------|-----------|
| **Strategic thinking** | Opus 4.5 | Complex synthesis, high-stakes decisions |
| **Agent work** | Opus 4.5 (default) | Multi-step reasoning, pattern recognition |
| **Skills - Analysis** | Opus 4.5 | Deep analysis, framework application |
| **Skills - Operational** | Sonnet 4.5 | File operations, formatting, quick tasks |
| **Skills - Data import** | Sonnet 4.5 | Template population, file organization |
| **Quick edits** | Sonnet 4.5 | Iterative editing, documentation |
| **File operations** | Haiku | Searches, reads, simple transforms |

---

## Model Capabilities

### Claude Opus 4.5 (claude-opus-4-5-20251101)
**Best for:**
- Multi-source synthesis (JPD, Gong, feedback, research)
- Strategic decision-making with long-term implications
- Complex pattern recognition across datasets
- Framework application (JTBD, SWOT, competitive analysis)
- Evidence triangulation and validation
- High-stakes prioritization decisions
- Sophisticated trade-off analysis

**Use when:**
- Quality > Speed
- Decision has strategic impact
- Multiple sources need synthesis
- Ambiguity requires deep reasoning
- Coaching modes (Consult, Challenge, Socratic)

### Claude Sonnet 4.5 (claude-sonnet-4-5-20250929)
**Best for:**
- Operational task execution
- Iterative editing and formatting
- Template population
- File organization and management
- Quick analysis tasks
- Prototyping ideas before deep analysis

**Use when:**
- Speed > Maximum Quality (but still high quality)
- Well-defined tasks with clear scope
- Operational vs strategic work
- Budget optimization needed
- Rapid iteration required

### Claude Haiku (latest)
**Best for:**
- File searches and pattern matching
- Simple data extraction
- Template-based generation
- Quick formatting tasks
- Repetitive operations

**Use when:**
- Simple, well-defined operations
- Speed and cost critical
- No complex reasoning needed
- Batch processing tasks

---

## Agent Model Recommendations

### Tier 1: Opus 4.5 (Strategic Reasoning Required)

#### 1. Strategic Synthesizer
**Model:** Opus 4.5
**Rationale:**
- Core responsibility: Multi-source intelligence gathering
- Requires sophisticated pattern recognition across JPD, Gong, feedback, research
- Evidence triangulation needs deep reasoning
- Strategic theme development has long-term implications
- Quality critical for product direction

**Task file:** [.claude/agents/strategic-synthesizer.md](.claude/agents/strategic-synthesizer.md)

#### 2. Opportunity Scorer
**Model:** Opus 4.5
**Rationale:**
- Complex multi-dimensional scoring framework
- Sophisticated trade-off analysis required
- Prioritization decisions have major resource implications
- Calibration across opportunities needs consistency
- Confidence assessment requires judgment

**Task file:** [.claude/agents/opportunity-scorer.md](.claude/agents/opportunity-scorer.md)

#### 3. Research Analyzer
**Model:** Opus 4.5
**Rationale:**
- Synthesizes qualitative insights from Gong calls
- Extract nuanced customer pain points and emotional context
- JTBD analysis requires deep customer empathy
- Pattern recognition across transcripts
- Voice of customer synthesis critical for strategy

**Task file:** [.claude/agents/research-analyzer.md](.claude/agents/research-analyzer.md)

#### 4. Roadmap Planner
**Model:** Opus 4.5
**Rationale:**
- Strategy-to-execution translation requires alignment
- Sequencing decisions have dependencies and implications
- Resource allocation needs trade-off analysis
- Now/Next/Later framework requires strategic thinking
- Roadmap decisions guide team direction

**Task file:** [.claude/agents/roadmap-planner.md](.claude/agents/roadmap-planner.md)

#### 5. Competitive Intelligence
**Model:** Opus 4.5
**Rationale:**
- Competitive positioning requires strategic analysis
- Battlecard development needs nuanced differentiation
- Win/loss analysis demands pattern recognition
- Market landscape assessment shapes strategy
- Quality critical for competitive positioning

**Task file:** [.claude/agents/competitive-intelligence.md](.claude/agents/competitive-intelligence.md)

#### 6. UX Researcher
**Model:** Opus 4.5
**Rationale:**
- User research synthesis requires empathy and pattern recognition
- Journey mapping needs holistic understanding
- Behavior analysis requires psychological insight
- Design validation demands careful evaluation
- Customer empathy critical for product success

**Task file:** [.claude/agents/ux-researcher.md](.claude/agents/ux-researcher.md)

### Tier 2: Sonnet 4.5 (Operational with Some Complexity)

#### 7. Backend Architect
**Model:** Sonnet 4.5
**Rationale:**
- API design is more technical than strategic
- Architectural decisions often have clear patterns
- Technical feasibility assessment is structured
- Fast iteration valuable for prototyping
- Still requires quality, but speed beneficial

**Task file:** [.claude/agents/backend-architect.md](.claude/agents/backend-architect.md)

#### 8. Frontend Developer
**Model:** Sonnet 4.5
**Rationale:**
- UI implementation is operational
- Component development follows patterns
- Performance optimization is technical
- Fast iteration valuable for rapid prototyping
- Feasibility reviews can be quick

**Task file:** [.claude/agents/frontend-developer.md](.claude/agents/frontend-developer.md)

#### 9. Visual Storyteller
**Model:** Sonnet 4.5
**Rationale:**
- Data visualization follows established patterns
- Presentation creation benefits from speed
- Storytelling structure is well-defined
- Iteration valuable for design refinement
- Quality adequate, speed beneficial

**Task file:** [.claude/agents/visual-storyteller.md](.claude/agents/visual-storyteller.md)

---

## Skills Model Recommendations

### Strategic Analysis Skills → Opus 4.5

#### analyze-pattern
**Model:** Opus 4.5
**Why:** Cross-source pattern recognition, multi-source validation, strategic theme identification
**File:** [.claude/skills/analyze-pattern/SKILL.md](.claude/skills/analyze-pattern/SKILL.md)

#### synthesize-insights
**Model:** Opus 4.5
**Why:** Strategic synthesis document creation, evidence triangulation, theme development
**File:** [.claude/skills/synthesize-insights/SKILL.md](.claude/skills/synthesize-insights/SKILL.md)

#### swot-analysis
**Model:** Opus 4.5
**Why:** Strategic framework application, competitive positioning, market analysis
**File:** [.claude/skills/swot-analysis/SKILL.md](.claude/skills/swot-analysis/SKILL.md)

#### competitive-analysis
**Model:** Opus 4.5
**Why:** Competitive deep dive, battlecard development, positioning strategy
**File:** [.claude/skills/competitive-analysis/SKILL.md](.claude/skills/competitive-analysis/SKILL.md)

#### roadmap-plan
**Model:** Opus 4.5
**Why:** Strategic roadmap creation, sequencing decisions, resource allocation
**File:** [.claude/skills/roadmap-plan/SKILL.md](.claude/skills/roadmap-plan/SKILL.md)

#### prioritize-opportunities
**Model:** Opus 4.5
**Why:** Multi-dimensional scoring, trade-off analysis, prioritization framework
**File:** [.claude/skills/prioritize-opportunities/SKILL.md](.claude/skills/prioritize-opportunities/SKILL.md)

#### jtbd-analysis
**Model:** Opus 4.5
**Why:** Deep customer empathy, JTBD framework application, needs analysis
**File:** [.claude/skills/jtbd-analysis/SKILL.md](.claude/skills/jtbd-analysis/SKILL.md)

#### analyze-data
**Model:** Opus 4.5
**Why:** Autonomous data analysis, insight generation, statistical reasoning
**File:** [.claude/skills/analyze-data/SKILL.md](.claude/skills/analyze-data/SKILL.md)

### Operational Skills → Sonnet 4.5

#### weekly-review
**Model:** Sonnet 4.5
**Why:** Structured review process, checklist execution, progress tracking
**File:** [.claude/skills/weekly-review/SKILL.md](.claude/skills/weekly-review/SKILL.md)

#### toggle-mcp
**Model:** Sonnet 4.5
**Why:** Configuration management, simple operational task
**File:** [.claude/skills/toggle-mcp/SKILL.md](.claude/skills/toggle-mcp/SKILL.md)

### Mode Switching → Sonnet 4.5

#### mode
**Model:** Sonnet 4.5
**Why:** Simple mode switching, file loading (operational task)
**File:** [.claude/skills/mode/SKILL.md](.claude/skills/mode/SKILL.md)

*Note: The actual coaching within each mode should use the model that matches the work being done.*

---

## Coaching Mode Recommendations

### Mode-Specific Model Selection

#### JDI Mode (Just Do It)
**Default Model:** Sonnet 4.5
**Rationale:** Bias toward action, efficiency, speed
**Upgrade to Opus when:** Task involves strategic decisions, even in execution mode

#### Consult Mode
**Default Model:** Opus 4.5
**Rationale:** Strategic consulting, challenging thinking, guiding decisions
**Stay with Opus:** This mode is inherently strategic

#### Socratic Mode
**Default Model:** Opus 4.5
**Rationale:** Deep questioning requires understanding underlying patterns
**Stay with Opus:** Teaching through questions needs sophisticated reasoning

#### Challenge Mode
**Default Model:** Opus 4.5
**Rationale:** Stress-testing ideas, arguing opposite side needs deep reasoning
**Stay with Opus:** Devil's advocate requires sophisticated counterarguments

#### Facilitate Mode
**Default Model:** Sonnet 4.5
**Rationale:** Workshop facilitation is more operational
**Upgrade to Opus when:** Strategic decisions emerge from facilitation

#### Teach Mode
**Default Model:** Opus 4.5
**Rationale:** Teaching frameworks requires deep understanding
**Stay with Opus:** Education benefits from highest quality explanations

---

## Cost Optimization Strategy

### Expected Usage Pattern

**Typical PM Week:**
- Strategic work: 20% of interactions (Opus)
- Analysis work: 30% of interactions (Opus)
- Operational work: 40% of interactions (Sonnet)
- Simple operations: 10% of interactions (Haiku)

**Estimated Cost Savings:** ~40-50% vs all-Opus approach while maintaining quality on strategic work

### When to Override Recommendations

**Use Opus even for "Sonnet tasks" when:**
- High stakes or visibility
- First time doing this type of task (learn patterns)
- Ambiguity in requirements
- Quality more important than speed/cost
- Building templates others will use

**Use Sonnet even for "Opus tasks" when:**
- Rapid prototyping or exploration
- Low-stakes iteration
- Clear patterns from previous work
- Budget constraints critical
- Speed essential (time-sensitive)

---

## Implementation Guide

### For Claude Code CLI

Currently, Claude Code doesn't support per-agent or per-skill model configuration. Model selection happens at invocation:

**Option 1: Manual Selection**
When launching tasks, you (the PM) can specify model preference:
```
"Use Opus 4.5 to launch the strategic-synthesizer agent..."
"Use Sonnet to import this Gong data..."
```

**Option 2: Default Settings**
Set your default model in Claude Code settings based on your typical work:
- If mostly strategic work: Default to Opus
- If mostly operational: Default to Sonnet

**Option 3: Context-Based Switching**
Claude should proactively recommend model based on task:
```
PM: "Analyze patterns across customer feedback"
Claude: "This is a strategic analysis task. I recommend using Opus 4.5
for deep pattern recognition. Should I proceed with Opus?"
```

### For Future Claude Code Features

If per-agent model configuration becomes available, add to agent frontmatter:
```yaml
---
name: strategic-synthesizer
model: opus-4.5
fallback: sonnet-4.5
---
```

---

## Decision Framework

### Quick Decision Tree

```
Is this task...

├─ Strategic decision-making?
│  ├─ Yes → Opus 4.5
│  └─ No ↓
│
├─ Multi-source synthesis?
│  ├─ Yes → Opus 4.5
│  └─ No ↓
│
├─ Complex pattern recognition?
│  ├─ Yes → Opus 4.5
│  └─ No ↓
│
├─ Template population / file ops?
│  ├─ Yes → Sonnet 4.5 or Haiku
│  └─ No ↓
│
├─ Operational execution?
│  ├─ Yes → Sonnet 4.5
│  └─ No ↓
│
└─ When in doubt → Start with Opus, optimize later
```

---

## Monitoring & Adjustment

### Track Over Time

**Metrics to Monitor:**
1. **Quality**: Are Sonnet tasks meeting quality bar?
2. **Cost**: Monthly spend on each model
3. **Speed**: Time-to-completion by model
4. **Task Distribution**: What percentage of work uses each model?

**Adjust When:**
- Sonnet quality insufficient → Upgrade more tasks to Opus
- Opus rarely needed → Increase Sonnet usage
- Haiku underutilized → Identify more simple tasks
- Budget exceeded → Review task distribution

### Quarterly Review

Every quarter, review:
1. Which agent/skill tasks could move to faster model?
2. Which tasks need upgrade to higher quality model?
3. Are new patterns emerging (e.g., certain analyses now routine)?
4. Has model capability improved (upgrades may enable downgrades)?

---

## Examples

### Example 1: Pattern Recognition
**Task:** Identify patterns across 15 JTBD interviews
**Recommended Model:** Opus 4.5
**Rationale:** Multi-source synthesis, strategic theme identification, pattern validation
**Agent:** strategic-synthesizer
**Estimated Cost:** High, but justified by strategic impact

### Example 2: Gong Import
**Task:** Import 5 Gong transcripts into workspace
**Recommended Model:** Sonnet 4.5
**Rationale:** Template population, file organization, operational task
**Skill:** import-gong
**Estimated Cost:** Low, appropriate for operational work

### Example 3: Opportunity Scoring
**Task:** Score 12 opportunities using prioritization framework
**Recommended Model:** Opus 4.5
**Rationale:** Multi-dimensional analysis, trade-off decisions, high stakes
**Agent:** opportunity-scorer
**Estimated Cost:** High, but critical for roadmap decisions

### Example 4: Weekly Review
**Task:** Conduct weekly PM review of progress
**Recommended Model:** Sonnet 4.5
**Rationale:** Structured checklist, progress tracking, routine task
**Skill:** weekly-review
**Estimated Cost:** Medium, good balance for routine work

### Example 5: Competitive Analysis
**Task:** Deep dive on competitor's new product launch
**Recommended Model:** Opus 4.5
**Rationale:** Strategic positioning, battlecard development, competitive intelligence
**Agent:** competitive-intelligence
**Estimated Cost:** High, justified by competitive impact

---

## Summary

**Default to Opus 4.5 for:**
- Strategic agents (synthesizer, scorer, research, roadmap, competitive, UX)
- Strategic analysis skills (pattern, synthesis, SWOT, competitive, JTBD, prioritize)
- Coaching modes (consult, socratic, challenge, teach)

**Use Sonnet 4.5 for:**
- Operational agents (backend, frontend, visual storyteller)
- Operational skills (imports, weekly review, mode switching)
- JDI mode execution
- Facilitate mode

**Use Haiku for:**
- Simple file operations
- Batch processing
- Template-based generation

**When in Doubt:** Start with Opus, measure results, optimize over time.

---

**Related Guides:**
- [File Structure](.claude/guides/file-structure.md)
- [Agent Usage](.claude/README.md)
- [Performance Optimization](../docs/Performance-Optimization.md)
