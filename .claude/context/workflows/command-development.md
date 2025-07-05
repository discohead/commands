# Workflow: Developing New AI Ecosystem Commands

## Prerequisites
- Understanding of the four-layer AI architecture
- Familiarity with existing command patterns
- Clear use case for the new command

## Steps

### 1. **Determine Command Category**
Decide where your command belongs:
- `ai-setup/` - For initial configuration generation
- `ai-maintenance/` - For updates to existing configs
- `workflows/` - For multi-step orchestrations
- Root level - For global utilities

### 2. **Create Command File**
Create a new `.md` file following naming conventions:
```bash
# For setup command
touch ai-setup/[target].md

# For maintenance command  
touch ai-maintenance/[target]-[action].md

# For workflow
touch workflows/ai-ecosystem-[action].md
```

### 3. **Define Command Structure**
Start with the standard template:
```xml
<user_request>
Please [describe what the command does]. Execute the [process name] outlined below immediately.
</user_request>

<task_confirmation>
This command is your instruction to actively [action]. You should begin [starting point] immediately and proceed through all phases without waiting for additional input.
</task_confirmation>

<system_role>
You are [expertise description with specific skills and experience].
</system_role>

<task_overview>
[High-level description of what will be accomplished]
</task_overview>

<critical_instructions>
- [Key requirement 1]
- [Key requirement 2]
- [Key requirement 3]
</critical_instructions>

<immediate_action>
Start by [specific first action]. You are actively performing this [task type] now.
</immediate_action>
```

### 4. **Design Phases**
Break complex operations into phases:
```xml
<phase id="1" name="Descriptive Phase Name">
<objective>Clear objective statement</objective>

<steps>
1. Specific action with example
2. Another concrete action
3. Validation or check
</steps>

<thinking_prompt>
Questions to ensure quality:
- What patterns are emerging?
- Are there edge cases to consider?
- How does this relate to the bigger picture?
</thinking_prompt>

<output_artifact>
<file_path>path/to/output.md</file_path>
<format>
# Expected document structure
</format>
</output_artifact>
</phase>
```

### 5. **Add Integration Points**
Include references to other commands/systems:
```xml
<prerequisite_reading>
Before proceeding, read:
1. `.claude/context/discovered-patterns.md` - For existing patterns
2. `CLAUDE.md` - For project context
</prerequisite_reading>

<deepwiki_integration>
If DeepWiki MCP is available:
@deepwiki ask_question "github.com/org/repo" "[relevant question]"
</deepwiki_integration>
```

### 6. **Test Command**
Test in a sample repository:
1. Copy the `<user_request>` content
2. Execute in Claude Code
3. Verify all phases complete successfully
4. Check output artifacts are created correctly
5. Validate generated content quality

### 7. **Document in README**
Add your command to the appropriate section:
```markdown
### `/your-command` - Brief Description

[Detailed description of what the command does]

**When to use**: 
- [Use case 1]
- [Use case 2]

**What it creates**:
- `path/to/output1` - [description]
- `path/to/output2` - [description]

**Dependencies**: [Any prerequisites]
```

### 8. **Consider Workflow Integration**
If your command should be part of a workflow:
- Add to existing workflow files
- Create new workflow if needed
- Ensure proper phase ordering

## Common Patterns to Follow

### Self-Contained Execution
Every command must be executable standalone:
```xml
<immediate_action>
Start this analysis by [action]. You are actively performing this now.
</immediate_action>
```

### Concrete Examples
Always include real examples:
```xml
<example>
<pattern_name>Repository Pattern</pattern_name>
<code_example>
```javascript
// Actual code example
class UserRepository extends BaseRepository {
  // Implementation
}
```
</code_example>
<rationale>Why this pattern is used</rationale>
</example>
```

### Output Specifications
Be explicit about outputs:
```xml
<output_artifact>
<file_path>exact/path/to/file.md</file_path>
<format>
# Precise structure expected
## With sections defined
</format>
</output_artifact>
```

## Testing Requirements

### Validation Checklist
- [ ] Command executes without errors
- [ ] All phases complete successfully
- [ ] Output files are created in specified locations
- [ ] Generated content follows specified formats
- [ ] Cross-references to other files are valid
- [ ] Command is idempotent (can run multiple times)

### Edge Cases to Test
- Empty repositories
- Missing prerequisites  
- Large codebases
- Different project types
- Partial execution recovery

## Common Pitfalls

### Avoid Abstract Instructions
❌ Bad: "Analyze the codebase for patterns"
✅ Good: "Search for class files that extend BaseRepository using: `find . -name '*.js' -exec grep -l 'extends BaseRepository' {} \;`"

### Missing Output Specifications
❌ Bad: "Create documentation"
✅ Good: Specify exact path and format with `<output_artifact>` tags

### Unclear Phase Objectives
❌ Bad: "Process the files"
✅ Good: "Extract naming conventions from all component files to identify patterns"

### No Thinking Prompts
❌ Bad: Just list steps
✅ Good: Include `<thinking_prompt>` to ensure deep analysis

## Maintenance

### Version Control
- Commit message should explain command purpose
- Document breaking changes
- Tag releases for command sets

### Updates
When updating commands:
1. Preserve backward compatibility
2. Test with existing outputs
3. Update README documentation
4. Consider impact on workflows

### Deprecation
If deprecating a command:
1. Add deprecation notice to command
2. Update README with migration path
3. Keep command for transition period
4. Update workflows to use new command