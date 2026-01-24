# PM Copilot V1.0: Strategic Product Management with Claude Code

**Transform Claude Code into your strategic PM thinking partner through an open-source framework for evidence-based product decisions.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Version](https://img.shields.io/badge/version-1.0-blue.svg)](https://github.com/mia-mcmillan/pm-copilot-template)

---

## What is PM Copilot?

PM Copilot V1.0 is a comprehensive framework that turns Claude Code into an active strategic thinking partner for product managers. Instead of just storing information in markdown files, your workspace actively helps you:

- **Synthesize insights** from customer interviews, sales calls, usage data, and market research
- **Challenge your assumptions** with proactive coaching patterns
- **Guide strategic decisions** through Jobs-to-be-Done, competitive analysis, and prioritization frameworks
- **Adapt to your context** with six coaching modes (from efficient execution to strategic consulting)
- **Maintain continuity** by remembering decisions and connecting insights across phases

---

## Framework Architecture

### 6 Coaching Modes (Context-Adaptive Behavior)
- **JDI Mode**: "Just do it" - efficient task execution
- **Consult Mode**: Strategic partner - challenges thinking, surfaces assumptions
- **Socratic Mode**: Learning through questions (doesn't give answers)
- **Challenge Mode**: Stress-tests ideas, argues opposite side
- **Facilitate Mode**: Structures workshops and team decisions
- **Teach Mode**: Explains frameworks and builds PM skills

**Switch modes**: `/mode consult` (or any other mode)

### 4 Coaching Patterns (Proactive Guidance)
- **Assumption Surfacing**: Detects unstated assumptions ("Have we validated this?")
- **Decision Prompts**: Recognizes strategic decisions ("Should we document this trade-off?")
- **Evidence Checking**: Identifies unsupported claims ("What data supports that?")
- **Strategic Questioning**: Context-appropriate questions ("What's the opportunity cost?")

### 6-Phase Workflow (Continuous Cycle)
1. **Collect** 📥 → Customer interviews, sales calls, usage data
2. **Analyze** 🔍 → Pattern recognition, JTBD, competitive positioning
3. **Strategize** 🎯 → Opportunities, roadmap, OKRs
4. **Experiment** 🧪 → Prototypes, validation, pilots
5. **Execute** 🚀 → Project tracking, kanban boards
6. **Assess** 📊 → Metrics, outcomes, learnings (loops back to Phase 1)

### 11 Skills with Templates
- 11 Skills for quick tasks (`/analyze-pattern`, `/prioritize-opportunities`, `/weekly-review`)
- 9 Specialized Agents for complex work (competitive analysis, roadmap planning, OKR development)
- 10 skills with bundled templates for essential PM activities

---

## Quick Start (10 Minutes)

### 1. Clone & Open
```bash
git clone https://github.com/mia-mcmillan/pm-copilot-template.git
cd pm-copilot-template

# Open in Obsidian (recommended) or any markdown editor
```

### 2. Connect Claude Code
```bash
claude
```

Then test:
```
Can you see the PM Copilot framework files?
```

### 3. Explore the Example
This template includes a complete fictitious example: **Tempo Fitness** (B2B corporate wellness SaaS)

**Follow the journey**:
- 📋 Customer interview → HR Director pain (remote employee engagement drop-off)
- 🔍 Pattern analysis → 82% churn rate, validated across 3 data sources
- 🎯 Opportunity → Team Fitness Challenges (RICE score: 22,500)
- 🗺️ Roadmap → Prioritized as "Now" (Q4 2025 launch)
- ✅ Execution → Kanban tracking, weekly reviews

**Key files to explore**:
1. `1-collect/primary/customer-interviews/2025-11-15 - Acme Corp - HR Director - JTBD.md` (Start here)
2. `2-analyze/patterns/Engagement Drop-off - Pattern.md` (Pattern synthesis)
3. `3-strategize/opportunities/OPP-101 - Team Fitness Challenges.md` (Opportunity definition)
4. `3-strategize/strategy/2025-Q4 - Roadmap.md` (Strategic roadmap)
5. `5-execute/projects/Q4 2025 Team Challenges - Kanban.md` (Project tracking)

### 4. Try Coaching Modes
```
/mode consult

I think we should prioritize AI Coaching before Team Challenges.
```

Watch Claude challenge your assumptions and ask for evidence.

**🎉 You're ready!** Explore the Tempo Fitness example, then customize for your product by replacing the example data in `1-collect/` through `6-assess/` with your own.

---

## Documentation

### For Getting Started
- **[Getting Started Guide](docs/Getting-Started.md)**: Step-by-step setup (10-15 minutes)
- **[CLAUDE.md](CLAUDE.md)**: Framework overview and configuration

### For Customization
- **[Team Collaboration](.claude/guides/team-collaboration.md)**: Multi-PM workspace coordination
- **[Performance Optimization](docs/Performance-Optimization.md)**: Speed up Claude Code responses

---

## What's Included

### Framework (Keep These)
```
.claude/
├── modes/          # 6 coaching modes
├── coaching/       # 4 coaching patterns
├── skills/         # 11 skills with 10 bundled templates
├── agents/         # 9 specialized agents
├── workflows/      # Phase transition guidance
└── guides/         # Team collaboration docs
```

### Example (Replace with Your Data)
```
1-collect/          # Tempo Fitness customer interviews, usage data
2-analyze/          # Pattern recognition, JTBD analysis
3-strategize/       # Opportunities, roadmap, OKRs
4-experiment/       # Prototypes, validation results
5-execute/          # Project kanban boards
6-assess/           # Metrics, weekly reviews, learnings
```

---

## Features & Capabilities

### ✨ Intelligent Synthesis
- Cross-source pattern recognition (interviews + usage data + sales calls)
- Evidence triangulation (validate insights across multiple sources)
- Automated RICE prioritization (reach, impact, confidence, effort scoring)

### 🤝 Strategic Coaching
- Mode-aware behavior (execution vs. strategy vs. learning)
- Proactive assumption surfacing ("Are we assuming X?")
- Evidence-based decision making ("What data supports this?")
- Strategic questioning ("What's the opportunity cost?")

### 📚 Comprehensive Templates
- Customer research (JTBD interviews, feedback synthesis)
- Strategic analysis (SWOT, competitive positioning, pattern recognition)
- Product planning (roadmaps, OKRs, prioritization frameworks)
- Execution tracking (kanban boards, decision records, weekly reviews)

### 🔗 Optional Integrations (MCP)
- **Gong**: Sales call intelligence
- **Snowflake**: Data warehouse queries
- **Google Drive**: Document/spreadsheet access
- **Jira Product Discovery**: Two-way sync with opportunities

---

## Real-World Example: Tempo Fitness

**Scenario**: B2B SaaS corporate wellness platform facing the question: "What should we build next?"

**Process**:
1. **Customer Interview** (Phase 1): HR Director at Acme Corp reveals remote employee engagement drop-off (80% → 20% in 8 weeks)
2. **Pattern Analysis** (Phase 2): Claude synthesizes 3 data sources:
   - Customer interviews: 4/5 HR Directors mention same pain
   - Usage data: 73% sign up → 18% active after 60 days (82% churn)
   - Sales calls: 91% mention "engagement," 74% mention "drop-off"
3. **Opportunity Definition** (Phase 3): OPP-101 - Team Fitness Challenges
   - RICE score: 22,500 (very high priority)
   - Competitive positioning: "Peloton engagement without equipment"
4. **Roadmap** (Phase 3): Prioritized as "Now" (Q4 2025) over AI personalization (validates with data)
5. **Execution** (Phase 5): Tracked via kanban, on track for Dec 15 launch
6. **Learning** (Phase 6): Weekly reviews capture insights ("Team chat is surprisingly high-value - elevated to critical path")

**Key Insight**: The framework doesn't just organize information—it actively guides strategic thinking from insight to shipped feature.

---

## Who Is This For?

### Product Managers
- Solo PMs needing a strategic thinking partner
- PM teams coordinating on shared strategic work
- PM leaders building product strategy frameworks

### Engineering Leaders
- Engineering managers making technical strategy decisions
- Staff+ engineers driving architectural direction
- CTOs evaluating build-vs-buy decisions

### Adjacent Roles (with customization)
- Designers: Adapt for design research and design system strategy
- Data Scientists: Use for experiment design and insight synthesis
- Founders: Strategic decision-making for early-stage products

---

## Requirements

### Required
- **Claude Code**: CLI tool from Anthropic ([claude.ai/code](https://claude.ai/code))
  - Requires Claude Pro ($20/month) or Claude Team ($25/user/month)
- **Markdown Editor**: Obsidian (recommended, free) or VS Code, Typora, etc.
- **Git**: For version control

### Optional
- **MCP Integrations**: Gong, Snowflake, Google Drive (optional, configure if you have access)
- **Obsidian Plugins**: Kanban, Dataview, Excalidraw (enhance experience but not required)

---

## Comparison to Alternatives

| Tool | Type | Strengths | PM Copilot Difference |
|------|------|-----------|----------------------|
| Notion | Database | Flexible, collaborative | Active coaching, not passive storage |
| ProductBoard | Roadmap tool | Purpose-built | Framework-first, not tool-locked |
| Jira/JPD | Issue tracking | Eng integration | Strategic thinking, not task management |
| Miro/Mural | Whiteboard | Visual brainstorming | Structured synthesis, not freeform |

**PM Copilot**: Strategic thinking partner powered by AI, not just a productivity tool.

---

## Contributing

Contributions welcome! This is open-source.

**Ideas for Contributions**:
- New coaching modes or patterns
- Domain-specific adaptations (e.g., "PM Copilot for Hardware," "PM Copilot for Healthcare")
- Template improvements
- Bug fixes or documentation updates
- Integration guides for new tools

**How to Contribute**: See `CONTRIBUTING.md` (coming soon) or open an issue/PR.

---

## License

MIT License - see [LICENSE](LICENSE) file for details.

---

## Support & Community

### Documentation
- **Getting Started**: [`docs/Getting-Started.md`](docs/Getting-Started.md)
- **Framework Overview**: [`CLAUDE.md`](CLAUDE.md)
- **Performance Tips**: [`docs/Performance-Optimization.md`](docs/Performance-Optimization.md)

### Community (Coming Soon)
- **GitHub Discussions**: Q&A and community support
- **Discord/Slack**: Real-time community chat
- **Examples Gallery**: See how others adapted the framework

### Issues & Bugs
- **Report Issues**: [GitHub Issues](https://github.com/mia-mcmillan/pm-copilot-template/issues)
- **Feature Requests**: [GitHub Discussions](https://github.com/mia-mcmillan/pm-copilot-template/discussions)

---

## Creator

Created by [Mia McMillan](https://www.linkedin.com/in/miamcmillan/) - Product Manager passionate about evidence-based product decisions and AI-augmented workflows.

---

## Acknowledgments

**Built on**:
- [Claude Code](https://claude.ai/code) by Anthropic
- [Obsidian](https://obsidian.md) (recommended editor)
- Inspired by: Shape Up (Basecamp), Jobs-to-be-Done framework, Evidence-based product management

**Inspiration**:

Videos that sparked the vision for this framework:
- [Carlo Vellotti's Claude Code Tutorial on Aakash Gupta's Product Growth Podcast ](https://www.youtube.com/watch?v=4nthc76rSl8)
- [Teresa Torres's Claude Code for PMs on Claire Vo's How I AI Podcast](https://www.youtube.com/watch?v=oBho3hZ7MHM)
- [Dennis Yang's Cursor for PMs on Claire Vo's How I AI Podcaast](https://www.youtube.com/watch?v=rwmR7m5rvqw)

**Special Thanks**:
- Anthropic team for Claude Code and the Claude Agent SDK
- Matillion for encouraging AI experimentation
- Claire Vo's How I AI Podcast
- Aakash Gupta's Product Growth Podcast
- Lenny Ratchitsky's Lenny's Podcast

---

## Roadmap

### V1.0 (Current)
- ✅ 6 coaching modes + 4 coaching patterns
- ✅ 11 skills with 10 bundled templates
- ✅ 6-phase workflow
- ✅ Complete Tempo Fitness example

### V1.1 (Planned)
- [ ] Additional coaching modes (Research Mode, Review Mode)
- [ ] Video walkthrough and tutorials

### V2.0 (Ideas welcome!)


---

## FAQ

**Q: Do I need Obsidian?**
A: No - any markdown editor works. Obsidian has nice features (graph view, backlinks) but VS Code, Typora, or even vim work fine.

**Q: Can I use this without Gong/Snowflake?**
A: Yes - those integrations are optional. The framework works with whatever data sources you have (Google Docs, CSV files, markdown notes).

**Q: Is this free?**
A: The framework is free (open-source). You need Claude Pro ($20/month) for Claude Code. Obsidian is free (Sync is $8/month optional).

**Q: Can teams use this?**
A: Yes! See `.claude/guides/team-collaboration.md` for multi-PM coordination guidelines (file ownership, handoffs, review workflows).

**Q: How do I customize for my product?**
A: Keep `.claude/` (framework including skills with templates), replace `1-collect/` through `6-assess/` with your data. Takes 30-60 minutes.

---

**Ready to get started?** Follow the [Getting Started Guide](docs/Getting-Started.md) (10-15 minutes).

**Questions?** Open an issue or check the [FAQ](docs/Getting-Started.md#common-questions).

**Built with PM Copilot V1.0** 🚀