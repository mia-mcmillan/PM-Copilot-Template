# Skills Migration Guide

**Migration Date**: 2026-01-21
**From**: Commands (`.claude/commands/`)
**To**: Skills (`.claude/skills/`)

---

## What Changed

PM Copilot has been upgraded from **legacy commands** to **modern skills** following the [official Claude Code skills standard](https://code.claude.com/docs/en/skills) and [Agent Skills open standard](https://agentskills.io).

### Key Improvements

✅ **Better Organization**: Each skill is now a directory with supporting files
✅ **YAML Frontmatter**: Proper metadata for discovery and auto-invocation
✅ **Supporting Files**: Templates bundled with skills
✅ **Auto-Invocation**: Claude can detect when to use skills automatically
✅ **Better Control**: Fine-grained control over invocation (manual-only, Claude-only)
✅ **Future-Proof**: Follows official standards for long-term compatibility

---

## Skills vs Commands Comparison

| Feature | Commands (Old) | Skills (New) |
|---------|---------------|--------------|
| **Location** | `.claude/commands/*.md` | `.claude/skills/*/SKILL.md` |
| **Structure** | Single file | Directory with supporting files |
| **Metadata** | None | YAML frontmatter |
| **Templates** | External references | Bundled in skill directory |
| **Discovery** | Manual only | Automatic + manual |
| **Invocation Control** | Limited | Full control |
| **Standard** | Legacy | Agent Skills open standard |

---

## Migration Status

### ✅ All 13 Skills (2 Removed)

| Old Command | New Skill | Status | Notes |
|-------------|-----------|--------|-------|
| `/analyze-data` | `/analyze-data` | ✅ Converted | Auto-invocation enabled + template |
| `/analyze-pattern` | `/analyze-pattern` | ✅ Converted | Auto-invocation enabled |
| `/ask-data` | - | ❌ Removed | Redundant with `/analyze-data` |
| `/competitive-analysis` | `/competitive-analysis` | ✅ Converted | Auto-invocation enabled + template |
| `/create-okrs` | `/create-okrs` | ✅ Converted | Auto-invocation enabled + template |
| `/explore-data` | - | ❌ Removed | Redundant with `/analyze-data` |
| `/import-gong` | - | ❌ Removed | External system integration |
| `/import-jpd` | - | ❌ Removed | External system integration |
| `/jtbd-analysis` | `/jtbd-analysis` | ✅ Converted | Auto-invocation enabled + template |
| `/mode` | `/mode` | ✅ Converted | Auto-invocation enabled |
| `/prioritize-opportunities` | `/prioritize-opportunities` | ✅ Converted | Auto-invocation enabled |
| `/roadmap-plan` | `/roadmap-plan` | ✅ Converted | Auto-invocation enabled |
| `/swot-analysis` | `/swot-analysis` | ✅ Converted | Auto-invocation enabled |
| `/synthesize-insights` | `/synthesize-insights` | ✅ Converted | Auto-invocation enabled |
| `/weekly-review` | `/weekly-review` | ✅ Converted | Auto-invocation enabled |

### Skills with Templates

4 skills now include bundled templates:
- `jtbd-analysis/template.md` - JTBD Analysis Template
- `create-okrs/template.md` - OKRs Template
- `competitive-analysis/template.md` - Competitive Positioning Template
- `analyze-data/template.md` - Data Analysis Template

---

## Using Skills

### Nothing Changes for You!

Skills work exactly like commands:
```bash
# Old way (still works)
/analyze-pattern

# New way (same thing)
/analyze-pattern
```

### New Feature: Auto-Invocation

Claude can now automatically detect when to use skills based on your request:

**Example:**
- **You say**: "Can you identify patterns across the customer feedback?"
- **Claude thinks**: *This matches the description of `/analyze-pattern`, let me use that skill*
- **Claude does**: Automatically invokes `/analyze-pattern` skill

---

## File Structure

### Before (Commands)
```
.claude/
└── commands/
    ├── analyze-pattern.md
    ├── create-okrs.md
    └── ...
```

### After (Skills)
```
.claude/
└── skills/
    ├── analyze-pattern/
    │   └── SKILL.md
    ├── create-okrs/
    │   ├── SKILL.md
    │   └── template.md
    ├── import-gong/
    │   ├── SKILL.md
    │   └── template.md
    └── ...
```

---

## YAML Frontmatter Reference

Each skill now has metadata at the top:

```yaml
---
name: analyze-pattern
description: Cross-source pattern recognition across customer insights
---
```

### Special Configuration

**Claude-Only Skills** (hide from user menu):
```yaml
---
name: internal-reference
description: Reference material
user-invocable: false
---
```

---

## Backward Compatibility

### Legacy Commands Still Work

The old `.claude/commands/` files are preserved and still functional. Claude Code will:
1. Check `.claude/skills/` first
2. Fall back to `.claude/commands/` if skill not found

### Gradual Migration

You can use both systems simultaneously during transition:
- New skills in `.claude/skills/`
- Old commands in `.claude/commands/` (until you're ready to remove)

### When to Remove Old Commands

Once you've verified skills work correctly, you can optionally:
```bash
# Archive old commands (optional)
mv .claude/commands .claude/commands-backup
```

---

## Testing Skills

### Verify Skills Are Loaded

Ask Claude:
```
What skills are available?
```

Claude should list all 13 skills with descriptions.

### Test Individual Skills

Try each skill:
```bash
# Test mode switching
/mode consult

# Test analysis
/analyze-pattern
```

### Test Auto-Invocation

Say something that should trigger a skill:
```
"Can you create OKRs for our strategic themes?"
```

Claude should automatically invoke `/create-okrs`.

---

## Benefits of Skills

### 1. Auto-Invocation

Claude can detect when to use skills based on natural language:
- **You**: "Analyze customer feedback patterns"
- **Claude**: *Uses `/analyze-pattern` automatically*

### 2. Better Organization

Each skill is self-contained with all its resources:
```
jtbd-analysis/
├── SKILL.md          # Instructions
└── template.md       # Output template
```

### 3. Fine-Grained Control

- `disable-model-invocation: true` - Manual-only (side effects)
- `user-invocable: false` - Claude-only (reference material)
- `allowed-tools: Read, Grep` - Restrict tool access

### 4. Supporting Files

Skills can include:
- Templates for output format
- Examples of good usage
- Reference material
- Scripts to execute

### 5. Future Extensions

Skills can be enhanced with:
- **Hooks**: Auto-run on git operations
- **Dynamic context**: Inject shell command output
- **Subagents**: Run in isolated contexts
- **Tool restrictions**: Limit Claude's capabilities per skill

---

## Advanced Features (Available)

### Dynamic Context Injection

Skills can execute commands and inject results:
```markdown
## PR Context
- Diff: !`gh pr diff`
- Comments: !`gh pr view --comments`
```

Commands run before Claude sees the skill.

### Subagent Execution

Run skills in isolated contexts:
```yaml
---
name: deep-research
description: Research thoroughly
context: fork
agent: Explore
---
```

### Tool Restrictions

Limit tool access during skill execution:
```yaml
---
name: read-only-analysis
description: Analyze without modifications
allowed-tools: Read, Grep, Glob
---
```

---

## Troubleshooting

### Skill Not Auto-Invoking

**Issue**: Claude doesn't automatically use the skill

**Solutions**:
1. Check the description is descriptive and uses natural keywords
2. Invoke explicitly with `/skill-name` to verify it works
3. Rephrase your request to match the description better
4. Run `/context` to check for warnings about skill loading

### Skill Triggers Too Often

**Issue**: Skill activates when you don't want it

**Solutions**:
1. Make the description more specific
2. Add `disable-model-invocation: true` to require explicit invocation

### Old Command Still Being Used

**Issue**: Changes to skill not reflected

**Solutions**:
1. Verify skill name matches old command name
2. Skills take precedence - check `.claude/skills/[name]/SKILL.md` exists
3. Restart Claude Code session
4. Remove old command file to force skill usage

### Template Not Found

**Issue**: Skill references template but can't find it

**Solutions**:
1. Verify template file is in skill directory: `.claude/skills/[name]/template.md`
2. Reference template with relative path: `[template.md](template.md)`
3. Check file permissions

---

## Migration Checklist

- ✅ All 15 commands converted to skills
- ✅ YAML frontmatter added to all skills
- ✅ 6 templates moved into skill directories
- ✅ Import skills marked as manual-only (`disable-model-invocation: true`)
- ✅ Documentation updated
- ✅ Migration guide created
- ⬜ User testing completed
- ⬜ Old commands archived (optional)

---

## Next Steps

### For You

1. **Test the skills**: Try using `/analyze-pattern`, `/mode consult`, etc.
2. **Try auto-invocation**: Ask Claude to do something and see if it auto-detects the right skill
3. **Verify templates**: Check that skills with templates work correctly
4. **Review migration**: Check [IMPLEMENTATION-REPORT.md](../IMPLEMENTATION-REPORT.md) for complete details

### For Future Enhancement

- Add more supporting files to skills (examples, scripts)
- Create hooks for automatic skill invocation on git events
- Add dynamic context injection for environment-specific data
- Build custom subagents for complex workflows

---

## Resources

- **Official Skills Documentation**: https://code.claude.com/docs/en/skills
- **Agent Skills Standard**: https://agentskills.io
- **Skills Directory**: `.claude/skills/`
- **Old Commands (Archive)**: `.claude/commands-legacy/`
- **Implementation Report**: `../IMPLEMENTATION-REPORT.md`
- **Detailed Reports (Archive)**: `../docs/archive/`

---

## Questions?

If you encounter issues:
1. Check this migration guide
2. Review the [official docs](https://code.claude.com/docs/en/skills)
3. Test individual skills explicitly
4. Check skill YAML frontmatter for errors

**Skills are the future of Claude Code customization!** 🚀

---

*Migration completed: 2026-01-21*
*Skills version: 1.0*
*Following: Agent Skills open standard*