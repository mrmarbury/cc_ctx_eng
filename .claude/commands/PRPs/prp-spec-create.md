# Create SPEC PRP (Standalone)

Generate a comprehensive specification-driven PRP with clear transformation goals and checkbox-based task tracking. This is a **standalone document** that does not require PRD.md, PLANNING.md, or TASKS.md files.

## Specification: $ARGUMENTS

## Analysis Process

1. **Current State Assessment**
   - Map existing implementation
   - Identify pain points
   - Document technical debt
   - Note integration points

2. **Desired State Research**
   - Best practices for target state
   - Implementation examples
   - Migration strategies
   - Risk assessment
   - Dependency mapping

3. **User Clarification**
   - Confirm transformation goals
   - Priority of objectives
   - Acceptable trade-offs

## PRP Generation

Using PRPs/templates/prp_spec.md template, create a **standalone specification** that includes:

### State Documentation

```yaml
current_state:
  files: [list affected files]
  behavior: [how it works now]
  issues: [specific problems]

desired_state:
  files: [expected structure]
  behavior: [target functionality]
  benefits: [improvements gained]
```

### Hierarchical Objectives

1. **High-Level**: Overall transformation goal
2. **Mid-Level**: Major milestones
3. **Low-Level**: Specific tasks with validation

### Task Specification with Checkboxes

**CRITICAL**: All tasks must use checkbox format `- [ ]` for tracking completion.

#### Information Dense Keywords:
- MIRROR: Mirror existing code state to another use case
- COPY: Copy existing code to another use case
- ADD: Add new code to the codebase
- MODIFY: Modify existing code
- DELETE: Delete existing code
- RENAME: Rename existing code
- MOVE: Move existing code
- REPLACE: Replace existing code
- CREATE: Create new code

#### Task Format Example:

```markdown
## Low-Level Tasks

> Ordered from start to finish

- [ ] **Task 1**: CREATE infrastructure setup
  ```
  Action: CREATE
  File: deploy/azure/infrastructure/main.tf
  Changes: 
    - Set up AKS cluster configuration
    - Configure resource groups and networking
    - Add monitoring and logging
  Validation:
    - Command: terraform plan
    - Expect: No errors, valid plan output
  ```

- [ ] **Task 2**: MODIFY authentication configuration
  ```
  Action: MODIFY
  File: config/keycloak/main.tf
  Changes:
    - Configure realm settings
    - Set up identity provider integration
    - Add client configurations
  Validation:
    - Command: terraform apply
    - Expect: Successful deployment
  ```
```

### Implementation Strategy

- Identify dependencies
- Order tasks by priority and implementation order and dependencies logic
- Include rollback plans
- Progressive enhancement

## User Interaction Points

1. **Objective Validation**
   - Review hierarchical breakdown
   - Confirm priorities
   - Identify missing pieces

2. **Risk Review**
   - Document identified risks
   - Find mitigations
   - Set go/no-go criteria

## Context Requirements

- Current implementation details
- Target architecture examples
- Migration best practices
- Testing strategies

## Standalone PRP Structure

The generated PRP should be **completely self-contained** with this structure:

```markdown
# Specification: [Project Name]

> Ingest the information from this file, implement the Low-Level Tasks, and generate the code that will satisfy the High and Mid-Level Objectives.

## High-Level Objective
- [Primary transformation goal]

## Mid-Level Objectives
- [List of concrete, measurable sub-objectives]
- [Each objective should be specific and actionable]

## Implementation Notes
- [Important technical details and requirements]
- [Dependencies and constraints]
- [Coding standards and architectural patterns]
- [Integration points and considerations]

## Context

### Beginning Context
- [Files that exist at start]
- [Current system state]

### Ending Context
- [Files that will exist at end]
- [Target system state]

## Low-Level Tasks

> Ordered from start to finish

- [ ] **Task 1**: [Action] [Brief description]
  ```
  Action: CREATE/MODIFY/DELETE/etc.
  File: path/to/file
  Changes:
    - Specific modification 1
    - Specific modification 2
  Validation:
    - Command: "validation command"
    - Expect: "success criteria"
  ```

- [ ] **Task 2**: [Action] [Brief description]
  ```
  [Same format as above]
  ```

[Continue for all tasks...]

## Validation Gates
- [ ] All tasks completed successfully
- [ ] Validation commands pass
- [ ] Integration tests pass
- [ ] Documentation updated
```

## Output

Save as: `PRPs/prp_spec_{spec-name}.md`

**IMPORTANT**: This is a standalone document. Do NOT create or reference PRD.md, PLANNING.md, or TASKS.md files.

## Quality Checklist

- [ ] Current state fully documented
- [ ] Desired state clearly defined
- [ ] All objectives measurable
- [ ] Tasks use checkbox format `- [ ]`
- [ ] Tasks ordered by dependency
- [ ] Each task has validation that AI can execute
- [ ] Implementation notes include technical details
- [ ] Beginning and ending context specified
- [ ] Completely standalone (no external document dependencies)

Remember: This PRP should contain everything needed to execute the transformation without requiring any other planning documents.
