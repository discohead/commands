# AI Setup Commands Context

This file contains specific context for working within the AI setup commands. For project-wide context, see the root CLAUDE.md.

## Component Overview
The ai-setup directory contains initial configuration generation commands that analyze target repositories and create AI assistant configurations from scratch. These commands perform deep codebase analysis and pattern discovery to establish the foundation for all four layers of the AI ecosystem.

## Architecture Within This Component
```
ai-setup/
├── context.md    # Generates Claude Code knowledge layer
├── cursor.md     # Creates Cursor behavioral rules
├── copilot.md    # Produces Copilot persistent instructions
└── agents.md     # Defines Codex cloud delegation tasks
```

## Key Files
- `context.md` - Comprehensive codebase analysis and Claude context generation
- `cursor.md` - Transforms discovered patterns into active behavioral rules
- `copilot.md` - Distills patterns into persistent coding instructions
- `agents.md` - Creates cloud-based task delegation definitions

## Local Patterns and Conventions

### Phase-Based Discovery
All setup commands use extensive discovery phases:
```xml
<phase id="1" name="Initial Reconnaissance">
<objective>Map the complete codebase structure</objective>
<steps>
1. Execute comprehensive file discovery
2. Analyze directory structure
3. Identify key entry points
</steps>
</phase>
```

### Prerequisite Dependencies
Later commands depend on earlier outputs:
```xml
<prerequisite_reading>
Before proceeding, read and internalize:
1. `.claude/context/discovered-patterns.md`
2. `.claude/context/architecture/system-design.md`
</prerequisite_reading>
```

### DeepWiki Integration
Setup commands can leverage external perspective:
```xml
<deepwiki_baseline>
@deepwiki read_wiki_structure "github.com/org/repo"
@deepwiki ask_question "github.com/org/repo" "architecture"
</deepwiki_baseline>
```

## Common Operations

### Adding a New Setup Command
1. Create `[target].md` file in this directory
2. Include comprehensive discovery phases
3. Define clear output artifacts
4. Consider dependencies on other setup commands
5. Add DeepWiki integration if valuable

### Modifying Discovery Logic
When updating analysis approaches:
1. Preserve phase structure
2. Maintain output compatibility
3. Test with various repository types
4. Update dependent commands if needed

## Dependencies and Interactions
- **Generates**: Configuration files in target repositories
- **Reads**: Target repository source code
- **Creates**: `.claude/context/` directory with discovered knowledge
- **Enables**: All subsequent maintenance commands

## Component-Specific Guidelines
- Setup commands should be idempotent
- Always check for existing configurations
- Discovery should be thorough but not redundant
- Output should be immediately actionable
- Include concrete examples from actual code

## Execution Patterns
```bash
# Individual setup command
/context

# Chained setup (in workflows)
/context && /cursor && /copilot && /agents
```

## Recent Changes and Evolution
- Added AGENTS.md generation for Codex integration
- Enhanced DeepWiki integration for external validation
- Improved pattern discovery algorithms
- Added more comprehensive thinking prompts

## Links to Related Documentation
- Workflow: `/workflows/ai-ecosystem-setup.md`
- Patterns: `/.claude/context/discovered-patterns.md#setup-patterns`
- Architecture: `/.claude/context/architecture/system-design.md#setup-layer`