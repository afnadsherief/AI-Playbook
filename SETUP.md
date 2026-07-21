# Setup Guide

Instructions for setting up your development environment for AI-Playbook.

## Prerequisites

- Git
- Markdown editor (recommended: VS Code with extensions)
- Python 3.10+ (for scripts)

## Installation

### Clone the Repository

```bash
git clone https://github.com/your-org/AI-Playbook.git
cd AI-Playbook
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

## Recommended Tools

### Editors

- **VS Code**: Recommended with Markdown All in One, Markdownlint
- **Typora**: For WYSIWYG Markdown editing
- **Obsidian**: For local knowledge base management

### Documentation

- **Markdownlint**: Linting for Markdown files
- **Prettier**: Code formatting
- **Vale**: Prose linting

### Automation

- **GitHub CLI**: For workflow management
- **Node.js**: For documentation tooling

## Repository Structure

See [ARCHITECTURE.md](ARCHITECTURE.md) for detailed structure.

## Development Workflow

1. Create a branch for your changes
2. Make changes following [CONTRIBUTING.md](CONTRIBUTING.md)
3. Test locally if applicable
4. Submit a pull request

## Scripts

See [scripts/](scripts/) for available automation:

- Setup scripts for environment initialization
- Validation scripts for content quality
- Build scripts for documentation generation

## Troubleshooting

### Common Issues

**Q: Markdown linting errors**
A: Run `markdownlint --fix .` to auto-fix issues

**Q: Missing dependencies**
A: Run `pip install -r requirements.txt`

**Q: Git conflicts**
A: Rebase on main: `git fetch origin && git rebase origin/main`

## Getting Help

- Open an issue for questions
- Check existing documentation
- Review [CONTRIBUTING.md](CONTRIBUTING.md)
