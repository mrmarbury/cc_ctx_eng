---
name: create-claude-md
description: Generate Elixir-specific CLAUDE.md with Phoenix, OTP, and Elixir best practices
arguments: "Elixir project type (e.g., 'Phoenix LiveView', 'OTP Application', 'Umbrella Project')"
---

# Create Elixir Project-Specific CLAUDE.md

## Project Type: $ARGUMENTS

Generate a comprehensive CLAUDE.md file specifically tailored for Elixir/Phoenix development with OTP design patterns, fault tolerance principles, and Elixir ecosystem best practices.

## Prerequisites
Ensure you have completed `/create-prd` first, as this command references the PRD for project context.

## Elixir-Specific Analysis
- Read and analyze the existing `PRD.md` for Elixir architectural decisions
- Identify Phoenix vs pure OTP application patterns
- Determine supervision tree structure and process architecture
- Assess LiveView, Channels, and real-time requirements
- Review database patterns and Ecto usage

## CLAUDE.md Template for Elixir Projects

Generate a comprehensive CLAUDE.md following this Elixir-optimized structure:

```markdown
# Claude Development Guide for [Project Name]

## Project Overview

**Project Type**: [Phoenix Web App/OTP Application/Umbrella Project]
**Primary Language**: Elixir
**Framework**: Phoenix Framework (if applicable)
**Architecture**: [Actor Model/OTP Supervision Tree/Distributed System]
**Database**: PostgreSQL with Ecto

## Project Context

### Purpose
[Brief description from PRD - leveraging Elixir's concurrency and fault tolerance]

### Key Features
[Core functionality emphasizing concurrent/real-time aspects]
- Feature 1: [Description with OTP process involvement]
- Feature 2: [Description with Phoenix/LiveView components]
- Feature 3: [Description with database/Ecto patterns]

### Target Users
[Primary user personas and concurrent usage patterns]

## Development Environment

### Prerequisites
```bash
# Required tools and versions
Elixir 1.15+
Erlang/OTP 26+
PostgreSQL 14+
Node.js 18+ (for Phoenix assets)
```

### Setup Instructions
```bash
# Clone and setup
git clone [repository-url]
cd [project-name]

# Install dependencies
mix deps.get

# Create and migrate database
mix ecto.setup

# Install Phoenix assets (if Phoenix project)
cd assets && npm install && cd ..

# Start development server
mix phx.server
```

### Project Structure
```
[project-name]/
├── lib/
│   ├── [project_name]/
│   │   ├── application.ex      # OTP Application
│   │   ├── [contexts]/         # Business logic
│   │   └── [schemas]/          # Ecto schemas
│   └── [project_name]_web/     # Phoenix web layer
│       ├── components/         # LiveView components
│       ├── controllers/        # HTTP controllers
│       ├── live/              # LiveView modules
│       └── router.ex          # Route definitions
├── config/
│   ├── config.exs             # Base configuration
│   ├── dev.exs               # Development settings
│   ├── prod.exs              # Production settings
│   └── test.exs              # Test configuration
├── priv/
│   └── repo/migrations/       # Database migrations
├── test/
│   ├── [project_name]/        # Context tests
│   └── [project_name]_web/    # Web layer tests
└── mix.exs                    # Project dependencies
```

## Development Guidelines

### Elixir Code Style and Standards
- **Formatting**: Use `mix format` with default settings
- **Linting**: Credo for static analysis and style checking
- **Type Checking**: Dialyzer for static type analysis
- **Documentation**: ExDoc for comprehensive documentation

### OTP Design Patterns
[Based on PRD technical architecture]
- **GenServer**: Long-running processes with state management
- **Agent**: Simple state wrapper for concurrent access
- **Task**: Asynchronous operations and parallel processing
- **Supervisor**: Fault tolerance and process lifecycle management
- **Application**: Top-level OTP application behavior

### Phoenix Framework Conventions
- **Contexts**: Business logic boundaries following domain-driven design
- **LiveView**: Real-time UI components with server-side rendering
- **Channels**: WebSocket communication for real-time features
- **Plugs**: Request/response transformation pipeline
- **Controllers**: HTTP request handling following REST patterns

### Database Schema
[From PRD data architecture]
- **Ecto Schemas**: Data structures with validations and associations
- **Migrations**: Database evolution with proper up/down functions
- **Changesets**: Data validation and transformation
- **Queries**: Ecto query composition and optimization
- **Transactions**: Multi-step operations with rollback capability

## Testing Strategy

### Test Types
- **Unit Tests**: ExUnit for individual functions and modules
  ```bash
  mix test
  ```
- **Integration Tests**: Context and API endpoint testing
  ```bash
  mix test --include integration
  ```
- **Property Tests**: StreamData for edge case discovery
  ```bash
  mix test --include property
  ```
- **LiveView Tests**: Phoenix LiveView testing helpers
  ```bash
  mix test test/my_app_web/live/
  ```

### Quality Gates
```bash
# Code quality checks
mix credo --strict
mix dialyzer
mix format --check-formatted

# Test coverage - aim for 90%+
mix coveralls.html

# Full validation pipeline
mix test && mix credo && mix dialyzer
```

## Working with Claude

### Key Commands to Run
- **Testing**: `mix test`
- **Linting**: `mix credo --strict`
- **Type Checking**: `mix dialyzer`
- **Formatting**: `mix format`
- **Dev Server**: `mix phx.server`
- **Database**: `mix ecto.migrate`

### Essential Claude Workflow

#### Session Initialization
- **Always read `PLANNING.md`** at the start of a new conversation to understand the project's OTP architecture, Phoenix patterns, and Elixir-specific constraints.
- **Check `TASKS.md`** before starting a new task. If the task isn't listed, add it with a brief description and today's date.
- **Use consistent Elixir naming conventions** as described in `PLANNING.md` (snake_case for functions, PascalCase for modules).

#### Task Management Protocol
**CRITICAL**: Proper task tracking is essential for Elixir project success.

**Marking Tasks Complete:**
- When a task is finished, immediately update `TASKS.md`
- Change `[ ]` to `[x]` for completed tasks
- Example: `- [ ] Implement User GenServer` becomes `- [x] Implement User GenServer`

**Reopening Tasks:**
- If a completed task needs rework, change `[x]` back to `[ ]`
- Example: `- [x] Implement User GenServer` becomes `- [ ] Implement User GenServer`
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
- [ ] Credo passes with no issues
- [ ] Dialyzer passes with no warnings
- [ ] Code is properly formatted with `mix format`
- [ ] No unused functions, variables, or imports
- [ ] Proper @spec annotations for public functions
- [ ] Documentation updated for new features

**Review Focus Areas:**

1. **OTP Architecture & Design Patterns**
   - Follows supervision tree patterns defined in `PLANNING.md`
   - Proper GenServer/Agent/Task usage
   - Message passing patterns and process communication
   - Error handling follows "let it crash" philosophy

2. **Phoenix Framework Patterns**
   - Context boundaries properly maintained
   - LiveView components follow best practices
   - Controller actions are thin and delegate to contexts
   - Proper use of Phoenix.PubSub for real-time features

3. **Elixir Code Quality**
   - Pattern matching used effectively
   - Guards implemented where appropriate
   - Proper use of pipe operator |>
   - Function clauses ordered from specific to general
   - Tail recursion optimization where needed

4. **Unused Code Detection**
   - Run `mix xref unreachable` to find unused code
   - Remove unused imports and aliases
   - Check for unused functions with `mix credo`
   - Verify all dependencies in mix.exs are used

5. **Testing Requirements**
   - **All tests must pass** - 0 tests executed indicates a problem
   - **Target: 90% test coverage minimum** for Elixir projects
   - Unit tests for all public functions
   - Integration tests for Phoenix controllers and LiveViews
   - Property tests for complex business logic

**Testing Validation Commands:**
```bash
# Run all tests - must show > 0 tests executed
mix test --cover

# Check test coverage - aim for 90%+
mix coveralls.html

# Verify no tests are skipped
mix test --include pending --include skip
```

**Elixir-Specific Review Process:**
1. **Self-Review**: Complete pre-review checklist
2. **OTP Validation**: Ensure proper supervision and fault tolerance
3. **Phoenix Patterns**: Verify context boundaries and web patterns
4. **Performance Check**: Review for potential bottlenecks
5. **Documentation**: Ensure @doc and @spec are complete

### Project-Specific Context
- Follow Phoenix framework conventions and patterns
- Use ExUnit for all new code with proper test structure
- Maintain OTP design principles throughout
- Reference PRD.md for business requirements
- Check PLANNING.md for architectural decisions

### Development Priorities
1. **Functionality**: Implement features per PRD specifications
2. **Fault Tolerance**: Ensure proper supervision and error handling
3. **Performance**: Leverage Elixir's concurrency for optimal performance
4. **Quality**: Maintain high code quality and test coverage (90%+)
5. **Documentation**: Keep documentation current with @doc and @spec
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

**Elixir-Specific Example:**
```
feat(contexts): implement user authentication context

- Add User context with GenServer for session management
- Implement password hashing with Argon2
- Create authentication plug for protected routes
- Add user registration and login workflows
- Include supervision tree for user processes

Closes #189
```

### Branch Strategy
- `main`: Production-ready code
- `develop`: Integration branch (if using git-flow)
- `feature/*`: New features or enhancements
- `fix/*`: Bug fixes
- `docs/*`: Documentation updates

### Commit Process
1. **Review Changes**: Use `git status` and `git diff` to understand what changed
2. **Stage Selectively**: Stage related changes together
3. **Write Clear Messages**: Focus on what and why, not how
4. **Test Before Commit**: Ensure `mix test && mix credo && mix dialyzer` passes
5. **Keep Commits Atomic**: One logical change per commit

### Pull Request Process
1. Create feature branch from main/develop
2. Implement changes with comprehensive tests
3. Run all quality gates locally (`mix test && mix credo && mix dialyzer`)
4. Submit PR with clear description (no AI attribution)
5. Address code review feedback
6. Merge after approval

## API Documentation

### Phoenix Endpoints
[If applicable - main API endpoints from PRD]
- REST API patterns following Phoenix conventions
- JSON API responses with proper error handling
- Authentication using Guardian or similar

### LiveView Components
[If applicable - LiveView patterns]
- Real-time UI components
- Server-side rendering with minimal JavaScript
- Event handling and state management

### WebSocket Channels
[If applicable - real-time features]
- Phoenix Channel patterns
- PubSub for broadcasting
- Presence tracking for user status

## Deployment

### Build Process
```bash
# Production build
MIX_ENV=prod mix compile

# Create release
MIX_ENV=prod mix release

# Database migrations in production
_build/prod/rel/my_app/bin/my_app eval "MyApp.Release.migrate"
```

### Environment Configuration
- **Development**: Local development with hot code reloading
- **Test**: Isolated test environment with test database
- **Production**: Optimized release with proper supervision

### Deployment Commands
```bash
# Build production release
MIX_ENV=prod mix release

# Start production server
_build/prod/rel/my_app/bin/my_app start

# Run database migrations
_build/prod/rel/my_app/bin/my_app eval "MyApp.Release.migrate"
```

## Development Workflow

### Branch Strategy
[Git workflow adapted for Elixir projects]
- `main`: Production-ready code
- `develop`: Integration branch
- `feature/*`: Feature development
- `hotfix/*`: Production fixes

### Commit Conventions
[Elixir-specific commit format]
```
type(scope): description

feat(contexts): add user authentication context
fix(live): resolve LiveView connection issues
docs(readme): update OTP architecture documentation
test(accounts): add property tests for user validation
```

### Pull Request Process
1. Create feature branch from develop
2. Implement changes with comprehensive tests
3. Run quality gates locally (`mix test && mix credo && mix dialyzer`)
4. Submit PR with description including OTP design decisions
5. Code review focusing on Elixir patterns
6. Merge to develop after approval

## Debugging and Troubleshooting

### Common Elixir/Phoenix Issues
- **GenServer bottlenecks**: Process message queue buildup
- **Database connection pool exhaustion**: Ecto configuration issues
- **LiveView connection problems**: WebSocket configuration
- **Memory leaks**: Improper process cleanup

### Debug Commands
```bash
# Debug mode with IEx
iex -S mix phx.server

# Observer for process monitoring
:observer.start()

# Process information
Process.info(pid)

# ETS table inspection
:ets.tab2list(:table_name)
```

### Performance Monitoring
- **Telemetry**: Built-in metrics collection
- **:observer**: Process and memory monitoring
- **Phoenix Dashboard**: Real-time application metrics
- **Custom metrics**: Application-specific monitoring

## Security Considerations

### Authentication & Authorization
[From PRD security framework]
- Guardian for JWT token management
- Role-based access control
- Session management with Phoenix

### Data Protection
- Ecto changeset validations
- SQL injection prevention through Ecto
- CSRF protection with Phoenix
- Input sanitization and validation

### Elixir-Specific Security
- Process isolation for security boundaries
- Pattern matching for input validation
- Supervision tree for fault isolation
- Rate limiting using GenServer patterns

## Dependencies

### Core Elixir Dependencies
- **phoenix**: Web framework
- **ecto_sql**: Database wrapper and query generator
- **postgrex**: PostgreSQL driver
- **jason**: JSON library
- **plug_cowboy**: HTTP server

### Development Dependencies
- **credo**: Static code analysis
- **dialyxir**: Dialyzer integration
- **ex_doc**: Documentation generation
- **excoveralls**: Test coverage reporting
- **phoenix_live_reload**: Hot code reloading

### Testing Dependencies
- **stream_data**: Property-based testing
- **bypass**: HTTP request mocking
- **phoenix_live_view_test**: LiveView testing helpers

## Resources

### Documentation
- [Elixir Documentation](https://elixir-lang.org/docs.html)
- [Phoenix Framework](https://phoenixframework.org/)
- [Ecto Documentation](https://hexdocs.pm/ecto/)
- [OTP Design Principles](https://erlang.org/doc/design_principles/users_guide.html)

### Tools and Extensions
- **IDE**: VS Code with ElixirLS extension
- **Debugging**: IEx REPL and :observer
- **Profiling**: :fprof and :eprof for performance analysis
- **Testing**: ExUnit with proper test structure

---

*This CLAUDE.md was generated based on PRD.md specifications and Elixir/Phoenix best practices, emphasizing OTP design patterns and fault-tolerant architecture.*
```

## Elixir-Specific Customizations

### Phoenix Web Application Focus
```markdown
### Phoenix Patterns
- **LiveView**: Real-time UI without JavaScript complexity
- **Contexts**: Business logic separation following DDD principles
- **Channels**: WebSocket communication for real-time features
- **Plugs**: Request/response transformation pipeline
- **Ecto**: Database operations with changesets and validations

### Quality Standards
```bash
# Elixir-specific quality checks
mix credo --strict
mix dialyzer
mix format --check-formatted
mix test --cover
```

### OTP Design Patterns
- Use GenServer for stateful processes
- Implement proper supervision trees
- Follow "let it crash" philosophy
- Use pattern matching and guards effectively
- Implement proper error handling with {:ok, result} | {:error, reason}
```

### Pure OTP Application Focus
```markdown
### OTP Architecture
- **Application**: Top-level OTP application behavior
- **Supervisor**: Fault tolerance and process lifecycle
- **GenServer**: Long-running processes with state
- **Agent**: Simple state management
- **Task**: Asynchronous operations

### Process Communication
- Message passing between processes
- PubSub for event broadcasting
- Registry for process discovery
- ETS for shared state when appropriate
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

### Elixir-Specific Quality Checklist
- [ ] Elixir/Phoenix conventions properly represented
- [ ] OTP design patterns clearly documented
- [ ] Supervision tree architecture included
- [ ] Quality gates include Credo and Dialyzer
- [ ] Testing strategy follows ExUnit best practices
- [ ] Code review process includes Elixir-specific patterns
- [ ] Performance considerations for concurrent applications
- [ ] Security measures appropriate for Elixir/Phoenix
- [ ] Documentation standards include @doc and @spec
- [ ] Deployment strategy uses Mix releases

### Next Steps
After CLAUDE.md creation:
1. Validate Elixir/Phoenix setup works correctly
2. Use `/create-planning` to generate OTP architecture planning
3. Continue with `/create-tasks` for Elixir-specific implementation breakdown

Remember: This CLAUDE.md leverages Elixir's unique strengths in concurrency, fault tolerance, and the Actor model while following Phoenix framework best practices.