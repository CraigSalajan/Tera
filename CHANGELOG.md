# Changelog

All notable changes to Tera will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [0.0.3] - 2025-01-04

### Added
- **Auto-update system**: Tera can now check for and install updates automatically
  - Checks for updates on startup and periodically (configurable)
  - "Check For Updates" command in Ctrl+P palette
  - Update notification dialog with options to update, dismiss, or skip version
  - Uses GitHub releases as the update source
- Update configuration options in config file:
  - `check_on_startup`: Enable/disable automatic update checks (default: true)
  - `check_interval_hours`: How often to check while running (default: 24)

### Changed
- Release asset naming now uses Rust target triples for cross-platform update compatibility

## [0.0.2] - 2025-01-03

### Added
- Initial public release
- Cross-platform terminal emulator (Windows, macOS, Linux)
- AI integration with Claude (Chat, Agent, Plan modes)
- Permission system for AI tool execution
- Command palette for quick access to features
- Multiple AI session support
- 256-color and true color (RGB) support
- Unicode and emoji support
- Configurable keybindings
- Shell integration with automatic working directory tracking

### Requirements
- Claude CLI (`npm install -g @anthropic-ai/claude-code`) for AI features
- Or `ANTHROPIC_API_KEY` environment variable for direct API access
