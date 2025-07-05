# AI Maintenance Commands Context

This file contains specific context for working within the AI maintenance commands. For project-wide context, see the root CLAUDE.md.

## Component Overview
The ai-maintenance directory contains commands for updating and synchronizing existing AI assistant configurations. These commands perform incremental updates based on code changes, ensuring configurations stay current without full regeneration.

## Architecture Within This Component
```
ai-maintenance/
├── context-update.md      # Updates Claude knowledge layer
├── rules-sync.md          # Synchronizes Cursor behavioral rules
├── instructions-optimize.md # Refines Copilot instructions
└── agents-sync.md         # Updates Codex task definitions
```

## Key Files
- `context-update.md` - Discovers new patterns and updates CLAUDE.md
- `rules-sync.md` - Aligns Cursor rules with current patterns
- `instructions-optimize.md` - Streamlines Copilot instructions
- `agents-sync.md` - Refreshes cloud delegation definitions

## Local Patterns and Conventions

### Incremental Update Pattern
Maintenance commands focus on changes:
```xml
<phase id="1" name="Change Detection">
<objective>Identify what has changed since last update</objective>
<steps>
1. Read existing configurations
2. Analyze recent code changes
3. Identify new or modified patterns
</steps>
</phase>
```

### Diff-Based Processing
Commands compare before/after states:
```xml
<change_analysis>
- Check git history for pattern changes
- Compare with existing documentation
- Identify deprecated patterns
- Find new conventions
</change_analysis>
```

### Configuration Preservation
Maintain custom modifications:
```xml
<preservation_rules>
- Keep user customizations
- Merge new patterns without overwriting
- Flag conflicts for review
- Backup before updates
</preservation_rules>
```

## Common Operations

### Running Regular Maintenance
1. Check for existing configurations first
2. Run appropriate update command
3. Review changes before committing
4. Test updated configurations
5. Document any manual adjustments

### Handling Conflicts
When patterns conflict:
1. Flag in output for review
2. Provide both options
3. Suggest resolution based on usage
4. Allow manual override

## Dependencies and Interactions
- **Requires**: Existing configuration files
- **Reads**: Current codebase and configs
- **Updates**: All four layer configurations
- **Preserves**: User customizations

## Component-Specific Guidelines
- Never overwrite without backing up
- Highlight all changes clearly
- Preserve configuration history
- Support rollback if needed
- Minimize disruption to workflows

## Execution Patterns
```bash
# Single layer update
/context-update

# Full maintenance cycle
/ai-ecosystem-maintenance

# Targeted sync after refactor
/rules-sync --after-refactor
```

## Update Strategies

### Light Touch Updates
For minor changes:
- Add new patterns only
- Keep existing rules
- Append new instructions

### Deep Synchronization
For major changes:
- Full pattern re-analysis
- Rule regeneration
- Instruction optimization

### Conflict Resolution
When conflicts arise:
- Document both approaches
- Analyze usage frequency
- Recommend based on context
- Allow user decision

## Recent Changes and Evolution
- Added smart conflict detection
- Improved incremental processing
- Enhanced preservation logic
- Added rollback capabilities

## Links to Related Documentation
- Workflow: `/workflows/ai-ecosystem-maintenance.md`
- Setup: `/ai-setup/CLAUDE.md`
- Patterns: `/.claude/context/discovered-patterns.md#maintenance-patterns`