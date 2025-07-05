# Synchronize Cursor Rules with Updated Context
<user_request>
Please synchronize the Cursor MDC rules with the updated Claude Code context to ensure behavioral guidance remains aligned with current codebase patterns. Execute the comprehensive synchronization process outlined below immediately.
</user_request>

<task_confirmation>
This command is your instruction to actively perform the rule synchronization task now. You should begin by reviewing both the updated Claude Code context and existing Cursor rules, then proceed through all phases without waiting for additional input. The goal is to evolve the rules to match current patterns while maintaining their prescriptive power.
</task_confirmation>

<system_role>
You are an expert behavioral rule architect specializing in evolutionary documentation systems. With deep experience in maintaining consistency between knowledge repositories and active behavioral guidance, you excel at identifying which discovered patterns should become enforced behaviors and which existing rules need refinement. You understand that rules are living documents that must evolve with codebases while maintaining their prescriptive power. Think of yourself as a translator who converts evolved understanding into refined behavioral guidance, ensuring AI assistants remain helpful as codebases mature.
</system_role>

<immediate_action>
Start this synchronization by first examining the recent changes documented in the Claude Code context update. Look for:
1. Any change analysis reports in `.claude/context/updates/`
2. Updated patterns in `.claude/context/discovered-patterns.md`
3. Modified architecture documentation
4. Deprecated patterns that need rule adjustments

Then immediately proceed to analyze how these changes affect the existing Cursor rules.
</immediate_action>

<task_overview>
Your mission is to synchronize Cursor MDC rules with the updated Claude Code context, ensuring behavioral guidance remains aligned with current codebase patterns and practices. This delicate process requires you to preserve effective existing rules while evolving those that no longer serve their purpose, adding new rules for emerged patterns, and removing rules for deprecated practices. The goal is maintaining a coherent, effective rule system that prevents real errors and guides toward current best practices.
</task_overview>

<system_role>
You are an expert behavioral rule architect specializing in evolutionary documentation systems. With deep experience in maintaining consistency between knowledge repositories and active behavioral guidance, you excel at identifying which discovered patterns should become enforced behaviors and which existing rules need refinement. You understand that rules are living documents that must evolve with codebases while maintaining their prescriptive power. Think of yourself as a translator who converts evolved understanding into refined behavioral guidance, ensuring AI assistants remain helpful as codebases mature.
</system_role>

<task_overview>
Your mission is to synchronize Cursor MDC rules with the updated Claude Code context, ensuring behavioral guidance remains aligned with current codebase patterns and practices. This delicate process requires you to preserve effective existing rules while evolving those that no longer serve their purpose, adding new rules for emerged patterns, and removing rules for deprecated practices. The goal is maintaining a coherent, effective rule system that prevents real errors and guides toward current best practices.
</task_overview>

<synchronization_philosophy>
Cursor rules serve a different purpose than Claude Code context. While context stores comprehensive knowledge, rules actively shape behavior. This synchronization ensures rules remain:
- **Relevant**: Addressing current patterns and preventing actual mistakes
- **Accurate**: Reflecting how the team currently works, not how they used to
- **Balanced**: Maintaining appropriate distribution across rule categories
- **Effective**: Each rule must earn its place by preventing errors or ensuring quality
</synchronization_philosophy>

<prerequisite_understanding>
<instruction>
Before beginning synchronization, you must understand both current states:

1. **Review Updated Claude Code Context**:
   - Read the change analysis report from recent context update
   - Study any newly documented patterns in `.claude/context/discovered-patterns.md`
   - Understand architectural evolutions in `.claude/context/architecture/`
   - Note deprecated patterns that need rule updates
   - Identify new workflows that might need behavioral guidance

2. **Analyze Existing Cursor Rules**:
   - Read all files in `.cursor/rules/` directory
   - Build mental model of current rule coverage
   - Note which rules might be outdated
   - Identify potential gaps in rule coverage

3. **Gather Additional Intelligence**:
   - Recent code review comments (if accessible)
   - Common mistakes in recent pull requests
   - Team feedback on rule effectiveness
   - Areas where AI suggestions have been consistently corrected
</instruction>

<thinking_prompt>
As you review both systems, consider these strategic questions:
- Which new patterns are mature enough to become enforced rules?
- Which existing rules might now be constraining rather than helpful?
- Are there patterns that have evolved but rules haven't kept pace?
- What mistakes are developers still making that rules could prevent?
- How has the team's expertise level changed, affecting what guidance they need?
</thinking_prompt>
</prerequisite_understanding>

<phase id="1" name="Rule Effectiveness Audit">
<objective>Evaluate current rules against updated context to identify needed changes</objective>

<audit_framework>
For each existing rule file, perform this analysis:

1. **Relevance Check**:
   - Does this rule address patterns still used in the codebase?
   - Has the pattern evolved in a way that makes the rule misleading?
   - Is this preventing real errors or just enforcing preferences?

2. **Accuracy Assessment**:
   - Do the examples still reflect current code?
   - Are the glob patterns still matching the right files?
   - Have file naming conventions changed?

3. **Impact Evaluation**:
   - In the "always" category: Is this still universal enough?
   - In component categories: Does this component type still exist?
   - In feature categories: Is this feature area still active?

4. **Gap Analysis**:
   - What new patterns lack corresponding rules?
   - What errors could rules prevent that they currently don't?
   - Are there new component types without rule coverage?
</audit_framework>

<categorization_review>
Rule categories may need rebalancing based on codebase evolution:

```
Current Always Rules (500 lines limit)
├─ Still Critical? → Keep with updates
├─ Now Contextual? → Move to auto-attached
└─ Deprecated? → Remove or archive

New Universal Patterns
├─ Prevents Errors? → Add to always rules
├─ Component-Specific? → Create auto-attached
└─ Complex Procedure? → Create agent-requested
```
</categorization_review>

<audit_output>
<file_path>.claude/context/updates/cursor-rules-audit-[DATE].md</file_path>
<format>
# Cursor Rules Audit Report - [DATE]

## Rules Effectiveness Summary

### Always Rules Status
- Total size: [X] lines of [500] limit
- Rules needing update: [count]
- Rules to remove: [count]
- Space for new rules: [lines available]

### Component Rules Coverage
| Component Type | Has Rules | Patterns Covered | Gaps Identified |
|----------------|-----------|------------------|-----------------|
| Controllers | ✓ | 8/10 patterns | New streaming pattern |
| Services | ✓ | 6/6 patterns | All covered |
| [etc...] | | | |

### Recommended Changes

#### High Priority Updates
1. **Rule**: `always/core-conventions.mdc`
   - **Issue**: Async pattern has evolved to use Result type
   - **Action**: Update examples and guidance
   - **Impact**: Affects all async code generation

#### New Rules Needed
1. **Pattern**: Result type error handling
   - **Category**: Always rule (universal adoption)
   - **Prevents**: Inconsistent error handling
   - **Size estimate**: ~50 lines

#### Rules to Deprecate
1. **Rule**: `features/legacy-api.mdc`
   - **Reason**: Legacy API fully migrated
   - **Action**: Archive with migration notes
</format>
</audit_output>
</phase>

<phase id="2" name="Rule Evolution Planning">
<objective>Plan specific updates to align rules with current patterns</objective>

<evolution_strategies>
Understanding how to evolve rules requires recognizing different types of changes:

1. **Pattern Refinement**:
   - The core pattern remains but implementation details evolved
   - Update examples while preserving the principle
   - Add notes about acceptable variations

2. **Pattern Revolution**:
   - Old pattern completely replaced by new approach
   - Requires careful migration guidance
   - May need temporary rules supporting both patterns

3. **Pattern Expansion**:
   - Pattern now applies to more contexts
   - Broaden glob patterns or create new rules
   - Ensure examples cover new applications

4. **Pattern Deprecation**:
   - Pattern being phased out but still exists
   - Add deprecation warnings to rules
   - Include migration guidance
</evolution_strategies>

<rule_update_template>
When updating an existing rule, follow this structure:

```mdc
---
description: [Updated description if behavior changed]
globs: [Updated patterns if file structure changed]
alwaysApply: [true/false - may change based on new scope]
---

# [Rule Category Name]

[Brief explanation - update if fundamental approach changed]

## [Specific Rule Name]

[Original rule content remains if still valid]

### ⚠️ Evolution Notice [Added: DATE]
This pattern is evolving. New code should follow the updated pattern below:

✅ **Current Best Practice**:
```[language]
// Modern implementation following new patterns
[code example from current codebase]
```

⚠️ **Transitional (Still Valid)**:
```[language]
// Previous pattern - still acceptable in existing code
[previous example]
```

❌ **Deprecated (Do Not Use)**:
```[language]
// Old pattern that should be actively migrated
[deprecated example]
```

### Migration Guide
When updating existing code:
1. [Step-by-step migration instructions]
2. [Common pitfalls to avoid]
3. [Testing considerations]
```
</rule_update_template>

<thinking_prompt>
As you plan rule evolution, consider:
- How can rules guide developers through transitions smoothly?
- Which rules need immediate updates versus gradual evolution?
- How do we balance stability with progress?
- What's the cognitive load of developers dealing with transitional patterns?
</thinking_prompt>
</phase>

<phase id="3" name="New Rule Creation">
<objective>Create rules for newly discovered patterns that warrant behavioral guidance</objective>

<rule_creation_criteria>
Before creating a new rule, verify the pattern meets these criteria:

1. **Maturity Assessment**:
   - Pattern appears in multiple areas of codebase
   - Multiple developers have adopted it
   - It's not experimental or personal preference

2. **Error Prevention Value**:
   - Not following this pattern causes real problems
   - Mistakes are common without guidance
   - The correct approach isn't immediately obvious

3. **Scope Appropriateness**:
   - Universal → Always rule
   - File-type specific → Auto-attached rule
   - Complex multi-step → Agent-requested rule
   - Rarely needed → Manual rule

4. **Context Efficiency**:
   - Rule can be explained concisely
   - Examples demonstrate the principle clearly
   - Benefit justifies context window usage
</rule_creation_criteria>

<new_rule_integration>
When adding new rules, ensure they integrate smoothly with existing rules:

1. **Naming Consistency**:
   - Follow established file naming patterns
   - Use similar section headings
   - Maintain consistent terminology

2. **Cross-Reference Related Rules**:
   - Link to complementary rules
   - Note differences from similar patterns
   - Avoid contradictions or overlaps

3. **Example Quality**:
   - Use real code from the current codebase
   - Show both correct and incorrect approaches
   - Include edge cases if relevant
</new_rule_integration>

<example_new_rule>
Based on newly discovered Result type pattern:

<file_path>.cursor/rules/always/result-type-handling.mdc</file_path>
```mdc
---
description: Result type pattern for consistent error handling across all async operations
globs: []
alwaysApply: true
---

# Result Type Error Handling

All async operations must return Result types to ensure consistent error handling and make error paths explicit in the type system.

## Using Result Types

Every async function should return a Result<T, E> instead of throwing errors:

✅ **Correct Implementation**:
```typescript
async function fetchUser(id: string): Promise<Result<User, ApiError>> {
  try {
    const user = await db.users.findById(id);
    if (!user) {
      return Result.error(new NotFoundError('User not found'));
    }
    return Result.ok(user);
  } catch (error) {
    logger.error('Failed to fetch user', { id, error });
    return Result.error(new DatabaseError('Failed to fetch user', error));
  }
}

// Usage makes error handling explicit
const userResult = await fetchUser(userId);
if (userResult.isError()) {
  return handleError(userResult.error);
}
const user = userResult.value;
```

❌ **Incorrect - Throwing Errors**:
```typescript
async function fetchUser(id: string): Promise<User> {
  const user = await db.users.findById(id);
  if (!user) {
    throw new Error('User not found'); // Don't throw
  }
  return user;
}
```

## Chaining Result Operations

Use Result methods for clean error propagation:

```typescript
const result = await fetchUser(userId)
  .andThen(user => validateUserPermissions(user))
  .andThen(user => enrichUserData(user))
  .mapError(error => new ApiError(500, 'User operation failed', error));
```
```
</example_new_rule>
</phase>

<phase id="4" name="Rule Size Optimization">
<objective>Ensure rule system remains within context limits while maximizing impact</objective>

<optimization_techniques>
When approaching size limits, apply these techniques in order:

1. **Consolidation**:
   - Combine related rules that are always used together
   - Merge similar patterns into single, comprehensive rules
   - Use more general examples that demonstrate multiple principles

2. **Compression**:
   - Replace verbose explanations with clear examples
   - Use concise language without losing clarity
   - Remove redundant sections between rules

3. **Redistribution**:
   - Move context-specific rules from always to auto-attached
   - Convert detailed procedures to agent-requested rules
   - Archive rarely-used rules as manual-only

4. **Prioritization**:
   - Keep rules preventing security issues
   - Keep rules preventing production errors
   - Keep rules ensuring code consistency
   - Remove rules for mere preferences
</optimization_techniques>

<size_tracking>
Monitor rule sizes throughout the synchronization process:

```
Always Rules Budget:
├─ Current: [X] lines
├─ After removals: [Y] lines
├─ After additions: [Z] lines
└─ Target: <500 lines with 10% buffer

If over budget:
1. Apply optimization techniques
2. Move lowest-impact rules to other categories
3. Consider creating specialized rule sets
```
</size_tracking>

<thinking_prompt>
During optimization, remember:
- Every line in an always rule costs precious context
- A concise rule that prevents errors is worth more than a detailed preference
- Examples often convey more than explanations
- The goal is behavioral impact, not comprehensive documentation
</thinking_prompt>
</phase>

<phase id="5" name="Rule Testing and Validation">
<objective>Verify synchronized rules achieve their behavioral objectives</objective>

<testing_methodology>
Test updated rules through practical validation:

1. **Isolation Testing**:
   - Disable all rules except the one being tested
   - Generate code that should trigger the rule
   - Verify Cursor applies the rule correctly

2. **Integration Testing**:
   - Enable all rules in their categories
   - Generate code for common scenarios
   - Check for rule conflicts or contradictions

3. **Error Prevention Testing**:
   - Attempt to generate code with known anti-patterns
   - Verify rules prevent or flag these patterns
   - Ensure error messages guide toward correct approach

4. **Real-world Validation**:
   - Apply rules to actual feature development
   - Note any friction or unhelpful constraints
   - Gather developer feedback on rule effectiveness
</testing_methodology>

<validation_checklist>
Before finalizing synchronized rules:

□ **Completeness**: All new patterns have appropriate rules?
□ **Accuracy**: All examples reflect current codebase?
□ **Clarity**: Rules are understandable without additional context?
□ **Effectiveness**: Rules prevent real errors observed in codebase?
□ **Efficiency**: Total size remains within limits?
□ **Consistency**: No contradictions between rules?
□ **Evolution Path**: Transitional patterns have clear guidance?
</validation_checklist>
</phase>

<phase id="6" name="Documentation and Communication">
<objective>Document changes and prepare team communication</objective>

<change_documentation>
<file_path>.cursor/rules/CHANGELOG.md</file_path>
<format>
# Cursor Rules Changelog

## [DATE] - Context Synchronization Update

### Added
- `always/result-type-handling.mdc` - New error handling pattern adopted team-wide
- `components/streaming-controllers.mdc` - Patterns for new streaming endpoints
- `workflows/gradual-migration.mdc` - Guide for transitioning between patterns

### Changed
- `always/core-conventions.mdc` - Updated async patterns to use Result types
- `components/controllers.mdc` - Added streaming response patterns
- `always/architecture-principles.mdc` - Refined service layer boundaries

### Deprecated
- `features/legacy-api.mdc` - Legacy API fully migrated, archived for reference
- Promise-based error handling in favor of Result types (see migration guide)

### Migration Notes
Teams should be aware of these transitional patterns:
1. **Error Handling**: Both try-catch and Result patterns coexist during migration
2. **API Responses**: Moving from direct returns to Result-wrapped responses

### Impact Summary
- Estimated prevention of ~30% of error-handling bugs
- Clearer error paths in generated code
- Better alignment with current team practices
</format>
</change_documentation>

<team_communication_template>
Prepare announcement for the development team:

```markdown
Subject: Cursor Rules Updated - Synchronized with Recent Patterns

Team,

The Cursor rules have been synchronized with our evolved codebase patterns. Key updates include:

**New Behavioral Guidance**:
- Result type error handling is now enforced in all async operations
- Streaming endpoint patterns added for new real-time features
- Updated async/await patterns reflecting our current best practices

**What This Means for You**:
- Cursor will now suggest Result types instead of thrown errors
- Auto-completions will follow our new streaming patterns
- Generated code will better match our current conventions

**Transitional Period**:
- Both old and new patterns are documented during migration
- Cursor will guide you toward new patterns in new code
- Existing code can be gradually migrated

**Action Items**:
1. Review updated rules in your area of focus
2. Report any rules that feel constraining or incorrect
3. Use new patterns in all new code

The rules now better reflect how we actually work versus how we used to work. This should reduce the "fighting with AI" feeling when Cursor suggests outdated patterns.

Questions or feedback? Please share in #ai-assistance channel.
```
</team_communication_template>
</phase>

<execution_instruction>
Begin by thoroughly understanding both the updated Claude Code context and the existing Cursor rules. Pay special attention to the change analysis and newly documented patterns, as these are your primary sources for identifying what needs synchronization.

Remember that rules are behavioral guidance, not documentation. Each rule should actively prevent errors or ensure quality. If a rule doesn't change behavior, it doesn't belong in the rule system.

Throughout this process, maintain empathy for developers who will work with these rules daily. Rules should feel like helpful guardrails, not arbitrary constraints. The best rules are those that developers would thank you for because they prevented a bug or saved time.

Your synchronization should create a harmonious system where Cursor's behavioral guidance perfectly reflects the team's current best practices as documented in Claude Code context. This alignment ensures AI assistance feels natural and helpful rather than outdated or constraining.
</execution_instruction>

<execution_reminder>
You are now actively performing this synchronization task. Begin with the prerequisite understanding phase where you review both the updated context and existing rules. Work systematically through each phase, creating and updating rule files as needed. This command is your complete authorization to proceed - do not pause for additional approval between phases.
</execution_reminder>