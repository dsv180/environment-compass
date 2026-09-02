# @letta-ai/environment-compass

## Purpose

Read-only orientation for the agent's runtime environment: HOME, CWD, MEMORY_DIR,
Node/Letta versions, git status of memory and workspace repos.

Cross-platform: Windows (Desktop / local), macOS (Desktop / local), Railway/Linux.

## Behavior

Registers a tool `environment_compass` and a slash command `/env-compass`.
Both produce the same report. No network calls, no writes — read-only.

## Platform fixes (Windows)

Upstream package was macOS-only. Fork includes:
- Windows detection via `process.platform === "win32"`
- PATHEXT-aware executable search (`letta.cmd`, `letta.exe`, `letta.ps1`)
- Desktop package path via `%LOCALAPPDATA%\Programs\letta-code\`
- Proper executable check (F_OK + extension, not X_OK) for Windows

## Entry points

- `mods/index.ts`

## Safety

This mod is trusted local code and can execute with the user's local permissions.
Review the source before installing or modifying it.