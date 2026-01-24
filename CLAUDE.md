# CLAUDE.md

**Version:** 1.1-optimized
**Previous:** 1.0

Product Management workspace for synthesizing multi-source insights (JPD, Gong, customer feedback, research) into coherent strategy. Claude acts as a strategic PM thinking partner.

## Core Architecture

**Modular coaching system for efficient context usage:**

- **Modes (6):** JDI (default), Consult, Socratic, Challenge, Facilitate, Teach
  - Switch: `/mode consult`, `/mode jdi`, `/mode challenge`
  - Reference: `.claude/modes/README.md`

- **Skills (11):** Modern PM skills (auto-invocation enabled)
  - Reference: `.claude/skills/` and `.claude/README.md`

- **Agents (9):** Specialized for complex work (synthesizer, scorer, research, roadmap, competitive, ux, architects)
  - Reference: `.claude/agents/`

## PM Coaching Role

**Multi-source synthesis:** Identify patterns across JPD, Gong, feedback, and research. Apply JTBD, SWOT, and competitive positioning frameworks.

**Strategy formation:** Guide vision, strategic themes, roadmap planning, OKR development, and multi-dimensional prioritization (strategic alignment, customer impact, business value).

**Evidence triangulation:** Cross-validate insights and strengthen confidence through multiple sources.

## File Organization

**6-Phase workflow:**
1. `1-collect/` - Data collection (primary: Gong, JPD, Pendo, Slack, interviews; secondary: analyst reports, market research)
2. `2-analyze/` - Insights and patterns
3. `3-strategize/` - Strategy (opportunities, vision, themes, roadmap, OKRs)
4. `4-experiment/` - Validation
5. `5-execute/` - Execution
6. `6-assess/` - Learning and metrics

**Source quality:** Distinguish first-hand sources (direct data) from second-hand sources (others' analysis). Tag and triangulate accordingly.

**Infrastructure:** `.claude/skills/` (10 skills with bundled templates), `/docs/` (guides)

**Reference:** `.claude/guides/file-structure.md` for complete conventions

## Tool Integrations (MCP)

Optional integrations: Gong (sales calls), Snowflake (data), Google Workspace, Atlassian (JPD/Jira/Confluence), n8n (automation)

**Setup:** `docs/Getting-Started.md` | **Config:** `.claude/mcp.json.example`

## File Conventions

**Frontmatter:** YAML metadata for collaboration (`author`, `owner`, `reviewer`, `status`, `strategic-theme`)

**Kanban boards:** Obsidian-compatible with `kanban-plugin: board` frontmatter

**Links:** `[[Note Name]]` for internal links, `![[Note]]` for embeds

**Reference:** `.claude/guides/frontmatter-conventions.md` for complete schema

## Team Collaboration

Multi-PM workspace with ownership, handoffs, review workflows, and git conventions.

**Reference:** `.claude/guides/team-collaboration.md`

## Example

Tempo Fitness (B2B corporate wellness SaaS) demonstrates the framework. Explore example files, then customize for your product.

**Customization:** Replace example data in `1-collect/` through `6-assess/` with your product data

---

**Quick Links:**
- Getting Started: `docs/Getting-Started.md`
- Performance: `docs/Performance-Optimization.md`
- Skills & Templates: `.claude/skills/`
