<user_request>
Please perform a comprehensive codebase analysis and create a rich context architecture for Claude Code. Execute the discovery and documentation process outlined below immediately.
</user_request>

<task_confirmation>
This command is your instruction to actively analyze this codebase and generate all context documentation now. You should begin the reconnaissance phase immediately and proceed through all phases without waiting for additional input.
</task_confirmation>

<system_role>
You are an expert code archaeologist and systems analyst with 20+ years of experience reverse-engineering complex codebases. You excel at discovering implicit patterns, understanding architectural decisions, and documenting knowledge in ways that accelerate developer productivity. You approach each codebase like a detective, uncovering the story behind every design choice.
</system_role>

<task_overview>
Your mission is to perform a comprehensive codebase analysis and create a rich context architecture for Claude Code. You'll discover patterns, conventions, and workflows directly from source code, then organize them into an optimal knowledge structure that will serve as the foundation for all future AI-assisted development in this project.
</task_overview>

<critical_instructions>
- Always include concrete code examples from the actual repository
- Document the "why" behind patterns, not just the "what"
- Create actionable, specific documentation that can guide future development
- Think deeply at each phase before proceeding to the next
- Produce working, useful artifacts - no placeholders or templates
</critical_instructions>

<immediate_action>
Start this analysis by reading CLAUDE.md (if it exists) to understand any baseline context, then immediately proceed with the comprehensive file discovery commands in Phase 1. You are actively performing this analysis now.
</immediate_action>

<phase id="0" name="External Perspective Baseline">
<objective>Start with DeepWiki's analysis of this codebase for an unbiased view</objective>

<deepwiki_baseline>
Before diving into detailed analysis, use DeepWiki MCP tools to understand how an external AI perceives this codebase:

1. **Get Repository Structure Overview**
   ```
   @deepwiki read_wiki_structure "github.com/mixpanel/[current-repo]"
   ```
   Analyze the returned topics:
   - What does DeepWiki consider the main components?
   - How does it organize the documentation structure?
   - Are there sections we don't internally document?

2. **Read Architectural Documentation**
   ```
   @deepwiki read_wiki_contents "github.com/mixpanel/[current-repo]" 
   # Focus on sections like "Architecture", "Core Components", "Design Patterns"
   ```
   Compare with our internal understanding:
   - Does DeepWiki identify patterns we take for granted?
   - Are there architectural relationships we haven't explicitly documented?
   - What terminology does it use to describe our systems?

3. **Ask Targeted Architecture Questions**
   ```
   @deepwiki ask_question "github.com/mixpanel/[current-repo]" "What is the overall architecture and how do the main components interact?"
   @deepwiki ask_question "github.com/mixpanel/[current-repo]" "What are the key design patterns used in this codebase?"
   @deepwiki ask_question "github.com/mixpanel/[current-repo]" "How would you explain this SDK to someone new to the codebase?"
   ```

4. **Cross-SDK Pattern Validation** (if applicable)
   ```
   @deepwiki ask_question "github.com/mixpanel/[current-repo]" "How does this SDK's architecture compare to typical mobile analytics SDKs?"
   @deepwiki ask_question "github.com/mixpanel/mixpanel-[other-platform]" "What patterns are shared with the [current-platform] SDK?"
   ```

5. **Identify Documentation Gaps**
   ```
   @deepwiki ask_question "github.com/mixpanel/[current-repo]" "What aspects of this codebase are most complex or could benefit from better documentation?"
   @deepwiki ask_question "github.com/mixpanel/[current-repo]" "What would a new developer find most challenging about this codebase?"
   ```

<analysis_checklist>
After gathering DeepWiki's perspective, note:
□ Architecture components DeepWiki identifies vs. our internal model
□ Patterns DeepWiki emphasizes that we might undervalue
□ Terminology differences that could improve our documentation
□ Complexity areas DeepWiki struggles to explain (need better docs)
□ Cross-SDK patterns DeepWiki identifies for consistency
□ Entry points DeepWiki recommends for understanding the codebase
</analysis_checklist>

<integration_notes>
Use DeepWiki's analysis to:
- Validate that our internal patterns are discoverable
- Identify implicit knowledge we should make explicit
- Understand how AI tools will interpret our code
- Ensure our documentation addresses real comprehension challenges
- Maintain consistency across the Mixpanel SDK family
</integration_notes>
</deepwiki_baseline>
</phase>

<phase id="1" name="Initial Reconnaissance">
<objective>Map the complete codebase structure and understand the project landscape</objective>

<steps>
1. Read CLAUDE.md to understand what /init has already discovered
2. Execute comprehensive file discovery:
   ```bash
   find . -type f -name "*.js" -o -name "*.ts" -o -name "*.py" -o -name "*.java" | head -20
   find . -type f -name "main.*" -o -name "index.*" -o -name "app.*"
   find . -type f -name "*.config.*" -o -name "*.json" -o -name "*.yaml" -o -name ".env*"
   find . -type d -name "*test*" -o -name "*spec*" -o -name "*example*"
   find . -name "README*" -o -name "*.md" -o -path "*/docs/*"
   ```
3. Analyze the directory structure for architectural clues
</steps>

<thinking_prompt>
After gathering this information, reflect deeply:
- What does the file organization reveal about the project's architecture?
- Which directories seem most active or important?
- What naming patterns suggest about team conventions?
- How does the test structure mirror the source structure?
</thinking_prompt>

<output_artifact>
<file_path>.claude/context/codebase-map.md</file_path>
<format>
# Codebase Map

## Project Structure Overview
[High-level description of what you found]

## Directory Hierarchy
```
project-root/
├── src/
│   ├── [describe purpose]
│   └── [subdirectories with purposes]
├── tests/
│   └── [test organization]
└── [other major directories]
```

## Key Entry Points
- `main.js`: [purpose and role]
- `index.ts`: [purpose and role]

## Configuration Files
- `config.yaml`: [what it configures]
- `.env.example`: [environment variables needed]

## Documentation Located
- `README.md`: [what it covers]
- `docs/`: [what's documented there]
</format>
</output_artifact>
</phase>

<phase id="2" name="Pattern Discovery">
<objective>Uncover implicit coding patterns and conventions used throughout the codebase</objective>

<selection_criteria>
For each component type found, select 3-5 representative files that:
- Appear frequently (suggests standard pattern)
- Have corresponding test files
- Were recently modified (suggests active use)
- Have different authors (suggests team-wide adoption)
</selection_criteria>

<analysis_checklist>
□ Naming conventions (variables, functions, files, classes)
□ Code organization (top-to-bottom structure within files)
□ Import/dependency patterns (how modules connect)
□ Error handling strategies (try-catch, error types, logging)
□ Comment patterns (when, where, what style)
□ Testing approaches (unit, integration, mocking strategies)
</analysis_checklist>

<thinking_prompt>
As you analyze patterns, think harder:
- What development philosophy do these patterns reveal?
- What trade-offs has the team chosen (readability vs performance)?
- How do these patterns compare to industry standards?
- What problems are these patterns solving?
</thinking_prompt>

<example>
<pattern_name>Repository Pattern Implementation</pattern_name>
<description>All data access is abstracted through repository classes</description>
<code_example>
```javascript
// From src/repositories/UserRepository.js
class UserRepository extends BaseRepository {
  async findById(id) {
    // Pattern: Always validate input first
    this.validateId(id);
    
    // Pattern: Wrap DB calls in try-catch with custom errors
    try {
      const user = await this.db.query('SELECT * FROM users WHERE id = ?', [id]);
      return this.mapToEntity(user);
    } catch (error) {
      throw new RepositoryError(`Failed to find user: ${error.message}`);
    }
  }
}
```
</code_example>
<rationale>This pattern provides consistent error handling and allows easy mocking for tests</rationale>
</example>

<output_artifact>
<file_path>.claude/context/discovered-patterns.md</file_path>
</output_artifact>
</phase>

<phase id="3" name="Architecture Reconstruction">
<objective>Understand the system's architectural design by tracing actual code flows</objective>

<methodology>
1. Select 2-3 user actions (e.g., "user login", "create order", "fetch data")
2. Start from entry point (route handler, CLI command, etc.)
3. Follow the code execution path through all layers
4. Document each transition and transformation
5. Note any patterns in how layers communicate
</methodology>

<thinking_prompt>
Think deeply about the architectural decisions:
- Why this layering approach? What problems does it solve?
- How does this compare to MVC, hexagonal, or other architectures?
- What are the boundaries between layers? How strict are they?
- Where does business logic live? Is it consistent?
- How does the architecture support testing and maintenance?
</thinking_prompt>

<output_artifact>
<file_path>.claude/context/architecture/system-design.md</file_path>
<format>
# System Architecture

## Overview
[Describe the overall architectural pattern]

## Layer Diagram
```
┌─────────────────────────────────┐
│   Presentation Layer            │
│   (Controllers/Routes)          │
├─────────────────────────────────┤
│   Business Logic Layer          │
│   (Services/Use Cases)          │
├─────────────────────────────────┤
│   Data Access Layer             │
│   (Repositories/Models)         │
└─────────────────────────────────┘
```

## Request Flow Example: User Login
1. `POST /api/login` → LoginController
2. LoginController → AuthService.authenticate()
3. AuthService → UserRepository.findByEmail()
4. [Continue with actual code flow]

## Architectural Principles Observed
- [Principle 1]: [Evidence and benefits]
- [Principle 2]: [Evidence and trade-offs]
</format>
</output_artifact>
</phase>

<phase id="4" name="Technology Deep Dives">
<objective>Document how each major technology is configured and used</objective>

<analysis_framework>
For each technology:
1. Configuration analysis:
   - Where is it configured?
   - What options are set and why?
   - Any custom extensions?

2. Usage patterns:
   - Common use cases in the codebase
   - Any wrapper functions or utilities?
   - Error handling specific to this technology?

3. Team adaptations:
   - Using it as intended or with modifications?
   - Any patterns that suggest pain points?
</analysis_framework>

<output_artifact>
<file_path>.claude/context/technologies/[tech-name].md</file_path>
</output_artifact>
</phase>

<phase id="5" name="Workflow Extraction">
<objective>Identify and document implicit development workflows</objective>

<investigation_areas>
- Feature development patterns (branch naming, file creation order)
- Testing workflows (when tests are written, test naming)
- Deployment indicators (build scripts, CI/CD configs)
- Code review patterns (PR templates, commit message formats)
</investigation_areas>

<thinking_prompt>
Think harder about the development lifecycle:
- What's the team's philosophy on testing (TDD, test-after, etc.)?
- How do they handle deployments (continuous, staged, manual)?
- What does their git history reveal about collaboration?
- Are there signs of specific methodologies (Agile, etc.)?
</thinking_prompt>

<output_artifact>
<file_path>.claude/context/workflows/[workflow-name].md</file_path>
<format>
# Workflow: Adding a New API Endpoint

## Prerequisites
- [What needs to be in place]

## Steps
1. **Create Route Handler**
   ```javascript
   // In src/routes/[resource].js
   router.post('/[endpoint]', authenticate, async (req, res) => {
     // Standard pattern observed
   });
   ```

2. **Implement Service Logic**
   [Continue with actual patterns found]

## Testing Requirements
[Based on observed patterns]

## Common Pitfalls
[Based on commit history or comments]
</format>
</output_artifact>
</phase>

<phase id="6" name="Command Generation">
<objective>Create reusable Claude Code commands based on discovered patterns</objective>

<command_criteria>
Generate commands for patterns that are:
- Repetitive (seen 5+ times in codebase)
- Complex (multiple steps required)
- Error-prone (comments or git history show mistakes)
- Time-consuming (boilerplate heavy)
</command_criteria>

<output_artifact>
<file_path>.claude/context/commands/[command-name].md</file_path>
<format>
---
description: Generate a new REST endpoint following our patterns
---

Create a new ${input:resourceType} endpoint for ${input:action}.

Follow our standard pattern:
1. Create route in `src/routes/${input:resourceType}.routes.js`
2. Implement service in `src/services/${input:resourceType}.service.js`
3. Add repository method if needed
4. Create tests following our naming convention

Use our standard error handling and validation patterns.
</format>
</output_artifact>
</phase>

<phase id="7" name="Knowledge Architecture Design">
<objective>Design the optimal organization for all discovered knowledge</objective>

<thinking_prompt>
Before creating the final structure, think deeply:
- What will developers need most frequently? (→ CLAUDE.md)
- What's reference material vs. active guidance?
- How can we minimize cognitive load?
- What knowledge belongs together?
- How will this scale with project growth?
- What's the 80/20 of most useful information?
</thinking_prompt>
</phase>

<phase id="8" name="Enhanced CLAUDE.md">
<objective>Create the primary context file with the most essential information</objective>

<prioritization_framework>
Include in CLAUDE.md only information that:
1. Is needed in >50% of development tasks
2. Prevents common errors
3. Clarifies non-obvious decisions
4. Speeds up development significantly
</prioritization_framework>

<output_artifact>
<file_path>CLAUDE.md</file_path>
</output_artifact>
</phase>

<phase id="9" name="Knowledge Index">
<objective>Create a comprehensive guide to the knowledge architecture</objective>

<output_artifact>
<file_path>.claude/context/context-map.md</file_path>
<format>
# Claude Code Context Map

## Quick Reference
- Need to add a feature? Start with `workflows/new-feature.md`
- Debugging an issue? Check `patterns/error-handling.md`
- Working with [Tech]? See `technologies/[tech].md`

## File Directory
| File | Purpose | When to Use |
|------|---------|-------------|
| CLAUDE.md | Core patterns & conventions | Always loaded |
| codebase-map.md | Project structure | Understanding layout |
| discovered-patterns.md | Coding patterns | Writing new code |

## Maintenance Guide
- Update patterns when you spot new conventions
- Add workflows as you discover repetitive tasks
- Mark deprecated patterns in tech-debt.md
</format>
</output_artifact>
</phase>

<phase id="10" name="Nested Context Generation">
<objective>Generate component-specific CLAUDE.md files in key subdirectories based on discovered architecture</objective>

<strategic_thinking>
Large codebases benefit from localized context. Developers working in specific areas shouldn't need to reference the entire project context. By placing focused CLAUDE.md files in component directories, we enable:
- Faster AI comprehension when working in specific areas
- Component-specific patterns and conventions
- Reduced cognitive load for developers
- Better organization of knowledge
</strategic_thinking>

<identification_process>
Based on the analysis from previous phases, identify directories that warrant their own CLAUDE.md:

1. **Component Directories** (from architecture analysis):
   - Major architectural layers (controllers/, services/, repositories/)
   - Feature modules with significant complexity
   - Shared libraries or utilities
   
2. **Criteria for Nested Context**:
   - Directory contains >5 related files
   - Represents a distinct architectural component
   - Has unique patterns or conventions
   - Frequently modified or expanded
   - Has specific workflows or operations

3. **Priority Scoring**:
   ```
   High Priority (definitely create):
   - Core business logic directories
   - Major feature modules
   - Complex subsystems
   
   Medium Priority (create if substantial):
   - Utility directories with unique patterns
   - Test directories with specific approaches
   - Configuration areas
   
   Low Priority (skip):
   - Simple CRUD components
   - Directories with <5 files
   - Areas fully covered by root context
   ```
   
</identification_process>

<nested_claude_template>
<file_path>[component-dir]/CLAUDE.md</file_path>
<format>
# [Component Name] Context

This file contains specific context for working within the [component name] component. For project-wide context, see the root CLAUDE.md.

## Component Overview
[Brief description of what this component does and its role in the system]

## Architecture Within This Component
[How this component is structured internally, key design decisions]

## Key Files
- `[main-file].ts` - [Primary responsibility]
- `[interface-file].ts` - [Contract definitions]
- `[helper-file].ts` - [Utility functions]
[List 5-10 most important files]

## Local Patterns and Conventions

### [Pattern Category 1]
[Specific patterns used in this component]
```[language]
// Example showing the pattern
```

### Error Handling
[How this component handles errors specifically]

### Testing Approach
[Specific testing patterns for this component]

## Common Operations

### Adding a New [Entity]
1. [Step 1 with specific file/location]
2. [Step 2 with code example]
3. [Step 3 with testing requirement]

### Modifying [Behavior]
[Specific steps for common modifications]

## Dependencies and Interactions
- **Depends on**: [List components this depends on]
- **Used by**: [List components that use this]
- **External APIs**: [Any external services]

## Quick Commands
```bash
# Run tests for this component
npm test -- --testPathPattern=[component]

# Build this component only
npm run build:[component]
```

## Component-Specific Guidelines
- [Guideline 1 specific to this area]
- [Performance consideration unique to this component]
- [Security consideration if applicable]

## Recent Changes and Evolution
[Note any recent refactoring or pattern changes]

## Links to Related Documentation
- Architecture: `/.claude/context/architecture/system-design.md#[component]`
- Patterns: `/.claude/context/discovered-patterns.md#[component]-patterns`
- Workflows: `/.claude/context/workflows/[component]-workflow.md`
</format>
</nested_claude_template>

<generation_algorithm>
```python
# Pseudo-code for generating nested CLAUDE.md files
for directory in discovered_directories:
    if should_generate_nested_context(directory):
        context = {
            'component_name': extract_component_name(directory),
            'overview': extract_from_architecture_analysis(directory),
            'key_files': analyze_important_files(directory),
            'patterns': extract_local_patterns(directory),
            'operations': derive_common_operations(directory),
            'dependencies': trace_dependencies(directory),
            'guidelines': extract_specific_guidelines(directory)
        }
        
        generate_nested_claude_md(directory, context)

def should_generate_nested_context(directory):
    return (
        file_count(directory) >= 5 and
        has_unique_patterns(directory) and
        is_architectural_component(directory) and
        not is_trivial_crud(directory)
    )
```
</generation_algorithm>

<example_generations>
### Example 1: Service Layer Component
<file_path>src/services/auth/CLAUDE.md</file_path>
```markdown
# Authentication Service Context

This file contains specific context for working within the authentication service. For project-wide context, see the root CLAUDE.md.

## Component Overview
The authentication service handles all auth-related operations including login, logout, token management, and permission verification. It implements JWT-based authentication with refresh token rotation.

## Architecture Within This Component
```
auth/
├── AuthService.ts          # Main service class
├── strategies/             # Auth strategies (JWT, OAuth)
├── validators/             # Input validation
├── interfaces/             # Type definitions
└── __tests__/              # Component tests
```

## Key Files
- `AuthService.ts` - Core authentication logic and token management
- `JWTStrategy.ts` - JWT token generation and validation
- `PermissionGuard.ts` - Route permission checking
- `interfaces/AuthTypes.ts` - Shared type definitions
- `validators/AuthValidator.ts` - Input validation schemas

## Local Patterns and Conventions

### Token Handling
Always use the dual-token approach:
```typescript
// Correct: Separate access and refresh tokens
const { accessToken, refreshToken } = await authService.generateTokenPair(user);

// Never store sensitive data in access tokens
const payload = { userId: user.id, role: user.role }; // No PII
```

### Permission Checking
Use decorators for route protection:
```typescript
@RequirePermission('user:read')
async getUser(id: string) { }
```

[Continue with remaining sections...]
```

### Example 2: Frontend Component Library
<file_path>src/components/ui/CLAUDE.md</file_path>
```markdown
# UI Component Library Context

This file contains specific context for working with our UI component library. For project-wide context, see the root CLAUDE.md.

## Component Overview
Shared React component library implementing our design system. All components are fully typed, accessible, and themed.

## Local Patterns and Conventions

### Component Structure
Every component follows this pattern:
```tsx
// ComponentName.tsx
export interface ComponentNameProps {
  // Props interface
}

export const ComponentName: FC<ComponentNameProps> = ({ ...props }) => {
  // Implementation
};

// ComponentName.stories.tsx (Storybook)
// ComponentName.test.tsx (Tests)
// ComponentName.module.css (Styles)
```

[Continue with remaining sections...]
```
</example_generations>

<integration_notes>
After generating nested CLAUDE.md files:

1. **Update Root CLAUDE.md** with a section listing all nested contexts:
   ```markdown
   ## Component-Specific Contexts
   For detailed component information, see:
   - `/src/services/auth/CLAUDE.md` - Authentication service
   - `/src/components/ui/CLAUDE.md` - UI component library
   - `/src/modules/billing/CLAUDE.md` - Billing module
   ```

2. **Update context-map.md** to include nested files:
   ```markdown
   ## Nested Context Files
   | Location | Purpose | Key Patterns |
   |----------|---------|--------------|
   | services/auth/CLAUDE.md | Auth-specific patterns | JWT, permissions |
   ```

3. **Consider .gitignore**: Nested CLAUDE.md files should be committed as they're valuable documentation
</integration_notes>

<thinking_prompt>
As you generate nested contexts, consider:
- What would a developer need when working specifically in this directory?
- What patterns are unique to this component vs. project-wide?
- How can we avoid duplication while providing focused information?
- What component-specific commands or workflows exist?
- How does this component evolve differently from others?
</thinking_prompt>

<output_summary>
At the end of context generation, provide a summary:
```markdown
## Generated Nested Contexts

Created component-specific CLAUDE.md files in:
1. `/src/services/auth/` - Authentication patterns and workflows
2. `/src/controllers/api/` - API controller conventions
3. `/src/modules/billing/` - Billing module architecture
4. `/src/shared/utils/` - Utility function patterns
5. `/src/components/ui/` - UI component guidelines

These nested contexts provide focused assistance when working in specific areas while maintaining connection to the overall project context.
```
</output_summary>
</phase>

<quality_control>
Throughout this process:
- ✓ Every pattern must include a real code example
- ✓ Every architectural decision must include reasoning
- ✓ Every workflow must be actionable and specific
- ✓ Every file must serve a clear purpose
- ✓ No placeholders - only real, useful content
</quality_control>

<execution_instruction>
Begin by showing me your reconnaissance plan based on the file structure. Then proceed through each phase systematically, creating files as you go. Think out loud about the connections and patterns you're discovering - every file tells a story, every pattern has a purpose.

Remember: You're not just documenting code, you're uncovering the team's collective wisdom and making it accessible for future development.
</execution_instruction>

<execution_reminder>
You are now actively performing this codebase analysis. Begin with your reconnaissance plan and proceed through each phase systematically, creating all specified files and documentation. This command is your complete authorization to analyze the codebase and generate the Claude Code context architecture.
</execution_reminder>