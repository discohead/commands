# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is the AI Assistant Ecosystem Commands repository - a collection of Claude Code command templates for managing AI assistant configurations across multiple development tools (Claude Code, Cursor, GitHub Copilot, and OpenAI Codex).

## Critical Patterns

### Command Execution Pattern
All commands follow an XML-based structure that must be preserved:
```xml
<user_request>Command trigger text</user_request>
<task_confirmation>Authorization to proceed</task_confirmation>
<system_role>AI persona definition</system_role>
<immediate_action>Start immediately with specific action</immediate_action>
<phase id="N">Structured execution steps</phase>
```

### Four-Layer Architecture
Always maintain awareness of the four layers when creating or modifying commands:
1. **Knowledge Layer** (CLAUDE.md) - Comprehensive context
2. **Behavioral Layer** (.cursor/rules/) - Active guidance rules  
3. **Persistent Layer** (.github/copilot-instructions.md) - Persistent patterns
4. **Delegation Layer** (AGENTS.md) - Cloud execution definitions

### Output Specifications
Always use explicit output artifacts:
```xml
<output_artifact>
<file_path>exact/path/to/file.md</file_path>
<format>Precise expected structure</format>
</output_artifact>
```

## Common Operations

### Adding a New Command
1. Choose appropriate directory (ai-setup/, ai-maintenance/, or workflows/)
2. Follow naming convention: `[target]-[action].md`
3. Use standard XML structure
4. Include concrete examples and thinking prompts
5. Update README.md with command documentation

### Testing Commands
1. Copy `<user_request>` content
2. Execute in test repository
3. Verify all phases complete
4. Check output artifacts
5. Validate generated content quality

### Modifying Existing Commands
1. Preserve XML structure
2. Maintain backward compatibility
3. Test with existing outputs
4. Update documentation if needed

## Key Files
- `README.md` - Comprehensive user guide and philosophy
- `workflows/ai-ecosystem-setup.md` - Complete setup orchestration
- `workflows/ai-ecosystem-maintenance.md` - Maintenance orchestration
- `ai-ecosystem-check.md` - Configuration validation utility
- `deepwiki-reflection.md` - DeepWiki integration guide

## Architecture Within This Repository
```
commands/
├── ai-setup/          # Initial configuration generators
├── ai-maintenance/    # Update and sync commands
├── workflows/         # Multi-command orchestrations
└── .claude/context/           # Generated context documentation
```

## Command Development Guidelines

### Required Elements
Every command must include:
- Clear `<user_request>` trigger
- `<immediate_action>` for proactive execution
- Concrete examples (no placeholders)
- Output specifications with exact paths
- Thinking prompts for quality analysis

### Phase Design
- Number phases sequentially
- One clear objective per phase
- Include validation steps
- Specify outputs explicitly

### Integration Points
- Reference prerequisite files with `<prerequisite_reading>`
- Include DeepWiki integration where valuable
- Chain commands through workflows
- Maintain cross-references

## Quick Commands
```bash
# Test a command in current directory
# Copy the <user_request> content and paste into Claude Code

# Check all commands are present
ls -la ai-setup/ ai-maintenance/ workflows/

# Find commands by pattern
grep -r "pattern" --include="*.md" .
```

## Recent Evolution
- Added Codex/AGENTS.md as fourth layer
- Integrated DeepWiki MCP for external validation
- Enhanced maintenance workflows
- Added cloud delegation capabilities

## Performance Considerations
- Commands may take 20-60 minutes for full analysis
- Large codebases benefit from phased execution
- Use targeted maintenance vs. full regeneration
- Consider caching DeepWiki responses

## Error Prevention
- Always test commands in isolated environments first
- Verify prerequisites before execution
- Check for existing configurations
- Validate outputs match specifications

## Links to Extended Documentation
- Patterns: `/.claude/context/discovered-patterns.md`
- Architecture: `/.claude/context/architecture/system-design.md`
- Workflows: `/.claude/context/workflows/`
- Technology guides: `/.claude/context/technologies/`