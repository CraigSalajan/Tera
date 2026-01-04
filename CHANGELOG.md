# Changelog

All notable changes to Tera will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

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
