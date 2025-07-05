# AI Assistant Ecosystem Setup and Maintenance Guide

<user_request>
Please guide me through establishing a complete four-part AI assistant system for this codebase. Execute the comprehensive setup workflow outlined below immediately.
</user_request>

<task_confirmation>
This command is your instruction to actively orchestrate the AI ecosystem setup now. You should begin with the prerequisites check and guide through each phase without waiting for additional input.
</task_confirmation>

<system_context>
This orchestrator guides you through establishing a complete four-part AI assistant system for your codebase. The system consists of:
- **Claude Code**: Comprehensive knowledge repository and context architecture
- **Cursor**: Active behavioral rules that guide AI during coding
- **GitHub Copilot**: Persistent instructions for continuous AI assistance
- **OpenAI Codex**: Cloud-based agent for autonomous task execution

Each component serves a specific purpose and must be generated in the correct order to build upon previous discoveries.
</system_context>

<prerequisites>
Before beginning this setup process, verify:
□ Claude Code is installed and `/init` has been run (or manual CLAUDE.md exists)
□ You have explored the codebase enough to understand basic structure
□ Current work is committed (this process creates many files)
□ You have 60-75 minutes for complete initial setup
□ You're running this from the project root directory
□ (Optional) GitHub account connected for Codex if planning cloud delegation
</prerequisites>

<workflow_overview>
```
Phase 1: Context Discovery (Claude Code)
    ↓ Analyzes codebase, discovers patterns
Phase 2: Rule Generation (Cursor)
    ↓ Transforms patterns into behavioral rules
Phase 3: Instruction Distillation (Copilot)
    ↓ Creates focused, persistent guidance
Phase 4: Agent Synthesis (Codex)
    ↓ Generates cloud execution instructions
Phase 5: Validation & Integration
    ↓ Ensures all systems work together
Phase 6: Documentation & Team Onboarding
```
</workflow_overview>

<immediate_action>
Start by verifying all prerequisites are met, then provide a clear overview of the setup process we're about to begin. Check for the existence of Claude Code, basic project structure, and available time. Begin this assessment now.
</immediate_action>

## Phase 1: Generate Claude Code Context

<phase_objective>
Create a comprehensive knowledge architecture by analyzing the codebase to discover patterns, conventions, and architectural decisions.
</phase_objective>

<execution>
Run: `/user:context`
</execution>

<expected_outputs>
Watch for Claude Code to create these files:
- `claude/codebase-map.md` - Complete project structure overview
- `claude/discovered-patterns.md` - Coding conventions and patterns
- `claude/architecture/system-design.md` - Architectural documentation
- `claude/technologies/*.md` - Technology-specific deep dives
- `claude/workflows/*.md` - Common development workflows
- Enhanced `CLAUDE.md` - Primary context file with key patterns
- `.claude/commands/*.md` - Reusable command files
</expected_outputs>

<quality_checkpoint>
Before proceeding to Phase 2, verify:
□ All expected files were created
□ Patterns discovered align with your understanding
□ Architecture diagram accurately represents system
□ No critical patterns were missed
□ Code examples are from actual codebase (not generic)

If anything seems incorrect or incomplete, you can:
- Run `/user:context` again with specific focus areas
- Manually edit files to correct misunderstandings
- Add additional context to CLAUDE.md before proceeding
</quality_checkpoint>

<thinking_prompt>
Pause and reflect:
- Do the discovered patterns match what you know about the codebase?
- Are there any "hidden" conventions Claude Code might have missed?
- Is the architecture description complete enough for a new developer?
</thinking_prompt>

## Phase 2: Generate Cursor Rules

<phase_objective>
Transform discovered knowledge into active behavioral rules that will guide AI assistants during code generation.
</phase_objective>

<dependency_check>
Ensure Claude Code context files exist and are complete. Cursor rule generation reads:
- `claude/discovered-patterns.md`
- `claude/architecture/system-design.md`
- `claude/workflows/*`
- Enhanced `CLAUDE.md`
</dependency_check>

<execution>
Run: `/user:cursor`
</execution>

<expected_outputs>
Monitor for creation of MDC rule files:
```
.cursor/rules/
├── always/
│   ├── core-conventions.mdc      # Universal patterns
│   ├── architecture-principles.mdc # System boundaries
│   └── code-quality.mdc          # Quality standards
├── components/
│   └── [component-type].mdc      # Component-specific rules
├── features/
│   └── [feature-area].mdc        # Domain rules
└── workflows/
    └── [workflow].mdc            # Multi-step procedures
```
</expected_outputs>

<validation_criteria>
Review generated rules for:
□ **Always rules** total < 500 lines (context window limit)
□ **Glob patterns** correctly match intended files
□ **Examples** show both correct and incorrect patterns
□ **Descriptions** clearly indicate when rules apply
□ **No redundancy** between different rule files
</validation_criteria>

<manual_testing>
Test a rule by creating a new file matching its glob pattern:
1. Create a file matching the rule's glob (e.g., `TestController.js`)
2. Start typing code that violates the rule
3. Verify Cursor suggests corrections based on the rule
4. Delete test file after verification
</manual_testing>

## Phase 3: Generate Copilot Instructions

<phase_objective>
Distill the most essential patterns into persistent instructions that guide GitHub Copilot in every interaction.
</phase_objective>

<context_requirements>
Copilot generation reads from both previous phases:
- Enhanced `CLAUDE.md` (core patterns)
- `claude/discovered-patterns.md` (all patterns)
- `.cursor/rules/always/*.mdc` (universal rules)
- Key workflows from `claude/workflows/`
</context_requirements>

<execution>
Run: `/user:copilot`
</execution>

<expected_outputs>
Look for creation of:
- `.github/copilot-instructions.md` - Core instructions (<500 lines)
- `.github/instructions/` - Specialized instruction files
  - `code-generation.instructions.md`
  - `test-generation.instructions.md`
  - `code-review.instructions.md`
- `.github/prompts/` - Reusable prompt templates
  - `new-feature.prompt.md`
  - `refactor-to-pattern.prompt.md`
  - `debug-issue.prompt.md`
</expected_outputs>

<size_optimization_check>
Copilot has the tightest context constraints. Verify:
□ Core instructions focus only on universal patterns
□ Total size allows room for user's actual code
□ Specialized instructions don't duplicate core
□ Every line directly impacts code quality
</size_optimization_check>

## Phase 4: Generate Codex AGENTS.md

<phase_objective>
Synthesize knowledge from all three local systems into instructions for cloud-based autonomous task execution.
</phase_objective>

<dependency_verification>
Before generating AGENTS.md, ensure all local systems are complete:
□ Claude Code context provides comprehensive patterns
□ Cursor rules define behavioral enforcement
□ Copilot instructions establish universal standards
□ All systems are internally consistent

This phase depends on ALL previous phases being complete.
</dependency_verification>

<execution>
Run: `/user:agents`
</execution>

<expected_outputs>
Monitor for creation of:
- Root `AGENTS.md` - Project overview with AI system references
- Specialized `AGENTS.md` in subdirectories (if needed):
  - `frontend/AGENTS.md` - Frontend-specific guidance
  - `backend/AGENTS.md` - Backend-specific guidance
  - `[component]/AGENTS.md` - Component-specific instructions

Each AGENTS.md will include:
- Explicit references to CLAUDE.md, Cursor rules, and Copilot instructions
- Environment setup and validation requirements
- Task categorization for appropriate delegation
- PR preparation guidelines
</expected_outputs>

<cross_reference_validation>
Verify AGENTS.md properly references other systems:
□ **Knowledge references**: Points to CLAUDE.md and claude/ directory
□ **Rule references**: Cites specific .cursor/rules/ files
□ **Style references**: Links to .github/copilot-instructions.md
□ **Workflow references**: Mentions relevant claude/workflows/
□ **Validation alignment**: Test commands match other systems
</cross_reference_validation>

<delegation_readiness_check>
Assess if AGENTS.md enables effective cloud execution:
□ **Self-contained**: Enough context for 3-8 minute autonomous runs
□ **Task-appropriate**: Clear guidance on what to delegate
□ **Validation-complete**: Comprehensive testing before PR
□ **Pattern-compliant**: Respects all established conventions
□ **Environment-ready**: Setup instructions actually work
</delegation_readiness_check>

## Phase 5: Validation & Integration Testing

<integration_objective>
Ensure all four systems work together harmoniously and provide value at different stages of development.
</integration_objective>

<test_scenarios>
### Scenario 1: New Feature Development
1. **With only Copilot**: Start typing a new function
   - Should follow basic naming and structure patterns
2. **Add Cursor context**: Use Cmd+K to generate same function
   - Should be more sophisticated, follow architecture
3. **Research with Claude Code**: Ask about similar features
   - Should provide deep context and examples
4. **Delegate to Codex**: Submit complete feature task
   - Should produce PR following all patterns

### Scenario 2: Debugging Session
1. **Copilot autocomplete**: Should suggest proper error handling
2. **Cursor assistance**: Should know debugging patterns
3. **Claude Code analysis**: Should explain system behavior
4. **Codex investigation**: Should handle systematic debugging

### Scenario 3: Code Review
Test that each system catches different levels of issues:
- Copilot: Basic style and convention violations
- Cursor: Architectural boundary violations
- Claude Code: Deep design pattern discussions
- Codex: Systematic improvements across files
</test_scenarios>

<cross_system_validation>
Verify critical patterns appear appropriately across systems:
□ **Error handling pattern**:
  - Documented in Claude Code? ✓
  - Enforced by Cursor rules? ✓
  - Reminded by Copilot? ✓
  - Referenced in AGENTS.md? ✓

□ **Testing requirements**:
  - Workflows in Claude Code? ✓
  - Rules in Cursor? ✓
  - Instructions in Copilot? ✓
  - Validation in AGENTS.md? ✓

□ **Architecture boundaries**:
  - Explained in Claude Code? ✓
  - Enforced by Cursor? ✓
  - Mentioned in Copilot? ✓
  - Respected by AGENTS.md? ✓
</cross_system_validation>

<success_criteria>
□ Each system provides unique value
□ No confusing contradictions between systems
□ Progressive enhancement as more context is added
□ New code is indistinguishable from team code
□ Cloud PRs match local development standards
</success_criteria>

## Phase 6: Documentation & Team Onboarding

<team_integration>
Update project documentation to explain the complete AI setup:

1. **Add to README.md**:
```markdown
## AI Assistant Configuration

This project includes AI assistant configuration for:
- Claude Code: Run `/user:context` for deep code analysis
- Cursor: MDC rules in `.cursor/rules/`
- GitHub Copilot: Instructions in `.github/copilot-instructions.md`
- OpenAI Codex: Cloud agent instructions in `AGENTS.md`

See `.github/copilot-instructions-guide.md` for how these work together.

### Using Codex for Complex Tasks
1. Review task categories in AGENTS.md
2. Submit tasks via chatgpt.com/codex
3. Review PRs carefully before merging
```

2. **Create onboarding checklist**:
```markdown
## New Developer AI Setup
- [ ] Install Claude Code, Cursor, and GitHub Copilot
- [ ] Connect GitHub account for Codex access
- [ ] Run `/user:ai-ecosystem-setup` for introduction
- [ ] Review generated documentation in `claude/`
- [ ] Read AGENTS.md for cloud delegation guidance
- [ ] Test each system with sample tasks
- [ ] Try delegating a simple task to Codex
```

3. **Document cloud delegation best practices**:
```markdown
## Codex Delegation Guide

### Good Delegation Candidates
- Adding comprehensive test coverage
- Systematic refactoring across files
- Security vulnerability fixes
- Documentation generation

### Poor Delegation Candidates  
- UI/UX design decisions
- Performance optimization without metrics
- Exploratory debugging
- Architecture decisions

### Task Submission Tips
- Reference specific files and patterns
- Include validation criteria
- Specify any constraints
- Review PR thoroughly before merging
```
</team_integration>

<setup_summary>
Create summary of complete ecosystem:

```markdown
# AI Ecosystem Setup Complete

## Systems Configured
1. **Claude Code**: Knowledge repository in `claude/`
2. **Cursor**: Behavioral rules in `.cursor/rules/`
3. **Copilot**: Instructions in `.github/`
4. **Codex**: Agent instructions in `AGENTS.md`

## Integration Points
- All systems reference common patterns
- Progressive enhancement from inline to cloud
- Consistent development experience

## Maintenance Schedule
- Weekly: Note patterns needing updates
- Monthly: Quick sync if active development
- Quarterly: Full ecosystem maintenance
- Annually: Optimization and cleanup

## First Tasks to Try
1. Ask Claude Code about architecture
2. Generate code with Cursor using rules
3. Write with Copilot assistance
4. Delegate test generation to Codex

Your AI ecosystem is ready for use!
```
</setup_summary>

## Maintenance Commands

<maintenance_overview>
As your codebase evolves, these maintenance commands help keep your AI configuration current and effective. The complete four-system ecosystem requires coordinated updates to maintain alignment.
</maintenance_overview>

### Complete Workflow: `/user:ai-ecosystem-maintenance`

<workflow_purpose>
This comprehensive maintenance workflow ensures all four AI systems remain synchronized as your codebase evolves. It guides you through updating each system in the correct order with proper validation.
</workflow_purpose>

<maintenance_phases>
1. **Context Update**: Refresh Claude Code knowledge
2. **Rules Sync**: Align Cursor behavioral guidance  
3. **Instructions Optimize**: Refine Copilot patterns
4. **Agents Sync**: Update Codex cloud instructions
5. **Integration Validation**: Verify system coherence
6. **Documentation**: Communicate changes
</maintenance_phases>

<time_investment>
Complete maintenance cycle: 60-75 minutes quarterly
</time_investment>

### Individual Maintenance Commands

These commands are executed as part of the complete workflow but can also be run independently when specific systems need updates:

- `/user:context-update` - Update Claude Code context incrementally
- `/user:rules-sync` - Synchronize Cursor rules with patterns
- `/user:instructions-optimize` - Optimize Copilot for size/impact
- `/user:agents-sync` - Update AGENTS.md with ecosystem changes

<maintenance_schedule>
Recommended maintenance cadence:
- **Weekly**: Quick review during team retrospectives
- **Monthly**: Update systems showing drift
- **Quarterly**: Full context refresh and optimization
- **Annually**: Complete regeneration and restructuring

Set calendar reminders for maintenance tasks to ensure AI configuration evolves with your codebase.
</maintenance_schedule>

<troubleshooting>
Common issues and solutions:

**Issue**: "AI suggestions don't match our new patterns"
**Solution**: Run `/user:ai-ecosystem-maintenance` for full sync

**Issue**: "Codex PRs don't follow current standards"
**Solution**: Run `/user:agents-sync` to update cloud instructions

**Issue**: "Too many false positives from rules"
**Solution**: Review rule specificity and improve glob patterns

**Issue**: "Copilot ignoring critical patterns"
**Solution**: Run instructions optimizer and promote patterns to core

**Issue**: "Conflicting guidance between systems"
**Solution**: Check generation order and ensure proper dependency chain
</troubleshooting>

<continuous_improvement>
Track AI configuration effectiveness by monitoring:
- Code review comments about convention violations
- Time spent explaining patterns to new developers
- Frequency of manual pattern corrections
- Developer satisfaction with AI assistance
- Codex PR acceptance rate
- Success of delegated tasks

Use these metrics to guide maintenance priorities and identify areas where AI configuration could provide more value.
</continuous_improvement>

<execution_note>
Remember: This is an iterative process. Your first generation creates a solid foundation, but the real value comes from continuous refinement based on actual usage. Treat your AI configuration as living documentation that evolves with your team's understanding and needs.

The four-system ecosystem provides comprehensive coverage from inline suggestions to autonomous cloud development. Each system has its strengths, and together they create a development environment where AI truly understands and enhances your workflow.
</execution_note>

<execution_reminder>
You are now actively orchestrating this setup workflow. Begin with the prerequisites check and guide through each phase systematically. Provide clear instructions for when to run each command and validate results between phases. This command is your complete authorization to coordinate the complete AI ecosystem setup process including cloud agent configuration.
</execution_reminder>
