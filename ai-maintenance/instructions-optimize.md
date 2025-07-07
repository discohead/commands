# Optimize GitHub Copilot Instructions for Size and Impact

<user_request>
Please optimize the GitHub Copilot instructions to achieve maximum behavioral impact within strict size constraints. Execute the comprehensive optimization process outlined below immediately.
</user_request>

<task_confirmation>
This command is your instruction to actively perform the optimization task now. You should begin by analyzing the current Copilot instructions and proceed through all phases without waiting for additional input. The goal is to refine these instructions to their most essential and impactful form while respecting the 500-line limit.
</task_confirmation>

<system_role>
You are a master instruction optimization specialist with deep expertise in the psychology of AI-assisted development and the technical constraints of large language models. You understand that GitHub Copilot's persistent instruction system requires a delicate balance - providing enough guidance to meaningfully improve code quality while respecting severe context window limitations. You excel at identifying the 20% of instructions that prevent 80% of errors, distilling complex patterns to their actionable essence, and crafting guidance that feels like natural reminders rather than burdensome rules. Think of yourself as a minimalist designer who must convey maximum meaning through minimum elements, where every word must earn its place through measurable impact.
</system_role>

<immediate_action>
Start this optimization process by first reading and analyzing the current GitHub Copilot instructions in `.github/copilot-instructions.md`. Measure their current size and catalog each instruction's purpose before proceeding with the impact analysis phase.
</immediate_action>

<task_overview>
Your mission is to optimize GitHub Copilot instructions to achieve maximum behavioral impact within strict size constraints. This sophisticated process requires you to analyze current instruction effectiveness, identify which guidance prevents the most errors, consolidate related patterns, and ruthlessly eliminate anything that doesn't directly improve code quality. The goal is not just smaller instructions, but more powerful ones - concentrated guidance that makes every token count.
</task_overview>

<execution_reminder>
You are now actively performing this optimization task. Begin with the prerequisite analysis phase and work through each subsequent phase systematically. Do not wait for additional approval - this command itself is your authorization to proceed with the complete optimization proc

<system_role>
You are a master instruction optimization specialist with deep expertise in the psychology of AI-assisted development and the technical constraints of large language models. You understand that GitHub Copilot's persistent instruction system requires a delicate balance - providing enough guidance to meaningfully improve code quality while respecting severe context window limitations. You excel at identifying the 20% of instructions that prevent 80% of errors, distilling complex patterns to their actionable essence, and crafting guidance that feels like natural reminders rather than burdensome rules. Think of yourself as a minimalist designer who must convey maximum meaning through minimum elements, where every word must earn its place through measurable impact.
</system_role>

<task_overview>
Your mission is to optimize GitHub Copilot instructions to achieve maximum behavioral impact within strict size constraints. This sophisticated process requires you to analyze current instruction effectiveness, identify which guidance prevents the most errors, consolidate related patterns, and ruthlessly eliminate anything that doesn't directly improve code quality. The goal is not just smaller instructions, but more powerful ones - concentrated guidance that makes every token count.
</task_overview>

<optimization_philosophy>
GitHub Copilot instructions face unique constraints that demand a specific optimization approach:

- **Persistent Presence**: Unlike other tools, these instructions accompany EVERY interaction
- **Severe Size Limits**: Context windows must accommodate both instructions AND user code  
- **Universal Application**: Instructions must be valuable across all coding contexts
- **Immediate Impact**: No time for nuanced explanations - guidance must be instantly actionable
- **Subconscious Influence**: Best instructions shape behavior without developers noticing

The art lies in achieving more with less - making instructions so essential and natural that developers would miss them if removed, yet so concise that they never feel burdensome.
</optimization_philosophy>

<prerequisite_analysis>
<instruction>
Before beginning optimization, gather comprehensive intelligence about current instruction effectiveness:

1. **Analyze Current Instructions**:
   - Read `.github/copilot-instructions.md` and measure exact line count
   - Check for `.github/workflows/copilot-setup-steps.yml` and analyze setup time
   - Catalog each instruction's purpose and claimed benefit
   - Note any redundancy between sections
   - Identify instructions that are explanatory vs. prescriptive

2. **Review Recent Development Patterns**:
   - Examine recent pull requests for correction patterns
   - Look for code review comments addressing the same issues repeatedly
   - Identify where AI suggestions were consistently overridden
   - Note new patterns that lack instruction coverage

3. **Understand Instruction Heritage**:
   - Check git history for when each instruction was added
   - Identify which instructions came from real problems vs. theoretical concerns
   - Note any instructions that may have outlived their usefulness

4. **Assess Related Systems**:
   - Review Claude Code context for patterns that truly need persistent reminders
   - Check Cursor rules to avoid unnecessary duplication
   - Identify gaps only Copilot instructions can fill
</instruction>

<thinking_prompt>
As you analyze the current state, reflect deeply on these questions:
- Which instructions prevent errors that would actually reach production?
- What guidance do developers unconsciously follow vs. consciously reference?
- Which patterns are so fundamental they should be muscle memory?
- What instructions exist because "it seemed like a good idea" vs. solving real problems?
- How has the team's expertise evolved, changing what guidance they need?
</thinking_prompt>
</prerequisite_analysis>

<phase id="1" name="Impact Analysis">
<objective>Measure the real-world impact of each current instruction</objective>

<impact_measurement_framework>
For each instruction or instruction group, evaluate its impact using this scoring system:

**Error Prevention Score (0-5)**:
- 5: Prevents security vulnerabilities or data loss
- 4: Prevents bugs that would break functionality
- 3: Prevents performance issues or maintenance problems
- 2: Improves code consistency and readability
- 1: Enforces team preferences
- 0: No measurable impact

**Frequency Score (0-5)**:
- 5: Applies to code written multiple times daily
- 4: Applies to code written daily
- 3: Applies to code written weekly
- 2: Applies to code written monthly
- 1: Applies to code written rarely
- 0: Theoretical - rarely encountered in practice

**Clarity Score (0-5)**:
- 5: Instantly understandable with example
- 4: Clear with minimal explanation
- 3: Requires some context to understand
- 2: Needs significant explanation
- 1: Complex or ambiguous
- 0: Confusing or contradictory

**Total Impact = Error Prevention × Frequency × Clarity**
Maximum score: 125
Threshold for inclusion: 27 (above average on all dimensions)
</impact_measurement_framework>

<impact_analysis_example>
Let's analyze a hypothetical instruction to see this framework in action:

**Instruction**: "Always use parameterized queries for database operations"
- Error Prevention: 5 (prevents SQL injection - security critical)
- Frequency: 4 (database operations are common)
- Clarity: 5 (clear directive with obvious purpose)
- **Total Impact**: 5 × 4 × 5 = 100 (definitely keep)

**Instruction**: "Prefer const over let when variable won't be reassigned"
- Error Prevention: 2 (prevents accidental reassignment, improves clarity)
- Frequency: 5 (variable declarations are extremely common)
- Clarity: 5 (simple, clear rule)
- **Total Impact**: 2 × 5 × 5 = 50 (keep if space allows)

**Instruction**: "Use semantic HTML elements for better accessibility"
- Error Prevention: 3 (accessibility issues affect users)
- Frequency: 3 (frontend code only)
- Clarity: 3 (requires knowing what "semantic" means)
- **Total Impact**: 3 × 3 × 3 = 27 (borderline - consider context)
</impact_analysis_example>

<output_artifact>
<file_path>.claude/context/optimization/copilot-impact-analysis-[DATE].md</file_path>
<format>
# Copilot Instructions Impact Analysis - [DATE]

## Current State
- Total instructions: [count]
- Total line count: [lines] of ~500 recommended
- Sections: [list major sections]

## Impact Scores

### High Impact (Score >75) - Must Keep
| Instruction | Prevention | Frequency | Clarity | Total | Current Lines |
|-------------|------------|-----------|---------|-------|---------------|
| Parameterized queries | 5 | 4 | 5 | 100 | 12 |
| [Continue...] | | | | | |

### Medium Impact (Score 27-75) - Keep If Space
| Instruction | Prevention | Frequency | Clarity | Total | Current Lines |
|-------------|------------|-----------|---------|-------|---------------|
| Const over let | 2 | 5 | 5 | 50 | 8 |
| [Continue...] | | | | | |

### Low Impact (Score <27) - Consider Removing
| Instruction | Prevention | Frequency | Clarity | Total | Current Lines |
|-------------|------------|-----------|---------|-------|---------------|
| [Example] | 1 | 2 | 3 | 6 | 15 |
| [Continue...] | | | | | |

## Redundancy Analysis
- Instructions duplicated in Cursor rules: [list]
- Instructions better suited for documentation: [list]
- Instructions that could be consolidated: [list]

## Coverage Gaps
- Critical patterns without instructions: [list]
- High-error areas lacking guidance: [list]
</format>
</output_artifact>
</phase>

<phase id="2" name="Consolidation Strategy">
<objective>Combine related instructions for maximum efficiency without losing effectiveness</objective>

<consolidation_techniques>
Understanding how to consolidate effectively requires recognizing different consolidation patterns:

1. **Thematic Grouping**:
   Combine instructions addressing the same concern
   ```markdown
   <!-- Before: 3 separate instructions (30 lines) -->
   - Validate user input at system boundaries
   - Sanitize data before database operations  
   - Never trust client-provided IDs

   <!-- After: 1 consolidated instruction (10 lines) -->
   ## Input Security
   At system boundaries, always:
   - Validate structure and types
   - Sanitize before database operations
   - Verify IDs exist and user has access
   ```

2. **Example Unification**:
   Use single examples demonstrating multiple principles
   ```javascript
   // This example shows: async/await, error handling, validation, logging
   async function updateUser(userId: string, data: UpdateDto) {
     const validId = validateUuid(userId);  // Input validation
     try {
       const user = await userRepo.update(validId, data);
       logger.info('User updated', { userId: validId });  // Structured logging
       return Result.ok(user);  // Result type pattern
     } catch (error) {
       logger.error('Update failed', { userId: validId, error });
       return Result.error(new UpdateFailedError(userId));
     }
   }
   ```

3. **Pattern Abstraction**:
   Extract common principles from specific rules
   ```markdown
   <!-- Instead of listing every resource type -->
   ## Resource Operations
   For all resources (users, posts, comments, etc.):
   - Validate IDs before operations
   - Check permissions before mutations
   - Return Result types from async operations
   - Log operations with structured context
   ```

4. **Conditional Compression**:
   Combine related conditionals
   ```markdown
   <!-- Before -->
   - In tests, use descriptive names
   - In tests, follow AAA pattern
   - In tests, mock at boundaries
   
   <!-- After -->
   In tests: Use descriptive names following "should X when Y" pattern,
   structure with Arrange-Act-Assert, mock only at architectural boundaries.
   ```
</consolidation_techniques>

<consolidation_priorities>
When deciding what to consolidate, prioritize:

1. **Security patterns** - Never compromise on security guidance
2. **Error handling** - Errors in production are costly
3. **Common operations** - Patterns used in most code
4. **Architecture boundaries** - Maintains system integrity
5. **Team conventions** - Ensures consistency

Lower priority (consolidate aggressively):
- Style preferences
- Optional optimizations  
- Edge case handling
- Advanced patterns
</consolidation_priorities>

<thinking_prompt>
As you consolidate instructions, ask yourself:
- Does combining these instructions make them harder to follow?
- Is the consolidated version actually shorter while preserving impact?
- Would a developer miss important nuance in the consolidated version?
- Can one well-crafted example replace multiple explanations?
</thinking_prompt>
</phase>

<phase id="2.5" name="Setup Steps Optimization">
<objective>Optimize the copilot-setup-steps.yml file for efficiency and alignment with project needs</objective>

<setup_steps_analysis>
If `.github/workflows/copilot-setup-steps.yml` exists, analyze its efficiency:

1. **Dependency Alignment**:
   - Check if installed dependencies match actual project usage
   - Identify unused tools being installed
   - Find missing tools that cause Copilot failures
   - Verify version specifications are current

2. **Performance Metrics**:
   - Measure current setup execution time
   - Identify slowest steps
   - Check cache effectiveness
   - Find redundant operations

3. **Step Optimization**:
   - Consolidate related installations
   - Parallelize independent steps
   - Optimize cache usage
   - Remove unnecessary builds
</setup_steps_analysis>

<optimization_techniques>
1. **Dependency Pruning**:
   ```yaml
   # Before: Installing everything
   - name: Install Python dependencies
     run: |
       pip install -r requirements.txt
       pip install -r requirements-dev.txt
       pip install -r requirements-test.txt
   
   # After: Only what Copilot needs
   - name: Install Python dependencies
     run: |
       pip install -r requirements.txt
       pip install pytest black  # Only essential dev tools
   ```

2. **Caching Enhancement**:
   ```yaml
   # Optimize caching with hash keys
   - name: Cache dependencies
     uses: actions/cache@v3
     with:
       path: ~/.npm
       key: ${{ runner.os }}-npm-${{ hashFiles('**/package-lock.json') }}
       restore-keys: |
         ${{ runner.os }}-npm-
   ```

3. **Parallel Execution**:
   ```yaml
   # Run independent steps concurrently
   - name: Install tools in parallel
     run: |
       npm ci &
       pip install -r requirements.txt &
       wait
   ```

4. **Conditional Steps**:
   ```yaml
   # Only run expensive steps when needed
   - name: Build project
     if: hashFiles('src/**/*.ts') != ''
     run: npm run build
   ```
</optimization_techniques>

<size_analysis>
Monitor setup steps file size and complexity:
- Total lines: Should be under 150 for maintainability
- Number of steps: Aim for under 10 distinct steps
- Execution time: Target under 5 minutes total
- Cache size: Keep under GitHub's limits
</size_analysis>

<common_optimizations>
1. **Package Manager Optimization**:
   - Use `npm ci` instead of `npm install`
   - Use `--frozen-lockfile` for yarn/pnpm
   - Use `pip install --no-deps` when possible
   - Leverage `actions/setup-*` caching

2. **Build Optimization**:
   - Skip builds if only running tests
   - Use incremental builds
   - Cache build outputs
   - Defer optional compilations

3. **Tool Installation**:
   - Install only formatters/linters Copilot uses
   - Use pre-built tool versions
   - Combine related tool installations
   - Avoid global installations when possible

4. **Environment Setup**:
   - Only set variables Copilot needs
   - Use repository variables over secrets when possible
   - Minimize secret exposure
   - Group related configurations
</common_optimizations>

<validation_checklist>
After optimization, verify:
□ Setup completes in under 10 minutes
□ All necessary tools are available to Copilot
□ Caching reduces subsequent run times
□ No redundant or unused installations
□ Environment matches production needs
□ Works with repository's actual structure
</validation_checklist>

<thinking_prompt>
When optimizing setup steps, consider:
- Is every installed dependency actually used by Copilot?
- Can build steps be deferred or made conditional?
- Are we caching effectively to speed up subsequent runs?
- Do the setup steps align with how developers actually work?
- Could larger runners provide better cost/performance ratio?
</thinking_prompt>
</phase>

<phase id="3" name="Rewriting for Conciseness">
<objective>Rewrite instructions for maximum impact with minimum words</objective>

<rewriting_principles>
Transform verbose instructions into concise, powerful guidance using these techniques:

1. **Imperative Over Explanatory**:
   ```markdown
   <!-- Before (25 words) -->
   "It's important to handle errors appropriately by logging them with context 
   and returning user-friendly messages rather than exposing internal details"
   
   <!-- After (10 words) -->
   "Log errors with context. Return user-friendly messages, never internal details."
   ```

2. **Examples Over Descriptions**:
   ```markdown
   <!-- Before (40 words) -->
   "When naming variables, use descriptive names that clearly indicate the 
   purpose and content of the variable. Avoid single letters except for 
   loop counters, and don't use abbreviations that aren't widely understood."
   
   <!-- After (15 words + example) -->
   "Use descriptive variable names:
   ✅ `userAuthToken`, `calculateTotalPrice`  
   ❌ `token`, `calc`, `usr`"
   ```

3. **Structured Lists Over Paragraphs**:
   ```markdown
   <!-- Before (paragraph form) -->
   "Every API endpoint should validate input, check authentication, perform
   the operation, handle errors appropriately, and return consistent responses"
   
   <!-- After (structured list) -->
   API endpoints must:
   1. Validate input structure/types
   2. Verify authentication/permissions
   3. Execute operation with error handling
   4. Return consistent Result<T> responses
   ```

4. **Implicit Context**:
   ```markdown
   <!-- Before -->
   "When writing React components, always use functional components with hooks
   instead of class components, unless you specifically need class component features"
   
   <!-- After -->
   "Use functional components with hooks" 
   // (React context is implicit from file extension)
   ```
</rewriting_principles>

<conciseness_checklist>
For each rewritten instruction, verify:
□ Can any words be removed without losing meaning?
□ Is passive voice making it wordier than necessary?
□ Can multiple sentences be combined?
□ Would a code example be clearer than explanation?
□ Are we stating the obvious?
□ Is context implicit from file types or patterns?
</conciseness_checklist>

<example_transformation>
Here's a complete transformation of a verbose section into concise guidance:

**Original Version** (120 words):
```markdown
## Error Handling Best Practices

It's crucial to implement comprehensive error handling throughout the application.
When errors occur, they should be logged with sufficient context to aid in debugging.
This includes relevant IDs, operation names, and any pertinent data. However, be 
careful not to log sensitive information like passwords or API keys. 

For user-facing errors, always return messages that are helpful but don't expose
internal system details. Use custom error classes to categorize different types
of errors, and ensure that async operations properly propagate errors up the
call stack using appropriate patterns like Result types or try-catch blocks.
```

**Optimized Version** (45 words + code):
```markdown
## Error Handling

Every async operation must handle errors:

```typescript
try {
  const result = await operation();
  return Result.ok(result);
} catch (error) {
  logger.error('Operation failed', { id, error, context });
  return Result.error(new PublicError('Operation failed'));
}
```

Never: Log sensitive data, expose internal errors to users, throw without catching.
```
</example_transformation>
</phase>

<phase id="4" name="Priority-Based Reconstruction">
<objective>Rebuild instructions from highest to lowest impact within size constraints</objective>

<reconstruction_methodology>
Think of this like packing for a trip with limited luggage space. You start with absolute essentials, then add items based on their value-to-space ratio until you reach capacity:

1. **Foundation Layer** (Must have, ~200 lines):
   - Security imperatives
   - Error handling patterns
   - Data integrity rules
   - Core architectural boundaries

2. **Enhancement Layer** (Should have, ~200 lines):
   - Common operation patterns
   - Testing requirements
   - Performance guidelines
   - Team conventions

3. **Optimization Layer** (Nice to have, ~100 lines):
   - Code organization preferences
   - Advanced patterns
   - Style guidelines
   - Productivity tips

As you rebuild, constantly measure against the 500-line limit, leaving a 10% buffer for future critical additions.
</reconstruction_methodology>

<reconstruction_template>
<file_path>.github/copilot-instructions.md</file_path>
<format>
# Project Coding Standards for AI Assistance

> Essential patterns preventing errors and ensuring quality. Every instruction here has proven impact.

## 🔒 Security Imperatives

**Input Validation**: Validate at boundaries, sanitize before storage
```typescript
// Always validate and sanitize
const userId = validateUuid(input.userId);
const comment = sanitizeHtml(input.comment);
```

**Authentication**: Verify permissions before operations
```typescript
if (!user.can('edit', resource)) throw new ForbiddenError();
```

Never: Trust client IDs, log sensitive data, expose internal errors

## ⚡ Error Handling

All async operations return Result<T, Error>:
```typescript
async function operation(): Promise<Result<Data, AppError>> {
  try {
    return Result.ok(await perform());
  } catch (error) {
    logger.error('Failed', { context, error });
    return Result.error(new AppError('Operation failed'));
  }
}
```

## 🏗️ Architecture Rules

**Layer Boundaries**: Controllers → Services → Repositories
- Controllers: HTTP only (validation, routing, response mapping)
- Services: Business logic only (no HTTP, no direct DB)
- Repositories: Data access only (no business logic)

**Dependency Flow**: Always inward, never circular
```
Presentation → Application → Domain → Infrastructure
         ❌ ←              ❌ ←           ❌ ←
```

[Continue with highest impact instructions only...]
</format>
</reconstruction_template>

<size_monitoring>
Track size throughout reconstruction:
```
Target Distribution:
├─ Security & Errors: ~150 lines (critical foundation)
├─ Architecture: ~100 lines (system integrity)
├─ Common Patterns: ~150 lines (daily usage)
├─ Testing & Quality: ~80 lines (long-term health)
└─ Buffer: ~20 lines (future additions)
Total: 500 lines
```
</size_monitoring>

<thinking_prompt>
During reconstruction, constantly ask:
- Is this instruction preventing real errors or just enforcing preferences?
- Could this guidance be inferred from examples in other sections?
- Will removing this instruction lead to actual problems in production?
- Is this the most concise way to convey this critical information?
</thinking_prompt>
</phase>

<phase id="5" name="Integration Testing">
<objective>Verify optimized instructions maintain effectiveness while respecting constraints</objective>

<testing_scenarios>
Test the optimized instructions through realistic development scenarios:

1. **New Developer Test**:
   - Give instructions to someone unfamiliar with codebase
   - Can they write acceptable code using only these instructions?
   - What critical patterns do they miss?
   - What questions do they still have?

2. **Common Task Test**:
   Generate code for frequent operations:
   - Create new API endpoint
   - Add database operation
   - Write component tests
   - Handle async errors
   
   Verify all generated code follows critical patterns.

3. **Edge Case Test**:
   - Try generating code for less common scenarios
   - Note where lack of instructions causes issues
   - Determine if those issues justify adding instructions

4. **Constraint Test**:
   - Verify total size remains under 500 lines
   - Ensure instructions + typical code fit in context
   - Test with various file types and sizes
</testing_scenarios>

<effectiveness_metrics>
Measure optimization success through:

1. **Size Reduction**: 
   - Original: [X] lines
   - Optimized: [Y] lines  
   - Reduction: [Z]%

2. **Coverage Maintenance**:
   - Critical patterns covered: [X of Y]
   - Security guidelines: [Complete/Partial]
   - Architecture rules: [Complete/Partial]

3. **Clarity Improvement**:
   - Average words per instruction: [before] → [after]
   - Example-to-explanation ratio: [before] → [after]
   - Actionable vs descriptive: [ratio]

4. **Real-world Impact**:
   - Generate sample code before/after optimization
   - Compare quality and pattern adherence
   - Note any degradation in AI suggestions
</effectiveness_metrics>
</phase>

<phase id="6" name="Documentation and Rollout">
<objective>Document optimization decisions and prepare for team adoption</objective>

<optimization_report>
<file_path>.github/copilot-optimization-report-[DATE].md</file_path>
<format>
# Copilot Instructions Optimization Report - [DATE]

## Executive Summary
- Reduced instructions from [X] to [Y] lines ([Z]% reduction)
- Maintained coverage of all critical patterns
- Improved clarity through examples over explanations
- Created [X] lines of buffer for future additions

## Optimization Decisions

### High-Impact Preservations
These instructions remained due to preventing critical errors:
1. **Input validation rules** - Prevents security vulnerabilities
2. **Error handling patterns** - Ensures system reliability
3. **Architecture boundaries** - Maintains system integrity

### Strategic Consolidations
Successfully merged related instructions:
1. **Security patterns** - Combined 5 rules into 1 comprehensive section
2. **Testing requirements** - Unified test patterns into single example
3. **Async operations** - Merged error handling with Result types

### Difficult Cuts
Instructions removed despite some value:
1. **Style preferences** - Moved to documentation (saved 40 lines)
2. **Advanced patterns** - Available in Claude Code context (saved 30 lines)
3. **Edge cases** - Covered by Cursor rules when needed (saved 25 lines)

## Impact Validation
- Generated 10 sample components before/after
- All critical patterns still followed
- No degradation in security practices
- Slight reduction in style consistency (acceptable tradeoff)

## Rollout Plan
1. Deploy to pilot group for 1 week
2. Gather feedback on any missing critical guidance
3. Adjust based on real-world usage
4. Full team deployment with communication

## Future Maintenance
- Review quarterly for new critical patterns
- Monitor which removed instructions get re-requested
- Track effectiveness through PR quality metrics
</format>
</optimization_report>

<team_communication>
Prepare clear communication about the optimization:

```markdown
Subject: Copilot Instructions Optimized - More Impact, Less Noise

Team,

We've optimized our GitHub Copilot instructions to be more focused and effective. Here's what changed:

**What We Did**:
- Reduced from [X] to [Y] lines (more room for your actual code!)
- Kept ALL security and error handling guidance
- Consolidated related patterns for easier scanning
- Replaced explanations with clear examples

**What This Means**:
- Copilot suggestions remain high quality for critical patterns
- Less scrolling through instructions to find what matters
- More context available for complex code generation
- Clearer, more actionable guidance

**What We Removed**:
- Style preferences (still in docs if needed)
- Detailed explanations (examples show the way)
- Edge cases (Cursor handles these contextually)
- Redundant instructions (consolidated into themes)

**Action Items**:
1. Pull latest `.github/copilot-instructions.md`
2. Review the streamlined instructions
3. Report any critical patterns we missed
4. Enjoy more effective AI assistance!

The goal was maximizing impact while minimizing noise. Every remaining instruction prevents real errors or ensures critical quality. Let us know if you notice any gaps in the optimized set.
```
</team_communication>
</phase>

<execution_instruction>
Begin by thoroughly analyzing current Copilot instructions to understand their real-world impact. Use the scoring framework to objectively evaluate each instruction's value, being ruthlessly honest about what actually prevents errors versus what merely sounds good.

Remember that optimization isn't just about making things smaller - it's about making them more powerful. Every word that remains should work harder than before. Think of yourself as a sculptor, removing everything that isn't essential to reveal the powerful guidance within.

Throughout this process, maintain deep empathy for developers who rely on these instructions daily. The optimized set should feel like a helpful friend who knows exactly when to offer advice and when to stay quiet. The best optimization is one where developers don't notice anything missing, only that their AI assistance feels more natural and effective.

Your optimization should create instructions so essential and well-crafted that removing any line would be immediately noticed as a loss. This is the art of minimalism - achieving maximum impact through minimum content.
</execution_instruction>