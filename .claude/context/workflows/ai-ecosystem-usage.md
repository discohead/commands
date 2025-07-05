# Workflow: Using the AI Ecosystem Commands

## Overview
This workflow guides you through effectively using AI Ecosystem commands to set up and maintain AI assistant configurations across your projects.

## Initial Setup Workflow

### 1. **Navigate to Target Repository**
```bash
cd /path/to/your/project
```

### 2. **Run Ecosystem Setup**
Execute the complete setup workflow:
```
/ai-ecosystem-setup
```

This orchestrates:
1. Context generation (Claude Code)
2. Cursor rules creation
3. Copilot instructions generation
4. Codex AGENTS.md creation

**Expected Duration**: 45-60 minutes for full analysis

### 3. **Verify Generated Files**
Check that all layers were created:
```bash
# Knowledge Layer
ls -la CLAUDE.md
ls -la .claude/context/

# Behavioral Layer  
ls -la .cursor/rules/

# Persistent Layer
ls -la .github/copilot-instructions.md

# Delegation Layer
ls -la AGENTS.md
```

### 4. **Review and Customize**
- Read generated `CLAUDE.md` for accuracy
- Check `.claude/context/context-map.md` for navigation
- Review `.cursor/rules/always.mdc` for critical patterns
- Examine `AGENTS.md` for cloud task definitions

## Maintenance Workflow

### 1. **Regular Maintenance** (Weekly/Bi-weekly)
Run the maintenance workflow:
```
/ai-ecosystem-maintenance
```

This updates all configurations based on code changes.

### 2. **Targeted Updates**
For specific layer updates:

```bash
# Update Claude context only
/context-update

# Sync Cursor rules
/rules-sync  

# Optimize Copilot instructions
/instructions-optimize

# Update Codex agents
/agents-sync
```

### 3. **Post-Refactor Updates**
After major refactoring:
1. Run `/context-update` first
2. Then `/ai-ecosystem-maintenance`
3. Review changes in all config files
4. Commit updates

## Integration Workflow

### 1. **With Version Control**
```bash
# Before running commands
git checkout -b update-ai-configs

# Run commands
/ai-ecosystem-maintenance

# Review changes
git diff

# Commit configurations
git add .
git commit -m "Update AI ecosystem configurations"
```

### 2. **With CI/CD**
Add to your CI pipeline:
```yaml
# .github/workflows/ai-config-check.yml
- name: Check AI Configurations
  run: |
    claude-code --command /ai-ecosystem-check
```

### 3. **With Team Collaboration**
1. One team member runs setup/maintenance
2. Commits configuration files
3. Team pulls updates
4. All tools use consistent patterns

## Command Selection Guide

### When to Use Setup Commands
| Scenario | Command | Duration |
|----------|---------|----------|
| New project | `/ai-ecosystem-setup` | 45-60 min |
| Just need context | `/context` | 20-30 min |
| Adding Cursor | `/cursor` | 10-15 min |
| Setting up Copilot | `/copilot` | 10 min |
| Enabling Codex | `/agents` | 15 min |

### When to Use Maintenance Commands
| Scenario | Command | Frequency |
|----------|---------|-----------|
| Regular updates | `/ai-ecosystem-maintenance` | Weekly |
| New patterns added | `/context-update` | As needed |
| Rules out of sync | `/rules-sync` | Bi-weekly |
| Copilot suggestions off | `/instructions-optimize` | Monthly |
| Cloud tasks outdated | `/agents-sync` | Bi-weekly |

### When to Use Utility Commands
| Need | Command |
|------|---------|
| Verify all configs exist | `/ai-ecosystem-check` |
| Quick status update | `/ai-ecosystem-check` |

## Best Practices

### 1. **Start Fresh**
For first-time setup:
- Remove any existing partial configurations
- Run full ecosystem setup
- Review all generated files

### 2. **Incremental Updates**
For ongoing maintenance:
- Use targeted maintenance commands
- Review diffs before committing
- Keep configurations in version control

### 3. **Team Coordination**
- Designate one person for initial setup
- Share configurations via version control
- Document any manual customizations
- Run maintenance on schedule

### 4. **Performance Optimization**
- Run analysis during off-hours
- Use targeted updates vs. full regeneration
- Cache DeepWiki results if available

### 5. **Quality Assurance**
- Review generated patterns for accuracy
- Test Cursor rules with sample code
- Verify Copilot suggestions align
- Validate Codex task definitions

## Troubleshooting

### Missing Prerequisites
If commands fail due to missing files:
1. Check previous command outputs
2. Run prerequisite commands first
3. Verify file paths are correct

### Large Codebases
For repos with many files:
1. Consider running context generation first
2. Use targeted maintenance commands
3. Break workflow into smaller sessions

### Integration Issues
If tools don't recognize configs:
1. Verify file locations match tool expectations
2. Check file permissions
3. Restart tools after configuration

### DeepWiki Unavailable
If DeepWiki MCP is not configured:
- Commands will skip external validation
- Rely on internal analysis only
- Consider configuring MCP for better results

## Advanced Workflows

### Custom Command Chains
Create your own workflow by chaining commands:
```bash
# Example: Update context and rules only
/context-update && /rules-sync
```

### Selective Layer Updates
Update specific layers based on changes:
```bash
# Frontend changes: Update UI patterns
/context-update --focus=components
/cursor --components-only

# Backend changes: Update service patterns  
/context-update --focus=services
/agents-sync --services
```

### Multi-Repository Management
For managing multiple related repos:
1. Run setup on each repository
2. Note shared patterns
3. Consider creating shared command templates
4. Synchronize updates across repos