# @letta-ai/environment-compass

Letta Code mod package.

## Install locally

```bash
letta install .
```

Run /reload in active sessions for changes to take effect.

## What's changed vs upstream

Fork adapted for local Windows Desktop + cloud dual use.

### Platform fixes (Windows, cross-platform)
- Windows detection via `process.platform === "win32"`
- PATHEXT-aware executable search (`letta.cmd`, `letta.exe`, `letta.ps1`)
- Desktop package path via `%LOCALAPPDATA%\Programs\letta-code\`
- Proper executable check (extension + F_OK, not X_OK)

### resolveMemoryDir fix (local + cloud)
`resolveMemoryDir()` now checks both paths by agentId:

1. `~/.letta/lc-local-backend/memfs/<agentId>/memory` — **local backend**
2. `~/.letta/agents/<agentId>/memory` — **cloud agent**

Previously only checked the cloud path, so the mod couldn't find memory for local-backend agents. Now works in both modes for the same agent.
