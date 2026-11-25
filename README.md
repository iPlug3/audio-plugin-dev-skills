# Audio Plugin Dev Skills

<!-- yarkr:badges:start -->
[![Indexed on Yarkr](https://api.yarkr.com/functions/v1/api/api/v1/badges/repos/iPlug3/audio-plugin-dev-skills/version.svg)](https://yarkr.com/arks/iplug3/audio-plugin-dev-skills)
<!-- yarkr:badges:end -->

A [Claude Code](https://docs.anthropic.com/en/docs/claude-code) plugin marketplace that provides skills for validating audio plugins across formats (VST3, AudioUnit, CLAP). Once installed, you can ask Claude to validate your plugins or use the slash commands directly in Claude Code.

## Installation

In Claude Code, run:

```
/plugin marketplace add iPlug3/audio-plugin-dev-skills
/plugin install audio-plugin-validators@audio-plugin-dev-skills
```

<!-- yarkr:install:start -->
## Install with Yarkr

This repo is indexed on [Yarkr](https://yarkr.com/arks/iplug3/audio-plugin-dev-skills) as the ark [iplug3/audio-plugin-dev-skills](https://yarkr.com/arks/iplug3/audio-plugin-dev-skills), so its skills install into Claude Code, Codex, Cursor and other agent harnesses with one command.

### CLI

Install the whole ark, which Yarkr keeps equal to this repo:

```bash
npx yarkr-cli sync iplug3/audio-plugin-dev-skills
```

Or add individual skills:

```bash
npx yarkr-cli add skill:iplug3/audio-plugin-dev-skills/check-codesign
npx yarkr-cli add skill:iplug3/audio-plugin-dev-skills/validate-audiounit
npx yarkr-cli add skill:iplug3/audio-plugin-dev-skills/validate-clap
```

No Node.js? `curl -fsSL https://yarkr.com/install.sh | sh` (macOS, Linux) or `irm https://yarkr.com/install.ps1 | iex` (Windows PowerShell) installs `yarkr` as a standalone binary; then type `yarkr` in place of `npx yarkr-cli`.

### MCP

Connect your agent to the ark over MCP:

```bash
npx yarkr-cli mcp add iplug3/audio-plugin-dev-skills
```

Or point any MCP client at `https://api.yarkr.com/functions/v1/api/mcp/o/iplug3/audio-plugin-dev-skills`.
<!-- yarkr:install:end -->

## Skills

### audio-plugin-validators

Validate VST3, AudioUnit, and CLAP plugins using official and third-party CLI tools.

| Skill | Description |
|-------|-------------|
| `validate-audiounit` | Validate AudioUnit v2/v3 plugins with `auval` |
| `validate-vst3` | Validate VST3 plugins with Steinberg's validator |
| `validate-clap` | Validate CLAP plugins with `clap-validator` |
| `validate-pluginval` | Validate VST3/AU plugins with pluginval |
| `validate-vst3-editorhost` | Test VST3 UI with EditorHost |
| `check-codesign` | Check macOS code signature, hardened runtime, entitlements, and notarization |

You can invoke these as slash commands (e.g. `/audio-plugin-validators:validate-vst3`) or just ask Claude to "validate my VST3 plugin" and it will use the appropriate skill.

### Requirements

- **auval**: Included with macOS
- **VST3 validator**: Build from [VST3 SDK](https://github.com/steinbergmedia/vst3sdk) or use pre-built
- **clap-validator**: [Download](https://github.com/free-audio/clap-validator/releases) or build with Cargo
- **pluginval**: [Download](https://github.com/Tracktion/pluginval/releases)

## License

Copyright (c) 2026 Oli Larkin

MIT
