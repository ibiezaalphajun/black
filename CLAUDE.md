# CLAUDE.md - AI Assistant Guide for Black Repository

**Last Updated:** 2026-01-19
**Repository:** ibiezaalphajun/black
**Current State:** Initial/Development Phase

---

## Table of Contents

1. [Repository Overview](#repository-overview)
2. [Codebase Structure](#codebase-structure)
3. [Development Workflow](#development-workflow)
4. [Coding Conventions](#coding-conventions)
5. [Git Practices](#git-practices)
6. [AI Assistant Guidelines](#ai-assistant-guidelines)
7. [Common Tasks](#common-tasks)

---

## Repository Overview

### Project Status
This repository is currently in its **initial phase** with minimal content. The project name "black" suggests potential directions:
- Python code formatter (Black) related tooling
- New Python project using Black
- General-purpose repository awaiting definition

### Current Repository State
```
black/
├── .git/           # Git repository metadata
└── README.md       # Minimal project description
```

### Key Information
- **Primary Branch:** `main` (or master)
- **Language:** Not yet determined (likely Python based on name)
- **Dependencies:** None configured yet
- **Testing:** No testing infrastructure present
- **CI/CD:** Not configured

---

## Codebase Structure

### Expected Structure (To Be Implemented)
When this project is fully developed, expect the following structure:

```
black/
├── src/                    # Source code directory
│   └── <project_name>/     # Main package
├── tests/                  # Test files
├── docs/                   # Documentation
├── .github/                # GitHub workflows and templates
│   └── workflows/          # CI/CD workflows
├── .gitignore              # Git ignore patterns
├── README.md               # Project documentation
├── CLAUDE.md               # This file - AI assistant guide
├── CONTRIBUTING.md         # Contribution guidelines (to be added)
├── LICENSE                 # Project license (to be added)
├── pyproject.toml          # Python project configuration (if Python)
├── setup.py or setup.cfg   # Python setup files (if needed)
└── requirements.txt        # Python dependencies (if Python)
```

### Current Files
- **README.md** (line 1): Contains project heading only

---

## Development Workflow

### Initial Setup
When setting up this repository for development:

1. **Determine Project Type**
   - Confirm the programming language and framework
   - Define the project's purpose and scope
   - Establish coding standards

2. **Configure Git**
   ```bash
   # Add .gitignore
   # Set up branch protection rules (if applicable)
   # Configure commit message conventions
   ```

3. **Set Up Build Tools**
   - Add package manager configuration
   - Set up dependency management
   - Configure build scripts

4. **Establish Testing Framework**
   - Choose testing framework
   - Set up test directory structure
   - Configure test runners

5. **Configure CI/CD**
   - Add GitHub Actions or equivalent
   - Set up automated testing
   - Configure linting and formatting checks

### Branch Strategy
- **Feature branches:** Use descriptive names (`feature/add-parser`, `fix/handle-edge-case`)
- **Claude branches:** Use format `claude/claude-md-<session-id>` for AI-assisted development
- **Main branch:** Keep stable and deployable

### Commit Conventions
Follow conventional commit format:
```
<type>(<scope>): <subject>

<body>

<footer>
```

**Types:**
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting, etc.)
- `refactor`: Code refactoring
- `test`: Adding or updating tests
- `chore`: Maintenance tasks

**Example:**
```
feat(parser): add support for custom delimiters

Implement custom delimiter parsing to handle edge cases
in user-provided input formats.

Closes #123
```

---

## Coding Conventions

### General Principles
1. **Simplicity First:** Avoid over-engineering; implement only what's needed
2. **Readability:** Write self-documenting code; use comments sparingly
3. **Consistency:** Follow established patterns in the codebase
4. **Testing:** Write tests for new features and bug fixes

### Python Conventions (If Applicable)
- **Code Style:** Follow PEP 8
- **Formatter:** Use Black with default settings
- **Linting:** Use flake8 or ruff
- **Type Hints:** Use type annotations for function signatures
- **Docstrings:** Use Google or NumPy style docstrings

```python
def example_function(param: str, count: int = 0) -> dict:
    """Brief description of function.

    Args:
        param: Description of param
        count: Description of count (default: 0)

    Returns:
        Dictionary containing results

    Raises:
        ValueError: If param is empty
    """
    pass
```

### File Organization
- One class per file (for complex classes)
- Group related functions in modules
- Keep files under 500 lines when possible
- Use `__init__.py` for package initialization

---

## Git Practices

### Before Making Changes
1. **Always read files before modifying**
   ```bash
   # Use Read tool to understand current state
   ```

2. **Check current branch**
   ```bash
   git status
   git branch
   ```

3. **Pull latest changes**
   ```bash
   git fetch origin
   git pull origin <branch-name>
   ```

### Making Commits
1. **Stage relevant files only**
   ```bash
   git add <specific-files>
   # Avoid: git add .
   ```

2. **Review changes before committing**
   ```bash
   git diff --staged
   ```

3. **Write descriptive commit messages**
   ```bash
   git commit -m "$(cat <<'EOF'
   feat: add initial project structure

   - Add src directory
   - Configure pyproject.toml
   - Set up testing framework
   EOF
   )"
   ```

4. **Push to correct branch**
   ```bash
   git push -u origin <branch-name>
   ```

### Branch Naming
- **Feature:** `feature/description-here`
- **Bugfix:** `fix/bug-description`
- **Documentation:** `docs/what-changed`
- **Claude sessions:** `claude/claude-md-<session-id>`

### Merge Strategy
- Squash commits for feature branches (when appropriate)
- Keep atomic commits on main branch
- Write clear merge commit messages

---

## AI Assistant Guidelines

### Core Principles

#### 1. Read Before Modifying
**ALWAYS** read files before making changes. Never propose modifications to code you haven't examined.

```
❌ Bad: "Let me update the config file..."
✅ Good: "Let me read the config file first... [uses Read tool]... Now I'll update it..."
```

#### 2. Understand Context
Before implementing features:
- Read related files
- Understand existing patterns
- Check for similar implementations
- Review tests for expected behavior

#### 3. Avoid Over-Engineering
- Implement only what's requested
- Don't add "nice to have" features
- Avoid premature optimization
- Keep solutions simple and focused

**Examples of over-engineering to avoid:**
- Adding error handling for impossible scenarios
- Creating abstractions for single-use code
- Adding configuration for fixed requirements
- Implementing features "for future use"

#### 4. Security Awareness
Check for common vulnerabilities:
- SQL injection
- Command injection
- XSS (cross-site scripting)
- Path traversal
- Insecure deserialization
- Hardcoded credentials

If you introduce a vulnerability, **immediately fix it**.

#### 5. Maintain Consistency
- Follow existing code style
- Match naming conventions
- Use established patterns
- Respect project structure

### Task Planning

For complex tasks, use the TodoWrite tool:

```markdown
1. Research existing implementation
2. Plan the changes needed
3. Implement core functionality
4. Add tests
5. Update documentation
```

Mark tasks as:
- `pending`: Not started
- `in_progress`: Currently working (ONE at a time)
- `completed`: Finished

### Working with Files

#### Reading Files
```
✅ Use Read tool for viewing file contents
❌ Don't use: cat, head, tail via Bash
```

#### Searching Code
```
✅ Use Grep tool for content search
✅ Use Glob tool for file pattern matching
✅ Use Task tool with Explore agent for open-ended exploration
❌ Don't use: grep, find, rg via Bash
```

#### Editing Files
```
✅ Use Edit tool for modifications
✅ Preserve exact indentation
✅ Make surgical changes
❌ Don't use: sed, awk via Bash
❌ Don't rewrite entire files for small changes
```

#### Creating Files
```
✅ Use Write tool for new files
⚠️  ONLY create files when absolutely necessary
⚠️  Prefer editing existing files
❌ Don't use: echo, cat with heredoc via Bash
```

### Communication Style

1. **Be Concise**
   - Short, clear responses
   - Use markdown formatting
   - Avoid unnecessary verbosity

2. **Be Direct**
   - No excessive praise or validation
   - Focus on technical accuracy
   - Disagree when necessary

3. **No Emojis**
   - Unless explicitly requested by user
   - Keep communication professional

4. **Show Progress**
   - Update todo list in real-time
   - Mark tasks complete immediately
   - Show what you're working on

### Error Handling

When errors occur:

1. **Read the error message carefully**
2. **Understand the root cause**
3. **Fix the issue, don't work around it**
4. **Test the fix**
5. **Explain what went wrong (briefly)**

Don't:
- Ignore errors
- Apply quick fixes without understanding
- Add try/catch blocks to hide issues
- Blame the tools or environment

---

## Common Tasks

### Starting a New Feature

```bash
# 1. Create feature branch
git checkout -b feature/my-feature

# 2. Use TodoWrite to plan the feature
# - Research existing code
# - Design the implementation
# - Implement core functionality
# - Add tests
# - Update documentation

# 3. Implement incrementally
# Mark each todo as in_progress → completed

# 4. Commit changes
git add <files>
git commit -m "feat: descriptive message"

# 5. Push to remote
git push -u origin feature/my-feature
```

### Fixing a Bug

```bash
# 1. Create fix branch
git checkout -b fix/bug-description

# 2. Investigate the bug
# - Read relevant code
# - Understand the issue
# - Identify root cause

# 3. Write a test that reproduces the bug

# 4. Fix the bug

# 5. Verify the test passes

# 6. Commit and push
git add <files>
git commit -m "fix: description of bug fix"
git push -u origin fix/bug-description
```

### Adding Tests

```python
# tests/test_example.py
import pytest
from src.example import function_to_test


def test_function_basic_case():
    """Test basic functionality."""
    result = function_to_test("input")
    assert result == "expected_output"


def test_function_edge_case():
    """Test edge case handling."""
    result = function_to_test("")
    assert result == ""


def test_function_error_case():
    """Test error handling."""
    with pytest.raises(ValueError):
        function_to_test(None)
```

### Refactoring Code

1. **Ensure tests exist** for code being refactored
2. **Run tests before refactoring**
3. **Make incremental changes**
4. **Run tests after each change**
5. **Commit working state frequently**

### Creating a Pull Request

```bash
# 1. Ensure all changes are committed
git status

# 2. Push to remote
git push -u origin <branch-name>

# 3. Use gh CLI to create PR
gh pr create --title "Title" --body "$(cat <<'EOF'
## Summary
- Bullet point summary of changes

## Test Plan
- How to test these changes
- What scenarios were covered

## Notes
- Any additional context
EOF
)"
```

---

## Project-Specific Notes

### Current Development Phase

This repository is in its **initial setup phase**. When developing:

1. **First establish the project foundation:**
   - Add `.gitignore`
   - Create `pyproject.toml` or equivalent
   - Set up directory structure
   - Add LICENSE file
   - Expand README.md

2. **Then add functionality incrementally:**
   - Start with core features
   - Add tests alongside code
   - Document as you go
   - Keep commits atomic

3. **Maintain this CLAUDE.md file:**
   - Update when conventions change
   - Add project-specific patterns
   - Document common pitfalls
   - Keep information current

### Future Sections to Add

As the project develops, consider adding:

- **API Documentation:** If building an API
- **Architecture Decisions:** Document key design choices
- **Performance Considerations:** Optimization guidelines
- **Deployment Guide:** How to deploy the project
- **Troubleshooting:** Common issues and solutions
- **Dependencies:** Why specific packages were chosen

---

## Questions & Support

### For AI Assistants

If you encounter situations not covered in this guide:

1. **Ask the user for clarification** using AskUserQuestion tool
2. **Research the codebase** thoroughly before making assumptions
3. **Follow general best practices** for the language/framework
4. **Update this document** with new conventions as they emerge

### For Human Developers

- This document is maintained for AI assistant guidance
- Feel free to update conventions as the project evolves
- Add project-specific patterns and requirements
- Keep information accurate and current

---

## Changelog

### 2026-01-19
- Initial creation of CLAUDE.md
- Established basic structure and guidelines
- Documented current repository state
- Added general AI assistant best practices

---

**Note:** This document should evolve with the project. Update it whenever:
- Project structure changes significantly
- New conventions are established
- Common patterns emerge
- New tools or frameworks are added
