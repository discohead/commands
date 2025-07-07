# System Architecture

## Overview

The AI Ecosystem Commands repository implements a **Command-Driven Architecture** where each markdown file serves as an executable command within the Claude Code environment. The system orchestrates configuration generation and maintenance across four distinct AI assistant tools, creating a unified ecosystem for AI-assisted development.

## Architectural Pattern

This is a **Document-as-Code** architecture where:
- Commands are markdown documents with embedded XML-like execution instructions
- Each command is self-contained with complete context and workflow
- Commands can reference and build upon outputs from other commands
- The system maintains state through generated configuration files

## Layer Diagram
```
┌─────────────────────────────────────────────────────────┐
│                   User Interface Layer                   │
│              (Claude Code Command Execution)             │
├─────────────────────────────────────────────────────────┤
│                  Command Processing Layer                │
│        (XML Tag Parsing & Phase-Based Execution)         │
├─────────────────────────────────────────────────────────┤
│                 Integration Layer                        │
│    (DeepWiki MCP, File System, External Tools)          │
├─────────────────────────────────────────────────────────┤
│              Configuration Generation Layer              │
│        (Pattern Discovery & Rule Transformation)         │
├─────────────────────────────────────────────────────────┤
│                  Target Systems Layer                    │
│  (Claude Code, Cursor, GitHub Copilot, OpenAI Codex)    │
└─────────────────────────────────────────────────────────┘
```

## Command Execution Flow Example: AI Ecosystem Setup

1. **User Trigger**: User executes `/ai-ecosystem-setup` workflow
   
2. **Workflow Orchestration**: 
   ```
   workflows/ai-ecosystem-setup.md
   ├─→ ai-setup/context.md (Phase 1)
   ├─→ ai-setup/cursor.md (Phase 2)
   ├─→ ai-setup/copilot.md (Phase 3)
   └─→ ai-setup/agents.md (Phase 4)
   ```

3. **Context Generation Flow** (`ai-setup/context.md`):
   ```
   Read CLAUDE.md → File Discovery → Pattern Analysis → 
   Architecture Mapping → Technology Deep Dive → 
   Workflow Extraction → Command Generation → 
   Knowledge Architecture → Enhanced CLAUDE.md
   ```

4. **Transformation Chain**:
   - Context discoveries → Cursor behavioral rules
   - Cursor rules + Context → Copilot persistent instructions
   - All layers → Codex AGENTS.md configuration

### Evolution [Updated: 2025-07-05]
The Persistent Layer (GitHub Copilot) now includes development environment configuration:
- **New**: `.github/workflows/copilot-setup-steps.yml` for environment setup
- **Impact**: Copilot can now properly build, test, and analyze projects
- **Pattern**: Phase 2.5 added to both setup and maintenance commands

## Architectural Principles Observed

### 1. **Self-Contained Commands**
**Evidence**: Each command file includes complete context, role definition, and execution instructions
**Benefits**: 
- Commands can be executed independently
- No hidden dependencies or external configuration required
- Easy to understand and modify individual commands

### 2. **Phase-Based Execution**
**Evidence**: All complex commands use numbered phases with clear objectives
**Benefits**:
- Systematic progress through complex operations
- Clear checkpoints for validation
- Natural breaking points for user intervention if needed

### 3. **Output-Driven Architecture**
**Evidence**: Commands specify exact output artifacts with paths and formats
**Benefits**:
- Predictable file structure
- Commands can reliably reference outputs from other commands
- Easy to validate successful execution

### 4. **Layered Knowledge Transformation**
**Evidence**: Four-layer architecture where each layer transforms knowledge for specific tools
**Trade-offs**:
- (+) Each tool gets optimized configuration format
- (+) Changes cascade appropriately through layers
- (-) Multiple files to maintain for complete configuration
- (-) Potential for layer drift if not synchronized

### 5. **External Validation Pattern**
**Evidence**: Optional DeepWiki MCP integration for external perspective
**Benefits**:
- Validates internal pattern discovery
- Identifies blind spots in analysis
- Provides terminology alignment with broader community

## Inter-Command Communication

Commands communicate through:

1. **File System State**: Generated files serve as persistent state
   ```
   context.md → creates → .claude/context/discovered-patterns.md
   cursor.md → reads → .claude/context/discovered-patterns.md
   ```

2. **Prerequisite Reading**: Commands explicitly declare dependencies
   ```xml
   <prerequisite_reading>
   1. `.claude/context/discovered-patterns.md`
   2. `CLAUDE.md`
   </prerequisite_reading>
   ```

3. **Workflow Orchestration**: Workflow commands coordinate execution order
   ```xml
   <phase id="2" name="Generate Cursor Rules">
   <command_trigger>/cursor</command_trigger>
   </phase>
   ```

## Command Categories Architecture

### Setup Commands (`ai-setup/`)
- **Purpose**: Initial configuration generation
- **Execution**: Heavy analysis and discovery
- **Output**: Comprehensive configuration files
- **Frequency**: Once per project (or after major changes)

### Maintenance Commands (`ai-maintenance/`)
- **Purpose**: Incremental updates to existing configurations
- **Execution**: Diff-based updates
- **Output**: Modified configuration files
- **Frequency**: Regular intervals or after significant changes

### Workflow Commands (`workflows/`)
- **Purpose**: Orchestrate multiple commands
- **Execution**: Sequential command triggering
- **Output**: Complete ecosystem configuration
- **Frequency**: Major milestones or initial setup

### Global Commands
- **Purpose**: Cross-cutting utilities
- **Execution**: Lightweight checks and updates
- **Output**: Status reports or minor updates
- **Frequency**: As needed

## Design Decisions and Rationale

### Why Document-as-Code?
- Commands are versionable and diffable
- Self-documenting through embedded descriptions
- Can be tested and validated like code
- Enables command sharing and customization

### Why XML-Like Tags?
- Clear structure without parsing ambiguity
- Familiar to developers
- Allows nested content and attributes
- Compatible with markdown rendering

### Why Four Layers?
- Each tool has different capabilities and contexts
- Separation allows independent evolution
- Clear transformation pipeline
- Enables tool-specific optimizations

### Why Phase-Based Execution?
- Complex operations need structure
- Provides progress visibility
- Allows for incremental execution
- Natural error recovery points