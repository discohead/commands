# Claude Code Context Map

## Quick Reference

### For Command Users
- **Need to set up AI ecosystem?** Start with `workflows/ai-ecosystem-setup.md`
- **Updating existing configs?** Use `workflows/ai-ecosystem-maintenance.md`
- **Just checking status?** Run `ai-ecosystem-check.md`
- **Setting up one tool?** See individual commands in `ai-setup/`

### For Command Developers
- **Creating new command?** Follow `.claude/context/workflows/command-development.md`
- **Understanding patterns?** Read `.claude/context/discovered-patterns.md`
- **System architecture?** See `.claude/context/architecture/system-design.md`
- **Testing commands?** Check testing section in command workflow

## File Directory

### Core Documentation
| File | Purpose | When to Use |
|------|---------|-------------|
| CLAUDE.md | Core patterns & conventions | Always loaded by Claude Code |
| README.md | User guide & philosophy | Understanding the ecosystem |
| deepwiki-reflection.md | DeepWiki integration | Setting up external validation |

### Command Files
| Directory | Purpose | Key Commands |
|-----------|---------|--------------|
| ai-setup/ | Initial generation | context.md, cursor.md, copilot.md, agents.md |
| ai-maintenance/ | Updates & sync | context-update.md, rules-sync.md, agents-sync.md |
| workflows/ | Multi-step processes | ai-ecosystem-setup.md, ai-ecosystem-maintenance.md |

### Generated Context (.claude/context/)
| File | Purpose | Content |
|------|---------|---------|
| codebase-map.md | Repository structure | Directory layout and key files |
| discovered-patterns.md | Command patterns | XML structure, naming, execution |
| architecture/system-design.md | System architecture | Layers, flow, principles |
| technologies/claude-code.md | Claude Code usage | Configuration and patterns |
| technologies/deepwiki-mcp.md | DeepWiki integration | Usage and best practices |
| workflows/command-development.md | Creating commands | Step-by-step guide |
| workflows/ai-ecosystem-usage.md | Using commands | Workflows and best practices |
| context-map.md | This file | Navigation and maintenance |

### Claude Code Commands (..claude/context/commands/)
| Command | Purpose |
|---------|---------|
| validate-ecosystem.md | Validate all AI configurations |
| generate-command.md | Create new command from template |

## Understanding the Architecture

### Command Flow
```
User Request → Command File → XML Parsing → Phased Execution → Output Artifacts
```

### Layer Relationships
```
Knowledge (CLAUDE.md) → Behavioral (Cursor) → Persistent (Copilot) → Delegation (Codex)
```

### File Dependencies
```
context.md generates → patterns/architecture/workflows
cursor.md reads → patterns to create rules
copilot.md reads → patterns + rules to create instructions
agents.md reads → all layers to create delegations
```

## Maintenance Guide

### Adding New Commands
1. Create command file in appropriate directory
2. Follow XML structure from `discovered-patterns.md`
3. Test thoroughly
4. Update README.md
5. Add to relevant workflows

### Updating Documentation
- **Patterns change**: Update `discovered-patterns.md`
- **New workflows**: Add to `workflows/` directory
- **Architecture evolves**: Update `system-design.md`
- **New integrations**: Add to `technologies/`

### Version Control
```bash
# Track all changes
git add .
git commit -m "feat: Add new command for X"

# Tag releases
git tag -a v1.0.0 -m "Initial command set"
```

## Navigation Tips

### By Task
- **Setup**: Start with workflows, then individual setup commands
- **Maintenance**: Use maintenance commands or full workflow
- **Development**: Read patterns and architecture first
- **Troubleshooting**: Check workflows for common issues

### By Experience Level
- **New users**: README → workflows → individual commands
- **Developers**: patterns → architecture → command development
- **Advanced**: Direct command modification with pattern knowledge

## Deprecated Patterns
None currently - all patterns are active

## Future Enhancements
- Additional MCP integrations beyond DeepWiki
- Command composition syntax
- Automated testing framework
- Performance profiling for commands

## Quick Links
- [Main README](../README.md)
- [Command Patterns](discovered-patterns.md)
- [System Architecture](architecture/system-design.md)
- [Command Development](workflows/command-development.md)