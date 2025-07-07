# Project Context Template with Context Engineering Toolkit

This template shows how to integrate context engineering toolkit knowledge into project-specific contexts.

---

# [Project Name] Context

## Overview
[Project description and key architectural points]

## Context Engineering Toolkit

This project's Claude Code context includes access to modern tools for efficient codebase exploration:
- **Fast search**: `rg` (ripgrep), `fd` 
- **Code intelligence**: `ast-grep`, `semgrep`, `comby`
- **Data processing**: `jq`, `yq`, `gron`, `mlr`, `jc`
- **Scripting**: `perl`, `ruby`, `awk`, `python` one-liners

Use these tools for surgical context extraction rather than exhaustive file reading.

## Efficient Context Discovery for [Project Name]

### Quick Architecture Overview
```bash
# Visualize project structure
tree -I 'node_modules|dist|build|.git' -L 3

# Count files by type
fd -e js -e ts -e jsx -e tsx | wc -l

# Find entry points
fd '^(index|main|app)\.' | head -10
```

### Common Search Patterns
```bash
# Find all React components
ast-grep --pattern 'function $COMPONENT($$) { $$$ return ( $$$ ) }'

# Locate API endpoints
rg '@(Get|Post|Put|Delete)\(' --type ts

# Find configuration usage
rg 'process\.env\.' --type js -o | sort | uniq -c

# Analyze imports
rg '^import.*from' | perl -ne 'print "$1\n" if /from ['\''"](.+?)['\''"]/' | sort | uniq -c | sort -rn | head -20
```

```bash

# Search for patterns with preview

# Explore test files
```

### Project-Specific Commands

#### For Authentication Module
```bash
# Find auth-related files

# Analyze auth patterns
ast-grep --pattern 'if ($$.authenticated) { $$$ }'

# Check JWT usage
rg 'jwt\.' --type ts | awk -F: '{print $2}' | sort | uniq -c
```

#### For API Development
```bash
# List all endpoints
rg 'router\.(get|post|put|delete|patch)' -o | sort | uniq -c

# Find middleware usage
ast-grep --pattern 'app.use($$$)'

# Analyze error handling
comby 'catch (:[err]) { :[body] }' '' -stats -matcher .js
```

#### For Frontend Components
```bash
# Component discovery
fd -e jsx -e tsx | xargs rg -l '^export default' | sort

# Find prop types
ast-grep --pattern 'interface $PROPS { $$$ }'

# Analyze state management
rg '(useState|useReducer|useContext)' --type tsx --stats
```

## Performance Tips

1. **File Discovery**: `fd` is ~100x faster than `find`
   ```bash
   # Instead of: find . -name "*.js" -o -name "*.ts"
   # Use: fd -e js -e ts
   ```

2. **Content Search**: `rg` respects `.gitignore` and is incredibly fast
   ```bash
   # Instead of: grep -r "pattern" .
   # Use: rg "pattern"
   ```

3. **Structural Search**: `ast-grep` understands code structure
   ```bash
   # Find all async functions that await multiple times
   ast-grep --pattern 'async function $F($$$) { $$$ await $$$ await $$$ }'
   ```

4. **Data Processing**: Chain tools for complex analysis
   ```bash
   # Analyze most imported modules
   rg '^import' --json | jq -r '.data.lines.text' | \
     perl -ne 'print "$1\n" if /from ['\''"](.+?)['\''"]/' | \
     sort | uniq -c | sort -rn | head -10
   ```

## Common Workflows

### Understanding a New Feature
```bash
# 1. Find related files

# 2. Understand the structure
ast-grep --pattern 'class $$ { $$$ }' src/features/feature-name/

# 3. Trace the data flow
rg 'featureName' --type ts -A 2 -B 2

# 4. Check tests
fd -e test.ts -e spec.ts | xargs rg -l 'feature-name'
```

### Debugging an Issue
```bash
# 1. Find error patterns
rg 'throw new' --type js -B 3

# 2. Check recent changes
git log -p --since="1 week ago" | rg 'function-name'

# 3. Analyze call hierarchy
rg 'functionName\(' --type ts
```

### Refactoring Code
```bash
# 1. Find all occurrences
rg 'oldPattern' -l | wc -l

# 2. Preview changes
comby 'oldPattern(:[args])' 'newPattern(:[args])' -matcher .js -d src/

# 3. Apply changes
comby 'oldPattern(:[args])' 'newPattern(:[args])' -matcher .js -d src/ -i
```

## Remember

**Context engineering is about precision, not exhaustion.** These tools help you:
- Find exactly what you need without reading entire files
- Understand patterns across the codebase quickly
- Make surgical changes with confidence
- Navigate unfamiliar code efficiently

Always prefer targeted searches over broad file reading. Let the tools do the heavy lifting.