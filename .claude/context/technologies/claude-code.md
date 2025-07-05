# Claude Code Technology Usage

## Overview
Claude Code serves as the execution environment for all commands in this repository. It interprets markdown files as executable commands through its command system.

## Configuration

### Command File Location
- **Default Path**: `~/..claude/context/commands/`
- **Discovery**: Claude Code automatically discovers `.md` files in this directory
- **Execution**: Commands are triggered by their file path (e.g., `/context`)

### Settings Configuration
```json
// ..claude/context/settings.local.json
{
  // User-specific Claude Code settings
}
```

## Usage Patterns

### Command Execution Pattern
Commands are executed by referencing their path relative to the commands directory:
- `/context` → executes `ai-setup/context.md`
- `/ai-ecosystem-setup` → executes `workflows/ai-ecosystem-setup.md`

### XML Tag Interpretation
Claude Code interprets specific XML-like tags within markdown:
- `<user_request>` - Command trigger text
- `<task_confirmation>` - Execution acknowledgment
- `<system_role>` - AI persona configuration
- `<phase>` - Structured execution steps

### File Operations
Commands heavily utilize Claude Code's file operation capabilities:
```bash
# Reading files for analysis
find . -type f -name "*.js" -o -name "*.ts"

# Creating configuration files
# Outputs to specified paths in <output_artifact> tags
```

### Context Management
Claude Code loads and maintains context from:
1. Root `CLAUDE.md` file
2. Generated `.claude/context/` directory contents
3. Command-specific context in XML tags

## Command Patterns

### Self-Contained Execution
Each command includes everything needed for execution:
```xml
<immediate_action>
Start by reading CLAUDE.md and proceed immediately...
</immediate_action>
```

### Multi-Phase Operations
Complex commands use phased execution:
```xml
<phase id="1" name="Discovery">
  <!-- Phase 1 operations -->
</phase>
<phase id="2" name="Analysis">
  <!-- Phase 2 operations -->
</phase>
```

### Output Artifacts
Commands specify exact outputs:
```xml
<output_artifact>
<file_path>.claude/context/architecture/system-design.md</file_path>
<format>
# Document structure template
</format>
</output_artifact>
```

## Integration Points

### DeepWiki MCP
Optional integration for external perspective:
```
@deepwiki read_wiki_structure "github.com/org/repo"
@deepwiki ask_question "github.com/org/repo" "question"
```

### File System
- Read operations for codebase analysis
- Write operations for configuration generation
- Directory creation for organized output

### External Tools
Commands can reference external tools:
- Git operations
- Build tools
- Testing frameworks

## Best Practices

### Command Design
1. Include complete context in each command
2. Use phases for complex operations
3. Specify exact output formats
4. Include thinking prompts for quality

### Error Handling
Commands include validation steps:
```xml
<prerequisite_check>
- Verify CLAUDE.md exists
- Check for required dependencies
- Validate previous command outputs
</prerequisite_check>
```

### Performance Optimization
- Batch file operations when possible
- Use targeted searches vs. full scans
- Cache discovered patterns for reuse

## Limitations and Workarounds

### Context Window Management
- Large codebases may exceed context limits
- Solution: Phased analysis with intermediate outputs

### Async Operations
- Commands execute synchronously
- Solution: Break into smaller, sequential commands

### State Management
- No built-in state between executions
- Solution: Use file system for persistence

## Command Development Guidelines

### Testing Commands
1. Test in isolated directories first
2. Verify output formats match specifications
3. Check for idempotency

### Debugging
- Use explicit output messages in phases
- Include validation checkpoints
- Log discovered patterns for verification

### Versioning
- Commands are versioned with the repository
- Changes should maintain backward compatibility
- Document breaking changes in commit messages