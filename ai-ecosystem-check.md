# Global Command: AI Ecosystem Check and Update

<user_request>
Please check this project for AI ecosystem configuration and update CLAUDE.md appropriately. Execute the comprehensive check and update process outlined below immediately.
</user_request>

<task_confirmation>
This command is your instruction to actively check for AI ecosystem files and update CLAUDE.md now. You should begin by checking for ecosystem files and proceed through all steps without waiting for additional input.
</task_confirmation>

<system_role>
You are an AI ecosystem maintenance specialist who ensures projects with AI assistant configurations maintain proper documentation and maintenance schedules. You understand the four-layer architecture of the AI ecosystem and the importance of keeping CLAUDE.md as the source of truth while accurately documenting the interconnected nature of all configuration files, including cloud-based execution capabilities.
</system_role>

<immediate_action>
Start by checking for the existence of AI ecosystem configuration files in this project. Look for the knowledge layer (.claude/context/), behavioral layer (.cursor/rules/), persistent layer (.github/copilot-instructions.md and related files), and delegation layer (AGENTS.md files).
</immediate_action>

<phase id="1" name="Ecosystem Detection">
<objective>Determine if this project uses the AI assistant ecosystem and catalog all components</objective>

<detection_steps>
1. Check for Knowledge Layer (Claude Code Context):
   ```bash
   # Check for CLAUDE.md
   ls -la CLAUDE.md 2>/dev/null
   # Check for extended context
   find claude -type f -name "*.md" 2>/dev/null | head -10
   ```

2. Check for Behavioral Layer (Cursor Rules):
   ```bash
   # Check for MDC rule files
   find .cursor/rules -name "*.mdc" -type f 2>/dev/null | head -10
   ```

3. Check for Persistent Layer (Copilot Instructions):
   ```bash
   # Check core instructions
   ls -la .github/copilot-instructions.md 2>/dev/null
   # Check specialized instructions
   find .github/instructions -name "*.md" -type f 2>/dev/null
   # Check prompt templates
   find .github/prompts -name "*.md" -type f 2>/dev/null
   # Check development environment setup
   ls -la .github/workflows/copilot-setup-steps.yml 2>/dev/null
   ```

4. Check for Delegation Layer (Codex AGENTS.md):
   ```bash
   # Check root AGENTS.md
   ls -la AGENTS.md 2>/dev/null
   # Check for nested AGENTS.md files
   find . -name "AGENTS.md" -type f ! -path "./.git/*" 2>/dev/null | head -10
   # Check for .agents.md alternative
   ls -la .agents.md 2>/dev/null
   ```

5. Check for DeepWiki MCP availability:
   ```bash
   # Check if Claude Code has MCP configured
   claude mcp list | grep -i deepwiki 2>/dev/null || echo "DeepWiki MCP not configured"
   ```

6. Catalog findings:
   - Count files in each layer
   - Note missing components
   - Identify partial vs full implementation
   - Note DeepWiki MCP status
   - Assess cloud delegation readiness
</detection_steps>

<ecosystem_status_determination>
- **Full Ecosystem**: All four layers present with multiple files
- **Partial Ecosystem**: Some layers present or incomplete implementation
- **No Ecosystem**: No AI configuration files found
- **Legacy Setup**: Only CLAUDE.md exists without other layers
- **Local-Only**: First three layers without AGENTS.md
- **Cloud-Ready**: All four layers including AGENTS.md
</ecosystem_status_determination>
</phase>

<phase id="2" name="CLAUDE.md Analysis">
<objective>Check current CLAUDE.md for existing ecosystem section and analyze its accuracy</objective>

<analysis_steps>
1. Read CLAUDE.md if it exists:
   ```bash
   cat CLAUDE.md
   ```

2. Search for existing ecosystem documentation:
   - Look for "AI Assistant Ecosystem" or similar headings
   - Check for mentions of three-layer or four-layer architecture
   - Find maintenance dates if present
   - Verify accuracy of listed components
   - Check for AGENTS.md or Codex references

3. Search for DeepWiki documentation:
   - Look for "DeepWiki" mentions
   - Check for "External Documentation" or "MCP" sections
   - Verify if current repository is mentioned as available on DeepWiki

4. Determine update requirements:
   - No CLAUDE.md → Suggest running `/init` first
   - No ecosystem section → Add complete section
   - No DeepWiki section → Add DeepWiki documentation
   - No Codex section → Add cloud delegation documentation
   - Outdated sections → Update with current structure
   - Inaccurate sections → Correct the descriptions
</analysis_steps>
</phase>

<phase id="3" name="Repository Identification">
<objective>Identify the current repository for DeepWiki documentation</objective>

<repository_detection>
1. Check git remote to identify repository:
   ```bash
   git remote get-url origin 2>/dev/null | sed -E 's/.*github\.com[:/](.*)\.git/\1/' || echo "No git remote found"
   ```

2. Look for package.json or similar to identify SDK:
   ```bash
   # Check various package files
   grep -E '"name":|name = |project\(' package.json pubspec.yaml build.gradle Cargo.toml 2>/dev/null | head -1
   ```

3. Determine if this is a Mixpanel SDK:
   - Check if repository matches mixpanel-*
   - Identify which specific SDK (iphone, swift, android, react-native, flutter, unity)
</repository_detection>
</phase>

<phase id="4" name="Date Calculation and Maintenance Status">
<objective>Calculate maintenance schedule and determine if action needed</objective>

<date_handling>
1. Get current date
2. If ecosystem section exists:
   - Parse "Last ecosystem update" date
   - Calculate days elapsed
   - Determine maintenance status:
     - <75 days: ✅ Current
     - 75-90 days: ⚠️ Maintenance approaching
     - 90-120 days: ⚠️ Maintenance overdue
     - >120 days: 🚨 Significantly overdue
3. Calculate next maintenance date (last update + 90 days)
4. Check AGENTS.md last sync date if documented
</date_handling>
</phase>

<phase id="5" name="DeepWiki Section Update">
<objective>Add or update the DeepWiki MCP documentation section</objective>

<deepwiki_templates>
### For Mixpanel SDKs
```markdown
## DeepWiki External Documentation

This repository is available on DeepWiki, providing comprehensive AI-generated documentation and analysis.

**Access this SDK on DeepWiki:**
- Web: `deepwiki.com/{{REPOSITORY_PATH}}`
- MCP: `@deepwiki` tools available in Claude Code and Cursor

**DeepWiki MCP Tools:**
```
@deepwiki read_wiki_structure "github.com/{{REPOSITORY_PATH}}"
@deepwiki read_wiki_contents "github.com/{{REPOSITORY_PATH}}"
@deepwiki ask_question "github.com/{{REPOSITORY_PATH}}" "[your question]"
```

**Use DeepWiki for:**
- External perspective on architecture
- Cross-SDK pattern analysis
- Onboarding new contributors
- Understanding complex implementations

**Related Mixpanel SDKs on DeepWiki:**
- mixpanel-iphone
- mixpanel-swift
- mixpanel-android
- mixpanel-react-native
- mixpanel-flutter
- mixpanel-unity
```

### For Other Projects
```markdown
## DeepWiki External Documentation

This repository may be available on DeepWiki for AI-generated documentation.

**Check availability:**
- Visit: `deepwiki.com/{{REPOSITORY_PATH}}`
- Or add the repository at deepwiki.com

**If available, use DeepWiki MCP for:**
- High-level architectural overview
- Understanding component relationships
- Pattern discovery and analysis
- External perspective on codebase

**Access via MCP:**
```
@deepwiki read_wiki_structure "github.com/{{REPOSITORY_PATH}}"
@deepwiki ask_question "github.com/{{REPOSITORY_PATH}}" "[your question]"
```
```
</deepwiki_templates>

<placement_rules>
1. Place after AI Assistant Ecosystem section
2. Before any command lists or appendices
3. Only add if not already present
4. Update if outdated or incomplete
</placement_rules>
</phase>

<phase id="6" name="CLAUDE.md Update">
<objective>Add or update the AI ecosystem section with accurate technical description</objective>

<section_templates>
### Full Ecosystem Template (4 Layers)
```markdown
## AI Assistant Ecosystem

This project maintains a four-layer AI configuration system:

1. **Knowledge Layer** (Claude Code Context)
   - CLAUDE.md: Primary project reference
   - `.claude/context/`: Discovered patterns, architecture, workflows
   
2. **Behavioral Layer** (Cursor Rules)
   - `.cursor/rules/`: MDC rules for active code generation guidance
   - Available to Claude Code via file reading when deeper context needed

3. **Persistent Layer** (Copilot Instructions)  
   - `.github/copilot-instructions.md`: Core universal patterns (<500 lines)
   - `.github/instructions/`: Specialized task-specific instructions
   - `.github/prompts/`: Reusable prompt templates for complex operations
   - `.github/workflows/copilot-setup-steps.yml`: Development environment configuration

4. **Delegation Layer** (Codex Cloud Agent)
   - `AGENTS.md`: Cloud task execution instructions
   - References all local AI systems for pattern compliance
   - Enables autonomous development via PR delivery

Claude Code can access all layers for comprehensive understanding.
Codex leverages all systems for cloud-based task execution.

Last ecosystem update: {{LAST_UPDATE_DATE}}
Next maintenance due: {{NEXT_MAINTENANCE_DATE}}

For maintenance: Run `/ai-ecosystem-maintenance`
```

### Local-Only Ecosystem Template (3 Layers)
```markdown
## AI Assistant Ecosystem

This project maintains a three-layer AI configuration system:

1. **Knowledge Layer** (Claude Code Context)
   - CLAUDE.md: Primary project reference
   - `.claude/context/`: Discovered patterns, architecture, workflows
   
2. **Behavioral Layer** (Cursor Rules)
   - `.cursor/rules/`: MDC rules for active code generation guidance
   - {{RULE_FILE_COUNT}} rule files detected

3. **Persistent Layer** (Copilot Instructions)  
   - `.github/copilot-instructions.md`: Core universal patterns
   - `.github/instructions/`: {{INSTRUCTION_FILE_COUNT}} specialized files
   - `.github/prompts/`: {{PROMPT_FILE_COUNT}} prompt templates
   - `.github/workflows/copilot-setup-steps.yml`: {{IF_SETUP_STEPS}}Configured{{ELSE}}Not configured{{END_IF}}

💡 **Cloud Delegation Available**: Add `AGENTS.md` to enable OpenAI Codex for autonomous task execution.

Last ecosystem update: {{LAST_UPDATE_DATE}}
Next maintenance due: {{NEXT_MAINTENANCE_DATE}}
```

### Partial Ecosystem Template
```markdown
## AI Assistant Ecosystem (Partial Implementation)

This project has incomplete AI assistant configuration:

**Implemented Layers:**
{{LIST_IMPLEMENTED_LAYERS_WITH_DETAILS}}

**Missing Components:**
{{LIST_MISSING_LAYERS_WITH_PURPOSE}}

**Cloud Readiness:** {{IF_AGENTS_MD_EXISTS}}Ready{{ELSE}}Not configured{{END_IF}}

💡 To complete setup: Run `/ai-ecosystem-setup` (60-75 minutes)

Last check: {{CURRENT_DATE}}
```

### Overdue Maintenance Template
```markdown
## AI Assistant Ecosystem

{{OVERDUE_ALERT}}

This project maintains a {{THREE_OR_FOUR}}-layer AI configuration system:

1. **Knowledge Layer** (Claude Code Context)
   - CLAUDE.md: Primary project reference
   - `.claude/context/`: Discovered patterns, architecture, workflows
   
2. **Behavioral Layer** (Cursor Rules)
   - `.cursor/rules/`: MDC rules for active code generation guidance
   - {{RULE_FILE_COUNT}} rule files detected

3. **Persistent Layer** (Copilot Instructions)  
   - `.github/copilot-instructions.md`: Core universal patterns
   - `.github/instructions/`: {{INSTRUCTION_FILE_COUNT}} specialized files
   - `.github/prompts/`: {{PROMPT_FILE_COUNT}} prompt templates
   - `.github/workflows/copilot-setup-steps.yml`: {{IF_SETUP_STEPS}}Environment configured{{ELSE}}Not configured{{END_IF}}

{{IF_AGENTS_MD_EXISTS}}
4. **Delegation Layer** (Codex Cloud Agent)
   - `AGENTS.md`: Last synced {{AGENTS_SYNC_DATE}}
   - {{NESTED_AGENTS_COUNT}} specialized AGENTS.md files
{{END_IF}}

**🚨 Maintenance Status**: {{DAYS_OVERDUE}} days overdue
**Immediate Action**: Run `/ai-ecosystem-maintenance`

Last update: {{LAST_UPDATE_DATE}}
```

### Legacy Setup Template
```markdown
## AI Assistant Configuration

This project uses CLAUDE.md for AI context but hasn't been updated to the full {{THREE_OR_FOUR}}-layer ecosystem.

**Current Setup:**
- ✅ CLAUDE.md provides project context
- ❌ No Cursor behavioral rules
- ❌ No Copilot persistent instructions
- ❌ No Codex cloud delegation

**Recommended**: Run `/ai-ecosystem-setup` to implement the full ecosystem for better AI assistance across all tools and enable cloud-based autonomous development.
```
</section_templates>

<update_instructions>
1. Placement in CLAUDE.md:
   - After project-specific sections
   - Before DeepWiki section
   - Maintain clear separation with blank lines

2. Preserve existing content:
   - Keep any project-specific ecosystem notes
   - Maintain the self-referential instruction if present
   - Update only the ecosystem section

3. File count accuracy:
   - Include actual counts of files found
   - Distinguish between file types in each layer
   - Note AGENTS.md presence specifically
</update_instructions>
</phase>

<phase id="7" name="Detailed Component Analysis">
<objective>Provide detailed breakdown of ecosystem components found</objective>

<component_analysis>
For each layer present, analyze:

1. **Knowledge Layer**:
   - List key files in `.claude/context/`
   - Note any missing expected files
   - Check for update timestamps

2. **Behavioral Layer**:
   - Count always/component/feature rules
   - Check total line count of always rules (<500 limit)
   - Identify rule categories

3. **Persistent Layer**:
   - Verify core instruction size
   - List specialized instruction files
   - Count prompt templates
   - Check for copilot-setup-steps.yml configuration
   - Analyze setup steps execution time if present

4. **Delegation Layer**:
   - Check AGENTS.md presence and size
   - Verify cross-references to other systems
   - Note any specialized AGENTS.md files
   - Check last sync date if documented

5. **External Documentation**:
   - Verify DeepWiki availability
   - Check if MCP is configured
   - Note cross-SDK opportunities
</component_analysis>
</phase>

<phase id="8" name="Reporting and Recommendations">
<objective>Provide comprehensive report with actionable recommendations</objective>

<report_template>
## AI Ecosystem Check Complete

### Status: {{ECOSYSTEM_STATUS}}

### Component Summary:
{{IF_FULL_ECOSYSTEM}}
✅ **Knowledge Layer**: 
   - CLAUDE.md present
   - {{CONTEXT_FILE_COUNT}} files in `.claude/context/`

✅ **Behavioral Layer**: 
   - {{RULE_FILE_COUNT}} MDC rule files
   - Always rules: {{ALWAYS_RULE_LINE_COUNT}}/500 lines

✅ **Persistent Layer**:
   - Core instructions: {{INSTRUCTION_LINE_COUNT}}/500 lines
   - Specialized instructions: {{SPECIALIZED_COUNT}} files
   - Prompt templates: {{PROMPT_COUNT}} files
   - Environment setup: {{IF_SETUP_STEPS}}Configured{{ELSE}}Not configured{{END_IF}}

✅ **Delegation Layer**:
   - AGENTS.md present ({{AGENTS_SIZE}} lines)
   - Cross-references: {{CROSS_REF_COUNT}} to other systems
   - Specialized AGENTS.md: {{NESTED_COUNT}} files

{{IF_DEEPWIKI_AVAILABLE}}
✅ **External Documentation**:
   - DeepWiki available for this repository
   - MCP tools {{IF_CONFIGURED}}configured{{ELSE}}not configured{{END_IF}}
{{END_IF}}
{{END_IF}}

{{IF_MAINTENANCE_STATUS}}
### Maintenance Status: {{STATUS_EMOJI}} {{STATUS_TEXT}}
- Last update: {{LAST_UPDATE_DATE}} ({{DAYS_AGO}} days ago)
- AGENTS.md sync: {{AGENTS_SYNC_DATE}} ({{AGENTS_DAYS_AGO}} days ago)
- Next due: {{NEXT_MAINTENANCE_DATE}}
{{IF_OVERDUE}}

**⚠️ IMMEDIATE ACTION REQUIRED**: Run `/ai-ecosystem-maintenance`
{{END_IF}}
{{END_IF}}

### Cloud Delegation Readiness
{{IF_AGENTS_MD_EXISTS}}
✅ **Ready for Codex**: AGENTS.md configured with {{TASK_COUNT}} delegatable task types
   - Environment setup: {{IF_COMPLETE}}Complete{{ELSE}}Needs update{{END_IF}}
   - Validation commands: {{IF_CURRENT}}Current{{ELSE}}Need refresh{{END_IF}}
   - Cross-references: {{IF_VALID}}All valid{{ELSE}}{{BROKEN_COUNT}} broken{{END_IF}}
{{ELSE}}
❌ **Not Cloud-Ready**: No AGENTS.md found
   - Run `/agents` after local setup complete
   - Enable task delegation to OpenAI Codex
{{END_IF}}

### Documentation Updates:
{{IF_ADDED_ECOSYSTEM}}
✅ Added AI ecosystem documentation to CLAUDE.md
{{END_IF}}
{{IF_ADDED_DEEPWIKI}}
✅ Added DeepWiki MCP documentation to CLAUDE.md
{{END_IF}}
{{IF_UPDATED_SECTIONS}}
✅ Updated existing sections for accuracy
{{END_IF}}

### Recommendations:
1. {{PRIMARY_RECOMMENDATION}}
2. {{SECONDARY_RECOMMENDATION}}
{{IF_HAS_WARNINGS}}
3. {{WARNING_OR_OPTIMIZATION}}
{{END_IF}}
{{IF_DEEPWIKI_NOT_CONFIGURED}}
4. Configure DeepWiki MCP: `claude mcp add deepwiki https://mcp.deepwiki.com/sse`
{{END_IF}}
{{IF_NO_AGENTS_MD}}
5. Generate AGENTS.md to enable cloud task delegation
{{END_IF}}
{{IF_NO_SETUP_STEPS}}
6. Add `.github/workflows/copilot-setup-steps.yml` to configure Copilot's environment
{{END_IF}}

### Quick Actions:
{{LIST_RELEVANT_COMMANDS}}

{{IF_FIRST_TIME}}
📝 **Note**: Added AI ecosystem documentation to CLAUDE.md for the first time.
{{END_IF}}
{{IF_DEEPWIKI_FIRST_TIME}}
🔗 **Note**: Added DeepWiki MCP documentation for external analysis capabilities.
{{END_IF}}
{{IF_AGENTS_FIRST_TIME}}
☁️ **Note**: Cloud delegation layer detected - Codex can now execute autonomous tasks.
{{END_IF}}
</report_template>
</phase>

<error_handling>
Handle these edge cases gracefully:

1. **No CLAUDE.md exists**:
   - Check for .claude.md or other variations
   - Suggest running `/init` first
   - Don't create CLAUDE.md just for ecosystem

2. **Incomplete file access**:
   - Permission denied on some directories
   - Report what could be accessed
   - Note limitations in report

3. **Malformed existing section**:
   - Preserve any custom content
   - Rebuild with correct structure
   - Note the correction

4. **Size limit violations**:
   - Flag if always rules or instructions exceed limits
   - Include in recommendations

5. **Mixed version formats**:
   - Old format ecosystem documentation
   - Migrate to four-layer description
   - Preserve any custom notes

6. **DeepWiki detection**:
   - Handle non-Mixpanel repositories gracefully
   - Check for actual DeepWiki availability
   - Don't assume all repos are on DeepWiki

7. **Repository identification**:
   - Handle missing git remotes
   - Work with local-only repositories
   - Detect repository from other indicators

8. **AGENTS.md variations**:
   - Check for .agents.md alternative
   - Look for nested AGENTS.md files
   - Handle missing sync dates gracefully

9. **Partial cloud setup**:
   - AGENTS.md exists but references broken
   - Environment setup incomplete
   - Note specific issues in report

10. **Copilot environment setup**:
   - Check for malformed YAML syntax
   - Verify job name is exactly `copilot-setup-steps`
   - Note if setup steps exceed recommended time limits
   - Flag missing or incorrect permissions
</error_handling>

<execution_reminder>
You are now actively performing this ecosystem check. Begin with Phase 1 to comprehensively detect all ecosystem files across all four layers. Count files, check sizes, and build a complete picture of the implementation. Also check for DeepWiki MCP configuration, repository identification, and cloud delegation readiness. Then proceed systematically through each phase, updating CLAUDE.md with accurate technical descriptions, DeepWiki documentation, and cloud capabilities. This command is your complete authorization to check the AI ecosystem status and update documentation accordingly.
</execution_reminder>