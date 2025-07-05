<user_request>
Please create GitHub Copilot instructions that complement the Claude Code context and Cursor rules by distilling essential patterns into persistent guidance. Execute the instruction generation process outlined below immediately.
</user_request>

<task_confirmation>
This command is your instruction to actively generate Copilot instructions now. You should begin by analyzing the existing AI assistant ecosystem and proceed through all phases without waiting for additional input.
</task_confirmation>

<system_role>
You are an expert instruction architect specializing in optimizing AI pair programming experiences. You excel at crafting persistent instructions that guide AI behavior without overwhelming context windows, creating instructions that feel like having the team's best developer whispering helpful reminders at just the right moments.
</system_role>

<task_overview>
Complete the AI coding assistant ecosystem by creating GitHub Copilot instructions that complement Claude Code context (comprehensive knowledge) and Cursor rules (active behavioral guidance). You'll distill discovered patterns into Copilot's unique persistent instruction system - creating focused, always-present guidance that makes Copilot truly understand your project.
</task_overview>

<copilot_philosophy>
Copilot instructions differ fundamentally from other AI tools:
- **Persistent**: Present in EVERY interaction, so must be essential
- **Focused**: Limited context window demands ruthless prioritization  
- **Prescriptive**: Direct commands, not reference documentation
- **Practical**: Must improve the most common coding scenarios
- **Invisible**: Should feel natural, not like following a checklist

Think of Copilot instructions like muscle memory for the AI - patterns so internalized that following them feels automatic.
</copilot_philosophy>

<immediate_action>
Start by reading the enhanced CLAUDE.md, claude/discovered-patterns.md, .cursor/rules/always/*.mdc, and key workflow files to understand what patterns should become persistent Copilot guidance. Begin this analysis now.
</immediate_action>

<prerequisite_analysis>
Before proceeding, analyze your existing AI assistant ecosystem:

1. **From CLAUDE.md**: Identify the 20% of patterns that affect 80% of code
2. **From discovered-patterns.md**: Extract patterns that prevent the most errors
3. **From .cursor/rules/always/**: Find rules that MUST be in every interaction
4. **From workflows/**: Identify steps that could be automated with smart defaults

Note: If CLAUDE.md mentions DeepWiki MCP, remember it as a supplemental resource for complex questions.

Categorize patterns by Copilot suitability:
- ✅ **Perfect**: Universal, concise, high-impact
- ⚠️ **Maybe**: Task-specific but important
- ❌ **Exclude**: Complex, contextual, or verbose
</prerequisite_analysis>

<phase id="1" name="Core Instructions Design">
<objective>Create the primary instruction file with maximum impact per line</objective>

<instruction_prioritization_framework>
**Must Include**:
- Patterns preventing security vulnerabilities
- Conventions used in >75% of files
- Error handling preventing production issues
- Naming patterns ensuring consistency

**Should Include**:
- Framework-specific patterns used frequently
- Testing patterns ensuring quality
- Documentation standards

**Consider Including**:
- Performance optimizations
- Advanced patterns for specific scenarios
- Team preferences improving readability
</instruction_prioritization_framework>

<structure_template>
<file_path>.github/copilot-instructions.md</file_path>
<format>
# Project Coding Standards for AI Assistance

> These instructions are automatically included in every GitHub Copilot interaction. They represent our most critical patterns and conventions.

## Core Principles
1. **[Principle Name]**: [One sentence explanation]
   - [Specific implementation detail]
   - [Example or clarification]

## Language and Framework Guidelines

### [Primary Language] Essentials
- **Naming**: [Specific patterns with examples]
- **Structure**: [How code should be organized]
- **Idioms**: [Language-specific patterns to follow]

### [Primary Framework] Patterns
- **Component Structure**: [Required elements and order]
- **State Management**: [How to handle state]
- **Side Effects**: [Where and how to handle]

## Code Generation Rules

When generating code, you MUST:
1. [Absolute requirement #1]
   ```[language]
   // Example showing correct implementation
   ```

2. [Absolute requirement #2]
   ```[language]
   // Example showing correct implementation
   ```

When generating code, NEVER:
- [Common mistake to avoid]
- [Anti-pattern to prevent]

## Testing Requirements

Every test must:
- Use descriptive names: `test('should [behavior] when [condition]')`
- Include arrange-act-assert structure
- Test edge cases, not just happy paths

## Documentation Standards

- Functions need JSDoc only if behavior isn't obvious from name
- Complex logic requires inline comments explaining "why"
- No redundant comments that repeat what code clearly shows

## Security and Performance

ALWAYS:
- Validate input at system boundaries
- Use parameterized queries for database access
- Handle errors with appropriate logging

NEVER:
- Log sensitive data (passwords, tokens, PII)
- Trust client-provided IDs without validation
- Use synchronous operations for I/O in event loops

## Additional Resources

DeepWiki MCP (@deepwiki) may be available for architectural questions and external perspective when needed.
</format>
</structure_template>

<instruction_writing_principles>
1. **Every line must earn its place** - Cut anything that doesn't prevent errors
2. **Show with examples** - One code example worth ten explanations
3. **Be absolute** - Use MUST/NEVER, not "should"
4. **Focus on the frequent** - Optimize for daily code
5. **Make it scannable** - Find what you need in seconds
</instruction_writing_principles>

<size_optimization>
To stay under 500 lines:
- Combine related rules into dense statements
- Use examples demonstrating multiple principles
- Remove unnecessary explanations
- Focus on what to do, not why
</size_optimization>
</phase>

<phase id="2" name="Specialized Instruction Files">
<objective>Create task-specific instructions that enhance without duplicating core</objective>

<specialization_strategy>
Copilot's specialized instructions map to developer tasks:
- **Code Generation**: Patterns for creating new code
- **Test Generation**: Patterns for writing tests
- **Code Review**: What to check and flag
- **Refactoring**: Safe transformation patterns
</specialization_strategy>

<example_specialized_instruction>
<file_path>.github/instructions/test-generation.instructions.md</file_path>
<content>
```markdown
---
applyTo: "**/*.test.*, **/*.spec.*, **/test/**, **/tests/**"
---
# Test Generation Guidelines

Apply all [general standards](../copilot-instructions.md) with these test-specific additions:

## Test Structure Pattern
```javascript
describe('ComponentName', () => {
  describe('methodName', () => {
    it('should return expected value when given valid input', () => {
      // Arrange
      const input = createValidInput();
      const expected = createExpectedOutput();
      
      // Act
      const result = component.method(input);
      
      // Assert
      expect(result).toEqual(expected);
    });
    
    it('should throw error when given invalid input', () => {
      // Edge cases always tested
    });
  });
});
```

## Test Data Builders
Always use builder pattern for test data:
```javascript
const userBuilder = () => ({
  id: 'test-id',
  name: 'Test User',
  email: 'test@example.com',
  with: (overrides) => ({ ...userBuilder(), ...overrides })
});
```

## Mock Patterns
- Mock at architectural boundaries only
- Use real implementations when possible
- Name mocks clearly: `mockUserRepository`
```
</content>
</example_specialized_instruction>
</phase>

<phase id="3" name="Prompt Files for Common Tasks">
<objective>Transform complex workflows into reusable, parameterized prompts</objective>

<prompt_file_strategy>
Prompts differ from instructions:
- **Instructions**: Shape all AI behavior unconsciously
- **Prompts**: Guide complex, multi-step tasks

Choose workflows that:
1. Require multiple coordinated steps
2. Have specific patterns that must be followed
3. Are performed frequently
4. Benefit from parameterization
</prompt_file_strategy>

<example_prompt_file>
<file_path>.github/prompts/add-api-endpoint.prompt.md</file_path>
<content>
```markdown
---
mode: 'agent'
tools: ['codebase', 'terminalLastCommand']
description: 'Add a new REST API endpoint following all conventions'
---

Create a new ${input:httpMethod} endpoint at ${input:path} for ${input:resourceName}.

## Step 1: Design the API Contract
First, define the endpoint interface:
- Request: ${input:requestDescription}
- Response: ${input:responseDescription}
- Authentication: ${input:authRequired:Yes|No}

## Step 2: Create Route Handler
Add to `src/routes/${input:resourceName}.routes.js`:
```javascript
router.${input:httpMethod|lowercase}('${input:path}', 
  ${input:authRequired|Yes:authenticate, }
  validate(${input:resourceName}Validation.${input:operation}),
  async (req, res, next) => {
    try {
      const result = await ${input:resourceName}Service.${input:operation}(req.body);
      res.json(ResponseMapper.toDto(result));
    } catch (error) {
      next(error);
    }
  }
);
```

[Continue with remaining steps...]
```
</content>
</example_prompt_file>
</phase>

<phase id="4" name="Integration Strategy">
<objective>Document how all three AI systems work together</objective>

<integration_documentation_template>
<file_path>.github/copilot-instructions-guide.md</file_path>
<content>
# GitHub Copilot Instructions Integration Guide

## The AI Assistant Ecosystem

Our project uses three complementary AI systems:

| System | Primary Role | When Active | Best For |
|--------|-------------|-------------|----------|
| **Claude Code** | Knowledge Repository | On-demand via CLI | Research, analysis, complex refactoring |
| **Cursor** | Active Behavioral Guide | During focused coding | Following patterns, preventing errors |
| **Copilot** | Persistent Pair Programmer | Always while typing | Quick completions, following conventions |

### How They Work Together

```
Claude Code (Knowledge) → Cursor Rules (Behavior) → Copilot Instructions (Habits)
     ↓                          ↓                            ↓
Deep understanding      Context-aware guidance      Persistent reminders
```

### When to Update Each System

1. **New Pattern Discovered**:
   - Document thoroughly in Claude Code context
   - Add behavioral rule to Cursor if context-specific
   - Add to Copilot instructions only if universal

2. **Common Error Found**:
   - Analyze root cause in Claude Code
   - Create preventive rule in Cursor
   - Add reminder to Copilot if frequent

### Quick Decision Guide

**Should this go in Copilot instructions?**
- Used in >50% of coding tasks? → Yes
- Prevents critical errors? → Yes  
- Under 3 lines to explain? → Yes
- Complex or contextual? → No, use Cursor
- Reference documentation? → No, use Claude Code
</content>
</integration_documentation_template>
</phase>

<phase id="5" name="Optimization and Testing">
<objective>Ensure instructions achieve maximum impact with minimum overhead</objective>

<optimization_checklist>
□ Size Validation: Core instructions < 500 lines?
□ Duplication Check: No repeated information across files?
□ Impact Analysis: Every instruction prevents errors or ensures quality?
□ Clarity Test: Instructions understandable without context?
□ Integration Check: Clear distinction from Cursor/Claude Code?
□ Prompt Value: Each prompt file saves >5 minutes vs manual?
</optimization_checklist>

<testing_framework>
**Isolation Test**: Generate code with ONLY Copilot instructions active
- Should follow all critical conventions
- Handle errors appropriately
- Be production-ready for common cases

**Specialization Test**: Activate specialized instructions for specific tasks
- Test generation should create comprehensive suites
- Code review should catch common issues

**Degradation Test**: Remove instructions to find minimal effective set
- What breaks first? (Critical instructions)
- What has no impact? (Remove these)
</testing_framework>
</phase>

<quality_principles>
Exceptional Copilot instructions are:
- **Essential**: Every line prevents problems or ensures quality
- **Invisible**: Feel natural, not like following a checklist
- **Persistent**: Valuable in every coding session
- **Complementary**: Enhance rather than duplicate other tools
- **Maintainable**: Easy to update as patterns evolve
</quality_principles>

<execution_instruction>
Begin by analyzing your AI assistant ecosystem to identify what truly belongs in Copilot's persistent context. Show me your analysis of:

1. Which patterns from Claude Code are universal enough for Copilot
2. Which Cursor rules should become persistent instructions
3. What gaps Copilot instructions need to fill

Then create each instruction file, explaining your decisions about what to include and—equally importantly—what to deliberately exclude. Remember: Copilot instructions are like muscle memory for the AI. Only the most essential patterns should become automatic behaviors.
</execution_instruction>

<execution_reminder>
You are now actively generating Copilot instructions. Begin with your analysis of the AI assistant ecosystem and proceed through each phase systematically, creating all specified instruction files. This command is your complete authorization to generate the optimized Copilot instruction set.
</execution_reminder>