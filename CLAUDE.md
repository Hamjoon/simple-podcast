# CLAUDE.md - AI Assistant Guide for simple-podcast

**Last Updated**: 2025-11-21
**Repository**: simple-podcast
**Current Status**: Early Development / Initial Setup

---

## Table of Contents

1. [Project Overview](#project-overview)
2. [Repository Structure](#repository-structure)
3. [Development Workflow](#development-workflow)
4. [Git Conventions](#git-conventions)
5. [Code Conventions](#code-conventions)
6. [Testing Guidelines](#testing-guidelines)
7. [AI Assistant Guidelines](#ai-assistant-guidelines)
8. [Common Tasks](#common-tasks)
9. [Troubleshooting](#troubleshooting)

---

## Project Overview

### Purpose
`simple-podcast` is a podcast-related application currently in its initial setup phase.

### Current State
- **Stage**: Repository initialization
- **Initial Commit**: aa5edb3 (Nov 21, 2025)
- **Files**: Minimal bootstrap configuration only
- **Technology Stack**: To be determined

### Project Goals
*To be documented as the project scope is defined*

---

## Repository Structure

### Current Structure
```
simple-podcast/
├── .git/                   # Git version control
├── .gitattributes          # Git line ending configuration (LF normalization)
├── README.md               # Project documentation
└── CLAUDE.md              # This file - AI assistant guide
```

### Expected Future Structure
*This section will be updated as the project structure is established*

Typical podcast application structure might include:
```
simple-podcast/
├── src/                    # Source code
│   ├── components/        # UI components
│   ├── services/          # Business logic
│   ├── utils/             # Utility functions
│   └── config/            # Configuration
├── tests/                 # Test files
├── docs/                  # Documentation
├── public/                # Static assets
└── scripts/               # Build/deployment scripts
```

---

## Development Workflow

### Branch Strategy

**Main Branch**: `main` (default)
**Feature Branches**: `claude/claude-md-*` (AI-generated feature branches)

#### Current Working Branch
- `claude/claude-md-mi8x1de5k3umycp6-0163qoaYkP4jVUkGSrjH9Dpq`

### Branch Naming Convention
- Feature branches: `feature/description-here`
- Bug fixes: `fix/description-here`
- AI assistant branches: `claude/claude-md-*` (auto-generated)

### Development Process

1. **Start**: Always check current branch and git status
2. **Develop**: Make incremental, logical changes
3. **Test**: Verify changes work as expected
4. **Commit**: Use clear, descriptive commit messages
5. **Push**: Push to the designated branch

---

## Git Conventions

### Commit Message Format

Follow conventional commit format:

```
<type>(<scope>): <subject>

<body>

<footer>
```

**Types**:
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting, etc.)
- `refactor`: Code refactoring
- `test`: Adding or updating tests
- `chore`: Maintenance tasks
- `perf`: Performance improvements

**Examples**:
```
feat(podcast): add audio player component
fix(api): resolve episode fetching error
docs(readme): update setup instructions
```

### Git Operations Best Practices

#### Pushing Changes
```bash
# Always use -u flag for new branches
git push -u origin <branch-name>

# Branch names MUST start with 'claude/' for AI assistant work
# Example: claude/claude-md-mi8x1de5k3umycp6-0163qoaYkP4jVUkGSrjH9Dpq
```

**Important**: If push fails with 403 error, verify the branch name starts with 'claude/' and matches the session ID.

**Retry Logic**: On network failures, retry up to 4 times with exponential backoff (2s, 4s, 8s, 16s)

#### Fetching/Pulling Changes
```bash
# Fetch specific branch
git fetch origin <branch-name>

# Pull specific branch
git pull origin <branch-name>
```

**Retry Logic**: Same as push - retry up to 4 times on network failures

### Files to Never Commit
- Environment files with secrets (`.env`, `credentials.json`)
- Node modules (`node_modules/`)
- Build artifacts (`dist/`, `build/`, `.next/`)
- IDE configurations (`.vscode/`, `.idea/`) - unless project-wide
- OS files (`.DS_Store`, `Thumbs.db`)
- Log files (`*.log`)

---

## Code Conventions

### General Principles
1. **Readability**: Write code for humans first
2. **Simplicity**: Prefer simple solutions over clever ones
3. **Consistency**: Follow existing patterns in the codebase
4. **Documentation**: Comment complex logic, document public APIs

### File Naming
*To be established based on chosen technology stack*

### Code Style
*To be established with linter/formatter configuration*

Common best practices:
- Use meaningful variable and function names
- Keep functions small and focused
- Avoid deep nesting (max 3-4 levels)
- Handle errors appropriately
- Remove dead code and console.logs before committing

---

## Testing Guidelines

### Testing Strategy
*To be established when testing framework is chosen*

### Running Tests
```bash
# Commands will be added when test framework is configured
# npm test
# npm run test:watch
# npm run test:coverage
```

### Test Coverage
- Aim for minimum 80% coverage on critical paths
- 100% coverage on utility functions
- Test edge cases and error conditions

---

## AI Assistant Guidelines

### Before Starting Any Task

1. **Check Git Status**
   ```bash
   git status
   git log -1
   ```

2. **Verify Current Branch**
   - Ensure you're on the correct feature branch
   - Branch should start with `claude/` for AI work

3. **Understand Context**
   - Read relevant files before making changes
   - Search codebase for similar patterns
   - Check for existing implementations

### Task Execution Best Practices

#### Use TodoWrite Tool
For multi-step tasks, ALWAYS use the TodoWrite tool to:
- Break down complex tasks
- Track progress
- Ensure nothing is missed
- Provide visibility to users

#### Parallel Operations
When tasks are independent, execute them in parallel:
```
- Multiple file reads
- Independent grep/glob searches
- Parallel tool calls in single message
```

#### Tool Usage Priority
1. **File Operations**: Use Read/Edit/Write tools (NOT cat/sed/echo)
2. **Search**: Use Grep/Glob tools (NOT grep/find commands)
3. **Exploration**: Use Task tool with Explore agent
4. **Bash**: Reserve for actual system commands only

#### Code References
When referencing code, use format: `file_path:line_number`

Example: "The error handling is in src/services/api.ts:142"

### Security Considerations

Always check for:
- Command injection vulnerabilities
- XSS vulnerabilities
- SQL injection (if database is added)
- Hardcoded secrets or credentials
- Improper authentication/authorization
- Insecure dependencies

**If you write insecure code, fix it immediately.**

### Commit Guidelines

**When to Commit**:
- Only when user explicitly requests it
- After completing a logical unit of work
- Before switching tasks or branches

**Commit Process**:
1. Run `git status` and `git diff` to review changes
2. Check recent commits for message style: `git log --oneline -5`
3. Stage relevant files only
4. Write clear commit message
5. Verify commit succeeded: `git status`

**NEVER**:
- Commit without explicit user request
- Use `--no-verify` flag (skip hooks) unless requested
- Force push to main/master
- Amend other developers' commits
- Commit files with secrets

---

## Common Tasks

### Setting Up Development Environment
*To be documented when project structure is established*

```bash
# Placeholder - will be updated
# npm install
# npm run dev
```

### Adding New Features
1. Create feature branch (if not on one)
2. Implement feature with tests
3. Update documentation
4. Run tests and linting
5. Commit changes
6. Push to remote

### Fixing Bugs
1. Reproduce the bug
2. Write a failing test
3. Fix the bug
4. Verify test passes
5. Commit with clear message

### Updating Dependencies
*To be documented when package management is set up*

```bash
# Placeholder - will be updated
# npm update
# npm audit fix
```

---

## Troubleshooting

### Common Issues

#### Git Push Fails with 403
**Cause**: Branch name doesn't match required pattern
**Solution**: Ensure branch starts with `claude/` and matches session ID

#### Network Failures
**Solution**: Automatic retry with exponential backoff (2s, 4s, 8s, 16s)

#### Merge Conflicts
**Solution**:
1. Fetch latest changes
2. Resolve conflicts manually
3. Test after resolution
4. Commit resolution

---

## Project-Specific Notes

### Technology Stack
*To be updated when decisions are made*

### Architecture Decisions
*Document key architectural decisions here*

### Dependencies
*List and explain key dependencies*

### Environment Variables
*Document required environment variables*

```bash
# Example .env structure (create .env.example)
# API_KEY=your_api_key_here
# DATABASE_URL=your_database_url
```

### API Endpoints
*Document API structure when implemented*

### Database Schema
*Document database structure when implemented*

---

## Resources

### Documentation
- README.md - User-facing documentation
- CLAUDE.md - This file (AI assistant guide)

### External Resources
*Add links to relevant documentation, APIs, etc.*

---

## Changelog

### 2025-11-21
- Initial CLAUDE.md created
- Repository initialized
- Basic git structure established

---

## Notes for Future Development

This CLAUDE.md file should be updated as the project evolves:

1. **When choosing tech stack**: Update Technology Stack section
2. **When adding dependencies**: Update Dependencies section
3. **When establishing conventions**: Update Code Conventions
4. **When adding tests**: Update Testing Guidelines
5. **When deploying**: Add Deployment section
6. **When adding CI/CD**: Document pipeline configuration

Keep this file current so AI assistants always have accurate, helpful guidance.

---

**End of CLAUDE.md**
