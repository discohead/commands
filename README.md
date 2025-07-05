# Claude Code AI Assistant Ecosystem Commands

<document_purpose>
This README serves as your comprehensive guide to managing a sophisticated four-part AI assistant ecosystem for software development. These commands enable you to establish and maintain AI configurations that evolve with your codebase, ensuring your AI assistants always provide relevant, high-quality assistance - whether working locally in real-time or delegating complex tasks to the cloud. Think of this as your playbook for orchestrating AI tools that truly understand your project.
</document_purpose>

## Understanding the AI Ecosystem Philosophy

Before diving into specific commands, it's important to understand why we've structured things this way. Imagine you're building a team of specialized assistants, each with their own strengths:

**Claude Code** acts as your comprehensive librarian and researcher. It maintains deep knowledge about your codebase - every pattern, every architectural decision, every workflow. Like a seasoned team member who's been with the project from the beginning, it can provide context and rationale for any aspect of your system. When available, it can also leverage DeepWiki MCP for external perspective on your repository.

**Cursor** serves as your active coding mentor. It provides real-time behavioral guidance while you write code, catching potential issues and suggesting patterns based on the current context. Think of it as having an experienced developer looking over your shoulder, gently steering you toward best practices.

**GitHub Copilot** functions as your persistent pair programmer. It offers continuous, lightweight assistance that shapes every line of code you write. Like muscle memory developed through years of practice, it helps you naturally follow your team's conventions without conscious effort.

**OpenAI Codex** operates as your cloud-based development agent. It handles complex, time-consuming tasks that can run in parallel while you continue working locally. Think of it as delegating a complete feature or refactor to a skilled colleague who will deliver their work via a pull request when finished.

The magic happens when these four systems work together. Claude Code discovers and documents patterns (with optional DeepWiki validation), Cursor transforms these into active rules, Copilot distills them into persistent habits, and Codex leverages all this knowledge to autonomously complete complex tasks in the cloud. This creates a feedback loop where your AI assistance continuously improves as your codebase evolves.

## Command Directory Structure

<structure_explanation>
The commands are organized into logical categories that reflect the lifecycle of AI configuration:

```
~/..claude/context/commands/
├── ai-setup/          # Initial configuration generation
│   ├── context.md
│   ├── cursor.md
│   ├── copilot.md
│   └── agents.md      # NEW: Codex AGENTS.md generation
├── ai-maintenance/    # Ongoing updates and optimization
│   ├── context-update.md
│   ├── rules-sync.md
│   ├── instructions-optimize.md
│   └── agents-sync.md # NEW: AGENTS.md synchronization
├── workflows/         # Multi-step orchestrated processes
│   ├── ai-ecosystem-setup.md
│   └── ai-ecosystem-maintenance.md
└── global/            # Global utility commands
    └── ai-ecosystem-check.md
```

This organization mirrors how you'll actually use these commands. First, you set up the AI ecosystem for a project. Then, you maintain it as the project evolves. The workflow commands guide you through these multi-step processes.
</structure_explanation>

## Initial Setup Commands

<command_category name="ai-setup">
These commands generate your initial AI configuration by analyzing your codebase and discovering patterns. Think of this as the "archaeological dig" phase where we uncover the implicit knowledge in your code and make it explicit.

### `/context` - Generate Claude Code Context

This command performs a comprehensive analysis of your codebase, discovering patterns, conventions, and architectural decisions. It's like having an expert developer study your entire project and document everything they learn. If DeepWiki MCP is available, it can provide external validation of discovered patterns.

**When to use**: 
- Starting AI configuration for a new project
- After major architectural changes
- When onboarding AI assistance to a legacy codebase

**What it creates**:
- `.claude/context/` directory with comprehensive documentation
- Enhanced `CLAUDE.md` with critical patterns
- Discovered patterns, architecture diagrams, and workflows
- Custom commands for common operations
- Optional DeepWiki integration notes if available

**External resources**: If your repository is available on DeepWiki, the context generation can leverage external analysis for additional perspective.

**Time investment**: 20-30 minutes for thorough analysis

### `/cursor` - Generate Cursor Rules

This command transforms discovered patterns into behavioral rules that actively guide AI code generation. It's like converting a style guide into an automated linter that prevents mistakes before they happen.

**When to use**: 
- After running context generation
- When team coding standards have evolved
- To enforce new architectural patterns

**What it creates**:
- `.cursor/rules/` directory with MDC rule files
- Always-applied rules for universal patterns
- Component-specific rules for contextual guidance
- Workflow rules for complex procedures
- Reference to DeepWiki for complex architectural questions

**Dependencies**: Requires Claude Code context files to exist

### `/copilot` - Generate Copilot Instructions

This command distills essential patterns into persistent instructions that accompany every Copilot interaction. Think of it as creating the "muscle memory" for your AI pair programmer.

**When to use**:
- After generating both context and rules
- When core patterns have stabilized
- To ensure consistent AI suggestions

**What it creates**:
- `.github/copilot-instructions.md` (< 500 lines)
- Specialized instruction files for specific tasks
- Prompt templates for common operations
- Brief mention of DeepWiki as supplemental resource

**Optimization focus**: Maximum impact within size constraints

### `/agents` - Generate Codex AGENTS.md

This command synthesizes knowledge from all three local systems into instructions for cloud-based task execution. It creates AGENTS.md files that reference your existing AI configuration, enabling Codex to work with full awareness of your patterns and conventions.

**When to use**:
- After completing local AI setup (context, rules, instructions)
- When you have complex tasks suitable for delegation
- To enable autonomous development capabilities

**What it creates**:
- Root `AGENTS.md` with project overview and AI system references
- Nested `AGENTS.md` files for specific components if needed
- Cross-references to CLAUDE.md, Cursor rules, and Copilot instructions
- Task validation and testing instructions
- Environment configuration guidance

**Cloud execution**: Tasks typically complete in 3-8 minutes and deliver via PR

**Time investment**: 10-15 minutes to generate comprehensive agent instructions
</command_category>

## Maintenance Commands

<command_category name="ai-maintenance">
These commands help you keep your AI configuration synchronized with your evolving codebase. Like tending a garden, regular maintenance ensures your AI assistance remains helpful rather than becoming outdated.

### `/context-update` - Update Context for New Patterns

This surgical update command analyzes what has changed since the last documentation generation and updates only the affected areas. It preserves valuable existing documentation while integrating new discoveries.

**When to use**:
- After significant new features
- Following architectural refactoring
- Quarterly maintenance schedule
- When you notice AI suggestions feel outdated

**What it updates**:
- Adds newly discovered patterns
- Marks deprecated patterns
- Updates architecture documentation
- Refreshes code examples
- Validates changes against DeepWiki if available

**Approach**: Incremental updates, not regeneration

### `/rules-sync` - Synchronize Cursor Rules

This command ensures your Cursor rules remain aligned with updated patterns and architectural changes. It's like retuning an instrument to ensure it still plays in harmony with the rest of the orchestra.

**When to use**:
- After updating Claude Code context
- When noticing repeated pattern violations
- Following team retrospectives on code quality
- When rules feel constraining rather than helpful

**What it synchronizes**:
- Updates existing rules with evolved patterns
- Adds rules for new conventions
- Deprecates rules for abandoned patterns
- Rebalances rule categories

**Validation**: Tests rules to ensure they guide effectively

### `/instructions-optimize` - Optimize Copilot Instructions

This command refines Copilot instructions to maximize their impact within strict size constraints. Like a poet refining verses, it ensures every word earns its place through measurable benefit.

**When to use**:
- When approaching size limits
- After identifying which patterns prevent most errors
- Annually for comprehensive optimization
- When AI suggestions don't match expectations

**Optimization goals**:
- Reduce size while maintaining coverage
- Focus on highest-impact guidance
- Improve clarity through examples
- Create space for future additions

**Success metrics**: Error prevention per line of instruction

### `/agents-sync` - Synchronize AGENTS.md

This command updates AGENTS.md files to reflect changes in your local AI systems and codebase patterns. It ensures cloud-based tasks remain aligned with current development practices.

**When to use**:
- After updating any of the three local AI systems
- When delegation patterns have evolved
- Following introduction of new workflows
- When Codex PRs don't match current standards

**What it synchronizes**:
- Updates cross-references to other AI files
- Refreshes task examples and validation steps
- Aligns with new architectural patterns
- Updates environment configuration needs

**Cloud awareness**: Considers what tasks benefit from cloud execution
</command_category>

## Orchestration Workflows

<command_category name="workflows">
These commands guide you through multi-step processes, ensuring you execute complex procedures in the correct order with proper validation at each stage.

### `/ai-ecosystem-setup` - Complete Ecosystem Setup

This master orchestrator walks you through the entire process of establishing AI assistance for a project. It ensures each phase builds properly on the previous one, with quality checkpoints throughout.

**Process overview**:
1. **Phase 1**: Generate comprehensive context (20-30 min)
2. **Phase 2**: Create behavioral rules (10-15 min)
3. **Phase 3**: Distill persistent instructions (10 min)
4. **Phase 4**: Synthesize cloud agent instructions (10-15 min)
5. **Phase 5**: Validate integration (5-10 min)
6. **Phase 6**: Document and communicate (5 min)

**Quality assurance**: Includes validation steps between phases

**Best practice**: Reserve 60-75 minutes for uninterrupted setup

### `/ai-ecosystem-maintenance` - Complete Maintenance Workflow

This orchestrator guides you through a comprehensive maintenance cycle for all four AI systems. It ensures updates are performed in the correct sequence with proper validation between phases.

**Process overview**:
1. **Phase 1**: Update Claude Code context (15-20 min)
2. **Phase 2**: Synchronize Cursor rules (10-15 min)
3. **Phase 3**: Optimize Copilot instructions (10-15 min)
4. **Phase 4**: Update AGENTS.md files (10-15 min)
5. **Phase 5**: Validate integration (5-10 min)
6. **Phase 6**: Document and communicate (5 min)

**Dependency management**: Each phase builds on the previous one
- Context updates must complete before rule sync
- Rule sync informs instruction optimization
- All three local systems update before AGENTS.md
- All four must complete before integration testing

**Quality assurance**: Validation checkpoints between each phase

**Best practice**: Schedule maintenance cycles quarterly or after major feature releases
</command_category>

## Global Utility Commands

### `/ai-ecosystem-check` - Check and Update Configuration

This utility command checks your project for AI ecosystem configuration and updates CLAUDE.md with current status. It also verifies DeepWiki availability, checks for AGENTS.md files, and ensures proper documentation.

**When to use**:
- To verify AI ecosystem setup status
- When unsure about maintenance schedule
- To add ecosystem documentation to CLAUDE.md
- To check DeepWiki MCP configuration
- To verify AGENTS.md presence and currency

**What it does**:
- Detects all AI configuration files (including AGENTS.md)
- Calculates maintenance status
- Updates CLAUDE.md with ecosystem information
- Adds DeepWiki documentation if available
- Reports on cloud delegation readiness

## Understanding Command Execution

All commands in this ecosystem are designed for immediate execution. When you run any setup or maintenance command, Claude Code will:

1. **Begin work immediately** - No need to provide additional confirmation
2. **Follow all phases sequentially** - Each command contains complete instructions
3. **Create or update files actively** - You'll see real-time progress
4. **Provide validation points** - Critical checkpoints ensure quality

This immediate execution design ensures efficient workflow and prevents the confusion of passive documentation. Each command is a work order, not just a reference guide.

### Workflow Commands vs Individual Commands

**Individual commands** (in `ai-setup/` and `ai-maintenance/`) execute their specific task autonomously:
- Run independently
- Complete without additional input
- Focus on one system

**Workflow commands** (in `workflows/`) orchestrate multiple commands:
- Guide you through running individual commands in sequence
- Provide validation between phases
- Ensure proper dependencies are respected
- Offer decision points for human judgment

## External Resources and Integrations

### DeepWiki MCP Integration

DeepWiki provides AI-generated documentation and analysis for GitHub repositories. When available, it can enhance your AI ecosystem with:

**External Perspective**: Get an outside view of your architecture and patterns to validate internal understanding.

**Setup DeepWiki MCP**:
```bash
claude mcp add deepwiki https://mcp.deepwiki.com/sse
```

**Usage in Commands**: Our ecosystem commands automatically detect and leverage DeepWiki when available, using it for:
- Pattern validation during context generation
- External perspective on architectural decisions
- Understanding complex implementations
- Supplemental documentation references

**Note**: DeepWiki is particularly valuable for Mixpanel SDK repositories, as it provides comprehensive analysis of these codebases.

### OpenAI Codex Integration

OpenAI Codex provides cloud-based autonomous development capabilities that complement local AI assistance.

**Key Differences**:
- **Execution**: Runs in cloud containers (3-8 minutes typical)
- **Delivery**: Creates pull requests rather than local changes
- **Scope**: Handles complete features, refactors, and complex tasks
- **Workflow**: Operates in parallel to your local development

**AGENTS.md Structure**: Codex reads AGENTS.md files that reference your other AI systems:
```markdown
## AI Context References

For comprehensive context, refer to:
- `CLAUDE.md` - Project patterns and conventions
- `.cursor/rules/` - Behavioral enforcement rules
- `.github/copilot-instructions.md` - Style guidelines

Respect all patterns documented in these files.
```

**Best Use Cases**:
- Large refactoring tasks
- Adding comprehensive test coverage
- Security vulnerability fixes
- Code review and improvements
- Feature implementations with clear specs

## Best Practices for AI Configuration Management

<best_practices>
Understanding when and how to use these commands is crucial for maintaining an effective AI assistance ecosystem. Here are practices that have proven successful:

### Establish a Maintenance Rhythm

Just as codebases need regular refactoring, AI configurations need periodic updates. Consider this maintenance schedule:

**Weekly**: During team retrospectives, note any patterns where AI suggestions consistently need correction. These are candidates for rule updates. Also note any complex tasks that could be delegated to Codex.

**Monthly**: Run a quick rules sync if you've been actively developing new features. Update AGENTS.md if delegation patterns have changed. This prevents drift between your actual patterns and AI guidance.

**Quarterly**: Perform a comprehensive context update. This deeper analysis can reveal evolutionary changes in your architecture and patterns. Use DeepWiki for external validation if available. Ensure all four systems remain aligned.

**Annually**: Optimize Copilot instructions to ensure they remain focused on highest-impact guidance. Review Codex task success rates and adjust AGENTS.md accordingly.

### Version Control Your AI Configuration

Treat your AI configuration as part of your codebase:
- Commit generated files to version control
- Review AI configuration changes in pull requests
- Tag versions before major updates
- Document why changes were made
- Track Codex PR success rates

This creates a valuable history of how your team's patterns and practices have evolved.

### Team Collaboration

AI configuration is most effective when it's a team effort:
- Share the initial setup across team members
- Rotate maintenance responsibilities
- Discuss configuration updates in team meetings
- Gather feedback on rule effectiveness
- Share DeepWiki insights when analyzing patterns
- Review Codex PRs to ensure they meet standards
- Celebrate successful cloud delegations

### Monitor Effectiveness

Track these indicators to know when maintenance is needed:
- Frequency of overriding AI suggestions
- Code review comments about pattern violations
- Time spent explaining conventions to new team members
- Developer satisfaction with AI assistance
- Codex PR acceptance rate
- Tasks suitable for cloud delegation

When these metrics decline, it's time for an update cycle.

### Leverage External Perspectives

When available, use tools like DeepWiki MCP to:
- Validate your internal pattern documentation
- Get fresh perspectives on architecture
- Understand how others might perceive your codebase
- Identify patterns you might take for granted

### Optimize Task Distribution

Choose the right AI system for each task:
- **Immediate fixes**: Copilot's inline suggestions
- **Active development**: Cursor's contextual rules
- **Deep questions**: Claude Code's knowledge queries
- **Complex work**: Codex's cloud execution

The AGENTS.md files help Codex understand when to leverage the other systems' knowledge.
</best_practices>

## Understanding Command Evolution

<evolution_philosophy>
These commands themselves are designed to evolve. As you use them across different projects, you'll discover improvements and refinements. The beauty of storing them in your home directory with version control is that every project benefits from these learnings.

Consider creating your own commands for project-specific needs:
- Migration commands for moving between frameworks
- Analysis commands for specific architectural patterns
- Integration commands for your team's unique tools
- External validation commands leveraging DeepWiki
- Cloud delegation patterns specific to your workflows

The commands provided here are a foundation. Build upon them to create an AI assistance ecosystem perfectly tailored to how your team works.
</evolution_philosophy>

## Troubleshooting Common Issues

<troubleshooting_guide>
When things don't work as expected, these solutions address the most common issues:

**"Commands aren't appearing in Claude Code"**
- Ensure files are in `~/..claude/context/commands/` directory
- Check file extensions are `.md`
- Restart Claude Code to refresh command list
- Verify file permissions allow reading

**"Generated patterns don't match our code"**
- Ensure you're running commands from project root
- Check that `/init` has been run or CLAUDE.md exists
- Verify Claude Code can access all source directories
- Consider running context generation with specific focus areas
- Use DeepWiki for external validation if available

**"Rules aren't affecting Cursor's suggestions"**
- Confirm `.cursor/rules/` directory exists in project
- Check glob patterns match your file naming
- Verify MDC syntax is correct
- Test with a file that explicitly matches rule globs

**"Copilot instructions seem to have no effect"**
- Ensure `.github/copilot-instructions.md` exists
- Verify file is under 500 lines
- Check for syntax errors in markdown
- Confirm Copilot extension is updated

**"AGENTS.md not being read by Codex"**
- Verify AGENTS.md is in project root or nested appropriately
- Check markdown syntax is valid
- Ensure cross-references to other AI files use correct paths
- Confirm Codex has access to the repository
- Test with simple task to verify basic functionality

**"Codex PRs don't follow our patterns"**
- Check AGENTS.md references to other AI systems
- Verify referenced files (CLAUDE.md, rules, instructions) are current
- Run agents-sync to update references
- Include explicit validation steps in AGENTS.md

**"Maintenance commands aren't finding changes"**
- Verify previous generation created all expected files
- Check git history is accessible
- Ensure sufficient time has passed for pattern evolution
- Consider if changes are significant enough to document

**"Commands seem to wait for input instead of executing"**
- Ensure you're using the latest version of commands with execution directives
- Check that the command starts with `<user_request>` and `<task_confirmation>` sections
- Verify the command includes `<immediate_action>` instructions
- Update older commands by adding these directive sections

**"DeepWiki MCP not working"**
- Verify DeepWiki is configured: `claude mcp list`
- Add if missing: `claude mcp add deepwiki https://mcp.deepwiki.com/sse`
- Check if your repository is available on DeepWiki
- Ensure MCP tools are enabled in your environment

**"Codex tasks timing out or failing"**
- Check if task is too large (break into smaller pieces)
- Verify setup scripts in AGENTS.md work correctly
- Ensure environment dependencies are properly specified
- Consider if task needs internet access configuration
- Review Codex logs for specific error messages
</troubleshooting_guide>

## Command Quick Reference

For easy reference, here's a summary of all commands and their primary purposes:

| Command | Purpose | When to Use | Time Required |
|---------|---------|-------------|---------------|
| `/context` | Generate initial Claude Code context | New project setup | 20-30 min |
| `/cursor` | Create Cursor behavioral rules | After context generation | 10-15 min |
| `/copilot` | Generate Copilot instructions | After rules creation | 10 min |
| `/agents` | Create Codex AGENTS.md files | After local setup complete | 10-15 min |
| `/ai-ecosystem-setup` | Complete setup orchestration | Initial configuration | 60-75 min |
| `/context-update` | Update context incrementally | Quarterly or after major changes | 15-20 min |
| `/rules-sync` | Synchronize rules with context | After context updates | 10-15 min |
| `/instructions-optimize` | Optimize instruction size/impact | Annually or when at limits | 15-20 min |
| `/agents-sync` | Update AGENTS.md files | After local system updates | 10-15 min |
| `/ai-ecosystem-maintenance` | Complete maintenance cycle | Quarterly updates | 60-75 min |
| `/ai-ecosystem-check` | Check configuration status | Anytime to verify setup | 2-5 min |

## Getting Started

<getting_started>
If you're new to this AI ecosystem approach, here's your roadmap:

1. **Start with one project**: Choose a codebase you know well for your first setup. This helps you validate that the AI discovers patterns correctly.

2. **Configure external tools** (optional): 
   - DeepWiki MCP for additional perspective: `claude mcp add deepwiki https://mcp.deepwiki.com/sse`
   - GitHub app for Codex access (see OpenAI documentation)

3. **Run the orchestrator**: Use `/ai-ecosystem-setup` for guided setup. The workflow will immediately begin checking prerequisites and guide you through each phase with validation steps.

4. **Work normally for a week**: Use your AI tools as usual and note where they excel or struggle. Try delegating a complex task to Codex.

5. **Perform first maintenance**: Based on your observations, run appropriate maintenance commands to refine the configuration.

6. **Expand to other projects**: Apply learnings from your first project to set up AI assistance for others.

Remember, the goal isn't perfect AI assistance immediately. It's creating a system that continuously improves, learning and evolving alongside your codebase. Each maintenance cycle makes your AI assistants more helpful, more aligned with how your team actually works.

The addition of cloud-based Codex extends your capabilities from real-time assistance to autonomous development, enabling you to delegate entire features while you focus on what matters most.
</getting_started>

## Contributing to These Commands

<contribution_guide>
These commands are living documents, designed to improve through community use. If you discover enhancements:

1. **Document your improvements**: Keep notes on what changes you make and why
2. **Test across projects**: Ensure improvements work generally, not just for one codebase
3. **Share with the community**: Consider contributing back improvements
4. **Learn from others**: See how other teams adapt these commands

The best improvements often come from real-world usage revealing opportunities the original design missed.
</contribution_guide>

## Final Thoughts

<closing_reflection>
Managing AI assistance for software development is an emerging practice. These commands represent current best practices, but the field is rapidly evolving. What matters most is the principle: AI assistance should be thoughtfully configured, actively maintained, and continuously improved.

Your AI assistants are like team members who need onboarding, ongoing training, and regular feedback. The effort you invest in their configuration pays dividends through improved code quality, faster development, and more consistent patterns across your team.

The addition of cloud-based execution through Codex represents the next evolution - moving from AI as an assistant to AI as a collaborative developer who can independently complete complex tasks while respecting all your established patterns and practices.

Use these commands not as rigid procedures but as a foundation for developing your own practices. The best AI configuration is one that fits naturally into your team's workflow, evolving alongside your codebase and development practices.

Happy coding with your well-configured AI teammates - both local and in the cloud!
</closing_reflection>