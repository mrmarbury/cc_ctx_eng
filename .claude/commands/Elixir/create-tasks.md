---
name: create-tasks
description: Generate Elixir-specific TASKS.md with OTP patterns, Phoenix development, and supervision tree implementation
arguments: "Milestone focus (e.g., 'OTP foundation', 'Phoenix web layer', 'LiveView components')"
---

# Create Elixir Project Task Breakdown

## Milestone Focus: $ARGUMENTS

Generate a comprehensive TASKS.md specifically designed for Elixir/Phoenix development, breaking down OTP architecture, supervision trees, GenServer patterns, and Phoenix framework implementation into actionable tasks.

## Prerequisites
Ensure you have completed the full Elixir planning workflow:
1. `/create-prd` - Elixir project requirements with OTP patterns
2. `/create-claude-md` - Elixir development context and conventions
3. `/create-planning` - OTP architecture and Phoenix implementation strategy

## Elixir Task Generation Analysis
- Extract OTP implementation phases from PLANNING.md
- Identify supervision tree setup and GenServer patterns
- Review Phoenix framework tasks and LiveView components
- Map tasks to Elixir architectural patterns and best practices

## TASKS.md Template for Elixir Projects

Generate a comprehensive task breakdown following this Elixir-optimized structure:

```markdown
# Elixir Project Task Breakdown: [Project Name]

## Overview

**Project**: [Project Name]  
**Language**: Elixir
**Framework**: Phoenix (if applicable)
**Architecture**: OTP Supervision Tree with Actor Model
**Last Updated**: [Current Date]  
**Total Milestones**: [Number]  
**Estimated Duration**: [Timeline from PLANNING.md]  

### Quick Navigation
- [Milestone 1: OTP Foundation](#milestone-1-otp-foundation)
- [Milestone 2: Phoenix Web Layer](#milestone-2-phoenix-web-layer)
- [Milestone 3: Business Logic Implementation](#milestone-3-business-logic-implementation)
- [Milestone 4: Production Readiness](#milestone-4-production-readiness)
- [Ongoing Tasks](#ongoing-tasks)

### Task Status Legend
- 🟢 **Completed**: Task finished and validated
- 🟡 **In Progress**: Currently being worked on
- 🔴 **Blocked**: Waiting on dependency or external factor
- ⚪ **Pending**: Not yet started
- 🔵 **Review**: Ready for review/testing

---

## Milestone 1: OTP Foundation
**Duration**: 2 weeks  
**Objective**: Establish core OTP architecture with supervision tree and basic Phoenix setup

### Success Criteria
- [ ] OTP Application starts with proper supervision tree
- [ ] All GenServers and Agents can be started/restarted
- [ ] Database connection pool is properly managed
- [ ] Basic Phoenix endpoint responds
- [ ] Telemetry and logging systems work

### OTP Application Setup

#### Project Initialization
- ⚪ **TASK-001**: Create Phoenix application with OTP structure
  - **Description**: Initialize Phoenix project with proper OTP application structure
  - **Acceptance Criteria**: 
    - Phoenix application generated with --database postgres
    - OTP Application module properly configured
    - Supervision tree structure matches PLANNING.md
    - Mix.exs dependencies are properly configured
    - Code reviewed and approved
    - Documentation updated and complete
  - **Dependencies**: None
  - **Estimated Effort**: 2 hours
  - **Labels**: `setup`, `otp`, `phoenix`

- ⚪ **TASK-002**: Configure development environment
  - **Description**: Set up Elixir development environment per CLAUDE.md
  - **Acceptance Criteria**:
    - All developers can run `mix phx.server` successfully
    - Database connection works with `mix ecto.create`
    - Hot code reloading functions properly
    - Environment variables documented in README
    - Code reviewed and approved
    - Documentation updated and complete
  - **Dependencies**: TASK-001
  - **Estimated Effort**: 3 hours
  - **Labels**: `setup`, `environment`, `database`

#### Supervision Tree Implementation
- ⚪ **TASK-003**: Implement main supervision tree
  - **Description**: Create main OTP supervision tree per PLANNING.md architecture
  - **Acceptance Criteria**:
    - Application.ex properly configured with child processes
    - Supervision strategy matches planned architecture
    - All supervisors can start and restart properly
    - Process tree visible in :observer.start()
    - Code reviewed and approved
    - Documentation updated and complete
  - **Dependencies**: TASK-002
  - **Estimated Effort**: 4 hours
  - **Labels**: `otp`, `supervision`, `architecture`

- ⚪ **TASK-004**: Set up database supervision and connection pooling
  - **Description**: Configure Ecto repository with proper connection pooling
  - **Acceptance Criteria**:
    - Ecto.Repo configured with connection pooling
    - Database supervisor handles connection failures
    - Connection pool size optimized for development
    - Database migrations can run successfully
    - Code reviewed and approved
    - Documentation updated and complete
  - **Dependencies**: TASK-003
  - **Estimated Effort**: 3 hours
  - **Labels**: `database`, `ecto`, `supervision`

#### Core GenServer Implementation
- ⚪ **TASK-005**: Create core business logic GenServers
  - **Description**: Implement main GenServers per PLANNING.md process design
  - **Acceptance Criteria**:
    - GenServers follow proper OTP patterns
    - State management uses proper Elixir conventions
    - handle_call/handle_cast/handle_info properly implemented
    - GenServers can be started by supervision tree
    - Proper error handling and timeouts implemented
    - Code reviewed and approved
    - Documentation updated and complete
  - **Dependencies**: TASK-004
  - **Estimated Effort**: 6 hours
  - **Labels**: `genserver`, `otp`, `business-logic`

- ⚪ **TASK-006**: Implement Agent-based state management
  - **Description**: Create Agents for simple state management needs
  - **Acceptance Criteria**:
    - Agent modules follow Elixir conventions
    - State operations are atomic and thread-safe
    - Agent processes supervised properly
    - State can be persisted if needed
    - Code reviewed and approved
    - Documentation updated and complete
  - **Dependencies**: TASK-005
  - **Estimated Effort**: 3 hours
  - **Labels**: `agent`, `state`, `otp`

#### Phoenix Endpoint Configuration
- ⚪ **TASK-007**: Configure Phoenix endpoint and basic routing
  - **Description**: Set up Phoenix web server with basic configuration
  - **Acceptance Criteria**:
    - Phoenix endpoint starts and responds to requests
    - Basic routing configured in router.ex
    - Plug pipeline properly configured
    - Static assets served correctly
    - Code reviewed and approved
    - Documentation updated and complete
  - **Dependencies**: TASK-003
  - **Estimated Effort**: 3 hours
  - **Labels**: `phoenix`, `web`, `routing`

#### Telemetry and Monitoring Setup
- ⚪ **TASK-008**: Implement telemetry and logging
  - **Description**: Set up comprehensive telemetry and logging system
  - **Acceptance Criteria**:
    - Telemetry events configured for key processes
    - Structured logging with proper log levels
    - Process monitoring with :observer integration
    - Custom metrics for business logic
    - Code reviewed and approved
    - Documentation updated and complete
  - **Dependencies**: TASK-007
  - **Estimated Effort**: 4 hours
  - **Labels**: `telemetry`, `monitoring`, `logging`

---

## Milestone 2: Phoenix Web Layer
**Duration**: 2 weeks  
**Objective**: Implement Phoenix framework patterns with contexts, controllers, and real-time features

### Success Criteria
- [ ] Phoenix contexts properly separate business logic
- [ ] Controllers handle HTTP requests correctly
- [ ] LiveView components work for real-time features
- [ ] WebSocket channels function properly
- [ ] Authentication and authorization implemented

### Phoenix Context Implementation

#### Context Architecture
- ⚪ **TASK-009**: Design and implement Phoenix contexts
  - **Description**: Create Phoenix contexts following DDD principles from PLANNING.md
  - **Acceptance Criteria**: 
    - Context modules properly separate business domains
    - Public APIs follow Elixir naming conventions
    - Context boundaries respected throughout application
    - Proper delegation to GenServers and business logic
    - Code reviewed and approved
    - Documentation updated and complete
  - **Dependencies**: TASK-008
  - **Estimated Effort**: 5 hours
  - **Labels**: `context`, `architecture`, `business-logic`

- ⚪ **TASK-010**: Implement Ecto schemas and changesets
  - **Description**: Create database schemas with proper validations
  - **Acceptance Criteria**:
    - Ecto schemas match database design from PLANNING.md
    - Changesets provide comprehensive validation
    - Associations properly configured
    - Database constraints mirror changeset validations
    - Code reviewed and approved
    - Documentation updated and complete
  - **Dependencies**: TASK-009
  - **Estimated Effort**: 6 hours
  - **Labels**: `ecto`, `schema`, `database`

#### Controller and Route Implementation
- ⚪ **TASK-011**: Create Phoenix controllers and routes
  - **Description**: Implement HTTP controllers following Phoenix conventions
  - **Acceptance Criteria**:
    - Controllers are thin and delegate to contexts
    - Proper HTTP status codes returned
    - Error handling follows Phoenix patterns
    - JSON API responses properly formatted
    - Code reviewed and approved
    - Documentation updated and complete
  - **Dependencies**: TASK-010
  - **Estimated Effort**: 4 hours
  - **Labels**: `controller`, `http`, `api`

- ⚪ **TASK-012**: Implement authentication system
  - **Description**: Set up user authentication using Guardian or similar
  - **Acceptance Criteria**:
    - User registration and login workflows complete
    - JWT tokens properly generated and validated
    - Password hashing uses secure algorithms
    - Session management follows security best practices
    - Code reviewed and approved
    - Documentation updated and complete
  - **Dependencies**: TASK-011
  - **Estimated Effort**: 8 hours
  - **Labels**: `auth`, `security`, `guardian`

#### LiveView Implementation (if applicable)
- ⚪ **TASK-013**: Create LiveView components
  - **Description**: Implement real-time UI components using Phoenix LiveView
  - **Acceptance Criteria**:
    - LiveView modules follow Phoenix conventions
    - Real-time updates work without page refresh
    - State management between server and client
    - Event handling properly implemented
    - Code reviewed and approved
    - Documentation updated and complete
  - **Dependencies**: TASK-012
  - **Estimated Effort**: 8 hours
  - **Labels**: `liveview`, `realtime`, `ui`

#### Phoenix Channels (if applicable)
- ⚪ **TASK-014**: Implement WebSocket channels
  - **Description**: Set up Phoenix Channels for real-time communication
  - **Acceptance Criteria**:
    - Channel modules properly handle join/leave
    - Message broadcasting works correctly
    - Presence tracking implemented if needed
    - Proper error handling for channel operations
    - Code reviewed and approved
    - Documentation updated and complete
  - **Dependencies**: TASK-013
  - **Estimated Effort**: 6 hours
  - **Labels**: `channels`, `websocket`, `realtime`

#### PubSub Integration
- ⚪ **TASK-015**: Implement Phoenix PubSub for event broadcasting
  - **Description**: Set up PubSub for process communication and events
  - **Acceptance Criteria**:
    - PubSub properly configured in supervision tree
    - Event broadcasting works between processes
    - Topic-based subscription patterns implemented
    - Integration with LiveView and Channels
    - Code reviewed and approved
    - Documentation updated and complete
  - **Dependencies**: TASK-014
  - **Estimated Effort**: 4 hours
  - **Labels**: `pubsub`, `events`, `communication`

---

## Milestone 3: Business Logic Implementation
**Duration**: 4 weeks  
**Objective**: Implement core business features with proper OTP patterns and fault tolerance

### Success Criteria
- [ ] All business workflows complete successfully
- [ ] GenServers handle state management properly
- [ ] External service integrations work reliably
- [ ] Background job processing functional
- [ ] Comprehensive test coverage achieved

### Core Business Features

#### [Core Feature 1 from PRD]
- ⚪ **TASK-016**: Implement [Feature 1] GenServer
  - **Description**: Create GenServer for [specific business logic]
  - **Acceptance Criteria**: 
    - GenServer implements proper OTP patterns
    - State management follows Elixir conventions
    - Error handling uses "let it crash" philosophy
    - Process can be supervised and restarted
    - Code reviewed and approved
    - Documentation updated and complete
  - **Dependencies**: TASK-015
  - **Estimated Effort**: 8 hours
  - **Labels**: `genserver`, `business-feature`, `otp`

- ⚪ **TASK-017**: Create [Feature 1] context API
  - **Description**: Implement Phoenix context for [Feature 1]
  - **Acceptance Criteria**:
    - Context provides clean public API
    - Proper delegation to GenServer processes
    - Error handling with {:ok, result} | {:error, reason}
    - Integration with Ecto for data persistence
    - Code reviewed and approved
    - Documentation updated and complete
  - **Dependencies**: TASK-016
  - **Estimated Effort**: 6 hours
  - **Labels**: `context`, `api`, `business-feature`

- ⚪ **TASK-018**: Implement [Feature 1] Phoenix integration
  - **Description**: Create controllers/LiveViews for [Feature 1]
  - **Acceptance Criteria**:
    - HTTP endpoints properly handle requests
    - LiveView components update in real-time
    - Form handling with proper validation
    - Error messages displayed to users
    - Code reviewed and approved
    - Documentation updated and complete
  - **Dependencies**: TASK-017
  - **Estimated Effort**: 8 hours
  - **Labels**: `phoenix`, `ui`, `integration`

#### External Service Integration
- ⚪ **TASK-019**: Implement external API integration
  - **Description**: Set up integration with external services using Tesla
  - **Acceptance Criteria**:
    - HTTP client properly configured with Tesla
    - Circuit breaker pattern for fault tolerance
    - Retry logic with exponential backoff
    - Proper error handling and logging
    - Code reviewed and approved
    - Documentation updated and complete
  - **Dependencies**: TASK-018
  - **Estimated Effort**: 8 hours
  - **Labels**: `integration`, `external-api`, `tesla`

#### Background Job Processing
- ⚪ **TASK-020**: Set up background job processing
  - **Description**: Implement background job system using Oban or similar
  - **Acceptance Criteria**:
    - Job queue properly configured and supervised
    - Job processing with proper error handling
    - Job scheduling and retry mechanisms
    - Monitoring and observability for jobs
    - Code reviewed and approved
    - Documentation updated and complete
  - **Dependencies**: TASK-019
  - **Estimated Effort**: 10 hours
  - **Labels**: `background-jobs`, `oban`, `processing`

#### Comprehensive Testing
- ⚪ **TASK-021**: Implement comprehensive test suite
  - **Description**: Create thorough test coverage for all components
  - **Acceptance Criteria**:
    - Unit tests for all GenServers and contexts
    - Integration tests for Phoenix endpoints
    - LiveView tests for real-time components
    - Property tests for complex business logic
    - Test coverage >90% for critical paths
    - Code reviewed and approved
    - Documentation updated and complete
  - **Dependencies**: TASK-020
  - **Estimated Effort**: 16 hours
  - **Labels**: `testing`, `quality`, `coverage`

---

## Milestone 4: Production Readiness
**Duration**: 2 weeks  
**Objective**: Prepare application for production deployment with monitoring and optimization

### Success Criteria
- [ ] Production configuration complete
- [ ] Monitoring and observability implemented
- [ ] Performance optimization complete
- [ ] Security hardening done
- [ ] Deployment pipeline functional

### Production Configuration

#### Release Configuration
- ⚪ **TASK-022**: Configure Mix releases for production
  - **Description**: Set up production releases with proper configuration
  - **Acceptance Criteria**:
    - Mix release builds successfully
    - Production configuration separated from development
    - Environment variables properly configured
    - Database migrations can run in production
    - Code reviewed and approved
    - Documentation updated and complete
  - **Dependencies**: TASK-021
  - **Estimated Effort**: 6 hours
  - **Labels**: `deployment`, `release`, `production`

#### Monitoring and Observability
- ⚪ **TASK-023**: Implement comprehensive monitoring
  - **Description**: Set up monitoring for production environment
  - **Acceptance Criteria**:
    - Telemetry events for all critical processes
    - Prometheus metrics exported
    - Health check endpoints implemented
    - Alerting for critical failures
    - Code reviewed and approved
    - Documentation updated and complete
  - **Dependencies**: TASK-022
  - **Estimated Effort**: 8 hours
  - **Labels**: `monitoring`, `telemetry`, `observability`

#### Performance Optimization
- ⚪ **TASK-024**: Optimize application performance
  - **Description**: Profile and optimize application performance
  - **Acceptance Criteria**:
    - Database queries optimized with proper indexes
    - Process bottlenecks identified and resolved
    - Memory usage optimized
    - Response times meet performance targets
    - Code reviewed and approved
    - Documentation updated and complete
  - **Dependencies**: TASK-023
  - **Estimated Effort**: 10 hours
  - **Labels**: `performance`, `optimization`, `profiling`

#### Security Hardening
- ⚪ **TASK-025**: Implement security best practices
  - **Description**: Harden application security for production
  - **Acceptance Criteria**:
    - Security headers properly configured
    - Input validation comprehensive
    - Authentication and authorization secure
    - Dependencies updated and vulnerability-free
    - Code reviewed and approved
    - Documentation updated and complete
  - **Dependencies**: TASK-024
  - **Estimated Effort**: 8 hours
  - **Labels**: `security`, `hardening`, `production`

#### Deployment Pipeline
- ⚪ **TASK-026**: Set up deployment pipeline
  - **Description**: Create automated deployment pipeline
  - **Acceptance Criteria**:
    - CI/CD pipeline runs all tests and quality checks
    - Automated deployment to staging and production
    - Database migration automation
    - Rollback procedures documented and tested
    - Code reviewed and approved
    - Documentation updated and complete
  - **Dependencies**: TASK-025
  - **Estimated Effort**: 12 hours
  - **Labels**: `deployment`, `ci-cd`, `automation`

---

## Ongoing Tasks

### Code Quality and Maintenance
- ⚪ **TASK-027**: Set up code quality automation
  - **Description**: Implement automated code quality checks
  - **Priority**: High
  - **Acceptance Criteria**:
    - Credo runs on every commit
    - Dialyzer checks for type errors
    - Test coverage reports generated
    - Code formatted with mix format
    - Code reviewed and approved
    - Documentation updated and complete
  - **Labels**: `quality`, `automation`, `maintenance`

- ⚪ **TASK-028**: Maintain dependency updates
  - **Description**: Keep dependencies current and secure
  - **Priority**: High
  - **Acceptance Criteria**:
    - Dependencies regularly updated
    - Security vulnerabilities addressed
    - Compatibility testing performed
    - Code reviewed and approved
    - Documentation updated and complete
  - **Labels**: `dependencies`, `security`, `maintenance`

### Documentation and Knowledge Sharing
- ⚪ **TASK-029**: Maintain technical documentation
  - **Description**: Keep all technical documentation current
  - **Priority**: Medium
  - **Acceptance Criteria**:
    - CLAUDE.md updated with new patterns
    - API documentation generated with ExDoc
    - OTP architecture documented
    - Code reviewed and approved
    - Documentation updated and complete
  - **Labels**: `documentation`, `knowledge-sharing`

---

## Elixir-Specific Task Management Guidelines

### Task Template Requirements
**CRITICAL**: Every task must include review and documentation in acceptance criteria:

**Standard Elixir Task Format:**
- ⚪ **TASK-XXX**: [Action] [Brief description]
  - **Description**: [Detailed description with OTP/Phoenix context]
  - **Acceptance Criteria**: 
    - [Functional requirements specific to Elixir]
    - [OTP pattern compliance]
    - [Phoenix convention adherence]
    - **Code reviewed and approved**
    - **Documentation updated and complete**
  - **Dependencies**: [Other tasks that must be completed first]
  - **Estimated Effort**: [Time estimate in hours]
  - **Labels**: [Elixir-specific category tags]

### Elixir-Specific Validation Commands
```bash
# Code quality pipeline
mix test --cover && mix credo --strict && mix dialyzer

# Format checking
mix format --check-formatted

# Documentation generation
mix docs

# Release building
MIX_ENV=prod mix release
```

### Task Status Updates
- Update task status as work progresses
- Mark GenServer/Agent implementations as complete only after supervision works
- Test OTP patterns thoroughly before marking complete
- Link to relevant commits and PRs

### Effort Estimation for Elixir Tasks
- **Small (1-4 hours)**: Simple functions, basic GenServer operations
- **Medium (4-12 hours)**: Complex GenServer logic, Phoenix integration
- **Large (12+ hours)**: Full feature implementation, complex OTP patterns

### Elixir-Specific Labels
- **OTP**: `genserver`, `agent`, `supervisor`, `otp`
- **Phoenix**: `phoenix`, `liveview`, `controller`, `context`
- **Database**: `ecto`, `schema`, `migration`, `query`
- **Real-time**: `channels`, `pubsub`, `presence`, `websocket`
- **Quality**: `testing`, `credo`, `dialyzer`, `performance`

---

*This task breakdown transforms the OTP architectural planning from PLANNING.md into actionable Elixir development work, organized by implementation phases and emphasizing fault-tolerant, concurrent patterns.*
```

## Milestone Focus Customizations

### OTP Foundation Focus
Generate tasks focused on:
- Supervision tree implementation
- GenServer and Agent setup
- Process communication patterns
- Fault tolerance mechanisms

### Phoenix Web Layer Focus
Emphasize tasks for:
- Context boundary implementation
- Controller and routing setup
- LiveView component development
- Real-time feature implementation

### LiveView Components Focus
Prioritize tasks for:
- Server-side rendering patterns
- Real-time UI state management
- WebSocket integration
- Component composition

## Output and Validation

### Save Location
Save the generated task breakdown as: `TASKS.md` in the project root

### Elixir-Specific Quality Checklist
- [ ] All milestones align with OTP architecture from PLANNING.md
- [ ] Tasks follow Elixir/Phoenix conventions and patterns
- [ ] GenServer and supervision tasks properly defined
- [ ] Phoenix context boundaries respected in task organization
- [ ] Testing strategy includes ExUnit and property testing
- [ ] Performance tasks include concurrency optimization
- [ ] Security tasks address Elixir-specific concerns
- [ ] Documentation tasks include @doc and @spec requirements
- [ ] Deployment tasks use Mix releases and OTP principles
- [ ] Ready for Elixir development team execution

### Next Steps
After TASKS.md creation:
1. Review task breakdown with Elixir development team
2. Adjust effort estimates based on team OTP experience
3. Begin development with OTP Foundation milestone
4. Use process monitoring tools (:observer) throughout development
5. Update task status regularly as work progresses

Remember: Great Elixir applications are built on solid OTP foundations. This breakdown ensures proper supervision, fault tolerance, and concurrent processing from the start.