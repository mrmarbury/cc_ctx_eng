---
name: create-tasks
description: Generate milestone-based TASKS.md with actionable todo list for project implementation
arguments: "Optional milestone focus (e.g., 'MVP', 'Phase 1', 'Backend', 'Frontend')"
---

# Create Project Task Breakdown

## Milestone Focus: $ARGUMENTS

Generate a comprehensive TASKS.md that breaks down your project into actionable, milestone-driven tasks. This transforms the high-level planning into specific, trackable work items for development.

## Prerequisites
Ensure you have completed the full planning workflow:
1. `/create-prd` - Project requirements and scope
2. `/create-claude-md` - Development context and tech stack  
3. `/create-planning` - Architecture and implementation strategy

## Task Generation Process

### 1. Document Analysis
- Extract implementation phases from PLANNING.md
- Identify key deliverables and dependencies from PRD.md
- Review technical requirements from CLAUDE.md
- Map tasks to architectural components

### 2. Task Breakdown Strategy
- Break down phases into specific, actionable tasks
- Organize tasks by milestone and priority
- Identify dependencies between tasks
- Estimate effort and complexity
- Assign task categories and labels

### 3. Milestone Planning
- Define clear milestone objectives
- Set milestone success criteria
- Plan milestone deliverables
- Identify milestone dependencies and blockers

## TASKS.md Template Structure

Generate a comprehensive task breakdown following this structure:

```markdown
# Project Task Breakdown: [Project Name]

## Overview

**Project**: [Project Name]  
**Last Updated**: [Current Date]  
**Total Milestones**: [Number]  
**Estimated Duration**: [Timeline from PLANNING.md]  

### Quick Navigation
- [Milestone 1: Foundation](#milestone-1-foundation)
- [Milestone 2: Core Development](#milestone-2-core-development)
- [Milestone 3: Feature Enhancement](#milestone-3-feature-enhancement)
- [Milestone 4: Launch Preparation](#milestone-4-launch-preparation)
- [Ongoing Tasks](#ongoing-tasks)

### Task Status Legend
- 🟢 **Completed**: Task finished and validated
- 🟡 **In Progress**: Currently being worked on
- 🔴 **Blocked**: Waiting on dependency or external factor
- ⚪ **Pending**: Not yet started
- 🔵 **Review**: Ready for review/testing

---

## Milestone 1: Foundation
**Duration**: [Timeline]  
**Objective**: [Primary objective from PLANNING.md]

### Success Criteria
- [ ] Development environment is fully functional
- [ ] Core infrastructure is deployed and tested
- [ ] Authentication system is working
- [ ] Basic API structure is implemented
- [ ] Database schema is created and validated

### Infrastructure & Setup

#### Development Environment
- ⚪ **TASK-001**: Set up project repository and initial structure
  - **Description**: Initialize git repository, create folder structure per PLANNING.md
  - **Acceptance Criteria**: 
    - Repository structure matches planned architecture
    - README.md with setup instructions is complete
    - .gitignore is properly configured
    - Code reviewed for structure and conventions
    - Documentation updated with setup process
  - **Dependencies**: None
  - **Estimated Effort**: 2 hours
  - **Labels**: `setup`, `infrastructure`

- ⚪ **TASK-002**: Configure development environment
  - **Description**: Set up local development environment per CLAUDE.md
  - **Acceptance Criteria**:
    - All developers can run the project locally
    - Environment variables are documented
    - Docker/containerization is working (if applicable)
    - Setup process reviewed and validated
    - Environment documentation is complete and accurate
  - **Dependencies**: TASK-001
  - **Estimated Effort**: 4 hours
  - **Labels**: `setup`, `environment`

- ⚪ **TASK-003**: Set up CI/CD pipeline
  - **Description**: Configure automated testing and deployment pipeline
  - **Acceptance Criteria**:
    - Automated tests run on every PR
    - Code quality checks are enforced
    - Deployment to staging is automated
  - **Dependencies**: TASK-001, TASK-002
  - **Estimated Effort**: 6 hours
  - **Labels**: `devops`, `automation`

#### Database & Data Layer
- ⚪ **TASK-004**: Design and implement database schema
  - **Description**: Create database tables per PLANNING.md data architecture
  - **Acceptance Criteria**:
    - All entity relationships are implemented
    - Database migrations are created
    - Indexes are optimized for expected queries
  - **Dependencies**: TASK-002
  - **Estimated Effort**: 8 hours
  - **Labels**: `database`, `backend`

- ⚪ **TASK-005**: Set up database connection and ORM
  - **Description**: Configure database connectivity and data access layer
  - **Acceptance Criteria**:
    - Database connection is secure and configurable
    - ORM/query builder is properly configured
    - Connection pooling is implemented
  - **Dependencies**: TASK-004
  - **Estimated Effort**: 4 hours
  - **Labels**: `database`, `backend`

#### Authentication & Security
- ⚪ **TASK-006**: Implement authentication system
  - **Description**: Build user authentication per security architecture
  - **Acceptance Criteria**:
    - User registration and login work correctly
    - Password hashing and validation are secure
    - JWT/session management is implemented
    - Code reviewed and approved
    - Documentation updated and complete
  - **Dependencies**: TASK-005
  - **Estimated Effort**: 12 hours
  - **Labels**: `auth`, `security`, `backend`

- ⚪ **TASK-007**: Set up authorization framework
  - **Description**: Implement role-based access control system
  - **Acceptance Criteria**:
    - User roles and permissions are defined
    - API endpoints are properly protected
    - Admin and user access levels work correctly
  - **Dependencies**: TASK-006
  - **Estimated Effort**: 8 hours
  - **Labels**: `auth`, `security`, `backend`

#### API Foundation
- ⚪ **TASK-008**: Create basic API structure
  - **Description**: Set up API framework and routing per CLAUDE.md
  - **Acceptance Criteria**:
    - API framework is configured and running
    - Basic routing structure is implemented
    - Error handling middleware is in place
  - **Dependencies**: TASK-002
  - **Estimated Effort**: 6 hours
  - **Labels**: `api`, `backend`

- ⚪ **TASK-009**: Implement API documentation
  - **Description**: Set up automated API documentation
  - **Acceptance Criteria**:
    - API endpoints are automatically documented
    - Documentation is accessible and up-to-date
    - Request/response examples are included
  - **Dependencies**: TASK-008
  - **Estimated Effort**: 4 hours
  - **Labels**: `documentation`, `api`

#### Frontend Foundation
- ⚪ **TASK-010**: Set up frontend application structure
  - **Description**: Initialize frontend framework per CLAUDE.md
  - **Acceptance Criteria**:
    - Frontend framework is configured and running
    - Component structure follows planned architecture
    - Build and development tools are working
  - **Dependencies**: TASK-002
  - **Estimated Effort**: 6 hours
  - **Labels**: `frontend`, `setup`

- ⚪ **TASK-011**: Implement authentication UI
  - **Description**: Create login and registration forms
  - **Acceptance Criteria**:
    - Login form connects to backend auth
    - Registration form validates and creates users
    - Error handling and user feedback work
  - **Dependencies**: TASK-006, TASK-010
  - **Estimated Effort**: 8 hours
  - **Labels**: `frontend`, `auth`, `ui`

---

## Milestone 2: Core Development
**Duration**: [Timeline]  
**Objective**: [Core functionality objective from PLANNING.md]

### Success Criteria
- [ ] Primary user workflows are functional
- [ ] Core business logic is implemented
- [ ] Data validation and error handling work
- [ ] Basic user interface is complete

### Core Features

#### [Core Feature 1 from PRD]
- ⚪ **TASK-012**: Design [Feature 1] data models
  - **Description**: [Specific feature implementation details]
  - **Acceptance Criteria**: 
    - [Specific, testable criteria]
    - Code reviewed and approved
    - Documentation updated and complete
  - **Dependencies**: [Previous tasks]
  - **Estimated Effort**: [Hours]
  - **Labels**: `core-feature`, `backend`

- ⚪ **TASK-013**: Implement [Feature 1] API endpoints
  - **Description**: [API implementation details]
  - **Acceptance Criteria**: [API functionality criteria]
  - **Dependencies**: TASK-012
  - **Estimated Effort**: [Hours]
  - **Labels**: `api`, `core-feature`

- ⚪ **TASK-014**: Create [Feature 1] user interface
  - **Description**: [UI implementation details]
  - **Acceptance Criteria**: [User interface criteria]
  - **Dependencies**: TASK-013
  - **Estimated Effort**: [Hours]
  - **Labels**: `frontend`, `ui`, `core-feature`

#### [Core Feature 2 from PRD]
- ⚪ **TASK-015**: [Feature 2 tasks following same pattern]
- ⚪ **TASK-016**: [Continue with consistent task breakdown]
- ⚪ **TASK-017**: [Each task includes all required fields]

#### Data Validation & Error Handling
- ⚪ **TASK-018**: Implement comprehensive input validation
  - **Description**: Add validation for all user inputs and API requests
  - **Acceptance Criteria**:
    - All forms validate data before submission
    - API endpoints reject invalid requests with clear errors
    - Client-side and server-side validation are coordinated
  - **Dependencies**: Core feature API tasks
  - **Estimated Effort**: 10 hours
  - **Labels**: `validation`, `security`, `backend`, `frontend`

#### Testing & Quality Assurance
- ⚪ **TASK-019**: Write unit tests for core features
  - **Description**: Implement unit tests per testing strategy in PLANNING.md
  - **Acceptance Criteria**:
    - Test coverage meets target percentage
    - All critical business logic is tested
    - Tests run automatically in CI/CD pipeline
  - **Dependencies**: Core feature implementation tasks
  - **Estimated Effort**: 16 hours
  - **Labels**: `testing`, `quality`

---

## Milestone 3: Feature Enhancement
**Duration**: [Timeline]  
**Objective**: [Enhancement objective from PLANNING.md]

### Success Criteria
- [ ] Advanced features are implemented and tested
- [ ] Performance optimization is complete
- [ ] User experience is polished
- [ ] Integration with external services works

### Advanced Features

#### [Advanced Feature 1 from PRD]
- ⚪ **TASK-020**: [Advanced feature tasks]
- ⚪ **TASK-021**: [Continue pattern for advanced features]

#### Performance Optimization
- ⚪ **TASK-022**: Implement caching strategy
  - **Description**: Add caching per performance plan in PLANNING.md
  - **Acceptance Criteria**:
    - Database query caching reduces response times
    - Static asset caching improves page load speeds
    - Cache invalidation works correctly
  - **Dependencies**: Core features complete
  - **Estimated Effort**: 12 hours
  - **Labels**: `performance`, `optimization`

#### External Integrations
- ⚪ **TASK-023**: Integrate with [Third-party Service]
  - **Description**: Implement integration per PLANNING.md requirements
  - **Acceptance Criteria**:
    - Service integration works reliably
    - Error handling for service failures
    - Configuration is secure and manageable
  - **Dependencies**: Core features complete
  - **Estimated Effort**: 8 hours
  - **Labels**: `integration`, `external`

---

## Milestone 4: Launch Preparation
**Duration**: [Timeline]  
**Objective**: [Launch readiness objective from PLANNING.md]

### Success Criteria
- [ ] Production environment is ready
- [ ] Security audit passes
- [ ] Performance testing meets targets
- [ ] Documentation is complete
- [ ] Launch plan is executed

### Production Readiness

#### Security & Compliance
- ⚪ **TASK-024**: Conduct security audit
  - **Description**: Perform comprehensive security review per PLANNING.md
  - **Acceptance Criteria**:
    - All security vulnerabilities are addressed
    - Penetration testing passes
    - Compliance requirements are met
  - **Dependencies**: All features complete
  - **Estimated Effort**: 16 hours
  - **Labels**: `security`, `audit`, `compliance`

#### Performance & Load Testing
- ⚪ **TASK-025**: Execute performance testing
  - **Description**: Validate performance targets from PLANNING.md
  - **Acceptance Criteria**:
    - Load testing meets concurrent user targets
    - Response time targets are achieved
    - System handles expected traffic volume
  - **Dependencies**: All features complete
  - **Estimated Effort**: 12 hours
  - **Labels**: `performance`, `testing`

#### Production Deployment
- ⚪ **TASK-026**: Set up production environment
  - **Description**: Configure production infrastructure per PLANNING.md
  - **Acceptance Criteria**:
    - Production environment matches staging
    - Monitoring and alerting are configured
    - Backup and disaster recovery work
  - **Dependencies**: All development complete
  - **Estimated Effort**: 20 hours
  - **Labels**: `deployment`, `infrastructure`

#### Documentation & Training
- ⚪ **TASK-027**: Complete user documentation
  - **Description**: Create end-user guides and help documentation
  - **Acceptance Criteria**:
    - User onboarding guide is complete
    - Feature documentation is comprehensive
    - FAQ addresses common questions
  - **Dependencies**: All features complete
  - **Estimated Effort**: 16 hours
  - **Labels**: `documentation`, `user-experience`

---

## Ongoing Tasks

### Maintenance & Monitoring
- ⚪ **TASK-028**: Set up monitoring and alerting
  - **Description**: Implement observability per PLANNING.md
  - **Priority**: High
  - **Labels**: `monitoring`, `operations`

- ⚪ **TASK-029**: Regular security updates
  - **Description**: Maintain dependency updates and security patches
  - **Priority**: High
  - **Labels**: `security`, `maintenance`

### Documentation
- ⚪ **TASK-030**: Maintain technical documentation
  - **Description**: Keep CLAUDE.md and technical docs current
  - **Priority**: Medium
  - **Labels**: `documentation`, `maintenance`

---

## Task Management Guidelines

### Task Template Requirements
**CRITICAL**: Every task must include review and documentation in acceptance criteria:

**Standard Task Format:**
- ⚪ **TASK-XXX**: [Task Title]
  - **Description**: [Detailed description of what needs to be done]
  - **Acceptance Criteria**: 
    - [Functional requirements]
    - [Quality requirements]
    - **Code reviewed and approved**
    - **Documentation updated and complete**
  - **Dependencies**: [Other tasks that must be completed first]
  - **Estimated Effort**: [Time estimate in hours]
  - **Labels**: [Category tags for organization]

### Task Status Updates
- Update task status as work progresses
- Add completion dates when tasks are finished
- Note any blockers or issues in task descriptions
- Link to relevant PRs or commits when completing tasks

### Effort Estimation
- **Small (1-4 hours)**: Simple implementation, well-defined scope
- **Medium (4-12 hours)**: Moderate complexity, some unknowns
- **Large (12+ hours)**: Complex implementation, significant research needed

### Priority Levels
- **Critical**: Blocks other work or milestone completion
- **High**: Important for milestone success
- **Medium**: Valuable but not blocking
- **Low**: Nice-to-have, can be deferred

### Labels for Organization
- **Component**: `frontend`, `backend`, `database`, `api`
- **Type**: `feature`, `bug`, `documentation`, `testing`
- **Priority**: `critical`, `high`, `medium`, `low`
- **Status**: `in-progress`, `blocked`, `review`, `testing`

---

*This task breakdown transforms the strategic planning from PLANNING.md into actionable development work organized by milestones and priorities.*
```

## Milestone Focus Customizations

### MVP Focus
Generate tasks focused on:
- Minimal viable feature set
- Basic functionality without polish
- Quick validation and feedback loops
- Essential infrastructure only

### Backend Focus
Emphasize tasks for:
- API development and documentation
- Database optimization and scaling
- Service integration and data flow
- Performance and security

### Frontend Focus
Prioritize tasks for:
- User interface development
- User experience optimization
- Component library creation
- Responsive design implementation

## Output and Validation

### Save Location
Save the generated task breakdown as: `TASKS.md` in the project root

### Quality Checklist
- [ ] All milestones align with PLANNING.md phases
- [ ] Tasks are specific and actionable
- [ ] Dependencies are clearly identified
- [ ] Effort estimates are realistic
- [ ] Success criteria are measurable
- [ ] Task organization supports efficient development
- [ ] Both technical and user-facing work is covered
- [ ] Testing and quality assurance tasks are included
- [ ] Documentation tasks are planned
- [ ] Ready for development team execution

### Next Steps
After TASKS.md creation:
1. Review task breakdown with development team
2. Adjust effort estimates based on team expertise
3. Begin development with Milestone 1 tasks
4. Use task tracking tools to monitor progress
5. Update task status regularly as work progresses

Remember: Great projects are built one task at a time. This breakdown turns your vision into executable reality.