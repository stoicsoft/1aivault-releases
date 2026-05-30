# 1AIVault Releases

This repository hosts the release artifacts and update manifests for [1AIVault](https://1aivault.com) — your portable AI vault for memories, skills, and configurations across every AI tool.

## About 1AIVault

**Your memory. Every AI. One vault.**

1AIVault is a local-first desktop app that captures memories, decisions, preferences, and skills once, then makes them available to every AI tool you use via the Model Context Protocol (MCP).

| Feature | Description |
|---------|-------------|
| **Portable Memory Vault** | A single SQLite vault on your machine — no servers, no cloud lock-in |
| **MCP Server** | Built-in MCP server exposes your vault to Claude Desktop, Claude Code, Cursor, Cline, Codex, and any MCP-compatible client |
| **Skills** | Author `.skill.md` files once and load them into any AI tool on demand |
| **Conversation Capture** | Auto-import conversations from Claude Code, Cursor, Cline, Claude Desktop, ChatGPT, Codex, Windsurf |
| **Browser Bridge** | Companion browser extension pipes web-based AI chats straight into the vault |
| **Topic Classification** | Local Ollama-powered classifier groups entries into topics with auto-generated digests |
| **Brain View** | Force-directed graph of how your topics connect across sources |
| **Tier Promotion** | Frequently-used memories surface to long-term tiers automatically |
| **Claude Code Sync** | Push vault entries into per-project `CLAUDE.md` and memory files |

## Auto-Updates

1AIVault includes automatic updates. When a new version is available, you'll be notified within the app and can update with a single click.

The app checks for updates from this repository using [electron-updater](https://www.electron.build/auto-update).

## Release Assets

Each release includes:

```
├── 1AIVault-{version}-mac-arm64.dmg           # macOS Apple Silicon (DMG)
├── 1AIVault-{version}-mac-arm64.dmg.blockmap
├── 1AIVault-{version}-mac-arm64.zip           # macOS Apple Silicon (ZIP, used by autoupdater)
├── 1AIVault-{version}-mac-arm64.zip.blockmap
├── 1AIVault-{version}-mac-x64.dmg             # macOS Intel (DMG)
├── 1AIVault-{version}-mac-x64.dmg.blockmap
├── 1AIVault-{version}-mac-x64.zip             # macOS Intel (ZIP)
├── 1AIVault-{version}-mac-x64.zip.blockmap
├── 1AIVault-Setup-{version}.exe               # Windows Installer (NSIS)
├── 1AIVault-Setup-{version}.exe.blockmap
├── 1AIVault-{version}.exe                     # Windows Portable
├── 1AIVault-{version}.AppImage                # Linux AppImage
├── 1aivault_{version}_amd64.deb               # Linux Debian
├── latest-mac.yml                             # macOS update manifest
├── latest.yml                                 # Windows update manifest
└── latest-linux.yml                           # Linux update manifest
```

## Verifying Downloads

All release artifacts are signed where supported:

- **macOS**: Notarized by Apple and signed with Developer ID
- **Windows**: Code-signed installer
- **Linux**: SHA512 checksums in the YAML manifests

To verify a download, check the SHA512 hash against the corresponding `.yml` manifest file.

## System Requirements

| Platform | Minimum Version |
|----------|-----------------|
| macOS | 11 (Big Sur) or later |
| Windows | Windows 10 or later |
| Linux | Ubuntu 20.04, Debian 11, or equivalent |

**Hardware:**
- 4 GB RAM (8 GB recommended if running local topic-classification models)
- 300 MB disk space, plus room for your vault DB

## Data Locations

1AIVault stores everything locally under `~/.1aivault/`:

```
~/.1aivault/
├── vault.db         # SQLite (WAL mode) — memories, skills, links, topics
├── skills/          # .skill.md files
└── backups/         # Pre-migration DB snapshots (last 7 kept)
```

Nothing leaves your machine unless you opt in to telemetry or crash reporting.

## License

1AIVault is commercial software. See [1aivault.com](https://1aivault.com) for pricing and terms.

## Support

- **Issues**: [GitHub Issues](https://github.com/stoicsoft/1aivault-releases/issues)
- **Email**: hello@stoicsoft.com

## Links

- [Website](https://1aivault.com)

---

Built with care by [StoicSoft](https://stoicsoft.com)
