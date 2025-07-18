---
name: create-claude-md
description: Generate project-specific CLAUDE.md with programming language context and development instructions
arguments: "Programming language/tech stack (e.g., 'Python FastAPI', 'React TypeScript', 'Go microservices')"
---

# Create Project-Specific CLAUDE.md

## Tech Stack: $ARGUMENTS

Generate a comprehensive CLAUDE.md file tailored to your project's programming language and technology stack. This builds upon the existing PRD to provide Claude with essential project context and development guidelines.

## Prerequisites
Ensure you have completed `/create-prd` first, as this command references the PRD for project context.

## CLAUDE.md Generation Process

### 1. Project Analysis
- Read and analyze the existing `PRD.md` for project context
- Identify the primary programming language and frameworks
- Determine development patterns and architectural decisions
- Assess testing requirements and deployment strategies

### 2. Language-Specific Context
Based on the specified tech stack, include relevant context:

**For Python Projects:**
- Virtual environment setup (venv, conda, poetry)
- Package management and dependencies
- Testing frameworks (pytest, unittest)
- Code quality tools (black, ruff, mypy)
- Common project structure and conventions

**For JavaScript/TypeScript Projects:**
- Node.js version and package managers (npm, yarn, pnpm)
- Framework-specific patterns (React, Vue, Angular, Next.js)
- Testing libraries (Jest, Vitest, Cypress)
- Build tools and bundlers (Vite, Webpack, Rollup)
- Type checking and linting (ESLint, Prettier, TypeScript)

**For Go Projects:**
- Module management and dependencies
- Testing conventions and benchmarks
- Build and deployment patterns
- Code formatting and linting (gofmt, golint)
- Common project structure

**For Other Languages:**
- Java: Maven/Gradle, Spring Boot, JUnit
- C#: .NET Core, NuGet, xUnit
- Rust: Cargo, testing conventions
- PHP: Composer, Laravel/Symfony patterns
- Ruby: Bundler, Rails conventions

### 3. Development Environment Setup
Include specific setup instructions for the tech stack:
- Required tools and versions
- Local development environment
- Database setup and migrations
- Environment variables and configuration
- IDE/editor recommendations and settings

## CLAUDE.md Template Structure

Generate a comprehensive CLAUDE.md following this structure:

```markdown
# Claude Development Guide for [Project Name]

## Project Overview

**Project Type**: [Web Application/API/CLI Tool/Library/etc.]
**Primary Language**: [Programming Language]
**Framework/Stack**: [Main frameworks and tools]
**Architecture**: [Monolith/Microservices/Serverless/etc.]

## Project Context

### Purpose
[Brief description from PRD - what problem this solves]

### Key Features
[Core functionality from PRD]
- Feature 1: Description
- Feature 2: Description
- Feature 3: Description

### Target Users
[Primary user personas from PRD]

## Development Environment

### Prerequisites
```bash
# Required tools and versions
[Language] [version]
[Package Manager] [version]
[Database] [version]
[Other tools]
```

### Setup Instructions
```bash
# Clone and setup
git clone [repository-url]
cd [project-name]

# Install dependencies
[package manager install command]

# Environment setup
cp .env.example .env
# Edit .env with your configuration

# Database setup
[database setup commands]

# Run development server
[dev server command]
```

### Project Structure
```
[project-name]/
├── [main source directory]/
│   ├── [core modules/components]
│   ├── [tests/]
│   └── [configuration/]
├── [docs/]
├── [scripts/]
├── [package manager files]
└── [configuration files]
```

## Development Guidelines

### Code Style and Standards
- **Formatting**: [Tool and configuration]
- **Linting**: [Linter and rules]
- **Type Checking**: [Type checker if applicable]
- **Testing**: [Testing framework and patterns]

### Architecture Patterns
[Based on PRD technical architecture]
- **Design Patterns**: [Patterns used in the project]
- **Data Flow**: [How data moves through the system]
- **Error Handling**: [Error handling strategy]
- **Logging**: [Logging framework and practices]

### Database Schema
[From PRD data architecture]
- **Primary Database**: [Database type and version]
- **Key Entities**: [Main data models]
- **Relationships**: [Important relationships]
- **Migrations**: [Migration strategy]

## Testing Strategy

### Test Types
- **Unit Tests**: [Framework and patterns]
  ```bash
  [unit test command]
  ```
- **Integration Tests**: [Framework and approach]
  ```bash
  [integration test command]
  ```
- **End-to-End Tests**: [Framework if applicable]
  ```bash
  [e2e test command]
  ```

### Quality Gates
```bash
# Code quality checks
[linting command]
[type checking command]
[test coverage command]

# Full validation pipeline
[complete quality check script]
```

## API Documentation

### Endpoints
[If applicable - main API endpoints from PRD]

### Authentication
[Auth strategy from PRD]

### Rate Limiting
[Rate limiting approach if applicable]

## Deployment

### Build Process
```bash
# Production build
[build command]

# Docker build (if applicable)
[docker commands]
```

### Environment Configuration
- **Development**: Local development settings
- **Staging**: Pre-production environment
- **Production**: Production environment settings

### Deployment Commands
```bash
# Deploy to staging
[staging deploy command]

# Deploy to production
[production deploy command]
```

## Development Workflow

### Branch Strategy
[Git workflow from team preferences]
- `main`: Production-ready code
- `develop`: Integration branch
- `feature/*`: Feature development
- `hotfix/*`: Production fixes

### Commit Conventions
[Commit message format]
```
type(scope): description

feat: add user authentication
fix: resolve database connection issue
docs: update API documentation
test: add unit tests for user service
```

### Pull Request Process
1. Create feature branch from develop
2. Implement changes with tests
3. Run quality gates locally
4. Submit PR with description
5. Code review and approval
6. Merge to develop

## Debugging and Troubleshooting

### Common Issues
[Language/framework specific common problems]

### Debug Commands
```bash
# Debug mode
[debug command]

# Log viewing
[log command]

# Database inspection
[db inspection commands]
```

### Performance Monitoring
[Monitoring tools and practices]

## Security Considerations

### Authentication & Authorization
[From PRD security framework]

### Data Protection
[Data security practices]

### Common Vulnerabilities
[Language/framework specific security concerns]

## Dependencies

### Core Dependencies
[Main production dependencies with versions]

### Development Dependencies
[Development tools and versions]

### Dependency Management
```bash
# Add dependency
[add dependency command]

# Update dependencies
[update command]

# Security audit
[audit command]
```

## Resources

### Documentation
- [Framework Documentation URL]
- [Language Documentation URL]
- [Database Documentation URL]

### Tools and Extensions
- **IDE**: [Recommended IDE/extensions]
- **Debugging**: [Debug tools]
- **Profiling**: [Performance tools]

## Working with Claude

### Key Commands to Run
- **Linting**: `[lint command]`
- **Testing**: `[test command]`
- **Type Checking**: `[type check command]`
- **Build**: `[build command]`
- **Start Dev Server**: `[dev server command]`

### Essential Claude Workflow

#### Session Initialization
- **Always read `PLANNING.md`** at the start of a new conversation to understand the project's architecture, goals, style, and constraints.
- **Check `TASKS.md`** before starting a new task. If the task isn't listed, add it with a brief description and today's date.
- **Use consistent naming conventions, file structure, and architecture patterns** as described in `PLANNING.md`.

#### Task Management Protocol
**CRITICAL**: Proper task tracking is essential for project success.

**Marking Tasks Complete:**
- When a task is finished, immediately update `TASKS.md`
- Change `[ ]` to `[x]` for completed tasks
- Example: `- [ ] Implement user authentication` becomes `- [x] Implement user authentication`

**Reopening Tasks:**
- If a completed task needs rework, change `[x]` back to `[ ]`
- Example: `- [x] Implement user authentication` becomes `- [ ] Implement user authentication`
- Add a note explaining why the task was reopened

**Adding New Tasks:**
- If working on something not in `TASKS.md`, add it immediately
- Format: `- [ ] [Task description] - Added [today's date]`
- **MUST include** in acceptance criteria: "Code reviewed and approved" and "Documentation updated and complete"
- Place in appropriate milestone section

#### Code Review Standards

**Pre-Review Checklist:**
Before requesting any code review, ensure:
- [ ] All tests pass successfully
- [ ] Code follows project style guidelines
- [ ] No unused imports, variables, or functions
- [ ] No commented-out code blocks
- [ ] Documentation is updated for new features

**Review Focus Areas:**

1. **Code Structure & Architecture**
   - Follows patterns defined in `PLANNING.md`
   - Proper separation of concerns
   - Consistent file and folder organization
   - Appropriate use of design patterns

2. **Code Quality**
   - No duplicate code or logic
   - Functions are single-purpose and well-named
   - Proper error handling and edge cases
   - Clear, readable code without excessive complexity

3. **Unused Code Detection**
   - Run static analysis tools to find unused code
   - Remove unused imports, variables, functions, and classes
   - Check for unused CSS classes and styles
   - Verify all dependencies in package files are actually used

4. **Testing Requirements**
   - **All tests must pass** - 0 tests executed indicates a problem
   - **Target: 80% test coverage minimum**
   - Unit tests for all business logic
   - Integration tests for API endpoints
   - E2E tests for critical user workflows

**Testing Validation Commands:**
```bash
# Run all tests - must show > 0 tests executed
[test command with coverage]

# Check test coverage - aim for 80%+
[coverage report command]

# Verify no tests are skipped
[test command with verbose output]
```

**Review Process:**
1. **Self-Review**: Complete pre-review checklist
2. **Automated Checks**: Ensure CI/CD pipeline passes
3. **Peer Review**: Have another developer review the code
4. **Testing Validation**: Verify all tests pass with adequate coverage
5. **Documentation Update**: Update relevant docs and comments

### Project-Specific Context
- Follow [framework] conventions and patterns
- Use [testing framework] for all new code
- Maintain [code quality standards]
- Reference PRD.md for business requirements
- Check PLANNING.md for architecture decisions

### Development Priorities
1. **Functionality**: Implement features per PRD specifications
2. **Quality**: Maintain high code quality and test coverage (80%+)
3. **Performance**: Follow performance best practices
4. **Security**: Implement security measures per PRD
5. **Documentation**: Keep documentation current
6. **Task Tracking**: Maintain accurate task status in TASKS.md

## 🔄 Git Workflow

### Commit Message Format

- **NEVER** include Claude Code, AI assistance, or automated generation references in commit messages

```
<type>(<scope>): <subject>

<body>

<footer>
```

**Types:** feat, fix, docs, style, refactor, test, chore

**Example:**
```
feat(auth): implement JWT authentication system

- Add JWT token generation and validation
- Implement secure password hashing with bcrypt
- Create authentication middleware for protected routes
- Add user session management with Redis
- Include password reset functionality

Closes #156
```

### Branch Strategy
- `main`/`master`: Production-ready code
- `develop`: Integration branch (if using git-flow)
- `feature/*`: New features or enhancements
- `fix/*`: Bug fixes
- `docs/*`: Documentation updates

### Commit Process
1. **Review Changes**: Use `git status` and `git diff` to understand what changed
2. **Stage Selectively**: Stage related changes together
3. **Write Clear Messages**: Focus on what and why, not how
4. **Test Before Commit**: Ensure all tests pass and quality gates succeed
5. **Keep Commits Atomic**: One logical change per commit

### Pull Request Process
1. Create feature branch from main/develop
2. Implement changes with comprehensive tests
3. Run all quality gates locally
4. Submit PR with clear description (no AI attribution)
5. Address code review feedback
6. Merge after approval

---

*This CLAUDE.md was generated based on PRD.md specifications and [tech stack] best practices.*
```

## Language-Specific Templates

### Python-Specific Additions
```markdown
### Python Environment
- **Version**: Python 3.11+
- **Virtual Environment**: `python -m venv venv`
- **Package Manager**: pip/poetry/conda
- **Dependencies**: requirements.txt or pyproject.toml

### Code Quality
```bash
# Formatting and linting
black .
ruff check --fix
mypy .

# Testing
pytest tests/ -v --cov=src
```

### Common Patterns
- Use type hints for all function signatures
- Follow PEP 8 style guidelines
- Use dataclasses or Pydantic for data models
- Implement proper exception handling
```

### JavaScript/TypeScript-Specific Additions
```markdown
### Node.js Environment
- **Version**: Node.js 18+ LTS
- **Package Manager**: npm/yarn/pnpm
- **TypeScript**: Latest stable version

### Code Quality
```bash
# Linting and formatting
eslint . --fix
prettier --write .
tsc --noEmit  # Type checking

# Testing
npm test
npm run test:coverage
```

### Common Patterns
- Use ESLint and Prettier configuration
- Follow TypeScript strict mode
- Implement proper error boundaries
- Use modern ES6+ features
```

## Output and Validation

### Save Location and Backup Strategy
**IMPORTANT**: Before creating the new CLAUDE.md:

1. **Check for existing CLAUDE.md**: If a CLAUDE.md file already exists in the project root
2. **Backup existing file**: Rename the existing file to `CLAUDE.md.backup.[timestamp]`
   - Example: `CLAUDE.md.backup.2024-01-15_14-30-25`
3. **Create new file**: Save the generated CLAUDE.md as: `CLAUDE.md` in the project root
4. **Notify user**: Inform the user that the previous CLAUDE.md was backed up

**Backup Process:**
```bash
# If CLAUDE.md exists, backup with timestamp
if [ -f "CLAUDE.md" ]; then
    mv CLAUDE.md "CLAUDE.md.backup.$(date +%Y-%m-%d_%H-%M-%S)"
    echo "Previous CLAUDE.md backed up as CLAUDE.md.backup.$(date +%Y-%m-%d_%H-%M-%S)"
fi
```

### Quality Checklist
- [ ] Tech stack accurately represented
- [ ] Development setup instructions complete
- [ ] Quality gates defined and executable
- [ ] Architecture patterns from PRD included
- [ ] Language-specific best practices covered
- [ ] Testing strategy clearly defined
- [ ] Deployment process documented
- [ ] Security considerations addressed
- [ ] Claude-specific guidance provided

### Next Steps
After CLAUDE.md creation:
1. Validate setup instructions work correctly
2. Use `/create-planning` to generate detailed architecture planning
3. Continue with `/create-tasks` for implementation breakdown

Remember: A great CLAUDE.md enables Claude to work effectively within your project's specific context and constraints.