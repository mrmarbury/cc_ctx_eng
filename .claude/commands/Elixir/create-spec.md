---
name: create-spec
description: Create standalone Elixir specification with checkbox-based task tracking
arguments: "Elixir project specification (e.g., 'Phoenix API with LiveView dashboard')"
---

# Create Elixir Specification (Standalone)

## Specification: $ARGUMENTS

Generate a comprehensive Elixir specification-driven document with checkbox-based task tracking. This is a **standalone document** optimized for Elixir/Phoenix development patterns.

## Analysis Process

### 1. **Elixir Ecosystem Assessment**
   - Identify if this is Phoenix web app, LiveView, GenServer, OTP application
   - Determine supervision tree structure and process architecture
   - Assess database needs (Ecto, PostgreSQL, etc.)
   - Evaluate real-time requirements (Phoenix Channels, PubSub)

### 2. **Phoenix/OTP Pattern Research**
   - Review Phoenix framework conventions and best practices
   - Identify appropriate OTP design patterns (GenServer, Agent, Task, etc.)
   - Research LiveView patterns if applicable
   - Evaluate umbrella app vs single app architecture

### 3. **Elixir Development Standards**
   - Follow Elixir style guide conventions
   - Use proper naming conventions (snake_case, module naming)
   - Implement proper error handling with {:ok, result} | {:error, reason}
   - Plan for concurrent/parallel processing patterns

## Elixir-Specific Requirements

### Development Environment
- **Elixir Version**: 1.15+ recommended
- **Erlang/OTP**: 26+ recommended
- **Phoenix Framework**: 1.7+ (if web application)
- **Database**: PostgreSQL with Ecto
- **Testing**: ExUnit with proper test structure

### Project Structure
```
my_app/
├── config/
│   ├── config.exs
│   ├── dev.exs
│   ├── prod.exs
│   └── test.exs
├── lib/
│   ├── my_app/
│   │   ├── application.ex
│   │   └── [domain modules]
│   └── my_app_web/
│       ├── components/
│       ├── controllers/
│       ├── live/
│       └── router.ex
├── priv/
│   └── repo/migrations/
├── test/
└── mix.exs
```

## Standalone Specification Structure

Create a comprehensive, self-contained specification:

```markdown
# Elixir Specification: [Project Name]

> Ingest the information from this file, implement the Low-Level Tasks, and generate the code that will satisfy the High and Mid-Level Objectives.

## High-Level Objective
- [Primary goal - e.g., "Build a real-time Phoenix application with LiveView"]

## Mid-Level Objectives
- [Elixir/Phoenix specific objectives]
- Set up Phoenix application with proper supervision tree
- Implement Ecto schemas and migrations
- Create LiveView components (if applicable)
- Set up proper error handling and logging
- Configure deployment pipeline

## Implementation Notes

### Elixir/Phoenix Conventions
- Follow Elixir naming conventions (snake_case for files, PascalCase for modules)
- Use proper OTP design patterns
- Implement supervision trees for fault tolerance
- Use pattern matching and guards effectively
- Follow Phoenix context patterns for business logic

### Dependencies and Requirements
- Phoenix framework (if web app)
- Ecto for database operations
- Jason for JSON handling
- Proper test setup with ExUnit
- Credo for code quality
- Dialyzer for static analysis

### Code Quality Standards
- All functions should have @spec type annotations
- Use @doc and @moduledoc for documentation
- Follow the principle of "let it crash"
- Implement proper error handling with {:ok, result} | {:error, reason}
- Use GenServer/Agent/Task appropriately

## Context

### Beginning Context
- [Starting files and project state]
- Empty or existing Elixir project
- Required dependencies and versions

### Ending Context
- [Expected final project structure]
- Fully functional Elixir application
- Proper test coverage
- Documentation complete

## Low-Level Tasks

> Ordered from start to finish

- [ ] **Task 1**: CREATE Phoenix application structure
  ```
  Action: CREATE
  Command: mix phx.new my_app --database postgres
  Changes:
    - Generate Phoenix application boilerplate
    - Set up proper directory structure
    - Configure database connection
  Validation:
    - Command: mix deps.get && mix compile
    - Expect: No compilation errors
  ```

- [ ] **Task 2**: CONFIGURE development environment
  ```
  Action: MODIFY
  File: config/dev.exs
  Changes:
    - Configure database settings
    - Set up proper logging levels
    - Configure Phoenix endpoint
  Validation:
    - Command: mix phx.server
    - Expect: Server starts without errors
  ```

- [ ] **Task 3**: CREATE Ecto schemas and migrations
  ```
  Action: CREATE
  File: lib/my_app/[domain]/[schema].ex
  Changes:
    - Define Ecto schemas with proper validations
    - Create database migrations
    - Set up associations and constraints
  Validation:
    - Command: mix ecto.migrate
    - Expect: Migration runs successfully
  ```

- [ ] **Task 4**: IMPLEMENT Phoenix contexts
  ```
  Action: CREATE
  File: lib/my_app/[context].ex
  Changes:
    - Create business logic modules
    - Implement CRUD operations
    - Add proper error handling
  Validation:
    - Command: mix test
    - Expect: All tests pass
  ```

- [ ] **Task 5**: CREATE Phoenix controllers/LiveViews
  ```
  Action: CREATE
  File: lib/my_app_web/controllers/[name]_controller.ex
  Changes:
    - Implement HTTP endpoints
    - Add proper error handling
    - Create LiveView components if needed
  Validation:
    - Command: mix phx.server && curl localhost:4000/api/endpoint
    - Expect: Proper HTTP responses
  ```

- [ ] **Task 6**: SET UP comprehensive testing
  ```
  Action: CREATE
  File: test/my_app/[context]_test.exs
  Changes:
    - Create unit tests for contexts
    - Add controller/LiveView tests
    - Set up test database
  Validation:
    - Command: mix test
    - Expect: All tests pass with >90% coverage
  ```

- [ ] **Task 7**: CONFIGURE code quality tools
  ```
  Action: MODIFY
  File: mix.exs
  Changes:
    - Add Credo, Dialyzer, ExCoveralls
    - Configure quality checks
    - Set up CI/CD pipeline
  Validation:
    - Command: mix credo && mix dialyzer
    - Expect: No issues found
  ```

- [ ] **Task 8**: IMPLEMENT OTP supervision tree
  ```
  Action: MODIFY
  File: lib/my_app/application.ex
  Changes:
    - Set up proper supervision tree
    - Configure child processes
    - Add proper restart strategies
  Validation:
    - Command: mix run --no-halt
    - Expect: Application starts and supervises properly
  ```

- [ ] **Task 9**: ADD logging and telemetry
  ```
  Action: CREATE
  File: lib/my_app/telemetry.ex
  Changes:
    - Configure telemetry events
    - Set up proper logging
    - Add metrics collection
  Validation:
    - Command: mix phx.server (check logs)
    - Expect: Proper telemetry events logged
  ```

- [ ] **Task 10**: CONFIGURE production deployment
  ```
  Action: CREATE
  File: rel/overlays/bin/migrate
  Changes:
    - Set up release configuration
    - Create deployment scripts
    - Configure production environment
  Validation:
    - Command: mix release
    - Expect: Release builds successfully
  ```

## Validation Gates
- [ ] All tasks completed successfully
- [ ] All tests pass with >90% coverage
- [ ] Credo passes with no issues
- [ ] Dialyzer passes with no warnings
- [ ] Application starts and runs properly
- [ ] Documentation is complete and accurate
- [ ] Code follows Elixir conventions
- [ ] OTP principles properly implemented

## Elixir-Specific Quality Checklist
- [ ] Proper use of pattern matching and guards
- [ ] Appropriate OTP design patterns used
- [ ] Supervision trees properly configured
- [ ] Error handling follows {:ok, result} | {:error, reason} pattern
- [ ] All public functions have @spec annotations
- [ ] Modules have proper @moduledoc documentation
- [ ] Phoenix contexts properly separate business logic
- [ ] Database operations use Ecto best practices
- [ ] LiveView components are properly structured (if applicable)
- [ ] Telemetry and logging configured correctly
```

## Output

Save as: `PRPs/elixir_spec_{project-name}.md`

**IMPORTANT**: This is a standalone document. Do NOT create or reference PRD.md, PLANNING.md, or TASKS.md files.

## Quality Checklist

- [ ] Elixir/Phoenix conventions properly specified
- [ ] OTP design patterns identified and planned
- [ ] Supervision tree architecture defined
- [ ] Tasks use checkbox format `- [ ]`
- [ ] Tasks ordered by dependency
- [ ] Each task has Elixir-specific validation
- [ ] Code quality tools (Credo, Dialyzer) integrated
- [ ] Testing strategy includes ExUnit best practices
- [ ] Deployment considerations included
- [ ] Completely standalone (no external document dependencies)

Remember: This specification should leverage Elixir's strengths - concurrency, fault tolerance, and the Actor model through OTP.