# Execute SPEC PRP (Standalone)

Implement a specification using an existing standalone SPEC PRP with checkbox-based task tracking.

## PRP File: $ARGUMENTS

## Execution Process

### 1. **Read and Understand Spec**
   - Read the entire SPEC PRP document
   - Understand current state vs desired state
   - Review all objectives and implementation notes
   - Identify task dependencies and order

### 2. **ULTRATHINK Planning**
   - Think hard before executing the plan
   - Create a comprehensive implementation strategy
   - Use the TodoWrite tool to track your progress
   - Identify patterns from existing code to follow
   - Plan for potential issues and rollbacks

### 3. **Execute Tasks with Checkbox Tracking**
   - Work through tasks in the specified order
   - **Mark each task as completed**: Change `- [ ]` to `- [x]` in the PRP file
   - Run validation commands after each task
   - Fix any failures before proceeding to next task
   - Update the PRP file with progress notes if needed

### 4. **Checkbox Management Protocol**
   **CRITICAL**: Maintain accurate task status in the PRP file:
   
   **Completing Tasks:**
   - When a task is finished, immediately update the PRP file
   - Change `- [ ] **Task 1**: CREATE infrastructure` to `- [x] **Task 1**: CREATE infrastructure`
   
   **Reopening Tasks:**
   - If a task needs rework, change back from `- [x]` to `- [ ]`
   - Add a note explaining why the task was reopened
   
   **Validation Requirements:**
   - Each task must pass its validation criteria before marking complete
   - If validation fails, keep task as `- [ ]` and fix the issues

### 5. **Verify Transformation**
   - Confirm all checkboxes are marked complete `- [x]`
   - Run all validation gates from the PRP
   - Test integration and end-to-end functionality
   - Verify the ending context matches what was achieved

### 6. **Final Validation**
   - [ ] All Low-Level Tasks completed and checked off
   - [ ] All Mid-Level Objectives achieved
   - [ ] High-Level Objective accomplished
   - [ ] All validation commands pass
   - [ ] System works as specified

## Implementation Guidelines

- **Follow the PRP exactly**: Don't deviate from the specified approach
- **Validate continuously**: Run validation after each task
- **Maintain checkboxes**: Keep the PRP file updated with progress
- **Think systematically**: Address dependencies before dependent tasks
- **Document issues**: Note any problems or deviations in the PRP file

## Success Criteria

The execution is complete when:
1. All tasks are marked with `- [x]` checkboxes
2. All validation commands pass successfully
3. The desired state from the PRP is achieved
4. Integration testing confirms functionality

Remember: The PRP file serves as both specification and progress tracker. Keep it updated throughout execution.