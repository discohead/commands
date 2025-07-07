# Example CLAUDE.md with Context Engineering Toolkit

This is an example of how a generated CLAUDE.md file should look with integrated context engineering toolkit knowledge.

---

# Project Context: E-Commerce Platform

## Overview

This is a modern e-commerce platform built with:
- Frontend: React 18 with TypeScript
- Backend: Node.js/Express API
- Database: PostgreSQL with Prisma ORM
- Auth: JWT with refresh tokens
- Payments: Stripe integration

## Context Engineering Toolkit

This project's Claude Code context includes access to modern tools for efficient codebase exploration:
- **Fast search**: `rg` (ripgrep), `fd` 
- **Code intelligence**: `ast-grep`, `semgrep`, `comby`
- **Data processing**: `jq`, `yq`, `gron`, `mlr`, `jc`
- **Scripting**: `perl`, `ruby`, `awk`, `python` one-liners

Use these tools for surgical context extraction rather than exhaustive file reading.

## Architecture

```
src/
├── api/           # Express REST API
├── components/    # React components
├── hooks/         # Custom React hooks
├── services/      # Business logic
├── utils/         # Shared utilities
└── types/         # TypeScript definitions
```

## Key Patterns

### API Endpoints
All endpoints follow RESTful conventions with middleware composition:
```typescript
router.post('/products',
  authenticate,
  validateRequest(createProductSchema),
  asyncHandler(productController.create)
);
```

### React Components
Using functional components with hooks:
```typescript
export const ProductCard: FC<ProductCardProps> = ({ product }) => {
  const { addToCart } = useCart();
  // Component logic
};
```

## Efficient Context Discovery Commands

### Quick Project Overview
```bash
# See project structure
tree -I 'node_modules|dist|coverage' -L 3

# Count source files
echo "TypeScript files: $(fd -e ts -e tsx | wc -l)"
echo "Test files: $(fd -e test.ts -e spec.ts | wc -l)"

# Find main entry points
fd '^(index|main|app)\.(ts|tsx|js)$'
```

### API Exploration
```bash
# List all API endpoints
rg 'router\.(get|post|put|delete|patch)' src/api/ -o | sort | uniq

# Find authenticated routes
rg 'authenticate' src/api/ -B 2 | rg 'router\.'

# Analyze middleware usage
ast-grep --pattern 'router.use($$$)' --lang typescript

# Find error handlers
rg 'catch.*next\(' src/api/ -A 3
```

### Frontend Analysis
```bash
# Find all React components
fd -e tsx src/components/ | xargs rg -l '^export.*(const|function).*: FC'

# Analyze hooks usage
rg 'use(State|Effect|Context|Reducer|Callback|Memo)' src/ --type tsx --stats

# Find pages/routes
fd -e tsx src/pages/ | sort

# Check Redux/Zustand usage
rg '(useSelector|useDispatch|useStore)' src/ --type tsx
```

### Database Queries
```bash
# Find all Prisma queries
rg 'prisma\.' src/ --type ts | awk -F'.' '{print $2}' | awk '{print $1}' | sort | uniq -c

# Analyze transactions
rg 'prisma\.\$transaction' src/ -A 5

# Find model references
ast-grep --pattern 'prisma.$MODEL.$METHOD($$$)' --lang typescript
```

### Testing Patterns
```bash
# Test coverage by module
fd -e test.ts -e spec.ts | xargs dirname | sort | uniq -c

# Find test utilities
rg 'beforeEach|afterEach|beforeAll|afterAll' src/ --type ts -l

# Analyze mocking patterns
rg '(jest\.mock|vi\.mock)' src/ --type ts
```

## Common Development Tasks

### Adding a New Feature
```bash
# 1. Find similar features for reference

# 2. Check existing patterns
ast-grep --pattern 'export const $FEATURE = () => { $$$ }'

# 3. Find related API endpoints
rg 'feature-name' src/api/ --type ts
```

### Debugging Issues
```bash
# Find error boundaries
ast-grep --pattern 'class $$ extends ErrorBoundary'

# Check error logging
rg 'logger\.(error|warn)' src/ --type ts -B 2

# Trace API calls
```

### Performance Optimization
```bash
# Find potential memo candidates
ast-grep --pattern 'const $$ = ($$) => { $$$ return <$$$ />; }'

# Check for missing dependencies
rg 'useEffect.*\[\]' src/ --type tsx

# Find large components
fd -e tsx src/components/ -x wc -l {} | sort -rn | head -10
```

## Quick Reference

### Find Implementations
```bash
# Interface implementations
ast-grep --pattern 'class $$ implements ProductService'

# Function usage
rg 'functionName\(' --type ts -A 2 -B 2

# Import analysis
rg '^import.*from.*@/services' | cut -d"'" -f2 | sort | uniq -c
```

### Code Quality Checks
```bash
# Find TODOs and FIXMEs
rg 'TODO|FIXME|HACK|XXX' --type ts --type tsx

# Check for console logs
rg 'console\.(log|error|warn)' src/ --type ts --type tsx

# Find any 'any' types
rg ': any' src/ --type ts --type tsx
```

```bash
# Browse files with preview

# Search with context

# Explore test files
```

## Performance Tips

1. **Searching**: Use `rg` with file type flags
   ```bash
   rg 'pattern' --type ts     # Only TypeScript files
   rg 'pattern' -g '!*.test.*' # Exclude test files
   ```

2. **File Finding**: Leverage `fd`'s smart defaults
   ```bash
   fd component         # Finds 'component' anywhere in path
   fd -e tsx -x wc -l   # Execute commands on found files
   ```

3. **Code Analysis**: Use AST tools for structural queries
   ```bash
   # Much faster than regex for finding React components
   ast-grep --pattern 'export const $$ = () => { $$$ }'
   ```

## Remember

When working in this codebase:
1. Use the context engineering tools to explore efficiently
2. Follow existing patterns found in similar features
3. Check tests for usage examples
5. Prefer surgical edits over large refactors

The toolkit helps you understand code without reading every file - use it!