# Tool Reference

## OpenAlice (Trading AI)
- **MCP:** http://localhost:3001/mcp
- **Web UI:** http://localhost:3002
- **Service:** systemd — `systemctl --user openalice`

## Claude Code
- **Path:** /home/vladimir/.npm-global/bin/claude
- **MCP:** stdio server
- **Use:** File, bash, web, subagent tools

## gog (Google Workspace)
- **Account:** chart.wizzard2020@gmail.com
- **Services:** Calendar, Gmail, Drive, Sheets, Docs, Contacts
- **Keyring Password:** mrford2026
- **Usage:**
  ```bash
  export GOG_KEYRING_PASSWORD="mrford2026"
  gog calendar events primary --from 2026-03-20T00:00:00Z --to 2026-03-21T00:00:00Z
  ```

## VPS Infrastructure
- **IP:** 85.17.246.64
- **OS:** Ubuntu 24.04
- **Trading Gateway:** Port 5555

## Trading Strategy Files
- Location: `~/.openclaw/workspace/trading/`
- MT5 EA: `Working_15MIN_ORB.mq5`

## Gmail Scripts
- Location: `~/.openclaw/workspace/scripts/`
- Commands: `gmail list`, `gmail send`, `gmail clean`
