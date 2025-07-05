# Codebase Map

## Project Structure Overview

This repository contains Claude Code command templates for managing AI assistant configurations across multiple development tools. It's a meta-repository that provides commands to generate and maintain AI context files in other repositories. The codebase follows a command-driven architecture where each markdown file represents an executable command within the Claude Code environment.

## Directory Hierarchy
```
~/..claude/context/commands/
├── ai-setup/                    # Initial AI configuration generation commands
│   ├── agents.md               # Generate AGENTS.md for OpenAI Codex
│   ├── context.md              # Generate Claude Code context architecture
│   ├── copilot.md              # Generate GitHub Copilot instructions
│   └── cursor.md               # Generate Cursor behavioral rules
├── ai-maintenance/             # Ongoing synchronization and optimization
│   ├── agents-sync.md          # Synchronize AGENTS.md with current patterns
│   ├── context-update.md       # Update Claude context with new patterns
│   ├── instructions-optimize.md # Optimize Copilot instructions
│   └── rules-sync.md           # Synchronize Cursor rules
├── workflows/                  # Multi-step orchestrated processes
│   ├── ai-ecosystem-maintenance.md # Complete maintenance workflow
│   └── ai-ecosystem-setup.md   # Complete initial setup workflow
├── .claude/context/                     # Generated context documentation (this directory)
├── ..claude/context/                    # Local Claude settings
│   └── settings.local.json     # User-specific settings
├── ai-ecosystem-check.md       # Global utility to verify all configurations
├── deepwiki-reflection.md      # DeepWiki MCP integration documentation
├── CLAUDE.md                   # Context file for this repository
└── README.md                   # Comprehensive user guide

```

## Key Entry Points
- `workflows/ai-ecosystem-setup.md`: Complete setup process for new projects
- `workflows/ai-ecosystem-maintenance.md`: Full maintenance cycle for existing projects
- `ai-ecosystem-check.md`: Verify all AI configurations are properly set up

## Configuration Files
- `..claude/context/settings.local.json`: Local Claude Code settings
- `.gitignore`: Excludes OS files, IDE configs, and logs

## Documentation Located
- `README.md`: Comprehensive guide explaining the four-layer AI ecosystem
- `CLAUDE.md`: Context for working within this commands repository
- `deepwiki-reflection.md`: Integration guide for DeepWiki MCP
- Individual command files: Self-documenting command templates with embedded instructions