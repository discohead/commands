# Discovered Patterns in AI Ecosystem Commands

## Command Structure Pattern

### XML-Like Tag Structure
All command files follow a consistent XML-like tag structure that enables Claude Code to execute structured workflows:

```xml
<user_request>
[The command trigger that users will type]
</user_request>

<task_confirmation>
[Acknowledgment and authorization to proceed]
</task_confirmation>

<system_role>
[AI persona and expertise definition]
</system_role>

<task_overview>
[High-level mission statement]
</task_overview>

<critical_instructions>
[Key principles and requirements]
</critical_instructions>

<immediate_action>
[Starting instructions to begin immediately]
</immediate_action>

<phase id="X" name="Phase Name">
[Detailed execution steps]
</phase>
```

**Rationale**: This structure provides clear separation of concerns and enables Claude Code to understand command context, requirements, and execution flow systematically.

## Naming Conventions

### File Organization Pattern
```
ai-setup/          # Initial configuration generation
ai-maintenance/    # Ongoing updates and synchronization
workflows/         # Multi-step orchestrated processes
```

**Rationale**: Categories reflect the lifecycle of AI configuration - setup, maintenance, and complex workflows.

### Command File Naming
- Setup commands: `[target].md` (e.g., `context.md`, `cursor.md`)
- Maintenance commands: `[target]-[action].md` (e.g., `context-update.md`, `rules-sync.md`)
- Workflows: `ai-ecosystem-[action].md` (e.g., `ai-ecosystem-setup.md`)

**Rationale**: Clear naming indicates both the target system and the action being performed.

## Execution Flow Patterns

### Phase-Based Execution
Commands are organized into numbered phases with specific objectives:

```xml
<phase id="1" name="Initial Reconnaissance">
<objective>Clear statement of phase goal</objective>
<steps>
1. Concrete action
2. Another action
</steps>
<thinking_prompt>
Reflection questions to guide analysis
</thinking_prompt>
</phase>
```

**Rationale**: Phases provide structure for complex operations and ensure systematic progress through multi-step processes.

### Immediate Action Pattern
Every command includes an `<immediate_action>` tag that instructs Claude to begin execution without waiting:

```xml
<immediate_action>
Start by [specific first action]. You are actively performing this analysis now.
</immediate_action>
```

**Rationale**: This pattern ensures commands execute proactively rather than waiting for additional user input.

## Documentation Patterns

### Output Artifact Pattern
Commands specify exact file paths and formats for generated content:

```xml
<output_artifact>
<file_path>.claude/context/discovered-patterns.md</file_path>
<format>
# Title
## Section
[Content structure]
</format>
</output_artifact>
```

**Rationale**: Explicit output specifications ensure consistent documentation structure across all generated files.

### Cross-Reference Pattern
Commands frequently reference other commands and generated files:

```xml
<prerequisite_reading>
Before proceeding, read and internalize:
1. `.claude/context/discovered-patterns.md` - Coding patterns
2. `.claude/context/architecture/system-design.md` - Architecture
</prerequisite_reading>
```

**Rationale**: This creates a knowledge graph where commands build upon each other's outputs.

## Integration Patterns

### Four-Layer Architecture Reference
All commands understand and reference the four-layer AI ecosystem:

1. **Knowledge Layer** - Claude Code Context (CLAUDE.md)
2. **Behavioral Layer** - Cursor Rules (.cursorrules)
3. **Persistent Layer** - GitHub Copilot Instructions
4. **Delegation Layer** - OpenAI Codex (AGENTS.md)

**Rationale**: This consistent mental model ensures all commands work together cohesively.

### DeepWiki Integration Pattern
Commands that analyze codebases include optional DeepWiki MCP integration:

```xml
<deepwiki_baseline>
Before diving into detailed analysis, use DeepWiki MCP tools...
@deepwiki read_wiki_structure "github.com/org/repo"
</deepwiki_baseline>
```

**Rationale**: External perspective validates internal discoveries and identifies blind spots.

## Quality Control Patterns

### Concrete Examples Requirement
Commands emphasize real examples over abstract descriptions:

```xml
<critical_instructions>
- Always include concrete code examples from the actual repository
- Document the "why" behind patterns, not just the "what"
- Produce working, useful artifacts - no placeholders or templates
</critical_instructions>
```

**Rationale**: Concrete examples ensure generated documentation is immediately actionable.

### Thinking Prompts Pattern
Commands include reflection prompts to ensure deep analysis:

```xml
<thinking_prompt>
Think deeply about the architectural decisions:
- Why this layering approach?
- What problems does it solve?
- How does this compare to standard architectures?
</thinking_prompt>
```

**Rationale**: Prompts prevent superficial analysis and encourage understanding of underlying principles.

## Command Composition Patterns

### Setup → Maintenance Lifecycle
Commands follow a natural progression:
1. `ai-setup/*` commands generate initial configurations
2. `ai-maintenance/*` commands update existing configurations
3. `workflows/*` orchestrate multiple commands

**Rationale**: This lifecycle approach ensures configurations evolve with the codebase.

### Dependency Chain Pattern
Later commands depend on outputs from earlier commands:
- `cursor.md` requires `context.md` outputs
- `copilot.md` requires both context and cursor outputs
- `agents.md` leverages all previous layers

**Rationale**: Dependencies ensure each layer builds upon established patterns rather than duplicating analysis.