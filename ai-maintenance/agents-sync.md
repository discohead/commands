# Synchronize AGENTS.md with AI Ecosystem Updates

<user_request>
Please update AGENTS.md files to reflect changes in Claude Code context, Cursor rules, and Copilot instructions. Execute the comprehensive synchronization process outlined below immediately.
</user_request>

<task_confirmation>
This command is your instruction to actively synchronize AGENTS.md files now. You should begin by analyzing what has changed in the AI ecosystem since the last update and proceed through all phases without waiting for additional input. The goal is to ensure cloud agent instructions remain aligned with evolved local patterns.
</task_confirmation>

<system_role>
You are an expert AI ecosystem synchronization specialist who ensures cloud agent instructions evolve in harmony with local AI systems. You excel at identifying which changes in Claude Code context, Cursor rules, or Copilot instructions impact cloud task execution and updating AGENTS.md files accordingly. You understand that maintaining alignment across all four systems is critical for consistent development practices, whether work happens locally or in the cloud. Think of yourself as a coordinator ensuring a remote team member's playbook stays current with the home office's evolving standards.
</system_role>

<immediate_action>
Start by identifying what has changed since AGENTS.md generation:
1. Check for updates in .claude/context/ directory
2. Review changes in .cursor/rules/
3. Examine modifications to .github/copilot-instructions.md
4. Read current AGENTS.md files to understand existing state

Begin this change analysis now.
</immediate_action>

<task_overview>
Your mission is to synchronize AGENTS.md files with evolved patterns and practices in your AI ecosystem. This delicate process requires you to preserve effective cloud-specific guidance while updating cross-system references, incorporating new patterns, deprecating obsolete practices, and ensuring Codex continues to produce PRs that meet current standards. The goal is maintaining coherent AI assistance whether developers work locally or delegate to the cloud.
</task_overview>

<synchronization_philosophy>
AGENTS.md synchronization differs from other maintenance tasks:
- **Reference Integrity**: Must maintain accurate pointers to other AI files
- **Pattern Evolution**: Track which patterns have matured or deprecated
- **Task Relevance**: Update which tasks are best suited for cloud delegation
- **Validation Currency**: Ensure test commands and checks remain valid
- **Environment Drift**: Account for dependency and tool changes

Synchronization ensures your cloud agent remains a productive team member despite never attending your standups.
</synchronization_philosophy>

<prerequisite_analysis>
<instruction>
Before synchronizing AGENTS.md, understand the scope of changes:

1. **Change Detection in AI Systems**:
   - New patterns in `.claude/context/discovered-patterns.md`
   - Updated rules in `.cursor/rules/`
   - Optimized instructions in `.github/copilot-instructions.md`
   - New workflows in `.claude/context/workflows/`
   - Deprecated practices marked in any system

2. **AGENTS.md Current State Analysis**:
   - Which patterns are currently referenced?
   - What validation steps are specified?
   - Which tasks are recommended for delegation?
   - How current are the environment specifications?

3. **Impact Assessment**:
   - Do changes affect cloud task execution?
   - Are referenced files still accurate?
   - Have validation commands changed?
   - Are recommended task types still relevant?
</instruction>

<thinking_prompt>
As you analyze changes, consider:
- Which evolved patterns most impact cloud-executed tasks?
- Are there new workflows Codex should know about?
- Have any practices Codex follows been deprecated?
- What new task types have emerged as delegation candidates?
- How can updates maintain cloud execution efficiency?
</thinking_prompt>
</prerequisite_analysis>

<phase id="1" name="Change Impact Analysis">
<objective>Determine which AI ecosystem changes require AGENTS.md updates</objective>

<impact_framework>
Categorize detected changes by cloud relevance:

**High Impact (Must Update)**:
- New architectural patterns or boundaries
- Changed testing requirements or commands  
- Updated security imperatives
- Modified validation procedures
- Deprecated patterns Codex might use
- New universal naming conventions

**Medium Impact (Should Update)**:
- New workflows suitable for delegation
- Evolved error handling patterns
- Additional code organization patterns
- Updated environment requirements
- New cross-cutting concerns

**Low Impact (Consider Updating)**:
- Local-only optimizations
- UI-specific patterns (unless Codex does frontend)
- Performance tweaks without structural changes
- Documentation style updates
</impact_framework>

<change_report>
<file_path>.claude/context/updates/agents-sync-analysis-[DATE].md</file_path>
<content>
```markdown
# AGENTS.md Synchronization Analysis - [DATE]

## Changes Since Last Update

### Claude Code Context
- New patterns: [list with relevance to cloud tasks]
- Updated workflows: [list if delegation-suitable]
- Deprecated practices: [list if Codex might use]

### Cursor Rules  
- New always rules: [list if universal]
- Modified rules: [list with impact]
- New component rules: [list if Codex works in those areas]

### Copilot Instructions
- Size optimization changes: [note key removals/additions]
- New universal patterns: [list]
- Updated examples: [note if significant]

## Impact on Cloud Execution

### Must Update in AGENTS.md
1. [Critical change]: [Why it affects Codex]
2. [Security update]: [Specific impact]
3. [Validation change]: [New commands/process]

### Should Update  
1. [New workflow]: [How it improves delegation]
2. [Pattern evolution]: [Better approach for Codex]

### Cross-Reference Updates Needed
- [File] has moved/been renamed
- [Pattern] now documented in [new location]
- [Workflow] has been redesigned

## New Delegation Opportunities
Based on evolved patterns, these tasks are now suitable for cloud:
1. [Task type]: [Why it's now delegatable]
2. [Task type]: [Enabler pattern/tool]
```
</content>
</change_report>
</phase>

<phase id="2" name="Reference Synchronization">
<objective>Update all cross-system references in AGENTS.md to remain accurate</objective>

<reference_update_patterns>
For each reference in AGENTS.md, verify and update:

**File References**:
```markdown
<!-- Before -->
See `.claude/context/workflows/testing.md` for test procedures

<!-- After (if file moved) -->
See `.claude/context/workflows/testing-strategy.md` for test procedures

<!-- After (if deprecated) -->
~~See `.claude/context/workflows/legacy-testing.md`~~ 
See `.claude/context/workflows/modern-testing.md` for current test procedures
```

**Pattern References**:
```markdown
<!-- Before -->
Follow error handling from `.cursor/rules/always/error-handling.mdc`

<!-- After (if pattern evolved) -->
Follow Result type pattern from `.cursor/rules/always/result-types.mdc`
Note: Legacy try-catch patterns are being migrated
```

**Command Updates**:
```markdown
<!-- Before -->
Validate with: `npm test`

<!-- After (if commands changed) -->
Validate with: `npm run test:ci` (includes linting and type checking)
```
</reference_update_patterns>

<systematic_update_approach>
1. **Extract all references from AGENTS.md**
2. **Verify each reference still exists and is current**
3. **Update paths, names, and descriptions**
4. **Add migration notes for deprecated patterns**
5. **Include new critical references discovered in other systems**
</systematic_update_approach>
</phase>

<phase id="3" name="Pattern Evolution Integration">
<objective>Incorporate evolved patterns and practices into cloud execution guidance</objective>

<pattern_update_framework>
For each evolved pattern relevant to cloud tasks:

**Pattern Addition Template**:
```markdown
### [Pattern Name] (Added [DATE])

This pattern has been adopted team-wide and must be followed:

[Brief description]

Example:
```[language]
// Current best practice
[Code example from updated patterns]
```

See `[reference to detailed documentation]` for more examples.
```

**Pattern Evolution Template**:
```markdown
### [Pattern Name] (Updated [DATE])

⚠️ This pattern has evolved. New code should follow the updated approach:

**Current Approach**:
```[language]
[New pattern example]
```

**Migration Notes**:
- Existing code using old pattern is being migrated
- Use new pattern for all new code
- See `.claude/context/workflows/migration-guide.md` for details
```

**Pattern Deprecation Template**:
```markdown
### ~~[Old Pattern Name]~~ (Deprecated [DATE])

❌ Do not use this pattern in new code.

✅ Instead, use [New Pattern Name]:
```[language]
[Correct approach example]
```

Reason: [Why deprecated]
Migration: [How to update existing code]
```
</pattern_update_framework>
</phase>

<phase id="4" name="Task Optimization Updates">
<objective>Update task recommendations based on new capabilities and patterns</objective>

<task_evolution_analysis>
Review how evolved patterns affect task delegation:

**New Delegatable Tasks**:
- Pattern standardization makes [task type] systematic
- New tooling enables automated [task type]
- Improved testing allows confident [task type]

**No Longer Suitable Tasks**:
- [Task type] needs real-time feedback with new process

**Improved Task Approaches**:
- [Task type] can now use [new tool/pattern]
- [Task type] benefits from [evolved workflow]
</task_evolution_analysis>

<task_section_updates>
Update AGENTS.md task guidance:

```markdown
## Optimal Task Types (Updated [DATE])

### Newly Delegatable Tasks

#### [Task Category]
With our new [pattern/tool], these tasks are now suitable for cloud execution:
- [Specific task example]
- [Another example]

Example prompt: "[Concrete task description]"

### Enhanced Task Approaches

#### Test Generation
Now using [new test framework/pattern]:
- [Updated approach]
- [New validation available]

#### Refactoring  
Leverage [new pattern] for more systematic updates:
- [Improved approach]
- [Better validation]

### Tasks No Longer Recommended
- ❌ [Task type]: New process needs iteration
```
</task_section_updates>
</phase>

<phase id="5" name="Environment and Validation Updates">
<objective>Ensure setup and validation instructions reflect current requirements</objective>

<environment_synchronization>
Update based on changes in:
1. **Dependency versions** from package files
2. **New development tools** added to project
3. **Changed build/test commands**
4. **New validation requirements**
5. **Updated CI/CD processes**

<environment_update_template>
```markdown
## Environment Configuration (Updated [DATE])

### Language Requirements
- Node.js: [new version] (upgraded from [old])
- [New language added]: [version]

### Setup Script Updates
```bash
#!/bin/bash
# Dependencies (updated versions)
npm install

# New required tools
npm install -g [new tool]

# New setup step
[additional configuration]
```

### Validation Commands (Updated)
- Build: `[updated command]` 
- Test: `[updated command]`
- Lint: `[updated command]`
- NEW: [New validation]: `[command]`

### Breaking Changes
⚠️ [Tool] now requires [configuration]
⚠️ Tests now need [environment variable]
```
</environment_update_template>
</environment_synchronization>
</phase>

<phase id="6" name="Comprehensive Testing">
<objective>Validate synchronized AGENTS.md maintains effectiveness</objective>

<testing_checklist>
After synchronization, verify:

□ **Reference Integrity**
  - All file paths resolve correctly
  - All referenced patterns exist
  - Commands execute successfully

□ **Pattern Currency**  
  - Examples use current patterns
  - No deprecated patterns remain
  - Migration guidance is clear

□ **Task Relevance**
  - Recommended tasks align with current capabilities
  - New delegation opportunities are included
  - Obsolete tasks are removed

□ **Environment Accuracy**
  - Setup scripts work with current dependencies
  - Validation commands are current
  - No missing requirements

□ **Cross-System Alignment**
  - AGENTS.md respects all current AI guidance
  - No contradictions with updated systems
  - Comprehensive coverage of critical patterns
</testing_checklist>

<validation_simulation>
Test with hypothetical task:
1. Would Codex find all needed patterns?
2. Would validation catch rule violations?
3. Would the PR meet current standards?
4. Are all tools and commands available?
</validation_simulation>
</phase>

<phase id="7" name="Documentation and Communication">
<objective>Document synchronization changes and inform team</objective>

<sync_summary>
<file_path>.claude/context/updates/agents-sync-summary-[DATE].md</file_path>
<content>
```markdown
# AGENTS.md Synchronization Summary - [DATE]

## Overview
- Previous sync: [DATE or "Initial generation"]
- Files updated: AGENTS.md [and any specialized versions]
- Major changes: [count]

## Key Updates

### Pattern Changes
1. **[Pattern]**: [What changed and why]
2. **[Pattern]**: [Impact on cloud tasks]

### New Task Capabilities
- [Task type]: Now delegatable due to [enabler]
- [Task type]: Improved approach using [pattern]

### Deprecated Practices
- [Practice]: Replaced by [new approach]
- Migration guidance added for existing code

### Environment Updates  
- [Tool/Dependency]: Updated to [version]
- New validation: [What and why]

## Cross-Reference Updates
- Updated [count] file references
- Added [count] new pattern references  
- Removed [count] deprecated references

## Impact on Cloud Execution
[Summary of how changes affect Codex task execution]

## Recommended Actions
1. Review updated task recommendations
2. Note new validation requirements
3. Consider delegating [new task type]

## Next Sync
Recommended: [DATE based on change velocity]
```
</content>
</sync_summary>

<team_notification>
```markdown
Subject: AGENTS.md Updated - Cloud AI Aligned with Latest Patterns

Team,

The Codex AGENTS.md configuration has been synchronized with our evolved patterns:

**Key Updates**:
- New Result type pattern for error handling
- Updated test validation commands  
- Additional tasks now suitable for delegation
- Deprecated promise-chain patterns removed

**What This Means**:
- Codex PRs will follow our latest patterns
- New task types can be delegated to cloud
- Validation matches our current CI/CD

**Action Items**:
- Review updated task recommendations
- Try delegating [suggested task type]
- Report any misaligned Codex PRs

The cloud AI remains in sync with our local development patterns.
```
</team_notification>
</phase>

<quality_principles>
Effective AGENTS.md synchronization:
- **Preserves cloud-specific value** while updating patterns
- **Maintains reference accuracy** across all systems
- **Evolves task recommendations** based on capabilities
- **Updates validation** to match current standards
- **Communicates changes** clearly to the team
</quality_principles>

<execution_instruction>
Begin by thoroughly analyzing what has changed across all three local AI systems since AGENTS.md was last updated. Focus on changes that affect:

1. How Codex should generate code
2. What validation ensures PR quality
3. Which tasks benefit from cloud execution
4. How the environment needs configuration

Then systematically update AGENTS.md to reflect these evolutions while preserving its effectiveness for autonomous cloud execution. Every update should help Codex continue producing PRs that seamlessly integrate with your evolved codebase.

Remember: Synchronization is about maintaining harmony between local and cloud AI assistance. The goal is ensuring a Codex PR is indistinguishable from work done by a developer using the latest local AI guidance.
</execution_instruction>

<execution_reminder>
You are now actively synchronizing AGENTS.md files. Begin with comprehensive change analysis across all AI systems and proceed through each phase systematically. This command is your complete authorization to update cloud agent instructions for continued alignment with your evolved AI ecosystem.
</execution_reminder>