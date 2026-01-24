# Performance Optimization Guide

**Version:** 1.0
**Last Updated:** 2026-01-23

This guide helps you optimize Claude Code performance in your PM Copilot workspace for faster response times and lower costs.

## Quick Wins

### 1. Disable Unused MCP Servers

MCP servers add significant latency to every request. Only enable what you need.

**Check status:**
```bash
/toggle-mcp status
```

**Disable all (fastest):**
```bash
/toggle-mcp off
```

**Enable only what you need:**
```bash
/toggle-mcp atlassian    # For JPD/Jira work
/toggle-mcp gong         # For sales call analysis
```

**Performance impact:**
- All disabled: Fastest (no external API calls)
- 1-2 servers: Moderate (only those API latencies)
- All enabled: Slowest (cumulative latency)

**Note:** Changes require Claude Code restart/reload to take effect.

### 2. Use .claudeignore

Exclude unnecessary directories from indexing.

**Already configured:**
- `.git/` - Version control (no need to index)
- `node_modules/`, `venv/` - Dependencies
- `.obsidian/` - Obsidian cache
- Temp files, OS files, logs

**Optional exclusions for large repos:**

Uncomment in `.claudeignore` if you have large data files:
```
# 1-collect/exports/     # Large export files
# *.csv                  # CSV data files
# *.sql                  # Database dumps
# archive/               # Old archived work
```

### 3. Simplify settings.local.json

Remove complex path expansions in `additionalDirectories`. The project root is already accessible.

**Minimal settings:**
```json
{
  "permissions": {
    "allow": [
      "Read(//Users/YOUR_USERNAME/Documents/**)"
    ]
  },
  "enableAllProjectMcpServers": false,
  "enabledMcpjsonServers": []
}
```

## Advanced Optimizations

### 4. Streamline CLAUDE.md

CLAUDE.md is loaded with every request. Keep it focused.

**Best practices:**
- Keep essential context only
- Move detailed docs to separate files
- Use "Reference: see X" pattern
- Avoid duplicating information
- Remove unnecessary examples

**Current CLAUDE.md:** ~200 lines (reasonable)
**Target for large projects:** <150 lines

### 5. Strategic Context Management

**DO:**
- ✅ Read specific files when you know what you need
- ✅ Use Task tool with Explore agent for open-ended searches
- ✅ Use targeted Grep patterns (e.g., `pattern: "class UserAuth"`)
- ✅ Request parallel tool calls for independent operations

**DON'T:**
- ❌ Request broad searches without specific targets
- ❌ Read entire directories speculatively
- ❌ Use Glob patterns like `**/*` without filters
- ❌ Ask Claude to "explore everything"

### 6. Use Haiku for Simple Tasks

When spawning agents with the Task tool, specify `"model": "haiku"` for straightforward work:

**Good for Haiku (fast & cheap):**
- File searches
- Simple code exploration
- Basic transformations
- Quick analysis
- Template generation

**Keep Sonnet for:**
- Complex reasoning
- Strategic analysis
- Multi-step planning
- Architectural decisions

**Example:**
```
Use Task tool with:
"model": "haiku"
"subagent_type": "Explore"
"prompt": "Find all files that handle user authentication"
```

### 7. Optimize Git Operations

**Keep repos clean:**
```bash
# Remove untracked files
git clean -fd

# Clear git cache if needed
rm -rf .git/index
git reset
```

**Large repos:**
- Use shallow clones: `git clone --depth 1`
- Avoid checking in large binaries
- Use Git LFS for large files

## Workspace-Specific Optimizations

### For PM Copilot Template

**Low-usage files to potentially exclude:**

Add to `.claudeignore` if not actively using:
```
# Archive old work
archive/
_archive/

# Large exports (if you have them)
1-collect/exports/*/raw-data/
*.csv
*.sql

# Old retrospectives (if accumulating)
# 6-assess/retrospectives/2025/
```

**Keep indexed:**
- `.claude/` - Skills (with bundled templates), agents, modes
- `docs/` - Documentation
- Current phase work (1-collect through 6-assess)

### MCP Server Recommendations

**Minimal setup (fastest):**
- Enable nothing by default
- Turn on as needed with `/toggle-mcp`

**Core PM workflow:**
- `atlassian` - JPD/Jira work
- `gong` - When analyzing sales calls

**Full workflow (slower):**
- `atlassian` + `gong` + `google-drive` + `n8n-mcp`
- Only enable when doing cross-tool work

## Troubleshooting Slow Performance

### Symptoms & Solutions

**Slow initial responses:**
- **Cause:** MCP servers initializing
- **Fix:** Disable unused servers with `/toggle-mcp off`

**Slow during file operations:**
- **Cause:** Large repo or many files
- **Fix:** Add exclusions to `.claudeignore`

**Slow during searches:**
- **Cause:** Broad search patterns
- **Fix:** Use specific patterns, target directories

**Slow with agents:**
- **Cause:** Using Sonnet for simple tasks
- **Fix:** Use Haiku model for straightforward work

### Diagnostic Commands

**Check repo size:**
```bash
du -sh .
```

**Count files:**
```bash
find . -type f | wc -l
```

**Find large files:**
```bash
find . -type f -size +1M -exec ls -lh {} \; | sort -k5 -hr | head -20
```

**Check git status:**
```bash
git status
git diff --stat
```

## Performance Monitoring

### Before & After Testing

**Baseline measurement:**
1. Note time for simple command: `/toggle-mcp status`
2. Note time for file search: "Find all skills with templates"
3. Note time for analysis: "Summarize the strategic themes"

**After optimization:**
1. Apply changes (disable MCPs, update .claudeignore)
2. Restart Claude Code
3. Re-run same commands and compare times

**Expected improvements:**
- MCP disable: 30-50% faster on average
- .claudeignore: 10-20% faster on large repos
- Haiku for agents: 3-5x faster on simple tasks

## Cost Optimization

### Token Usage

**Input tokens (charged per request):**
- CLAUDE.md loaded every time
- Files read during conversation
- Agent context and history

**Output tokens (charged per response):**
- Claude's responses
- Agent outputs
- Tool calls

### Reducing Costs

**Reduce input tokens:**
- Keep CLAUDE.md concise
- Use .claudeignore to limit indexed files
- Use targeted reads instead of broad searches
- Clear conversation history periodically

**Reduce output tokens:**
- Ask for concise responses when appropriate
- Use Haiku for simple tasks (cheaper)
- Avoid asking Claude to "show all results"

**Model pricing (approximate):**
- **Sonnet 4.5:** $3 per million input tokens, $15 per million output tokens
- **Haiku 4:** $0.25 per million input tokens, $1.25 per million output tokens

Haiku is **12x cheaper** for input, **12x cheaper** for output.

## Best Practices Summary

### DO:
- ✅ Disable unused MCP servers
- ✅ Use .claudeignore for large repos
- ✅ Keep CLAUDE.md focused and concise
- ✅ Use Haiku for simple agent tasks
- ✅ Make targeted file reads and searches
- ✅ Request parallel operations when possible
- ✅ Restart Claude Code after MCP changes

### DON'T:
- ❌ Enable all MCP servers by default
- ❌ Index unnecessary directories
- ❌ Include verbose documentation in CLAUDE.md
- ❌ Use Sonnet for straightforward tasks
- ❌ Make broad, unfocused searches
- ❌ Read entire directories speculatively
- ❌ Forget to restart after config changes

## Quick Reference

### Performance Commands

```bash
# Check MCP status
/toggle-mcp status

# Disable all MCPs (fastest)
/toggle-mcp off

# Enable specific MCP
/toggle-mcp atlassian

# Check repo size
du -sh .

# Find large files
find . -type f -size +1M -exec ls -lh {} \; | sort -k5 -hr | head -10

# Clear git cache
git clean -fd
```

### Configuration Files

- `.claudeignore` - Exclude directories from indexing
- `.claude/settings.local.json` - Local permissions and MCP settings
- `.claude/mcp.json` - Project MCP server configuration
- `CLAUDE.md` - Core instructions (keep concise)

## Support

**Still experiencing slow performance?**

1. Check diagnostics above
2. Review .claudeignore exclusions
3. Verify MCP servers are disabled: `/toggle-mcp status`
4. Consider splitting large files or reorganizing structure
5. Open an issue: https://github.com/anthropics/claude-code/issues

---

**Related Documentation:**
- Getting Started Guide: `docs/Getting-Started.md`
- MCP Configuration Template: `.claude/mcp.json.example`
- Skills Documentation: `.claude/README.md`
