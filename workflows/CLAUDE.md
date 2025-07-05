# Workflows Context

This file contains specific context for working with AI ecosystem workflows. For project-wide context, see the root CLAUDE.md.

## Component Overview
The workflows directory contains multi-step orchestration commands that coordinate multiple individual commands to achieve complex goals. These workflows ensure proper sequencing, dependency management, and comprehensive configuration across all four layers of the AI ecosystem.

## Architecture Within This Component
```
workflows/
├── ai-ecosystem-setup.md       # Complete initial setup orchestration
└── ai-ecosystem-maintenance.md # Full maintenance cycle orchestration
```

## Key Files
- `ai-ecosystem-setup.md` - Orchestrates all setup commands for new projects
- `ai-ecosystem-maintenance.md` - Coordinates all maintenance commands for updates

## Local Patterns and Conventions

### Workflow Orchestration Pattern
Workflows coordinate multiple commands:
```xml
<phase id="1" name="Generate Claude Code Context">
<command_trigger>/context</command_trigger>
<wait_for_completion>Yes</wait_for_completion>
<expected_duration>20-30 minutes</expected_duration>
</phase>

<phase id="2" name="Create Cursor Rules">
<command_trigger>/cursor</command_trigger>
<dependencies>Requires Phase 1 completion</dependencies>
</phase>
```

### Progressive Enhancement
Each phase builds on previous:
```xml
<workflow_progression>
1. Knowledge Discovery (context)
2. Behavioral Rules (cursor)
3. Persistent Patterns (copilot)
4. Cloud Delegation (agents)
</workflow_progression>
```

### Validation Checkpoints
Workflows include verification:
```xml
<validation_checkpoint>
<check>Verify CLAUDE.md exists and is populated</check>
<check>Confirm .claude/context/ directory has patterns</check>
<on_failure>Stop and report missing prerequisites</on_failure>
</validation_checkpoint>
```

## Common Operations

### Creating a New Workflow
1. Identify the multi-step process needed
2. Map out command dependencies
3. Create workflow file with clear phases
4. Include timing estimates
5. Add validation checkpoints
6. Test end-to-end execution

### Modifying Workflows
When updating orchestration:
1. Maintain phase dependencies
2. Update timing estimates
3. Preserve validation checks
4. Test partial execution
5. Document changes

## Dependencies and Interactions
- **Orchestrates**: All individual commands
- **Manages**: Execution order and timing
- **Validates**: Inter-command dependencies
- **Reports**: Overall progress and status

## Workflow-Specific Guidelines
- Always include time estimates
- Provide clear phase descriptions
- Include rollback instructions
- Support partial execution
- Add progress indicators

## Execution Patterns
```bash
# Full setup from scratch
/ai-ecosystem-setup

# Complete maintenance cycle
/ai-ecosystem-maintenance

# Resume interrupted workflow
/ai-ecosystem-setup --resume-from-phase-3
```

## Workflow Design Principles

### Atomicity
Each phase should:
- Complete fully or fail clearly
- Not leave partial states
- Be resumable if interrupted

### Idempotency
Workflows must:
- Handle re-execution gracefully
- Check for existing work
- Skip completed phases

### Observability
Provide clear:
- Progress indicators
- Time estimates
- Success/failure status
- Next steps guidance

## Error Handling
```xml
<error_handling>
<on_phase_failure>
- Report which phase failed
- Explain the error
- Suggest fixes
- Allow resume from failure point
</on_phase_failure>
</error_handling>
```

## Recent Changes and Evolution
- Added resumability for long workflows
- Improved progress reporting
- Enhanced dependency validation
- Added partial execution support

## Links to Related Documentation
- Setup Commands: `/ai-setup/CLAUDE.md`
- Maintenance Commands: `/ai-maintenance/CLAUDE.md`
- Usage Guide: `/.claude/context/workflows/ai-ecosystem-usage.md`
- Architecture: `/.claude/context/architecture/system-design.md#workflow-layer`