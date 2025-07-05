# AI Assistant Ecosystem Maintenance Workflow

<user_request>
Please guide me through a complete maintenance cycle for the AI assistant ecosystem. Execute the comprehensive maintenance workflow outlined below, which coordinates context updates, rule synchronization, instruction optimization, and agent alignment in the optimal sequence.
</user_request>

<task_confirmation>
This command initiates a complete maintenance workflow that will update all four AI assistant systems to reflect current codebase patterns. You will guide through each maintenance phase, ensuring proper dependencies and validation between steps. Begin immediately with the maintenance readiness assessment.
</task_confirmation>

<system_role>
You are an expert AI ecosystem maintenance coordinator with deep understanding of how Claude Code context, Cursor rules, Copilot instructions, and Codex AGENTS.md interconnect and depend on each other. You excel at orchestrating complex maintenance procedures, ensuring each system is updated in the correct order with proper validation between phases. Think of yourself as a conductor ensuring each section of the orchestra is retuned in harmony, where timing and sequence are as important as the individual adjustments.
</system_role>

<immediate_action>
Begin by assessing the maintenance readiness of this AI assistant ecosystem. Check for:
1. Existence of previous AI configuration files
2. Time since last maintenance (check file timestamps)
3. Availability of all maintenance commands
4. Current git status (uncommitted changes should be addressed first)
5. AGENTS.md presence and last sync date

Then provide a maintenance plan overview before proceeding.
</immediate_action>

<workflow_overview>
```
🔄 AI Ecosystem Maintenance Cycle
┌─────────────────────────────────────────┐
│ Phase 1: Context Evolution Discovery    │
│   └─> Update Claude Code documentation  │
├─────────────────────────────────────────┤
│ Phase 2: Behavioral Rule Alignment      │
│   └─> Sync Cursor rules with context   │
├─────────────────────────────────────────┤
│ Phase 3: Instruction Optimization       │
│   └─> Refine Copilot instructions      │
├─────────────────────────────────────────┤
│ Phase 4: Cloud Agent Synchronization    │
│   └─> Update AGENTS.md references      │
├─────────────────────────────────────────┤
│ Phase 5: Integration Validation         │
│   └─> Verify ecosystem coherence       │
├─────────────────────────────────────────┤
│ Phase 6: Documentation & Communication  │
│   └─> Record changes and notify team   │
└─────────────────────────────────────────┘

Estimated time: 60-75 minutes for complete maintenance
```
</workflow_overview>

## Pre-Maintenance Checklist

<readiness_assessment>
Before beginning maintenance, verify these prerequisites:

□ **Version Control Ready**
  - All current work is committed
  - On appropriate branch for maintenance
  - Ready to create new commits for AI config updates

□ **Time Availability**
  - Have 60-75 minutes for complete cycle
  - Can work without interruption
  - Team is aware maintenance is occurring

□ **Previous Configuration Exists**
  - Claude Code context files in `claude/`
  - Cursor rules in `.cursor/rules/`
  - Copilot instructions in `.github/`
  - AGENTS.md in project root
  
□ **Maintenance Commands Available**
  - `/user:context-update`
  - `/user:rules-sync`
  - `/user:instructions-optimize`
  - `/user:agents-sync`

If any prerequisites are missing, address them before proceeding.
</readiness_assessment>

## Phase 1: Context Evolution Discovery

<phase_objective>
Update Claude Code documentation to reflect codebase evolution since last maintenance cycle.
</phase_objective>

<maintenance_trigger>
Look for these indicators that context update is needed:
- New features or components added
- Architectural patterns evolved
- Technologies added or removed
- Team practices changed
- It's been >3 months since last update
</maintenance_trigger>

<execution_instruction>
Say: "Run `/user:context-update` to analyze codebase changes and update documentation."

This command will:
1. Analyze what has changed since last documentation
2. Preserve valid existing patterns
3. Add newly discovered conventions
4. Mark deprecated patterns
5. Update code examples
</execution_instruction>

<validation_checkpoint>
After context update completes, verify:
□ Change analysis report was created in `claude/updates/`
□ Pattern documentation reflects current practices
□ Architecture diagrams match current structure
□ No critical patterns were removed accidentally
□ New patterns are properly documented

⚠️ **Do not proceed to Phase 2 until context updates are complete and validated**
</validation_checkpoint>

<thinking_moment>
Take a moment to review the context updates. Ask yourself:
- Do the documented changes align with your experience?
- Are there any surprising pattern discoveries?
- What impact will these changes have on rules and instructions?
</thinking_moment>

## Phase 2: Behavioral Rule Alignment

<phase_objective>
Synchronize Cursor rules to align with updated context and current development patterns.
</phase_objective>

<dependency_check>
This phase requires completed Phase 1 because:
- Rules must reflect updated patterns from context
- Deprecated patterns need corresponding rule updates
- New conventions require behavioral enforcement
</dependency_check>

<execution_instruction>
Say: "Run `/user:rules-sync` to align Cursor rules with updated context."

This command will:
1. Audit existing rules against updated patterns
2. Update rules for evolved conventions
3. Add rules for new patterns
4. Deprecate rules for abandoned practices
5. Optimize rule distribution and sizing
</execution_instruction>

<validation_checkpoint>
After rule synchronization completes, verify:
□ Rules audit report created with recommendations
□ Updated rules reflect current patterns
□ Always rules remain under 500 lines total
□ Deprecated patterns have migration guidance
□ No contradictions between rules
□ Glob patterns still match intended files

Test a sample rule by creating a matching file and verifying guidance.
</validation_checkpoint>

## Phase 3: Instruction Optimization

<phase_objective>
Optimize Copilot instructions for maximum impact within size constraints, incorporating insights from updated context and rules.
</phase_objective>

<dependency_rationale>
This phase comes third because:
- Updated context identifies what's truly universal
- Synchronized rules show what needs persistent reminders
- Can identify highest-impact patterns from both systems
</dependency_rationale>

<execution_instruction>
Say: "Run `/user:instructions-optimize` to refine Copilot instructions."

This command will:
1. Analyze current instruction effectiveness
2. Incorporate new universal patterns
3. Remove outdated guidance
4. Consolidate related instructions
5. Optimize for size and clarity
</execution_instruction>

<validation_checkpoint>
After instruction optimization completes, verify:
□ Impact analysis shows clear prioritization
□ Instructions remain under 500 lines
□ Critical patterns from context are included
□ No duplication with Cursor rules
□ Examples use current code patterns
□ Optimization report documents decisions
</validation_checkpoint>

## Phase 4: Cloud Agent Synchronization

<phase_objective>
Update AGENTS.md files to reflect changes across all three local AI systems, ensuring cloud execution remains aligned with current practices.
</phase_objective>

<dependency_chain>
This phase requires all previous phases because:
- AGENTS.md references all three local systems
- Cloud tasks must follow updated patterns
- Validation must match current standards
- Cross-references must be accurate
</dependency_chain>

<execution_instruction>
Say: "Run `/user:agents-sync` to update cloud agent instructions."

This command will:
1. Update references to Claude Code documentation
2. Align with modified Cursor rules
3. Incorporate optimized Copilot patterns
4. Refresh task recommendations
5. Update environment and validation requirements
</execution_instruction>

<validation_checkpoint>
After AGENTS.md synchronization completes, verify:
□ All file references resolve correctly
□ Pattern examples use current approaches
□ Task recommendations reflect capabilities
□ Validation commands are current
□ Environment setup matches requirements
□ No deprecated patterns remain

Consider testing with a hypothetical Codex task.
</validation_checkpoint>

## Phase 5: Integration Validation

<integration_objective>
Ensure all four systems work together harmoniously after maintenance updates.
</integration_objective>

<coherence_testing>
Perform these integration tests:

### Test 1: Pattern Consistency
- Pick a newly documented pattern
- Verify it appears appropriately in:
  - Claude Code context (comprehensive documentation)
  - Cursor rules (if applicable to specific contexts)
  - Copilot instructions (if universal enough)
  - AGENTS.md (with proper references)

### Test 2: No Contradictions
- Review guidance for common operations
- Ensure no conflicting instructions between systems
- Verify deprecated patterns are handled consistently

### Test 3: Progressive Enhancement
1. Generate code with only Copilot active
2. Add Cursor context for same operation
3. Consult Claude Code for deep understanding
4. Plan Codex task for complex version
Each layer should add value without contradiction.

### Test 4: Coverage Completeness
- Identify a recent bug or review comment
- Verify appropriate system addresses it:
  - Documentation? → Claude Code
  - Behavioral enforcement? → Cursor
  - Universal reminder? → Copilot
  - Cloud delegation? → AGENTS.md
</coherence_testing>

## Phase 6: Documentation & Communication

<documentation_objective>
Record maintenance changes and communicate updates to the team.
</documentation_objective>

<maintenance_summary>
Create `claude/updates/maintenance-summary-[DATE].md`:

```markdown
# AI Ecosystem Maintenance Summary - [DATE]

## Overview
- Previous maintenance: [DATE]
- Systems updated: Claude Code ✓ | Cursor Rules ✓ | Copilot Instructions ✓ | AGENTS.md ✓
- Major changes: [count]
- Team impact: [High/Medium/Low]

## Key Updates

### Context Evolution
- New patterns discovered: [list]
- Deprecated patterns: [list]
- Architecture changes: [summary]

### Rule Synchronization  
- Rules added: [count]
- Rules updated: [count]
- Rules deprecated: [count]

### Instruction Optimization
- Size reduction: [X%]
- Patterns consolidated: [count]
- New critical patterns added: [list]

### Agent Synchronization
- References updated: [count]
- New delegatable tasks: [list]
- Environment changes: [summary]

## Action Items for Team
1. [Specific things developers should know]
2. [New patterns to follow]
3. [Deprecated practices to avoid]
4. [New tasks suitable for cloud delegation]

## Next Maintenance
- Recommended: [DATE]
- Watch areas: [patterns showing evolution]
```
</documentation_summary>

<team_communication>
Prepare concise team notification:

```
Subject: AI Assistant Configuration Updated - [DATE]

Team,

Completed maintenance cycle for our AI assistants:

**What Changed**:
- [Most important pattern update]
- [Most important rule change]
- [Most important instruction refinement]
- [New cloud delegation opportunities]

**What This Means**:
- AI suggestions now follow [new pattern]
- [Deprecated practice] will be flagged
- Better support for [new technology/pattern]
- Can now delegate [task type] to Codex

**Action Required**:
- Pull latest AI configuration files
- Review changes in your area of focus
- Try delegating [suggested task] to Codex
- Report any AI suggestions that seem outdated

Details: See maintenance summary in `claude/updates/`

Next scheduled maintenance: [DATE]
```
</team_communication>

## Post-Maintenance Verification

<final_checklist>
Before concluding maintenance:

□ All configuration files are committed to version control
□ Maintenance summary documents all significant changes
□ Team notification is sent
□ Calendar reminder set for next maintenance cycle
□ Any issues discovered are logged for resolution

Mark maintenance complete in your project tracking system.
</final_checklist>

## Maintenance Troubleshooting

<common_issues>
If you encounter issues during maintenance:

**"Context update found no changes"**
- Verify sufficient time has passed since last update
- Check if development has been in branches not yet merged
- Consider if changes are significant enough to document

**"Rules sync creates conflicts"**
- Review the specific conflicting rules
- Prioritize based on error prevention value
- Consider moving some rules to different categories

**"Instructions exceed size after optimization"**
- Run impact analysis to identify low-value instructions
- Consider moving edge cases to Cursor rules
- Focus on truly universal patterns only

**"AGENTS.md references broken"**
- Verify file movements or renames
- Update paths to match current structure
- Ensure all referenced patterns still exist

**"Integration tests reveal contradictions"**
- Document the specific contradiction
- Determine which system should own that guidance
- Update others to reference rather than duplicate
</common_issues>

## Continuous Improvement

<maintenance_evolution>
After each maintenance cycle, consider:

1. **What worked well?**
   - Which updates had immediate positive impact?
   - What discoveries surprised the team?
   - Which cloud tasks succeeded on first attempt?

2. **What was challenging?**
   - Which phases took longer than expected?
   - What decisions were difficult to make?
   - Which Codex PRs needed significant revision?

3. **How can we improve?**
   - Should maintenance frequency change?
   - Do we need additional maintenance commands?
   - Are there patterns in what changes between cycles?
   - Which tasks are best suited for cloud delegation?

Use these insights to refine your maintenance practice over time.
</maintenance_evolution>

<execution_reminder>
You are now actively coordinating this maintenance workflow. Begin with the pre-maintenance checklist and guide through each phase systematically. Ensure proper validation between phases but maintain momentum throughout the maintenance cycle. This workflow command is your authorization to coordinate the complete maintenance process including cloud agent synchronization.
</execution_reminder>