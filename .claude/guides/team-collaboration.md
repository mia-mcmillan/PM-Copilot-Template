# Team Collaboration Guidelines

This workspace supports multiple PMs working together. Follow these conventions to coordinate effectively and avoid conflicts.

## Multi-PM Workspace Coordination

**File Ownership Conventions**:
- Add `author:` field to document frontmatter to indicate primary author
- Use filename prefixes to indicate work status:
  - `DRAFT-` - Work in progress, not ready for team review
  - `WIP-` - Active work, input welcome
  - `REVIEW-` - Ready for peer review
  - No prefix - Approved/final, ready for team use

**Avoiding Duplicate Work**:
- Check existing files in target folder before creating new analysis
- Search for related patterns/insights before starting new research
- Update existing documents rather than creating duplicates
- Use `working/[pm-name]/` folders for personal exploration

**Handoff Procedures**:
- Document context in file frontmatter when passing work between PMs
- Include `handoff-notes:` field with key context and next steps
- Link to related files and data sources for continuity
- Tag successor PM with `@pm-name` in handoff note

## Assignment and Ownership Patterns

**Kanban Boards**:
- Individual ownership: `@pm-name` on task items
- Shared ownership: `@team` for collaborative work
- Unassigned work: No @ tag, available for any PM to claim

**Opportunity Files**:
- Add `owner:` field to frontmatter in `3-strategize/opportunities/`
- Owner is responsible for updates and driving to decision
- Multiple PMs can collaborate, but one owns final call

**Strategic Artifacts**:
- Designate lead PM for each strategic theme, OKR set, roadmap
- Lead PM coordinates input but maintains final document
- Document in `4-execute/dashboards/Team Coordination Dashboard.md`

**Coverage Matrix**:
- Maintain PM-to-product-area mapping in Team Coordination Dashboard
- Update quarterly or when responsibilities shift
- Helps route customer feedback and opportunities to right PM

## Review and Approval Workflows

**Document Progression**:
- Strategic artifacts follow: Draft → Review → Approved progression
- Use `status:` field in frontmatter: `draft`, `review`, `approved`
- File prefix changes as status progresses (remove `DRAFT-`/`REVIEW-` when approved)

**Peer Review Requirements**:
- Strategic synthesis documents require 2nd PM review
- OKRs and roadmaps require team review before finalization
- Competitive analysis should be validated by another PM
- SWOT analysis benefits from multiple perspectives

**Review Assignment**:
- Add `reviewer:` field in frontmatter when requesting review
- Reviewers use Obsidian comments or inline markdown comments for feedback
- Comments format: `<!-- REVIEWER: [PM Name] - [Feedback] -->`
- Mark review complete by updating `status:` and adding `reviewed-by:` field

**Feedback Conventions**:
- Use constructive, specific feedback tied to strategic frameworks
- Reference evidence/sources when suggesting changes
- Distinguish between blocking issues vs. suggestions
- Respond to feedback inline or in review notes section

## Credential and Integration Setup

**Recommended: AWS Secrets Manager** (Preferred for Team Use):
- Team uses AWS Secrets Manager for centralized credential management
- Each PM runs: `./scripts/start_claude.sh` to launch with credentials loaded
- Credentials fetched from AWS at runtime, never stored locally
- Requires one-time AWS CLI setup: `aws configure`
- IAM permissions needed: `secretsmanager:GetSecretValue` for `pm-workspace/*`
- See: `docs/AWS-Secrets-Manager-Setup.md` for complete setup guide
- Test setup with: `./scripts/test_aws_secrets.sh`

**Fallback: Individual Environment Files**:
- Alternative if AWS Secrets Manager unavailable
- Each PM maintains personal `.env` file (git-ignored)
- Use `.env.template` as starting point
- Never commit actual credentials to repository
- Store sensitive tokens in password manager

**MCP Configurations**:
- Personal MCP configs live in `~/.config/claude/mcp.json` (not in repo)
- Team shares MCP server setup documentation in `/docs/`
- Each PM configures own API keys for Gong, Snowflake, Google Drive
- Test connections individually using provided test scripts

**Shared Data Exports**:
- Exports go in standard `1-collect/exports/[source]/` folders
- Add `exported-by:` metadata to file frontmatter
- Include `export-date:` for tracking freshness
- Document any filtering or selection criteria used

**Query Results and Analysis**:
- Tag Snowflake/Gong query outputs with PM who ran them
- Include query parameters in file metadata
- Share reusable queries in `scripts/queries/` folder
- Document custom analyses in file header

## Git Workflow for Team

**Branch Naming**:
- Feature work: `pm-name/feature-description`
- Analysis work: `analysis/topic-name`
- Strategic docs: `strategy/document-name`
- Bug fixes: `fix/issue-description`

**Commit Message Conventions**:
- Include PM initials in brackets: `[MM] Add JTBD analysis for feature X`
- Use conventional commits: `feat:`, `docs:`, `analysis:`, `strategy:`
- Reference related files in commit body
- Keep commits focused and atomic

**Pull Request Requirements**:
- Strategic artifacts (roadmaps, OKRs, vision docs) require PR review
- PRs need at least one other PM approval
- Direct commits OK for personal research, drafts, and working folders
- Include context and rationale in PR description

**Merge Conflict Resolution**:
- Newest insight wins when conflicts occur
- Preserve all data sources and references from both versions
- When in doubt, discuss with other PM before resolving
- Document resolution rationale in commit message

**Commit Safety Checklist**:
Before staging and committing files, always follow this checklist:
1. Run `pwd` to verify you're in the correct repository
2. Run `git status` to review what files have changed
3. Run `git diff` to understand the changes being committed
4. Stage only the files you intend to commit (avoid `git add .` or `git add -A`)
5. Write clear, descriptive commit messages following team conventions
6. Run `git status` again to verify staged files before commit
7. After commit, verify success with `git log --oneline -1`

**Why This Matters**:
- Prevents accidentally committing to the wrong repository
- Avoids committing unintended files (credentials, personal notes, temp files)
- Ensures commits are focused and reviewable
- Maintains clean git history for team collaboration

## File and Folder Conventions

**Multi-Author Documents**:
- List all contributing PMs in frontmatter: `authors: [PM1, PM2, PM3]`
- Primary author listed first
- Update `last-updated-by:` when making significant changes
- Maintain version history in frontmatter or comments

**Personal Working Folders**:
- Each phase has optional `working/[pm-name]/` subfolder
- Use for personal exploration, drafts, and in-progress research
- Content here is visible to team but not considered final
- Clean up or promote to main folders periodically

**Shared vs Personal Content**:
- Files in main phase folders are team-visible and team-relevant
- Working folders are for individual exploration
- Templates are shared resources (coordinate changes with team)
- Scripts should be general-purpose, not PM-specific

**Archiving Convention**:
- Move outdated analyses to `archive/[year]/[phase]/` rather than delete
- Maintains history and context for future reference
- Archive quarterly during strategic reviews
- Keep archive structure parallel to main structure

## Team Synchronization

**Weekly PM Sync**:
- Review active opportunities and their status
- Discuss strategic priorities and any shifts
- Surface blockers and conflicts early
- Update Team Coordination Dashboard

**Monthly Strategic Review**:
- Revisit strategic themes and alignment
- Review and adjust roadmap priorities
- Evaluate prioritization framework effectiveness
- Discuss competitive landscape changes

**Dashboard Maintenance**:
- Maintain `4-execute/dashboards/Team Coordination Dashboard.md`
- Shows PM ownership, active work, capacity
- Updated weekly during PM sync
- Links to key strategic artifacts

**Communication Conventions**:
- Reference file paths in Slack/discussions: `See 2-analyze/insights/[file]`
- Use Obsidian links in internal docs: `[[File Name]]`
- Tag PMs for attention: `@pm-name` in comments or kanban cards
- Keep discussions in context (in files or linked notes)

## Handling Competing Priorities

**Escalation Path**:
- Document conflicts in Team Coordination Dashboard
- Discuss in weekly PM sync first
- Escalate to PM leadership if unresolved
- Use objective frameworks (strategic alignment, customer impact) to guide decisions

**Prioritization Tie-Breakers**:
- Strategic theme alignment scoring (highest wins)
- Customer impact assessment (most impacted customers)
- Business value analysis (revenue/retention impact)
- Effort estimation (higher ROI wins)

**Resource Conflicts**:
- Use OKR framework to determine focus areas
- Reference quarterly strategic themes
- Consider capacity and expertise fit
- Balance quick wins with strategic initiatives

**Customer-Facing Conflicts**:
- Default to customer impact over internal preference
- Gather additional customer evidence if unclear
- Use JTBD analysis to understand true need
- Consider which solution serves more jobs-to-be-done