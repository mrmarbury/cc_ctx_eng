# PRP Final Review Command

Execute the automatic final review task specifically for a completed PRP implementation.

## Usage

```
/PRPs:prp-final-review
```

## What This Command Does

Automatically executes the comprehensive review and cleanup task as defined in CLAUDE.md after all explicit PRP tasks are completed.

### Workflow:
1. **Create TodoWrite breakdown** of all review components
2. **Execute comprehensive review** covering:
   - Code quality review
   - Testing & validation
   - Security audit
   - Documentation validation
   - Integration testing
   - Bug fixes & improvements
3. **Mark review complete** in TodoWrite
4. **Provide summary** of findings and fixes

### Key Features:
- Follows the global review standards from CLAUDE.md
- Ensures consistent quality across all PRP implementations
- Automatic execution without manual task definition
- Comprehensive coverage of all quality aspects

## When to Use

- After completing all explicit tasks in any PRP file
- When all PRP checkboxes are marked as `[x]`
- Before considering a PRP implementation "done"
- As part of automated PRP execution workflows

## Requirements

- All explicit PRP tasks must be completed first
- TodoWrite should show all PRP tasks as completed
- Codebase should be in a stable state for review

## Output

- Detailed TodoWrite tracking of review progress
- Summary of code quality improvements
- Test results and validation outcomes
- Documentation updates and fixes
- Security audit findings and resolutions