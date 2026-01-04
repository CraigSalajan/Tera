# Tera User Guide

A modern, cross-platform terminal emulator with integrated AI assistance.

![Platforms](https://img.shields.io/badge/platforms-Windows%20%7C%20macOS%20%7C%20Linux-blue)

## Table of Contents

- [Installation](#installation)
- [Quick Start](#quick-start)
- [Features](#features)
- [Keyboard Shortcuts](#keyboard-shortcuts)
- [AI Modes](#ai-modes)
- [Configuration](#configuration)
- [Troubleshooting](#troubleshooting)
- [Getting Help](#getting-help)

## Installation

### Windows

1. Download `tera-x.x.x-windows-x64.zip` from the [Releases](../../releases) page
2. Extract the ZIP file to a location of your choice (e.g., `C:\Program Files\Tera`)
3. (Optional) Add the folder to your system PATH for command-line access
4. Run `tera.exe`

### macOS

**Intel Macs:**
```bash
# Download and extract
curl -LO https://github.com/YOURORG/tera-releases/releases/latest/download/tera-x.x.x-macos-x64.tar.gz
tar -xzf tera-x.x.x-macos-x64.tar.gz

# Move to Applications (optional)
sudo mv tera /Applications/

# Run
tera
```

**Apple Silicon (M1/M2/M3):**
```bash
# Download and extract
curl -LO https://github.com/YOURORG/tera-releases/releases/latest/download/tera-x.x.x-macos-arm64.tar.gz
tar -xzf tera-x.x.x-macos-arm64.tar.gz

# Move to Applications (optional)
sudo mv tera /Applications/

# Run
tera
```

> **Note:** On first run, macOS may show a security warning. Go to **System Preferences > Security & Privacy > General** and click "Open Anyway".

### Linux

```bash
# Download and extract
curl -LO https://github.com/YOURORG/tera-releases/releases/latest/download/tera-x.x.x-linux-x64.tar.gz
tar -xzf tera-x.x.x-linux-x64.tar.gz

# Move to bin (optional)
sudo mv tera /usr/local/bin/

# Run
tera
```

## Quick Start

1. **Launch Tera** - Run the `tera` executable
2. **Use the terminal** - Start typing commands as you would in any terminal
3. **Access AI features** - Press `Shift+Tab` to cycle through AI modes
4. **Get help** - Press `Ctrl+P` to open the command palette

## Features

### Terminal Emulation

Tera provides a full-featured terminal experience:

- **256 colors and true color (RGB) support**
- **Scrollback buffer** - 10,000 lines by default
- **Multiple shells** - Works with PowerShell, Bash, Zsh, Fish, and more
- **Unicode support** - Full emoji and international character support
- **Shell integration** - Automatic working directory tracking

### AI Integration

Tera includes a powerful AI assistant powered by Claude:

- **Chat mode** - Have conversations and get explanations
- **Agent mode** - Let AI execute commands with your approval
- **Plan mode** - Get implementation plans before making changes
- **Permission system** - Full control over what AI can do

### Modern Interface

- **Dark theme** - Easy on the eyes with a VS Code-inspired color scheme
- **Command palette** - Quick access to all features
- **Session management** - Multiple AI sessions for different projects

## Keyboard Shortcuts

### Navigation

| Shortcut | Action |
|----------|--------|
| `Shift+Tab` | Cycle AI modes (Terminal > Chat > Agent > Plan) |
| `Ctrl+;` | Toggle focus between terminal and AI panel |
| `Ctrl+[` / `Ctrl+]` | Switch between AI sessions |
| `Ctrl+P` | Open command palette |

### Editing

| Shortcut | Action |
|----------|--------|
| `Ctrl+Shift+C` | Copy selected text |
| `Ctrl+Shift+V` | Paste from clipboard |

### AI Panel (when focused)

| Shortcut | Action |
|----------|--------|
| `Enter` | Send message to AI |
| `Shift+Enter` | New line in message |
| `Escape` | Return to Terminal mode |

## AI Modes

### Terminal Mode

The default mode. The AI panel is hidden, and all keyboard input goes directly to your shell. This is your regular terminal experience.

### Chat Mode

Talk to the AI assistant without giving it the ability to run commands. Perfect for:

- Asking questions about code
- Getting explanations of concepts
- Brainstorming ideas
- Learning new technologies

### Agent Mode

The AI can execute tools and commands, but **always asks for your permission first**. When AI wants to run a command or modify a file, you'll see a permission prompt with options:

- **Allow Once** - Approve this specific action only
- **Allow for Session** - Auto-approve this type of action until you close Tera
- **Allow Permanently** - Always auto-approve this type of action
- **Deny** - Reject the action

This mode is great for:

- Automating repetitive tasks
- Getting help with file operations
- Debugging with AI assistance

### Plan Mode

The AI creates detailed plans for what it would do, without actually executing anything. Use this to:

- Preview changes before committing
- Understand AI's approach to a problem
- Review implementation strategies

## Configuration

Tera stores configuration files in platform-specific locations:

| Platform | Location |
|----------|----------|
| Windows | `%APPDATA%\tera\Tera\config.toml` |
| macOS | `~/Library/Application Support/com.tera.Tera/config.toml` |
| Linux | `~/.config/tera/config.toml` |

### Example Configuration

```toml
[terminal]
# Font settings
font_family = "JetBrains Mono"
font_size = 14.0

# Scrollback history (number of lines)
scrollback_lines = 10000

# Override default shell (optional)
# shell = "pwsh.exe"      # Windows
# shell = "/bin/zsh"      # macOS/Linux

[ai]
# Default AI provider
default_provider = "anthropic"

[ai.anthropic]
# Model to use
model = "claude-sonnet-4-20250514"

# API key (or use ANTHROPIC_API_KEY environment variable)
# api_key = "sk-ant-..."

[keybindings]
# Customize keyboard shortcuts
ai_panel = "Ctrl+K"
explain_selection = "Ctrl+Shift+E"
new_tab = "Ctrl+T"
close_tab = "Ctrl+W"
copy = "Ctrl+Shift+C"
paste = "Ctrl+Shift+V"
```

### Setting Up AI Features

To use AI features, you need either:

1. **Claude CLI** (recommended): Install via npm:
   ```bash
   npm install -g @anthropic-ai/claude-code
   ```
   Then authenticate with your Anthropic account.

2. **API Key**: Set the `ANTHROPIC_API_KEY` environment variable or add it to your config file.

## Troubleshooting

### Common Issues

#### "Command not found" when running tera

Make sure the Tera executable is in your system PATH, or run it using the full path.

#### AI features not working

1. Check that you have Claude CLI installed: `claude --version`
2. Verify you're authenticated: `claude auth status`
3. Check your API key is set if using direct API access

#### Window appears blank on Linux

Install required dependencies:
```bash
# Ubuntu/Debian
sudo apt-get install libxkbcommon-dev libwayland-dev

# Fedora
sudo dnf install libxkbcommon-devel wayland-devel
```

#### macOS security warning

On first launch, macOS may block the app. Go to:
**System Preferences > Security & Privacy > General** and click "Open Anyway"

#### Slow performance

1. Reduce scrollback buffer size in config
2. Close unused AI sessions
3. Make sure you're running the release build (not debug)

### Log Files

Tera writes logs that can help diagnose issues:

| Platform | Location |
|----------|----------|
| Windows | `%APPDATA%\tera\Tera\logs\` |
| macOS | `~/Library/Application Support/com.tera.Tera/logs/` |
| Linux | `~/.local/share/tera/logs/` |

To enable debug logging, set the environment variable:
```bash
RUST_LOG=debug tera
```

## Getting Help

### Reporting Issues

Found a bug or have a feature request? Please open an issue on our [GitHub Issues](../../issues) page.

When reporting a bug, please include:

1. Your operating system and version
2. Tera version (shown in the command palette)
3. Steps to reproduce the issue
4. Any error messages from the log files

### Feature Requests

We welcome feature requests! Please search existing issues first to avoid duplicates, then open a new issue describing:

1. The feature you'd like to see
2. Why it would be useful
3. Any implementation ideas you have

---

**Tera** - A smarter terminal for a smarter workflow.
