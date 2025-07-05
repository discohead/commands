<user_request>
Please transform the discovered patterns and workflows from Claude Code context into actionable Cursor MDC rules. Execute the rule generation process outlined below immediately.
</user_request>

<task_confirmation>
This command is your instruction to actively generate Cursor rules now. You should begin by reading the Claude Code context files and proceed through all phases without waiting for additional input.
</task_confirmation>

<system_role>
You are an expert AI behavior architect specializing in creating precise, actionable rules for AI coding assistants. You transform discovered patterns into behavioral guidance that shapes AI output quality, distinguishing between reference knowledge and active behavioral rules.
</system_role>

<task_overview>
Transform the comprehensive Claude Code context architecture into a complementary set of Cursor MDC rules. These rules will actively guide AI behavior during code generation, ensuring consistent application of discovered patterns and preventing common mistakes.
</task_overview>

<critical_principles>
- Rules guide behavior; context stores knowledge
- Every rule must be actionable and specific
- Prioritize preventing errors over documenting features
- Balance comprehensiveness with context window limitations
- Include concrete examples showing right vs wrong approaches
- Make rules self-contained
</critical_principles>

<immediate_action>
Start by reading .claude/context/discovered-patterns.md, .claude/context/architecture/system-design.md, .claude/context/workflows/*, and the enhanced CLAUDE.md to understand which patterns should become behavioral rules. Begin this analysis now.
</immediate_action>

<prerequisite_reading>
Before proceeding, read and internalize:
1. `.claude/context/discovered-patterns.md` - Coding patterns and conventions
2. `.claude/context/architecture/system-design.md` - Architectural principles
3. `.claude/context/workflows/*` - Standard development workflows
4. `CLAUDE.md` - Critical patterns summary

Note: If CLAUDE.md mentions DeepWiki MCP availability, remember it as a supplemental resource for complex questions.

Identify which patterns represent:
- Unbreakable conventions (→ Always Rules)
- Context-specific patterns (→ Auto-Attached Rules)
- Complex procedures (→ Agent-Requested Rules)
- Edge cases (→ Manual Rules)
</prerequisite_reading>

<phase id="1" name="Rule Categorization">
<objective>Transform discovered knowledge into a strategic rule hierarchy</objective>

<categorization_framework>
<category name="Always Rules" context_cost="High" application="Universal">
<criteria>
- Applied to EVERY code generation
- Total size must be <500 lines across all always rules
- Only include if violation would break core conventions
- Must prevent frequent or critical errors
</criteria>
</category>

<category name="Auto-Attached Rules" context_cost="Medium" application="Contextual">
<criteria>
- Applied when specific file patterns are in context
- Can be more detailed than always rules
- Should prevent context-specific mistakes
</criteria>
</category>

<category name="Agent-Requested Rules" context_cost="Low" application="On-Demand">
<criteria>
- AI decides when to include based on task
- For complex, multi-step procedures
- Must include clear description for AI to recognize need
</criteria>
</category>

<category name="Manual Rules" context_cost="Zero" application="User-Triggered">
<criteria>
- Only included when explicitly requested
- For rare or dangerous operations
- Legacy system knowledge
</criteria>
</category>
</categorization_framework>

<thinking_prompt>
Consider:
- What errors repeat in the codebase?
- Which broken conventions immediately identify code as "not from this team"?
- What's the minimum ruleset for AI code to match team code?
- How to maximize impact while minimizing context usage?
</thinking_prompt>
</phase>

<phase id="2" name="Rule Structure Design">
<objective>Create optimal directory structure for rule organization</objective>

<structure_template>
```
.cursor/rules/
├── always/                      # Universal rules (<500 lines total)
│   ├── core-conventions.mdc     # Naming, structure, organization
│   ├── architecture-principles.mdc # Boundaries, dependencies, flow
│   └── code-quality.mdc         # Error handling, testing, docs
├── components/                  # Auto-attached by component type
│   ├── controllers.mdc          # **/*Controller.{ts,js}
│   ├── services.mdc             # **/*Service.{ts,js}
│   ├── models.mdc               # **/models/*.{ts,js}
│   └── repositories.mdc         # **/*Repository.{ts,js}
├── features/                    # Domain-specific rules
│   ├── authentication.mdc       # **/auth/**/*.{ts,js}
│   ├── api-design.mdc           # **/api/**/*.{ts,js}
│   └── data-validation.mdc      # Validation patterns
└── workflows/                   # Agent-requested procedures
    ├── new-feature.mdc          # Complete feature addition
    ├── refactoring.mdc          # Safe refactoring patterns
    └── debugging.mdc            # Debugging approaches
```
</structure_template>
</phase>

<phase id="3" name="Rule Creation">
<objective>Transform patterns into precise MDC rules with optimal impact</objective>

<mdc_template>
```mdc
---
description: [One sentence explaining when/why AI should apply this rule]
globs: [Optional: File patterns like "**/*Controller.ts"]
alwaysApply: [true for always rules, false otherwise]
---

# [Rule Category Name]

[2-3 sentences explaining the principle behind these rules]

## [Specific Rule 1]
[Precise, actionable instruction]

✅ **Correct:**
```[language]
[Code example showing the right way]
```

❌ **Incorrect:**
```[language]
[Code example showing common mistakes]
```

## [Specific Rule 2]
[Continue with other critical rules...]

@[reference-file.ts] [Optional: Include for complex patterns]
```
</mdc_template>

<rule_writing_guidelines>
1. Start with the most impactful rules
2. Show, don't just tell - examples required
3. Be prescriptive - "You must..." not "It's common to..."
4. Include brief rationale (aids AI reasoning)
5. Keep scannable - use headers and formatting
6. Test for clarity - must work without other context
</rule_writing_guidelines>

<example_rule>
<file_path>.cursor/rules/always/core-conventions.mdc</file_path>
<content>
```mdc
---
description: Core naming and structure conventions that apply to all code
globs: []
alwaysApply: true
---

# Core Coding Conventions

These conventions ensure consistency across our entire codebase and make code immediately recognizable as belonging to this project.

## Variable and Function Naming

Use descriptive camelCase names that clearly indicate purpose.

✅ **Correct:**
```javascript
const userAuthToken = generateToken(user);
function calculateTotalPrice(items) { }
```

❌ **Incorrect:**
```javascript
const token = generate(u);  // Too vague
function calc(i) { }         // Unclear purpose
```

## Async Operation Patterns

Always use async/await over promises for better readability and error handling.

✅ **Correct:**
```javascript
async function fetchUserData(userId) {
  try {
    const user = await userRepository.findById(userId);
    return user;
  } catch (error) {
    logger.error('Failed to fetch user:', error);
    throw new UserNotFoundError(userId);
  }
}
```

❌ **Incorrect:**
```javascript
function fetchUserData(userId) {
  return userRepository.findById(userId)
    .then(user => user)
    .catch(error => {
      throw error; // No logging, generic error
    });
}
```

## External Resources

When facing complex architectural questions, DeepWiki MCP may be available as @deepwiki for additional perspective.
```
</content>
</example_rule>
</phase>

<phase id="4" name="Component-Specific Rules">
<objective>Create targeted rules for each major component type</objective>

<component_analysis_framework>
For each component type:
1. Identify unique patterns that only apply to this component
2. Extract conventions that would be wrong elsewhere
3. Document relationships with other components
4. Specify required elements (methods, properties, etc.)
</component_analysis_framework>

<example_component_rule>
<file_path>.cursor/rules/components/controllers.mdc</file_path>
<content>
```mdc
---
description: REST controller implementation patterns and requirements
globs: ["**/*Controller.ts", "**/*Controller.js", "**/controllers/*.{ts,js}"]
alwaysApply: false
---

# Controller Implementation Rules

Controllers in this codebase follow strict RESTful patterns and handle HTTP concerns only. Business logic must be delegated to services.

## Required Controller Structure

Every controller must follow this pattern:

✅ **Correct:**
```typescript
@Controller('/users')
export class UserController {
  constructor(
    private readonly userService: UserService,
    private readonly validator: ValidationService
  ) {}

  @Get('/:id')
  @UseGuards(AuthGuard)
  async getUser(@Param('id') id: string): Promise<UserResponse> {
    // 1. Validate input
    const validatedId = this.validator.validateUuid(id);
    
    // 2. Delegate to service
    const user = await this.userService.findById(validatedId);
    
    // 3. Transform to response DTO
    return UserResponse.fromDomain(user);
  }
}
```

## Controller Responsibilities

Controllers MUST ONLY handle:
1. HTTP parameter extraction
2. Input validation coordination
3. Service method delegation  
4. Response transformation

Controllers MUST NOT:
- Contain business logic
- Access repositories directly
- Handle transactions
- Make decisions beyond HTTP routing
```
</content>
</example_component_rule>
</phase>

<phase id="5" name="Workflow Automation Rules">
<objective>Transform multi-step workflows into agent-requestable procedures</objective>

<workflow_transformation_process>
1. Take each workflow from .claude/context/workflows/
2. Add decision points and error handling
3. Include validation steps
4. Reference relevant always/auto rules
5. Provide complete, runnable examples
</workflow_transformation_process>

<example_workflow_rule>
<file_path>.cursor/rules/workflows/new-feature.mdc</file_path>
<content>
```mdc
---
description: Complete guide for implementing a new feature following all conventions
globs: []
alwaysApply: false
---

# New Feature Implementation Workflow

Follow these steps to add a new feature while maintaining all architectural patterns and conventions.

## Step 1: Design API Contract

First, design your API endpoints following RESTful conventions:

```typescript
// In api-spec.ts or similar
interface TodoEndpoints {
  'GET /todos': { response: TodoDto[] };
  'GET /todos/:id': { params: { id: string }, response: TodoDto };
  'POST /todos': { body: CreateTodoDto, response: TodoDto };
  'PUT /todos/:id': { params: { id: string }, body: UpdateTodoDto, response: TodoDto };
  'DELETE /todos/:id': { params: { id: string }, response: void };
}
```

## Step 2: Create Domain Model

Define your domain model with validation:

```typescript
// In src/models/Todo.ts
export class Todo {
  constructor(
    public readonly id: string,
    public title: string,
    public completed: boolean,
    public createdAt: Date
  ) {
    this.validate();
  }

  private validate(): void {
    if (!this.title || this.title.trim().length === 0) {
      throw new ValidationError('Todo title cannot be empty');
    }
  }
}
```

[Continue with remaining steps...]
```
</content>
</example_workflow_rule>
</phase>

<phase id="6" name="Rule Optimization">
<objective>Ensure the rule system is efficient and maintainable</objective>

<optimization_checklist>
□ Size Check: Total always rules < 500 lines?
□ Overlap Analysis: Any rules covering the same topic?
□ Glob Coverage: Do patterns match intended files without over-matching?
□ Description Clarity: Would an AI understand when to apply each rule?
□ Example Quality: Does each rule have clear correct/incorrect examples?
□ Completeness: Do rules cover all critical patterns from context?
□ Independence: Can each rule be understood without reading others?
</optimization_checklist>
</phase>

<phase id="7" name="Documentation">
<objective>Create README documenting rule system</objective>

<output_artifact>
<file_path>.cursor/rules/README.md</file_path>
<format>
# Cursor Rules Guide

## Overview
These MDC rules complement the Claude Code context by providing active behavioral guidance during code generation.

## Rule Organization
- `/always` - Universal conventions applied to all code
- `/components` - Component-specific patterns (auto-attached by file type)
- `/features` - Domain and feature-specific rules
- `/workflows` - Multi-step procedures for complex tasks

## How Rules Relate to Claude Code Context
| Claude Code Context | Cursor Rules | Purpose |
|-------------------|--------------|---------|
| `.claude/context/discovered-patterns.md` | `/always/core-conventions.mdc` | Enforce discovered patterns |
| `.claude/context/architecture/` | `/always/architecture-principles.mdc` | Maintain architectural boundaries |
| `.claude/context/workflows/` | `/workflows/*.mdc` | Guide complex procedures |

## Additional Resources
If DeepWiki MCP is available (@deepwiki), it can provide supplemental context for complex architectural questions.

## Quick Reference
| Rule File | Applies To | Key Patterns |
|-----------|------------|--------------|
| `core-conventions.mdc` | All files | Naming, async patterns, imports |
| `controllers.mdc` | `*Controller.{ts,js}` | REST patterns, no business logic |
| [Continue for all rules...] |

## Maintenance
- Update rules when patterns evolve
- Test rules by generating code and checking compliance
- Keep rules in sync with Claude Code context
</format>
</output_artifact>
</phase>

<quality_standards>
Excellent Cursor rules are:
- **Prescriptive**: Tell the AI exactly what to do
- **Preventive**: Stop errors before they happen
- **Precise**: No room for misinterpretation
- **Practical**: Based on real patterns and problems
- **Performant**: Minimal context for maximum impact
</quality_standards>

<execution_instruction>
Begin by analyzing your Claude Code context files and creating a comprehensive categorization of patterns into rule types. Show me your categorization analysis first, explaining your reasoning for each decision. Then proceed to create each rule file, providing commentary on why you've made specific choices about rule content and organization.

Focus on creating rules that will make AI-generated code indistinguishable from code written by your team's best developers. Every rule should earn its place by preventing errors or ensuring consistency.
</execution_instruction>

<execution_reminder>
You are now actively generating Cursor rules. Begin with your categorization of discovered patterns and proceed through each phase systematically, creating all specified rule files. This command is your complete authorization to generate the complete Cursor rules system.
</execution_reminder>