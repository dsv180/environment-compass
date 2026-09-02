# @letta-ai/environment-compass (Windows & Cloud Adaptation)
A mod for Letta Code that gives the agent an understanding of the environment it runs in. The mod is passive: it does not modify the system, but only reads its state and provides this data to the agent for decision-making.
[Russian version](README.md)

## What's changed vs upstream
This fork adapts the original `environment-compass` mod for robust dual use in **local backend** (specifically optimized for Windows environments) and **cloud** agent modes.
### Key Improvements
#### 1. Universal Memory Directory Resolution (`resolveMemoryDir`)
The original mod only checked the cloud agent path, causing it to fail for local backend agents. This fork resolves this by dynamically checking both paths:
- `~/.letta/lc-local-backend/memfs/<agentId>/memory` — **Local backend**
- `~/.letta/agents/<agentId>/memory` — **Cloud agent**
#### 2. Windows Environment Fixes
Added comprehensive cross-platform support for Windows local installations:
- **OS Detection:** Accurate environment detection via `process.platform === "win32"`.
- **Executable Search:** PATHEXT-aware executable resolution (correctly finds `letta.cmd`, `letta.exe`, `letta.ps1`).
- **Package Path Resolution:** Correctly resolves the local installation path via `%LOCALAPPDATA%\Programs\letta-code\`.
- **File Permissions:** Fixed executable checks to use `F_OK` instead of `X_OK` (which fails on Windows).
## Installation
Install locally:
```bash
letta install .
```
Run `/reload` in your active Letta sessions for the changes to take effect.
## Origin & Attribution
This mod is an adaptation of the community-developed **Environment Compass**, originally demonstrated as part of the **Letta Mod Challenge** (Letta Office Hours). This fork adapts it for cross-platform use across **Windows (local backend)** and **Cloud** environments.
## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.