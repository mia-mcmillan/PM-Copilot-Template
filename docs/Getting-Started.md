---
title: PM Copilot V1.0 - Getting Started Guide
version: 1.0
last-updated: 2025-11-22
---

# PM Copilot V1.0: Getting Started Guide

Welcome to PM Copilot V1.0! This guide will help you set up your strategic PM thinking partner workspace in 10-15 minutes.

---

## What You're Getting

**PM Copilot V1.0** is a comprehensive framework that turns Claude Code into your strategic product management thinking partner. It includes:

- **Complete Framework**: 6 coaching modes, 4 coaching patterns, 11 skills, 9 specialized agents
- **6-Phase Workflow**: Collect → Analyze → Strategize → Experiment → Execute → Assess (with feedback loops)
- **10 Templates**: Skills with bundled templates for essential PM activities
- **Working Example**: Tempo Fitness (fictional B2B SaaS) showing the full workflow in action

---

## Prerequisites

### Required

1. **Claude Code** (CLI tool from Anthropic)
   - Requires Claude Pro ($20/month) or Claude Team ($25/user/month)
   - Download: [claude.ai/code](https://claude.ai/code)
   - Installation: Follow Anthropic's setup guide

2. **Markdown Editor**
   - **Recommended**: Obsidian (free, powerful linking and visualization)
     - Download: [obsidian.md](https://obsidian.md)
   - **Alternatives**: VS Code, Typora, iA Writer (any markdown editor works)

3. **Git** (for version control)
   - macOS: Pre-installed or `brew install git`
   - Windows: [git-scm.com](https://git-scm.com)
   - Linux: `sudo apt install git` or equivalent

### Optional (but Recommended)

4. **MCP Integrations** (for data access)
   - **Gong**: Sales call intelligence (requires Gong account + API access)
   - **Snowflake**: Data warehouse queries (requires Snowflake account)
   - **Google Drive**: Document/spreadsheet access (requires Google account)
   - See: Setup guides in `/docs/` for each integration

---

## Quick Start (10 Minutes)

### Step 1: Clone the Repository (2 min)

```bash
# Clone the template
git clone https://github.com/[username]/pm-copilot-template.git

# Navigate to the directory
cd pm-copilot-template

# Optional: Create your own repo
git remote remove origin
git remote add origin https://github.com/[your-username]/[your-repo-name].git
```

### Step 2: Open in Obsidian (3 min)

1. **Launch Obsidian**
2. **Open vault**:
   - Click "Open folder as vault"
   - Select the `pm-copilot-template` folder
3. **Trust author** (if prompted):
   - Obsidian will ask if you trust the author of `.obsidian/` config
   - Click "Trust author and enable plugins"
4. **Install Community Plugins** (optional but recommended):
   - Settings → Community plugins → Browse
   - Install: "Kanban" (for kanban boards), "Dataview" (for queries), "Excalidraw" (for diagrams)

**Obsidian Tips**:
- Use `Cmd/Ctrl + O` for quick file switcher
- Use `Cmd/Ctrl + P` for command palette
- Enable "Readable line length" in Settings → Editor for better readability

### Step 3: Connect Claude Code (2 min)

1. **Start Claude Code** in the template directory:
   ```bash
   cd pm-copilot-template
   claude
   ```

2. **Test the connection**:
   ```
   Can you see the PM Copilot framework files in the .claude folder?
   ```

   Claude should respond affirmatively and describe what it sees.

3. **Try mode switching**:
   ```
   /mode consult
   ```

   Claude should confirm it's in Consult Mode.

**Troubleshooting**:
- If Claude can't see files: Check you're in the right directory (`pwd`)
- If `/mode` doesn't work: Ensure `.claude/modes/` folder exists with mode files

### Step 4: Explore the Tempo Fitness Example (3 min)

1. **Navigate to Phase 1** (Data Collection):
   - Open: `1-collect/primary/customer-interviews/2025-11-15 - Acme Corp - HR Director - JTBD.md`
   - Read the customer interview (Sarah Martinez, HR Director)
   - Notice the JTBD structure and pain points

2. **Navigate to Phase 2** (Analysis):
   - Open: `2-analyze/patterns/Engagement Drop-off - Pattern.md`
   - See how multiple data sources are synthesized into a pattern
   - Notice the evidence from interviews + usage data + sales calls

3. **Navigate to Phase 3** (Strategy):
   - Open: `3-strategize/opportunities/OPP-101 - Team Fitness Challenges.md`
   - See how the pattern translates into a prioritized opportunity
   - Notice the RICE score, competitive positioning, and strategic alignment

4. **Navigate to Phase 5** (Execution):
   - Open: `5-execute/projects/Q4 2025 Team Challenges - Kanban.md`
   - See project tracking with tasks in progress
   - Notice decisions made and risks tracked

**Key Insight**: Follow the file links (e.g., `[[JTBD - HR Director - Remote Team Engagement]]`) to see how insights connect across phases.

---

## Next Steps (15-30 Minutes)

### Understand the Framework

Read these key files to understand the architecture:

1. **Framework Overview**: [`CLAUDE.md`](../CLAUDE.md) (root directory)
   - Coaching modes, patterns, workflow phases
   - 10-minute read

2. **Mode Documentation**: `.claude/modes/README.md`
   - When to use each mode
   - 5-minute read

3. **Coaching Patterns**: `.claude/coaching/README.md`
   - How patterns guide proactive behavior
   - 5-minute read

### Try the Coaching Modes

**Exercise**: Ask Claude to analyze the Tempo Fitness opportunity in different modes.

1. **JDI Mode** (action-oriented):
   ```
   /mode jdi

   Create a one-pager summary of OPP-101 - Team Fitness Challenges
   ```

   Expected: Claude creates summary without questioning your request.

2. **Consult Mode** (strategic challenge):
   ```
   /mode consult

   I think we should prioritize AI Personalized Coaching (OPP-103)
   before Team Challenges (OPP-101).
   ```

   Expected: Claude challenges assumptions, asks for evidence, questions strategic fit.

3. **Socratic Mode** (learning through questions):
   ```
   /mode socratic

   How should I prioritize between OPP-101 and OPP-103?
   ```

   Expected: Claude asks questions to guide your thinking, doesn't give answers.

### Try the Slash Commands

**Exercise**: Use commands to create strategic artifacts.

1. **Pattern Analysis**:
   ```
   /analyze-pattern

   Analyze the "Engagement Drop-off" pattern and identify any gaps in our evidence.
   ```

2. **Opportunity Prioritization**:
   ```
   /prioritize-opportunities

   Score all opportunities in 3-strategize/opportunities/ using RICE framework.
   ```

3. **Weekly Review**:
   ```
   /weekly-review

   Create a weekly review for this week covering progress on Team Challenges MVP.
   ```

---

## Customization (30-60 Minutes)

Once you've explored the Tempo Fitness example, customize it for your product.

### Step 1: Keep the Framework

**DO NOT MODIFY** these directories (they contain the framework logic):
- `.claude/` - Coaching modes, patterns, commands, agents
- `.claude/skills/` - Skills with bundled templates

### Step 2: Replace the Example Data

**DELETE OR REPLACE** these directories (they contain Tempo Fitness example data):
- `1-collect/` - Replace with your customer interviews, usage data
- `2-analyze/` - Replace with your insights, patterns, analyses
- `3-strategize/` - Replace with your opportunities, roadmap, OKRs
- `4-experiment/` - Replace with your prototypes, tests, validation
- `5-execute/` - Replace with your project kanban boards
- `6-assess/` - Replace with your metrics, reviews, learnings

**Strategy**: Start with Phase 1 (Collect) and work through the phases.

### Step 3: Update Configuration Files

**Edit**: `CLAUDE.md` (root directory)
- Update "Example Scenario: Tempo Fitness" section with your product
- Update company name, product name, key opportunity
- Keep all framework sections intact

**Edit**: `README.md` (root directory)
- Update Quick Start examples to reference your product
- Keep workflow and directory structure documentation
- Update any Tempo Fitness references

### Step 4: Populate Your Data

**Recommended Sequence**:
1. **Phase 1**: Add 3-5 customer interviews using template
2. **Phase 2**: Analyze for patterns (use `/analyze-pattern` command)
3. **Phase 3**: Define 1-3 opportunities using template
4. **Phase 3**: Create roadmap (use `/roadmap-plan` command)
5. **Phases 4-6**: Add as you execute

**Strategy**: Start with Phase 1 and work through the phases methodically, using skills to guide analysis and synthesis.

---

## Common Questions

### Q: Do I have to use Obsidian?

**A**: No. The framework is markdown-based and works with any editor. Obsidian has nice features for linking documents (graph view, backlinks), but VS Code, Typora, or even vim work fine.

**Pros of Obsidian**: Graph view, backlinks, plugins (Kanban, Dataview), great for knowledge management
**Pros of VS Code**: Already familiar if you're an engineer, great git integration, extensible

### Q: Can I use this without Gong/Snowflake integrations?

**A**: Absolutely. Those are optional. The framework works with whatever data sources you have:
- Customer interviews in Google Docs → Copy to markdown
- Usage analytics in Excel → Export to CSV, analyze in markdown
- Sales call notes in Notion → Copy to markdown

The coaching modes and patterns work regardless of where your data lives.

### Q: How do I share this with my team?

**A**: Two approaches:

**1. Shared Git Repository** (recommended for teams):
- Push to private GitHub repo
- Team members clone and pull regularly
- Use branches for individual work
- Create PRs for major strategic decisions

**2. Shared Obsidian Vault** (if co-located or using sync service):
- Use Obsidian Sync ($8/month) or Dropbox/iCloud
- Define file ownership conventions (see `team-collaboration.md`)
- Use frontmatter `status` field for review workflows

### Q: Can I use this for non-PM work?

**A**: Yes, with customization. The principles (multi-source synthesis, pattern recognition, evidence-based decisions, strategic frameworks) apply to any strategic work:

- **Engineering Leaders**: Replace PM templates with technical strategy templates
- **Designers**: Adapt for design research, design system strategy
- **Data Scientists**: Use for experiment design, model evaluation, insight synthesis

The architecture (modes, patterns, workflow) is domain-agnostic. Customize templates and coaching patterns for your discipline.

### Q: How much does this cost?

**A**: Framework is free (open-source). Costs:
- **Claude Pro**: $20/month (required for Claude Code)
- **Obsidian**: Free (Sync is $8/month optional)
- **MCP Integrations**: Depends on services (Gong, Snowflake, etc.)

**Typical Setup**: $20/month (Claude Pro) + $0 (Obsidian free) = $20/month total.

### Q: Is my data private?

**A**: Yes. Everything is local-first:
- Files stored on your computer (not cloud by default)
- Claude Code runs locally, sends prompts to Claude API (encrypted)
- MCP integrations you control (only connect if you choose)

**To Share Safely**:
- Use private GitHub repo (don't push to public with customer data)
- Sanitize customer names/companies before sharing externally
- Review `.gitignore` to ensure sensitive files aren't committed

### Q: Can I contribute improvements to the framework?

**A**: Yes! This is open-source. Contributions welcome:
- New coaching modes or patterns
- Domain-specific adaptations (e.g., "PM Copilot for SaaS," "PM Copilot for Hardware")
- Template improvements
- Bug fixes or documentation updates

**How to Contribute**: See `CONTRIBUTING.md` in the GitHub repo (create PR with your changes).

---

## Troubleshooting

### Issue: Claude doesn't see my files

**Symptoms**: Claude says "I don't see any files" or can't find `.claude/` folder

**Solutions**:
1. Verify you're in the right directory: `pwd` should show `pm-copilot-template`
2. Check folder exists: `ls -la .claude/` should show mode/pattern files
3. Restart Claude Code: Exit and `claude` again from the correct directory

### Issue: `/mode` command doesn't work

**Symptoms**: Claude says "I don't recognize that command" or doesn't switch modes

**Solutions**:
1. Ensure `.claude/modes/` folder has mode files (jdi.md, consult.md, etc.)
2. Check CLAUDE.md is in root directory (Claude reads this for configuration)
3. Try absolute path: `/mode consult` instead of just `consult`
4. Check for typos: `/mode socratic` not `/mode socractic`

### Issue: Links in Obsidian don't work

**Symptoms**: Clicking `[[Link]]` doesn't navigate to file

**Solutions**:
1. Ensure file exists: Use Quick Switcher (`Cmd+O`) to search for file name
2. Check link syntax: Should be `[[File Name]]` not `[[File Name.md]]`
3. Obsidian may need indexing: Wait 30 seconds after opening vault
4. Try search: `Cmd+Shift+F` to find content even if link is broken

### Issue: Kanban boards don't display

**Symptoms**: Kanban markdown file opens as text, not visual board

**Solutions**:
1. Install Kanban plugin: Settings → Community plugins → Browse → "Kanban"
2. Check frontmatter: File should have `kanban-plugin: board` in YAML frontmatter
3. Right-click file → "Open with Kanban" if it opened in edit mode

### Issue: Claude gives generic responses, not coaching

**Symptoms**: Claude doesn't challenge assumptions or ask strategic questions

**Solutions**:
1. Switch to Consult Mode explicitly: `/mode consult`
2. Verify CLAUDE.md is being read (ask Claude "What coaching modes do you have?")
3. Be specific in your prompts: "Help me think through..." triggers coaching better than "Do X"
4. Check coaching patterns are loaded: Ask Claude "What coaching patterns guide your behavior?"

---

## Next Steps

### After Setup (First Week)

**Day 1-2: Explore**
- Read through all Tempo Fitness example files
- Try each coaching mode with different requests
- Experiment with slash commands

**Day 3-4: Start Customizing**
- Add your first customer interview
- Run `/analyze-pattern` on your existing data
- Create your first opportunity document

**Day 5-7: Build Habit**
- Use Claude in Consult Mode for strategic decisions
- Create weekly reviews (use template)
- Share with one teammate to get feedback

### Resources & Support

**Documentation**:
- Framework Overview: [`CLAUDE.md`](../CLAUDE.md)
- Performance Guide: [`docs/Performance-Optimization.md`](./Performance-Optimization.md)
- Team Collaboration: [`.claude/guides/team-collaboration.md`](../.claude/guides/team-collaboration.md)

**Community** (coming soon):
- GitHub Discussions: Ask questions, share adaptations
- Discord/Slack: Real-time community support
- Examples Gallery: See how others adapted the framework

**Updates**:
- Watch GitHub repo for new releases
- Major versions will have migration guides
- Backwards compatibility maintained within major versions

---

## Success Checklist

You're ready to start when you can check all these boxes:

- [ ] Cloned repository and opened in Obsidian (or preferred editor)
- [ ] Connected Claude Code and tested file access
- [ ] Switched modes successfully (`/mode consult`, `/mode jdi`)
- [ ] Explored Tempo Fitness example files (at least 5 files across phases)
- [ ] Ran at least one slash command (`/analyze-pattern` or `/weekly-review`)
- [ ] Asked Claude a strategic question in Consult Mode (saw it challenge assumptions)
- [ ] Read framework overview (CLAUDE.md)
- [ ] Identified which templates you'll use first for your product

---

**Ready to go?** Start with Phase 1 (Collect) - add your first customer interview or insights to begin building your product management knowledge base.

**Questions?** Open an issue on GitHub or check the [FAQ above](#common-questions).

**Good luck building strategically! 🚀**