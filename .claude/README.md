# Claude Code Configuration

This directory contains custom skills and agent definitions for Claude Code following the [Agent Skills open standard](https://agentskills.io).

## Structure

```
.claude/
├── skills/          # Modern PM skills (replaces commands)
│   ├── analyze-pattern/
│   │   └── SKILL.md
│   ├── synthesize-insights/
│   │   └── SKILL.md
│   ├── swot-analysis/
│   │   └── SKILL.md
│   ├── competitive-analysis/
│   │   ├── SKILL.md
│   │   └── template.md
│   ├── create-okrs/
│   │   ├── SKILL.md
│   │   └── template.md
│   └── ... (13 total skills)
├── agents/          # Specialized agents for complex work
│   ├── strategic-synthesizer.md
│   ├── opportunity-scorer.md
│   ├── research-analyzer.md
│   ├── roadmap-planner.md
│   └── competitive-intelligence.md
└── modes/           # Coaching modes
    ├── jdi.md
    ├── consult.md
    ├── challenge.md
    └── ...
```

## Using Skills

Skills provide quick access to common PM tasks with automatic invocation.

### Syntax
```
/skill-name
```

### Available Skills

| Skill | Purpose | Auto-Invoke | Templates |
|-------|---------|-------------|-----------|
| `/analyze-pattern` | Cross-source pattern recognition | ✅ Yes | - |
| `/synthesize-insights` | Strategic synthesis document | ✅ Yes | - |
| `/swot-analysis` | SWOT analysis | ✅ Yes | - |
| `/competitive-analysis` | Competitive deep dive | ✅ Yes | ✅ Template |
| `/roadmap-plan` | Strategic roadmap creation | ✅ Yes | - |
| `/prioritize-opportunities` | Opportunity scoring | ✅ Yes | - |
| `/weekly-review` | Weekly PM review | ✅ Yes | - |
| `/create-okrs` | OKR development | ✅ Yes | ✅ Template |
| `/jtbd-analysis` | Jobs-to-be-Done analysis | ✅ Yes | ✅ Template |
| `/analyze-data` | Autonomous data analysis | ✅ Yes | ✅ Template |
| `/mode` | Switch coaching modes | ✅ Yes | - |

### Example Usage

**Explicit invocation:**
```
/analyze-pattern
```

**Auto-invocation** (new feature):
```
"Can you identify patterns across customer feedback?"
→ Claude automatically uses /analyze-pattern
```

## Using Specialized Agents

Agents are designed for complex, multi-step tasks that require deep analysis.

### Launching Agents

In Claude Code, launch an agent using:
```
Use the Task tool to launch the [agent-name] agent with the following request:
[Your detailed request]
```

### Available Agents

#### 1. Strategic Synthesizer
**Best for:**
- Multi-source intelligence gathering
- Pattern recognition across data sources
- Strategic synthesis documents
- Theme development

**Example:**
```
Launch strategic-synthesizer agent to analyze all insights from the past month
and create a strategic synthesis identifying 3-5 key themes.
```

#### 2. Opportunity Scorer
**Best for:**
- Systematic opportunity prioritization
- Multi-dimensional scoring
- Resource allocation decisions
- Trade-off analysis

**Example:**
```
Launch opportunity-scorer agent to score all opportunities in /opportunities/
using the prioritization framework and create a prioritized list.
```

#### 3. Research Analyzer
**Best for:**
- Gong call transcript analysis
- Customer feedback synthesis
- Market research analysis
- Voice of customer extraction

**Example:**
```
Launch research-analyzer agent to analyze all Gong calls from Q4
and extract key customer pain points and feature requests.
```

#### 4. Roadmap Planner
**Best for:**
- Strategy-to-execution translation
- Roadmap creation and sequencing
- Resource allocation planning
- Now/Next/Later framework

**Example:**
```
Launch roadmap-planner agent to create a Q1 2025 roadmap based on
current strategic themes and prioritized opportunities.
```

#### 5. Competitive Intelligence
**Best for:**
- Competitive deep dives
- Market landscape analysis
- Win/loss analysis
- Battlecard development

**Example:**
```
Launch competitive-intelligence agent to conduct a comprehensive
competitive analysis of [Competitor Name].
```

## When to Use Commands vs Agents

### Use Slash Commands When:
- Quick, focused task with clear scope
- Single document output
- Standard framework application
- Time-sensitive need

### Use Agents When:
- Complex multi-step analysis
- Need to synthesize many sources
- Require deep strategic thinking
- Creating comprehensive strategy documents
- Want autonomous execution

## Customizing Commands & Agents

### Adding New Commands
1. Create new `.md` file in `.claude/commands/`
2. Define clear task description and output format
3. Follow existing command structure as template

### Modifying Agents
1. Edit agent `.md` file in `.claude/agents/`
2. Update role description, frameworks, or best practices
3. Test with sample tasks

### Best Practices
- Keep commands focused on single outputs
- Make agents comprehensive but give clear guidance
- Include quality checklists
- Document common pitfalls
- Provide output standards and templates

## Integration with Workflow

### Typical PM Workflow Using Claude Code

**Phase 1: Intelligence Gathering**
```
/analyze-pattern  # Identify recurring themes
Launch research-analyzer agent  # Deep dive on customer insights
```

**Phase 2: Strategic Analysis**
```
/synthesize-insights  # Create strategic synthesis
/swot-analysis  # Understand position
/competitive-analysis  # Analyze competitive landscape
```

**Phase 3: Strategy Formation**
```
/create-okrs  # Develop measurable objectives
Launch strategic-synthesizer agent  # Comprehensive strategy document
```

**Phase 4: Execution Planning**
```
/prioritize-opportunities  # Score and rank opportunities
/roadmap-plan  # Translate to roadmap
Launch roadmap-planner agent  # Detailed sequencing and planning
```

**Phase 5: Ongoing Management**
```
/weekly-review  # Track progress weekly
/jtbd-analysis  # Deep dive on specific customer needs (as needed)
```

## Tips for Effective Use

1. **Be Specific**: Provide context when invoking commands/agents
2. **Chain Commands**: Use output of one command as input to next
3. **Reference Docs**: Commands will link to source documents - review them
4. **Iterate**: Refine analyses based on new information
5. **Maintain Context**: Keep related documents linked
6. **Review Regularly**: Update commands/agents based on what works

## Troubleshooting

**Command not working?**
- Check file exists in `.claude/commands/`
- Ensure proper markdown formatting
- Check Claude Code version compatibility

**Agent not producing expected output?**
- Review agent prompt in `.claude/agents/`
- Provide more specific instructions
- Check that required source files exist
- Ensure enough context is available

## Contributing

As you use these commands and agents:
1. Note what works well
2. Identify gaps or improvements
3. Update documentation
4. Share learnings with team

---

*These tools are designed to make you a more effective strategic product manager.*
