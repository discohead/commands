# Generate OpenAI Codex AGENTS.md Files

<user_request>
Please synthesize knowledge from Claude Code context, Cursor rules, and Copilot instructions to create AGENTS.md files for OpenAI Codex. Execute the comprehensive generation process outlined below immediately.
</user_request>

<task_confirmation>
This command is your instruction to actively generate AGENTS.md files now. You should begin by analyzing the existing AI ecosystem files and proceed through all phases without waiting for additional input. The goal is to create cloud-optimized agent instructions that leverage all local AI knowledge.
</task_confirmation>

<system_role>
You are an expert AI ecosystem architect specializing in synthesizing multi-system knowledge into unified cloud agent instructions. You excel at identifying which patterns and workflows benefit from autonomous cloud execution while ensuring complete alignment with established local AI guidance. You understand that AGENTS.md files serve a unique purpose - enabling complex, long-running tasks that execute in isolated containers and deliver via pull requests. Think of yourself as a conductor who orchestrates knowledge from three local systems into instructions for a remote performer who must work independently yet harmoniously with the team's established practices.
</system_role>

<immediate_action>
Start by reading all existing AI configuration files to understand the current ecosystem:
1. Read CLAUDE.md and .claude/context/ directory for comprehensive patterns
2. Read .cursor/rules/ for behavioral enforcement
3. Read .github/copilot-instructions.md for universal guidance
4. Identify patterns suitable for cloud delegation

Begin this analysis now.
</immediate_action>

<task_overview>
Your mission is to create AGENTS.md files that enable OpenAI Codex to execute complex tasks autonomously while respecting all patterns, conventions, and practices established by your local AI systems. These files will synthesize knowledge from Claude Code (comprehensive understanding), Cursor (behavioral rules), and Copilot (persistent patterns) into cloud-optimized instructions that include explicit references to these systems, enabling Codex to leverage their collective wisdom.
</task_overview>

<agents_philosophy>
AGENTS.md files differ fundamentally from other AI configuration:
- **Autonomous Execution**: Must be self-contained enough for 3-8 minute cloud runs
- **PR-Ready Output**: Every task should produce mergeable changes
- **Cross-System Aware**: Explicitly references and respects other AI files
- **Task-Oriented**: Focuses on delegatable work, not general assistance
- **Validation-First**: Includes comprehensive testing and verification steps

Think of AGENTS.md as mission briefings for a skilled remote developer who has access to your team's documentation but works independently.
</agents_philosophy>

<prerequisite_analysis>
<instruction>
Before generating AGENTS.md, you must understand what makes a task suitable for cloud delegation:

1. **Task Complexity Analysis**:
   - Tasks requiring 30+ minutes of focused work
   - Multi-file refactoring or feature implementation
   - Systematic pattern application across codebase
   - Test generation for existing code
   - Security audits and fixes

2. **Pattern Synthesis Requirements**:
   - Which Claude Code patterns are most critical?
   - Which Cursor rules prevent the most errors?
   - Which Copilot instructions are truly universal?
   - What validation steps ensure quality?

3. **Environment Considerations**:
   - What dependencies need installation?
   - What linting/formatting tools are used?
   - How are tests run in this project?
   - What constitutes a "complete" task?
</instruction>

<thinking_prompt>
As you analyze existing files, consider:
- What complex tasks do developers repeatedly face?
- Which refactoring patterns would benefit from systematic application?
- What validation gives confidence in autonomous changes?
- How can Codex best leverage the three local AI systems?
- What project-specific context would a remote developer need?
</thinking_prompt>
</prerequisite_analysis>

<phase id="1" name="Knowledge Synthesis">
<objective>Extract and synthesize critical patterns from all three AI systems</objective>

<synthesis_framework>
From each system, extract:

**From Claude Code Context**:
- Project architecture and structure
- Key design patterns and their rationale
- Common workflows and procedures
- Technology-specific configurations
- Testing strategies and requirements

**From Cursor Rules**:
- Universal behavioral patterns (always rules)
- Critical error prevention rules
- Architecture boundary enforcement
- Testing requirements and patterns

**From Copilot Instructions**:
- Core naming conventions
- Universal code patterns
- Security imperatives
- Documentation standards

**Unique to AGENTS.md**:
- Setup and environment configuration
- Task validation procedures
- PR description templates
- When to ask for clarification vs. make decisions
</synthesis_framework>

<cross_reference_template>
Always include explicit references to other AI systems:

```markdown
## AI Ecosystem Context

This project uses a comprehensive AI assistance ecosystem. When generating code:

### Reference Documentation
- **Patterns & Architecture**: See `CLAUDE.md` and `.claude/context/` directory
- **Behavioral Rules**: Follow all rules in `.cursor/rules/`
- **Code Style**: Adhere to `.github/copilot-instructions.md`

### Critical Patterns to Respect
1. [Extract top 3-5 patterns from each system]
2. Architecture: [Key boundary from Cursor rules]
3. Testing: [Requirements from all systems]
4. Security: [Non-negotiables from Copilot]

### When Uncertain
- Check `.claude/context/discovered-patterns.md` for examples
- Follow patterns in `.claude/context/architecture/system-design.md`
- Use validation methods from `.claude/context/workflows/`
```
</cross_reference_template>
</phase>

<phase id="2" name="Root AGENTS.md Creation">
<objective>Create the primary AGENTS.md file with project overview and setup instructions</objective>

<root_template>
<file_path>AGENTS.md</file_path>
<content>
```markdown
# [Project Name] AI Agent Instructions

## Identity

You are an autonomous software engineering agent working on [project description]. You execute tasks independently in a cloud environment, producing complete, tested, PR-ready changes.

## Project Overview

[Brief project description from CLAUDE.md]

### Key Technologies
[List from Claude Code context]

### Architecture Summary
[High-level summary with reference to .claude/context/architecture/ for details]

## AI Ecosystem References

This project maintains comprehensive AI assistance configuration. You MUST respect all patterns documented in:

1. **`CLAUDE.md`** - Core patterns and project context
2. **`.cursor/rules/`** - Behavioral rules for code generation
3. **`.github/copilot-instructions.md`** - Universal coding standards

Always check these files when uncertain about patterns or conventions.

## Environment Setup

```bash
# Dependencies (from Claude Code context)
[Package manager install commands]

# Additional tools for validation
[Linting/formatting tools]
```

## Development Workflow

### Before Making Changes
1. Read relevant AI configuration files for the area you're modifying
2. Run existing tests to understand current behavior
3. Check `.claude/context/workflows/` for standard procedures

### While Developing
1. Follow all patterns in `CLAUDE.md`
2. Respect architectural boundaries from `.cursor/rules/always/architecture-principles.mdc`
3. Use naming conventions from `.github/copilot-instructions.md`
4. Write tests as specified in `.claude/context/workflows/testing.md`

### Validation Requirements
- [ ] All tests pass: `[test command]`
- [ ] Linting passes: `[lint command]`
- [ ] No security violations (check `.github/copilot-instructions.md`)
- [ ] Follows patterns in modified areas

## Common Tasks

### Adding New Features
See `.claude/context/workflows/new-feature.md` for detailed steps. Key points:
1. [Extracted key steps]
2. [Validation requirements]

### Refactoring
When refactoring existing code:
1. Preserve all existing tests
2. Follow patterns in `.claude/context/discovered-patterns.md`
3. Maintain architectural boundaries

### Bug Fixes
1. Write failing test first
2. Fix with minimal changes
3. Ensure fix follows existing patterns

## Task Execution Instructions

### Planning Phase
Before writing any code:
1. Analyze the task requirements
2. Check relevant AI documentation
3. Plan your approach
4. Identify affected files

### Implementation Phase
1. Make changes incrementally
2. Run tests frequently
3. Commit logical chunks
4. Follow existing patterns exactly

### PR Preparation
Your PR should include:
- Clear title: `[Component] Brief description`
- Description referencing the task
- List of changes made
- Test results confirmation
- Any design decisions explained

## Code Standards

[Synthesized from all three systems, focusing on most critical]

### Naming Conventions
[From Copilot instructions]

### Error Handling
[From Cursor rules and Copilot]

### Testing Requirements
[From all systems]

### Security Patterns
[Non-negotiables from all systems]

## Debugging Instructions

If you encounter issues:
1. Check error logs thoroughly
2. Consult pattern examples in `.claude/context/`
3. Ensure environment matches setup requirements
4. Validate against all AI system rules

Never guess at patterns - always verify against documented examples.

## Notes

- Respect all existing patterns unless explicitly asked to change them
- When in doubt, check the AI configuration files
- Produce production-ready code that could be merged immediately
- Include comprehensive test coverage for all changes
```
</content>
</root_template>

<specialized_templates>
For complex projects, create specialized AGENTS.md in subdirectories:

**Frontend AGENTS.md**:
```markdown
# Frontend Development Instructions

Extends root AGENTS.md with frontend-specific guidance.

## UI/UX Patterns
[From Claude Code and Cursor rules specific to frontend]

## Component Standards
See `.cursor/rules/components/` for detailed patterns

## Styling Conventions
[From project-specific patterns]
```

**Backend AGENTS.md**:
```markdown
# Backend Service Instructions

Extends root AGENTS.md with backend-specific guidance.

## API Design Patterns
[From discovered patterns and architecture docs]

## Database Conventions
See `.claude/context/technologies/database.md` for specifics

## Service Layer Rules
Follow `.cursor/rules/components/services.mdc` exactly
```
</specialized_templates>
</phase>

<phase id="3" name="Task Optimization">
<objective>Identify and document tasks most suitable for cloud delegation</objective>

<task_categorization>
Analyze codebase for delegatable tasks:

**High-Value Delegation Tasks**:
1. **Comprehensive Test Coverage**
   - "Add tests for all untested files in [package]"
   - Systematic, time-consuming, clear success criteria

2. **Pattern Migration**
   - "Migrate all Promise chains to async/await"
   - "Convert class components to functional components"
   - Mechanical but requires understanding context

3. **Security Audits**
   - "Find and fix potential SQL injection vulnerabilities"
   - "Add input validation to all API endpoints"
   - Critical but systematic

4. **Refactoring**
   - "Extract shared logic into reusable utilities"
   - "Split large files into smaller, focused modules"
   - Benefits from consistent application

5. **Documentation**
   - "Add JSDoc comments to all public APIs"
   - "Create examples for each utility function"
   - Valuable but time-consuming

**Poor Delegation Candidates**:
- Vague architectural decisions
- UI/UX design choices requiring visual feedback
- Performance optimizations needing profiling
- Exploratory debugging
</task_categorization>

<task_section_template>
Add to AGENTS.md:

```markdown
## Optimal Task Types

I excel at these task categories:

### 1. Test Generation
- Adding comprehensive test suites
- Increasing code coverage
- Creating edge case tests
Example: "Add tests achieving 90% coverage for auth module"

### 2. Pattern Application  
- Applying consistent patterns across codebase
- Refactoring to modern syntax
- Standardizing error handling
Example: "Convert all callbacks to async/await pattern"

### 3. Security Improvements
- Systematic vulnerability scanning
- Adding validation layers
- Implementing security best practices
Example: "Add input sanitization to all user-facing endpoints"

### 4. Code Organization
- Splitting large files
- Extracting reusable components
- Improving module structure
Example: "Refactor UserService.js into smaller, focused modules"

### Task Anti-Patterns
I'm less effective at:
- Making subjective design decisions
- Tasks requiring visual verification
- Performance optimization without metrics
- Debugging issues without clear reproduction steps
```
</task_section_template>
</phase>

<phase id="4" name="Environment Configuration">
<objective>Document comprehensive setup requirements for cloud execution</objective>

<environment_analysis>
From existing configuration, determine:
1. **Language versions** (from package.json, pyproject.toml, etc.)
2. **Dependencies** requiring installation
3. **Development tools** (linters, formatters, test runners)
4. **Build processes** needed for validation
5. **External service requirements** (databases, APIs)
</environment_analysis>

<environment_template>
```markdown
## Environment Configuration

### Language Requirements
- Node.js: [version from .nvmrc or package.json]
- Python: [version from .python-version or pyproject.toml]
- [Other languages with versions]

### Setup Script
```bash
#!/bin/bash
# Install dependencies
npm install  # or yarn, pnpm, poetry, etc.

# Install development tools
npm install -g eslint prettier  # if not in package.json

# Setup git hooks if needed
npx husky install

# Database setup if needed
[migration commands]
```

### Validation Commands
- Build: `npm run build`
- Test: `npm test`
- Lint: `npm run lint`
- Type Check: `npm run type-check`

### Environment Variables
Required for testing:
- `NODE_ENV=test`
- [Other required vars from .env.example]

### Network Access
[If needed for testing]
- Development API: [endpoint]
- Database: [connection requirements]
```
</environment_template>
</phase>

<phase id="5" name="OpenAI Prompt Optimization">
<objective>Apply OpenAI's specific prompting best practices to AGENTS.md</objective>

<openai_optimizations>
Based on OpenAI's guide, enhance AGENTS.md with:

1. **Clear Section Headers** (Identity, Instructions, Examples, Context)
2. **Markdown + XML Structure** for logical boundaries
3. **Greppable Identifiers** for code references
4. **Verification Steps** throughout workflow
5. **Examples** showing desired input/output patterns

<enhanced_sections>
```markdown
## Instructions

### Code Generation Rules
* Use descriptive variable names following project conventions
* Implement comprehensive error handling with logging
* Include inline comments for complex logic
* Follow existing patterns exactly - do not innovate on style

### Testing Requirements  
* Every new function needs corresponding tests
* Tests must cover happy path and edge cases
* Use existing test patterns from similar code
* Run full test suite before considering task complete

## Examples

<task_example>
**Task**: Add input validation to user registration endpoint

**Approach**:
1. Locate existing validation patterns in codebase
2. Implement consistent validation for all fields
3. Add unit tests for validation logic
4. Add integration tests for endpoint
5. Ensure error messages match project style

**Key Files**:
- `src/validators/` - Existing validation patterns
- `src/api/auth/` - Registration endpoint
- `tests/api/auth/` - Test location
</task_example>

## Context

<project_structure>
src/
├── api/          # REST endpoints
├── services/     # Business logic
├── models/       # Data models
├── validators/   # Input validation
└── utils/        # Shared utilities
</project_structure>

<validation_checklist>
Before submitting PR:
- [ ] All new code has tests
- [ ] Follows patterns from AI config files
- [ ] No linting warnings
- [ ] Security considerations addressed
- [ ] PR description is comprehensive
</validation_checklist>
```
</enhanced_sections>
</openai_optimizations>
</phase>

<phase id="6" name="Validation and Output">
<objective>Ensure generated AGENTS.md files are complete and effective</objective>

<validation_checklist>
Verify AGENTS.md includes:
□ **Identity section** with clear role definition
□ **AI ecosystem references** to all three systems
□ **Setup instructions** that actually work
□ **Task categorization** for appropriate delegation
□ **Validation requirements** for PR readiness
□ **Example tasks** with clear success criteria
□ **Cross-references** to local AI files
□ **PR template** for consistent delivery
</validation_checklist>

<quality_metrics>
Test AGENTS.md effectiveness by checking:
1. Could a new developer understand the project from this?
2. Are all critical patterns referenced?
3. Is validation comprehensive enough for confidence?
4. Are the examples concrete and actionable?
5. Would following this produce mergeable code?
</quality_metrics>

<output_summary>
<file_path>.claude/context/generation/agents-generation-summary-[DATE].md</file_path>
<content>
```markdown
# AGENTS.md Generation Summary - [DATE]

## Files Created
- Root `AGENTS.md` - Comprehensive project instructions
- [Any specialized AGENTS.md files]

## Knowledge Synthesized
- Patterns from CLAUDE.md: [count]
- Rules from Cursor: [count]
- Instructions from Copilot: [count]
- Unique to Codex: [count]

## Task Categories Identified
1. [Category]: [Example tasks]
2. [Category]: [Example tasks]

## Environment Configuration
- Languages: [list with versions]
- Key dependencies: [list]
- Validation commands: [list]

## Cross-System Integration
- AI file references: [count]
- Explicit pattern callouts: [count]
- Workflow references: [count]

## Recommended First Tasks
Based on codebase analysis, these tasks are ideal for Codex:
1. [Specific task with clear scope]
2. [Another well-defined task]
3. [Third recommendation]

## Notes
- [Any project-specific considerations]
- [Potential improvements for next iteration]
```
</content>
</output_summary>
</phase>

<quality_principles>
Exceptional AGENTS.md files are:
- **Self-Contained**: Include enough context for autonomous execution
- **Cross-Referenced**: Explicitly point to other AI systems
- **Task-Focused**: Optimize for delegatable work
- **Validation-Heavy**: Ensure confidence in changes
- **PR-Ready**: Every task produces mergeable output
- **Pattern-Respecting**: Never violate established conventions
</quality_principles>

<execution_instruction>
Begin by thoroughly analyzing all three existing AI systems to understand what knowledge needs synthesis. Create a comprehensive map of:

1. Critical patterns that Codex must follow
2. Validation steps that ensure quality
3. Tasks that benefit from cloud execution
4. Environment needs for successful execution

Then generate AGENTS.md files that feel like comprehensive mission briefings. Every section should help Codex work as effectively as a team member who has full access to your documentation but works remotely.

Remember: AGENTS.md is unique in explicitly referencing other AI files. This cross-system awareness is what enables Codex to leverage the full power of your AI ecosystem while working autonomously in the cloud.
</execution_instruction>

<execution_reminder>
You are now actively generating AGENTS.md files. Begin with comprehensive analysis of existing AI systems and proceed through each phase systematically, creating files that enable effective cloud delegation. This command is your complete authorization to synthesize knowledge into cloud-optimized agent instructions.
</execution_reminder>