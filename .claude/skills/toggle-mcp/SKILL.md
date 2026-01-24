# toggle-mcp

## Overview
Quickly enable or disable MCP servers to optimize Claude Code performance.

## Invocation
- **Manual**: `/toggle-mcp [server-name]` or `/toggle-mcp status`
- **Auto-invoke**: No (requires explicit user action)

## Purpose
MCP servers add latency to responses. This skill provides a fast way to:
- Check which MCP servers are currently enabled
- Enable specific servers when needed
- Disable servers to speed up responses
- Toggle all servers on/off at once

## Available MCP Servers
- **atlassian**: Jira Product Discovery, Jira, Confluence integration
- **pendo**: Product analytics and usage data (Pendo integration)
- **n8n-mcp**: Workflow automation (n8n integration)
- **google-drive**: Google Docs, Sheets, Slides access
- **google-workspace**: Full Google Workspace integration (Docs, Sheets, Drive, Calendar)
- **slack**: Slack message search and posting
- **gong**: Sales call analysis (Gong API integration)
- **snowflake**: Data warehouse queries (Snowflake database)

## Behavior

### Show Status
When invoked with `status` or no arguments:
1. Read `.claude/settings.local.json`
2. Display current state of all configured MCP servers
3. Show which are enabled/disabled

### Enable Server
When invoked with server name (e.g., `/toggle-mcp gong`):
1. Read current settings
2. If server is disabled, enable it
3. If server is enabled, disable it
4. Update `.claude/settings.local.json`
5. Confirm the change

### Quick Commands
- `/toggle-mcp status` - Show current MCP server status
- `/toggle-mcp atlassian` - Toggle Atlassian server
- `/toggle-mcp pendo` - Toggle Pendo server
- `/toggle-mcp n8n-mcp` - Toggle n8n server
- `/toggle-mcp google-drive` - Toggle Google Drive server
- `/toggle-mcp google-workspace` - Toggle Google Workspace server
- `/toggle-mcp slack` - Toggle Slack server
- `/toggle-mcp gong` - Toggle Gong server
- `/toggle-mcp snowflake` - Toggle Snowflake server
- `/toggle-mcp all` - Toggle all servers (enable if any disabled, disable if all enabled)
- `/toggle-mcp off` - Disable all servers (speed mode)
- `/toggle-mcp on` - Enable all servers

## Implementation

1. **Read current settings** from `.claude/settings.local.json`
2. **Parse JSON** to get `enabledMcpjsonServers` array
3. **Modify array** based on command:
   - Add server name if enabling
   - Remove server name if disabling
   - Empty array to disable all
   - Add all known servers to enable all
4. **Write updated JSON** back to settings file
5. **Confirm change** to user

## Output Format

**Status display:**
```
MCP Server Status:
✅ atlassian (enabled)
❌ pendo (disabled)
❌ n8n-mcp (disabled)
❌ google-drive (disabled)
❌ google-workspace (disabled)
❌ slack (disabled)
✅ gong (enabled)
❌ snowflake (disabled)

Current mode: Fast (2 servers enabled)
```

**After toggle:**
```
✅ Enabled snowflake
MCP servers now active: atlassian, gong, snowflake
⚠️ Restart required: Reload VS Code window or restart Claude Code CLI
```

## Performance Impact

**All servers disabled**: Fastest responses, no external API calls
**Atlassian only**: Moderate - SSE connection to Atlassian MCP
**Pendo only**: Moderate - SSE connection to Pendo MCP
**n8n-mcp only**: Moderate - API calls to n8n workflows
**Google Drive only**: Moderate - OAuth and Google API calls
**Google Workspace only**: Moderate - Full Google Workspace API integration
**Slack only**: Moderate - Slack API calls
**Gong only**: Moderate - API calls only when analyzing transcripts
**Snowflake only**: Slower - database connection overhead
**Multiple enabled**: Cumulative latency from all active servers
**All 8 enabled**: Slowest - maximum latency but full functionality

## Notes
- Changes require Claude Code restart/reload to take effect
- Settings file is at `.claude/settings.local.json`
- MCP server configurations are in `~/.config/claude-code/mcp_config.json`
- This skill only toggles existing configured servers
