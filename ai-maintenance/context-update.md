# Update Claude Code Context for Codebase Evolution

<user_request>
Please perform an incremental update of the Claude Code context architecture to reflect how this codebase has evolved since the last documentation generation. Follow the comprehensive process outlined below.
</user_request>

<task_confirmation>
I need you to actively execute this context update task now, not wait for further instructions. This command itself IS the instruction to proceed with the analysis and updates described below.
</task_confirmation>

<system_role>
You are an expert code archaeologist specializing in incremental analysis and documentation evolution. With deep experience in maintaining living documentation systems, you excel at identifying what has changed, what remains valid, and what needs updating. You approach existing documentation with respect, preserving hard-won insights while carefully integrating new discoveries. Think of yourself as a curator who must decide which exhibits to keep, which to update, and which to add to an existing collection.
</system_role>

<task_overview>
Your mission is to incrementally update the Claude Code context architecture to reflect how the codebase has evolved since the last documentation generation. Unlike initial context creation, you must preserve existing valid patterns while identifying and documenting new developments. This requires careful analysis of both the current codebase state and the existing documentation to perform a precise, surgical update.
</task_overview>

<execution_directive>
Begin immediately by analyzing the existing Claude Code documentation to understand the current state. You should start this process now without waiting for additional input.
</execution_directive>

<system_role>
You are an expert code archaeologist specializing in incremental analysis and documentation evolution. With deep experience in maintaining living documentation systems, you excel at identifying what has changed, what remains valid, and what needs updating. You approach existing documentation with respect, preserving hard-won insights while carefully integrating new discoveries. Think of yourself as a curator who must decide which exhibits to keep, which to update, and which to add to an existing collection.
</system_role>

<task_overview>
Your mission is to incrementally update the Claude Code context architecture to reflect how the codebase has evolved since the last documentation generation. Unlike initial context creation, you must preserve existing valid patterns while identifying and documenting new developments. This requires careful analysis of both the current codebase state and the existing documentation to perform a precise, surgical update.
</task_overview>

<critical_principles>
- Preserve valid existing documentation - don't regenerate from scratch
- Focus on areas of significant change rather than re-analyzing everything
- Maintain consistency with established documentation style and structure
- Add new discoveries without disrupting existing organization
- Update examples to reflect current code while keeping historical context where valuable
- Flag deprecated patterns explicitly rather than silently removing them
</critical_principles>

<prerequisite_analysis>
<instruction>
Before beginning updates, you must understand the current documentation state:

1. **Read ALL existing Claude Code context files**:
   - `CLAUDE.md` - Current primary context
   - `.claude/context/codebase-map.md` - Existing structure documentation
   - `.claude/context/discovered-patterns.md` - Previously identified patterns
   - `.claude/context/architecture/*.md` - Current architecture documentation
   - `.claude/context/technologies/*.md` - Technology-specific documentation
   - `.claude/context/workflows/*.md` - Documented workflows

2. **Identify the last update timestamp** (if noted in files)

3. **Build a mental model** of what the documentation currently captures

As you read, note:
- Which sections seem comprehensive and current
- Which sections might be outdated based on file dates
- Any documentation gaps that were acknowledged
- The overall organization structure to maintain
</instruction>
</prerequisite_analysis>

<context_engineering_toolkit>
<phase id="0.5" name="Context Engineering Toolkit Setup">
<objective>Leverage modern tools for efficient incremental analysis</objective>

<toolkit_reminder>
This update process is powered by Claude Code's context engineering toolkit:
- **Fast search**: `rg` (ripgrep), `fd` 
- **Code intelligence**: `ast-grep`, `semgrep`, `comby`
- **Data processing**: `jq`, `yq`, `gron`, `mlr`, `jc`
- **Scripting**: `perl`, `ruby`, `awk`, `python` one-liners

These tools enable surgical context extraction and precise change detection.
</toolkit_reminder>

<efficient_update_commands>
```bash
# Quick change overview
echo "=== Recent changes summary ==="
git log --since="3 months ago" --oneline | wc -l  # Number of commits
git diff --stat HEAD~100 | tail -1                # Lines changed


# Pattern change detection
echo "=== Pattern evolution ==="
for pattern in "class.*extends" "async function" "interface.*{" "type.*="; do
  echo "Pattern: $pattern"
  git diff HEAD~100 | rg "$pattern" | wc -l
done

# Find files needing documentation updates
fd -e md -p ".claude" | xargs -I {} sh -c 'echo "=== {} ==="; git log -1 --format="%ar" -- {}'
```
</efficient_update_commands>

<smart_sampling>
Instead of reading every file, use intelligent sampling:
```bash
# Find most changed files by commit count
git log --since="3 months ago" --pretty=format: --name-only | sort | uniq -c | sort -rg | head -10 | awk '{print $2}' | xargs cat --style=changes

# Find files with most pattern changes
git diff HEAD~100 --name-only | xargs -I {} sh -c 'echo -n "{}: "; git diff HEAD~100 -- {} | rg "^[+-].*\b(class|function|interface|type)\b" | wc -l' | sort -t: -k2 -rn | head -10

```
</smart_sampling>

<update_strategy>
1. Use `rg` and `fd` to quickly identify change hotspots
2. Apply `ast-grep` to detect structural changes
3. Use `comby` to find pattern migrations
4. Process configs with `jq`/`yq` for setting changes
</update_strategy>
</phase>
</context_engineering_toolkit>

<phase id="1" name="Change Detection">
<objective>Identify areas of significant change since last documentation update</objective>

<change_detection_methodology>
1. **Git History Analysis with Modern Tools**:
   ```bash
   # Find most active areas (customize date based on last update)
   git log --since="3 months ago" --pretty=format: --name-only | sort | uniq -c | sort -rg | head -20
   
   # Identify new directories or major additions with fd
   git log --since="3 months ago" --diff-filter=A --pretty=format: --name-only | fd -t f '\.(js|ts|py|java)$' | head -20
   
   # Look for significant refactoring
   git log --since="3 months ago" --grep="refactor" --oneline
   
   # Find changed patterns with ripgrep
   git diff HEAD~100 --name-only | xargs rg -l 'class|function|interface' | sort | uniq
   ```

2. **Structural Comparison with Context Engineering Tools**:
   ```bash
   # Fast directory structure comparison
   tree -d -I 'node_modules|dist|build' -L 3 > current-structure.txt
   
   # Find new file types
   fd -t f | perl -ne 'print "$1\n" if /\.([^.\/]+)$/' | sort | uniq -c | sort -rn
   
   # Detect moved files
   git log --since="3 months ago" --summary --name-status | rg '^R' | head -20
   ```
   - Compare results with documented structure in `codebase-map.md`
   - Note new directories, removed areas, or reorganizations

3. **Pattern Evolution Detection with AST Analysis**:
   ```bash
   # Detect new patterns with AST
   ast-grep --pattern 'class $$ { $$$ }' --json | jq '.matches | length' > current-class-count.txt
   ast-grep --pattern 'async function $$($$$) { $$$ }' --stats
   
   # Find new architectural patterns
   comby -stats 'try { :[body] } catch (:[err]) { :[handler] }' '' .js -d src/
   
   # Semantic pattern analysis
   semgrep --config=auto --metrics=on --json | jq '.metrics.total_matches'
   ```
   - Compare against patterns in `discovered-patterns.md`
   - Look for new patterns or evolution of existing ones

4. **Technology Stack Changes with Smart Analysis**:
   ```bash
   # Dependency changes analysis
   git diff HEAD~100 package.json | rg '^[+-]\s*"' | sort
   
   # New configuration files
   fd -H '^\.' -t f --changed-within 3months | rg '\.(json|yaml|yml|toml|ini)$'
   
   # Framework usage evolution
   rg -t js -t ts --stats 'import .* from ["'\''](react|vue|angular|express|fastify)' | tail -20
   
   # New technology markers
   fd -e dockerfile -e yaml | xargs rg -l '(postgres|mongodb|redis|kafka|rabbitmq)' | sort | uniq
   ```
</change_detection_methodology>

<thinking_prompt>
As you analyze changes, consider:
- Are these changes evolutionary (building on existing patterns) or revolutionary (new approaches)?
- Do changes in one area cascade to affect other documented areas?
- Are there new team members whose code introduces different patterns?
- Has the team's maturity led to more sophisticated patterns?
</thinking_prompt>

<output_artifact>
<file_path>.claude/context/updates/change-analysis-[DATE].md</file_path>
<format>
# Change Analysis Report - [DATE]

## Summary of Changes Since [LAST_UPDATE_DATE]

### High-Activity Areas
1. **[Area Name]**: [Description of changes]
   - Files affected: [count]
   - Nature of changes: [refactoring/new features/bug fixes]
   - Pattern implications: [any pattern changes noted]

### New Additions
- **New Directories**: 
  - `[path]`: [apparent purpose]
- **New Technologies**: 
  - [technology]: [how it's being used]
- **New Patterns**: 
  - [pattern]: [where observed]

### Deprecated/Removed
- [What was removed and why, if evident]

### Areas Requiring Deep Analysis
1. [Area]: [Why it needs investigation]
</format>
</output_artifact>
</phase>

<phase id="2" name="Targeted Pattern Analysis">
<objective>Deep-dive into changed areas to understand pattern evolution</objective>

<analysis_approach>
For each high-change area identified in Phase 1:

1. **Sample Selection**:
   - Choose 3-5 most-modified files
   - Include any new "template" or "example" files
   - Select files with different authors to catch team-wide patterns

2. **Pattern Comparison**:
   - Compare current implementation against documented patterns
   - Note evolution (pattern refined) vs revolution (pattern replaced)
   - Identify entirely new patterns not previously documented

3. **Cross-Reference Analysis**:
   - Check if changed patterns affect other areas
   - Verify architectural boundaries still hold
   - Confirm naming conventions remain consistent
</analysis_approach>

<pattern_evolution_framework>
For each evolved or new pattern, document:

1. **Pattern Lifecycle Stage**:
   - 🌱 Emerging: Seen in <3 places, might be experimental
   - 🌿 Growing: Adopted by multiple developers/features
   - 🌳 Mature: Team-wide adoption, stable pattern
   - 🍂 Deprecated: Being phased out, document migration path

2. **Evolution Context**:
   - What problem does the new/evolved pattern solve?
   - Why did the team move away from the old pattern?
   - Is this a gradual migration or clean break?

3. **Documentation Decision**:
   - Update existing pattern documentation
   - Add new pattern section
   - Mark old pattern as deprecated with migration guide
   - Note both patterns as co-existing during transition
</pattern_evolution_framework>

<example_evolution>
### Example: Error Handling Evolution

**Previously Documented**:
```javascript
try {
  const result = await operation();
  return result;
} catch (error) {
  logger.error(error);
  throw new ApiError(500, 'Operation failed');
}
```

**Evolved Pattern**:
```javascript
try {
  const result = await operation();
  return Result.ok(result);
} catch (error) {
  logger.error('Operation failed', { 
    error, 
    context: { userId, operation: 'operationName' },
    traceId: context.traceId 
  });
  return Result.error(
    new ApiError(500, 'Operation failed', { cause: error })
  );
}
```

**Evolution Notes**:
- Adopted Result type pattern for better error handling
- Enhanced logging with structured context
- Added error causality chain
- Pattern is in "Growing" stage - seen in new code but not yet migrated everywhere
</example_evolution>
</phase>

<phase id="3" name="Architecture Impact Assessment">
<objective>Determine if architectural changes require documentation updates</objective>

<architectural_review_checklist>
□ **Layer Violations**: Are the documented boundaries still respected?
□ **New Layers**: Have new architectural layers been introduced?
□ **Component Evolution**: Have any components changed responsibility?
□ **Integration Changes**: New external service integrations?
□ **Data Flow Updates**: Has data flow through the system changed?
□ **New Cross-Cutting Concerns**: Authentication, caching, monitoring additions?
</architectural_review_checklist>

<architectural_update_decision_tree>
```
Has the fundamental architecture changed?
├─ Yes → Create new architecture document version
│   └─ Preserve old as `system-design-v1.md`
└─ No → Have components evolved?
    ├─ Yes → Update component sections
    │   └─ Note evolution timeline
    └─ No → Document new integration points only
```
</architectural_update_decision_tree>

<thinking_prompt>
Consider architectural evolution:
- Is the team moving toward a different architectural style?
- Are changes tactical (local improvements) or strategic (architectural shift)?
- Do changes suggest the team is preparing for specific scalability needs?
- Are boundaries becoming more or less strict?
</thinking_prompt>
</phase>

<phase id="4" name="Documentation Updates">
<objective>Update existing documentation files with new discoveries</objective>

<update_strategy>
For each documentation file requiring updates:

1. **Preserve Structure**: Maintain existing organization and headings
2. **Add Timestamps**: Mark updated sections with `[Updated: DATE]`
3. **Show Evolution**: Use "Previously" and "Currently" sections for major changes
4. **Append New**: Add new patterns/features to appropriate sections
5. **Mark Deprecated**: Use ⚠️ DEPRECATED markers with migration notes
6. **Update Examples**: Replace outdated code examples with current ones
</update_strategy>

<file_update_patterns>
### Updating `CLAUDE.md`
- Add new critical patterns to relevant sections
- Update command lists if new common commands discovered
- Refresh quick reference with evolved patterns
- Keep size under original limits by removing less critical items if needed

### Updating `discovered-patterns.md`
```markdown
## [Pattern Category]

### [Pattern Name]
[Original documentation remains]

#### Evolution [Updated: DATE]
This pattern has evolved to address [new requirements]:

**Current Implementation**:
```language
[New example]
```

**Migration Status**: 
- New code: Uses new pattern exclusively
- Existing code: Gradual migration in progress
- Migration guide: See `workflows/migrate-to-new-pattern.md`
```

### Updating Architecture Documentation
- Add new components to existing diagrams
- Note relationship changes between components
- Document new boundaries or layers
- Update data flow diagrams with new paths
- Preserve historical context with versioning notes

### Creating New Documentation
Only create entirely new files for:
- Completely new technologies added to stack
- New architectural patterns that don't fit existing categories
- New workflows that represent different ways of working
</file_update_patterns>

<quality_preservation>
When updating, maintain the quality standards of the original documentation:
- Every pattern includes real code examples
- Architectural decisions include reasoning
- Updates are as detailed as original content
- New sections match existing style and depth
</quality_preservation>
</phase>

<phase id="5" name="Validation and Coherence Check">
<objective>Ensure updates maintain documentation system coherence</objective>

<coherence_checklist>
□ **Cross-Reference Integrity**: Do all internal links still work?
□ **Consistency Check**: Do updates contradict any unchanged documentation?
□ **Completeness Verification**: Are all identified changes documented?
□ **Style Consistency**: Do updates match existing documentation style?
□ **Example Validity**: Do all code examples reflect current codebase?
□ **No Orphans**: Are deprecated patterns referenced elsewhere?
</coherence_checklist>

<validation_commands>
```bash
# Verify all referenced files exist
grep -r "@\|\.md)" .claude/context/ | grep -v ".git" | [verify links]

# Check for TODOs or placeholders that need attention
grep -r "TODO\|FIXME\|XXX" .claude/context/

# Ensure no accidental duplicates
find .claude/context/ -type f -name "*.md" | xargs grep -h "^##" | sort | uniq -d
```
</validation_commands>

<final_review_questions>
- Would a developer new to the project still understand the documentation?
- Do the updates tell a coherent story of the codebase evolution?
- Are there any gaps that the updates have revealed?
- Is the documentation still serving its purpose effectively?
</final_review_questions>
</phase>

<phase id="6" name="Update Summary and Next Steps">
<objective>Create a summary of changes and maintenance recommendations</objective>

<output_artifact>
<file_path>.claude/context/updates/update-summary-[DATE].md</file_path>
<format>
# Context Update Summary - [DATE]

## Overview
- **Previous Update**: [DATE or "Initial Generation"]
- **Files Modified**: [count]
- **New Patterns Documented**: [count]
- **Deprecated Patterns**: [count]
- **New Technologies**: [list]

## Key Changes

### Major Pattern Evolutions
1. **[Pattern Name]**
   - Reason for change: [explanation]
   - Migration status: [percentage or description]
   - Documentation updated in: [files]

### Architectural Updates
- [Description of any architectural changes]

### New Discoveries
- [Patterns or conventions newly documented]

## Recommendations

### Immediate Actions
1. [Critical updates team should know about]

### Future Maintenance
- Next recommended update: [timeframe]
- Areas to watch: [parts of codebase showing signs of change]
- Documentation gaps identified: [any areas needing attention]

### Team Communication
Suggested announcement for team:
```
The AI assistant context has been updated to reflect recent codebase evolution.
Key updates include:
- [main update 1]
- [main update 2]
Please review changes in areas you work with frequently.
```

## Metrics
- Documentation coverage: [estimate]%
- Pattern compliance observed: [estimate]%
- Areas needing attention: [count]
</format>
</output_artifact>
</phase>

<toolkit_propagation_update>
<phase id="6.5" name="Context Engineering Toolkit Integration">
<objective>Ensure updated contexts include knowledge of modern context engineering tools</objective>

<propagation_checklist>
When updating any context file, ensure it includes:

1. **Toolkit Availability Notice** (if not already present):
```markdown
## Context Engineering Toolkit

This project's Claude Code context includes access to modern tools for efficient codebase exploration:
- **Fast search**: `rg` (ripgrep), `fd` 
- **Code intelligence**: `ast-grep`, `semgrep`, `comby`
- **Data processing**: `jq`, `yq`, `gron`, `mlr`, `jc`
- **Scripting**: `perl`, `ruby`, `awk`, `python` one-liners
```

2. **Updated Discovery Commands** for changed areas:
```markdown
## Efficient Context Discovery - [Component Name]

# Find implementations in this module
ast-grep --pattern 'class $$ implements $$' src/[component]/

# Search for usage patterns
rg '[ComponentName]' --type ts -A 2 -B 2 | head -20

# Analyze recent changes
git log -p --since="1 month ago" -- src/[component]/ | rg '^\+.*class'
```

3. **Performance Tips** specific to the update:
```markdown
## Quick Analysis Commands

# See what changed in this update
git diff [last-update-hash]..HEAD -- .claude/context/ | cat

# Find new patterns quickly
fd -e js -e ts --changed-within 3months | xargs rg -l 'pattern'
```
</propagation_checklist>

<integration_approach>
For each file being updated:
1. Check if toolkit section exists
2. If not, add it after the main introduction
3. Update any old `find`/`grep` commands to use modern equivalents
4. Add project-specific discovery commands based on actual patterns found
5. Include performance comparison if replacing slow commands
</integration_approach>
</phase>
</toolkit_propagation_update>

<execution_instruction>
Begin by thoroughly analyzing the existing Claude Code documentation to understand the current state. Then identify what has changed in the codebase since that documentation was created. Focus your efforts on areas of significant change rather than re-analyzing the entire codebase.

Remember: You're a curator updating an exhibition, not rebuilding the museum. Preserve what remains valuable, update what has evolved, and add what is newly discovered. The goal is continuous improvement, not constant regeneration.

Throughout this process, maintain a clear trail of what changed and why, so future updates can build on your work just as you're building on the original documentation.
</execution_instruction>