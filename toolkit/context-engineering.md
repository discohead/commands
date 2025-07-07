# Context Engineering Toolkit

## Philosophy

This toolkit represents a paradigm shift in how AI assistants understand codebases. Rather than exhaustive enumeration, we practice **surgical context extraction** - using powerful tools to rapidly locate and extract precisely the information needed to solve tasks.

Think of these tools as your **context construction arsenal** - each optimized for specific types of discovery and analysis.

## Core Tools

### Discovery & Navigation

- **`fd`** - Lightning-fast file finding with intuitive syntax
  ```bash
  fd -e js -e ts              # Find all JS/TS files
  fd -H '^\..*rc'             # Find hidden config files
  fd -t d components          # Find directories named 'components'
  ```

- **`rg` (ripgrep)** - Blazing fast pattern search
  ```bash
  rg 'class.*extends'         # Find class inheritance
  rg -t js 'TODO|FIXME'       # Find todos in JS files
  rg --json 'import.*from'    # JSON output for processing
  ```

  ```bash
  ```

### Code Intelligence

- **`ast-grep`** - AST-based code search understanding structure
  ```bash
  ast-grep --pattern 'async function $FUNC($$$) { $$$ }'
  ast-grep --pattern 'useState<$TYPE>($VALUE)'
  ```

- **`semgrep`** - Semantic code analysis for patterns and security
  ```bash
  semgrep --config=auto --json | jq '.results[].path' | uniq
  semgrep --pattern '$X == $X' --lang js    # Find tautologies
  ```

- **`comby`** - Structural search and transformation
  ```bash
  comby 'if (:[x]) { return :[y] }' 'return :[x] ? :[y] : undefined' .js
  comby -stats 'try { :[body] } catch' ''   # Count try-catch blocks
  ```

### Data Processing

- **`jq`** - JSON Swiss Army knife
  ```bash
  cat package.json | jq '.dependencies | keys[]'
  fd -e json | xargs jq -s 'map(.version) | unique'
  ```

- **`yq`** - YAML/XML processing
  ```bash
  yq '.services | keys' docker-compose.yml
  yq -p yaml -o json config.yaml     # Convert YAML to JSON
  ```

- **`gron`** - Make JSON greppable
  ```bash
  cat package.json | gron | rg 'dependencies'
  gron api-response.json | rg 'user.email'
  ```

### Visualization & Presentation

- **`cat`** - Cat with syntax highlighting
  ```bash
  fd README | xargs cat -l markdown
  cat --diff old.js new.js
  ```

- **`tree`** - Directory structure visualization
  ```bash
  tree -I 'node_modules|dist' -L 3
  tree -J > structure.json    # JSON output
  ```

### Advanced Processing

- **`mlr` (Miller)** - CSV/TSV/JSON data processing
  ```bash
  mlr --icsv --ojson cat data.csv
  mlr --json filter '$status == "active"' then stats1 -a count -f id
  ```

- **`jc`** - Convert command output to JSON
  ```bash
  ls -la | jc --ls | jq '.[].size'
  ps aux | jc --ps | jq '.[] | select(.command | contains("node"))'
  ```

### Scripting Languages for One-Liners

- **`perl`** - Text processing powerhouse
  ```bash
  perl -ne 'print if /pattern/' file.txt              # Like grep
  perl -pe 's/old/new/g' file.txt                     # Like sed
  perl -ne 'print "$1\n" if /func (\w+)/' *.js       # Extract function names
  ```

- **`ruby`** - Expressive one-liners
  ```bash
  ruby -ne 'puts $_ if $_ =~ /pattern/' file.txt
  ruby -pe '$_.gsub!(/old/, "new")' file.txt
  ruby -ne 'puts $_.split[1] if /^import/' *.js      # Extract import names
  ```

- **`awk`** - Pattern scanning and data extraction
  ```bash
  awk '/pattern/ {print $2}' file.txt
  awk -F: '{print $1}' /etc/passwd                   # Extract usernames
  awk 'NR%2==0' file.txt                             # Print even lines
  ```

- **`python`** - Versatile scripting
  ```bash
  python -c "import json; print(json.load(open('package.json'))['name'])"
  python -c "import sys; print(len(sys.stdin.read().split()))"  # Word count
  ```

## Context Engineering Patterns

### 1. Rapid Architecture Discovery
```bash
# Find entry points
fd -e js -e ts | xargs rg -l '^(import.*express|app\.listen)'

# Map component hierarchy
ast-grep --pattern 'export default function $COMPONENT' --json | \
  jq -r '.matches[].metavariables.COMPONENT.text' | sort

# Discover API routes
rg '@(Get|Post|Put|Delete)\(' --type ts -A 2
```

### 2. Dependency Analysis
```bash
# Extract all imports
rg '^import.*from' --no-heading | \
  perl -ne 'print "$1\n" if /from ['\''"](.+?)['\''"]/' | \
  sort | uniq -c | sort -rn

# Find circular dependencies
fd -e js | xargs -I {} sh -c 'echo "=== {} ==="; rg "from.*{}" --type js'
```

### 3. Pattern Evolution
```bash
# Track pattern changes over time
git log -p --since="1 month ago" | \
  rg -U "class.*extends.*{" -A 5 | \
  awk '/^commit/ {c=$2} /^[+-]/ {print c, $0}'
```

### 4. Technology Stack Analysis
```bash
# Comprehensive stack detection
echo "=== Package Managers ===" && fd 'package\.json|requirements\.txt|Gemfile|go\.mod'
echo "=== Frameworks ===" && rg -o -I '(express|django|rails|gin)' | sort | uniq -c
echo "=== Databases ===" && rg -i '(mongodb|postgres|mysql|redis)' --type-add 'config:*.{json,yaml,yml,env}'
```

## Integration Strategy

### Phase 1: Discovery Enhancement
Replace basic `find` commands with `fd` and `rg`:
```bash
# Old: find . -type f -name "*.js" -o -name "*.ts"
# New: fd -e js -e ts

# Old: grep -r "pattern" .
# New: rg "pattern"
```

### Phase 2: Pattern Intelligence
Add AST-based analysis:
```bash
# Structural patterns
ast-grep --pattern 'class $$ extends React.Component'

# Security patterns
semgrep --config=auto --metrics=on
```

```bash
# Select files to analyze

# Choose patterns to investigate
```

## Propagation to Project Contexts

When generating project-specific contexts, always include:

1. **Tool Availability Notice**
```markdown
This project's Claude Code context includes access to modern context engineering tools:
- Fast search: rg, fd
- Code intelligence: ast-grep, semgrep, comby
- Data processing: jq, yq, gron, mlr
```

2. **Project-Specific Patterns**
```markdown
## Efficient Context Discovery Commands

# Find all test files
fd -e test.js -e spec.ts

# Locate configuration
fd -H '^\..*rc|config' -t f

# Search for specific patterns
rg 'TODO|FIXME|HACK' --type js
```

3. **Optimization Hints**
```markdown
## Context Optimization

When exploring this codebase:
1. Use `fd` for file discovery (100x faster than find)
2. Use `rg` for content search (respects .gitignore)
3. Use `ast-grep` for structural patterns
5. Process JSON with `jq`, YAML with `yq`
```

## Performance Comparisons

```bash
# Finding files
time find . -name "*.js" -o -name "*.ts"     # ~2.5s
time fd -e js -e ts                           # ~0.05s

# Searching content  
time grep -r "import" . --include="*.js"     # ~4.2s
time rg "import" --type js                    # ~0.08s

# Processing JSON
time cat large.json | python -m json.tool    # ~1.8s
time cat large.json | jq '.'                 # ~0.3s
```

## Remember

**Context engineering is about precision, not exhaustion.** Use these tools to surgically extract exactly what you need, when you need it. The goal is to construct the optimal context window for solving the task at hand, not to index everything.