# Repository Standards

Standards for organizing and maintaining code repositories.

## Purpose

Ensure repositories are:
- Consistently structured across the organization
- Easy to navigate and understand
- Properly configured for CI/CD
- Secure by default

## Scope

Applies to all code repositories including:
- Application code
- Library packages
- Infrastructure as Code
- Documentation repositories

## Standards

### 1. Repository Structure

Every repository must include:

```
├── .github/
│   ├── workflows/       # CI/CD pipelines
│   ├── ISSUE_TEMPLATE/  # Issue templates
│   └── PULL_REQUEST_TEMPLATE.md
├── docs/                # Documentation
├── src/ or app/         # Source code
├── tests/               # Test files
├── scripts/             # Utility scripts
├── .gitignore
├── .editorconfig
├── LICENSE
├── README.md
└── [config files]       # package.json, pyproject.toml, etc.
```

### 2. Required Files

#### README.md

Must include:
- Project description (2-3 sentences)
- Quick start instructions
- Prerequisites
- Installation steps
- Basic usage examples
- Links to full documentation
- Contributing guidelines
- License information

#### LICENSE

Every repository must have an explicit license. Choose based on:
- **MIT**: Permissive, widely compatible
- **Apache 2.0**: Patent grants, compatible with GPL
- **GPL 3.0**: Copyleft, strong sharing requirement
- **Proprietary**: For internal-only projects

#### .gitignore

Include appropriate ignores for:
- Build artifacts
- Dependencies
- IDE settings
- OS-specific files
- Sensitive configuration
- Logs and temporary files

### 3. Configuration Standards

#### EditorConfig

```ini
root = true

[*]
charset = utf-8
end_of_line = lf
insert_final_newline = true
trim_trailing_whitespace = true

[*.{js,py,java}]
indent_style = space
indent_size = 4

[*.{md,yaml,json}]
indent_style = space
indent_size = 2
```

#### Git Configuration

Set at repository level:
- Default branch name
- Merge strategy preferences
- Hooks for validation

### 4. Dependency Management

- Pin exact versions in production
- Use lock files
- Regularly audit dependencies
- Document non-obvious dependencies

### 5. Repository Naming

Use kebab-case: `awesome-project`

Avoid:
- Underscores (inconsistent across tools)
- CamelCase (inconsistent casing)
- Project codes (meaningless without context)

## Examples

### Good: Complete Repository Structure

```
my-service/
├── .github/
│   ├── workflows/
│   │   ├── ci.yml
│   │   └── cd.yml
│   └── PULL_REQUEST_TEMPLATE.md
├── src/
│   ├── __init__.py
│   └── main.py
├── tests/
│   ├── __init__.py
│   └── test_main.py
├── docs/
│   └── api.md
├── .gitignore
├── .editorconfig
├── README.md
├── LICENSE
├── pyproject.toml
└── uv.lock
```

### Bad: Minimal Repository

```
my-project/
├── main.py
└── README.md
```

Missing: tests, docs, CI/CD, proper configuration

## Checklist

### Repository Creation

- [ ] Chosen appropriate license
- [ ] Created standard directory structure
- [ ] Added .gitignore with appropriate patterns
- [ ] Added EditorConfig
- [ ] Created comprehensive README
- [ ] Configured branch protection
- [ ] Set up CI/CD pipeline
- [ ] Added issue and PR templates

### Repository Maintenance

- [ ] Dependencies regularly updated
- [ ] Security vulnerabilities patched
- [ ] Documentation current
- [ ] Dead code removed
- [ ] Unused files cleaned up

## Anti-Patterns

### 1. Monorepo Everything

Putting unrelated projects in one repository:
- Slows down cloning
- Complicates CI/CD
- Makes permissions difficult
- Blurs ownership

**Solution**: Separate concerns; use monorepo tools only when genuinely needed.

### 2. No Documentation

Repositories without README or docs:
- Forces tribal knowledge
- Onboarding blocker
- Knowledge loss risk

**Solution**: Document everything; start with basics.

### 3. Commit History Rewriting

Force-pushing to shared branches:
- Breaks other people's work
- Loses history
- Creates confusion

**Solution**: Never rewrite shared branch history.

### 4. Binary Files in Git

Large binaries in version control:
- Bloats repository
- Slows operations
- Doesn't diff well

**Solution**: Use Git LFS or external storage.

## Future Improvements

- Create repository templates for common project types
- Automate repository health checks
- Add repository scoring metrics
- Implement automated onboarding checks
- Create cross-repository dependency tracking
