# DeepWiki MCP Technology Usage

## Overview
DeepWiki MCP (Model Context Protocol) provides external documentation and analysis capabilities for repositories. It serves as an unbiased third-party perspective on codebases, helping validate internally discovered patterns.

## Configuration

### Prerequisites
- DeepWiki MCP must be configured in Claude Desktop
- Repository must be indexed in DeepWiki (typically public GitHub repos)
- MCP tools must be available in the Claude Code session

### Tool Availability Check
Commands that use DeepWiki include optional sections:
```xml
<deepwiki_baseline>
Before diving into detailed analysis, use DeepWiki MCP tools...
Note: This requires DeepWiki MCP to be configured
</deepwiki_baseline>
```

## Usage Patterns

### Repository Structure Discovery
```bash
@deepwiki read_wiki_structure "github.com/org/repo"
```
Returns:
- Main components as understood externally
- Documentation structure
- Key topics and sections

### Content Reading
```bash
@deepwiki read_wiki_contents "github.com/org/repo"
# Can specify sections like "Architecture", "Core Components"
```
Used for:
- Reading architectural documentation
- Understanding design patterns
- Comparing with internal documentation

### Targeted Questions
```bash
@deepwiki ask_question "github.com/org/repo" "What is the overall architecture?"
@deepwiki ask_question "github.com/org/repo" "What patterns are used?"
```

### Cross-Repository Analysis
```bash
@deepwiki ask_question "github.com/org/repo-android" "Compare with iOS version"
```
Enables:
- Cross-platform pattern validation
- Consistency checking across SDK family
- Best practice identification

## Integration Patterns

### Validation Pattern
Used in `ai-setup/context.md`:
```xml
1. Internal discovery (file analysis)
2. DeepWiki validation (external perspective)
3. Gap identification (what we missed)
4. Documentation enhancement
```

### Terminology Alignment
DeepWiki helps identify:
- Industry-standard terminology
- Common architectural patterns
- Naming conventions used externally

### Blind Spot Detection
DeepWiki reveals:
- Implicit assumptions in code
- Undocumented architectural decisions
- Complex areas needing better documentation

## Command Integration Examples

### Context Generation (`ai-setup/context.md`)
Uses DeepWiki for:
- Initial architecture understanding
- Pattern validation
- Documentation gap analysis
- Entry point recommendations

### Cursor Rules (`ai-setup/cursor.md`)
References DeepWiki for:
- Complex architectural questions
- External best practices
- Pattern explanations

### Maintenance Commands
Check DeepWiki for:
- New patterns in updated code
- Architectural evolution
- Community best practices

## Best Practices

### When to Use DeepWiki
1. **Initial Analysis**: Get unbiased overview before deep dive
2. **Pattern Validation**: Confirm discovered patterns are standard
3. **Gap Finding**: Identify missing documentation
4. **Cross-Reference**: Compare with similar projects

### Query Optimization
- Ask specific, focused questions
- Use architectural terminology
- Request comparisons for context
- Seek explanations for complex areas

### Integration Strategy
1. Use as supplement, not replacement
2. Validate findings with code analysis
3. Note discrepancies for investigation
4. Update docs based on insights

## Output Processing

### Analysis Checklist Template
```
□ Architecture components DeepWiki identifies
□ Patterns DeepWiki emphasizes
□ Terminology differences
□ Complexity areas identified
□ Cross-SDK patterns found
□ Recommended entry points
```

### Documentation Updates
Based on DeepWiki findings:
- Add missing architectural docs
- Clarify complex patterns
- Align terminology
- Improve entry points

## Limitations

### Repository Coverage
- Only works with indexed repositories
- May have outdated information
- Coverage varies by repository

### Analysis Depth
- High-level architectural view
- May miss implementation details
- General patterns over specifics

### Availability
- Requires MCP configuration
- Not available in all environments
- Optional component in commands

## Graceful Degradation

Commands handle DeepWiki unavailability:
1. Skip DeepWiki phases if not available
2. Proceed with internal analysis only
3. Note in output that external validation was skipped
4. Still produce complete documentation

## Future Enhancements

Potential improvements:
- Automated DeepWiki availability detection
- Caching of DeepWiki responses
- Diff tracking between analyses
- Integration with more MCP tools