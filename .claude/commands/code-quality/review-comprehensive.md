# Comprehensive Code Review Command

Execute the automatic final review task as defined in CLAUDE.md. This provides thorough quality assurance for any codebase.

## Usage

```
/code-quality:review-comprehensive
```

## What This Command Does

Executes all components of the automatic final review task:

### 1. Code Quality Review
- Check for unused variables, resources, or modules
- Remove any dead code or commented-out sections that are no longer needed
- Ensure all resources follow naming conventions (max 32 characters, initse prefix)
- Verify all files are under 500 lines limit
- Check line length compliance (max 140 characters)

### 2. Testing & Validation
- Run all existing tests and ensure they pass
- Execute `terraform test` for all modules
- Verify all test assertions are meaningful and comprehensive
- Test complete deployment flow from start to finish

### 3. Security Audit
- Verify all sensitive values are marked as `sensitive = true`
- Check that no secrets or credentials are hardcoded
- Ensure Key Vault access follows principle of least privilege
- Validate that all Azure resources have appropriate tags
- Review network security and access controls

### 4. Documentation Validation
- Ensure README.md is accurate and up-to-date
- Verify all configuration examples work as documented
- Check that all outputs and variables are properly documented
- Update any outdated or incorrect documentation

### 5. Integration Testing
- Test the complete deployment flow from infrastructure to configuration
- Verify all setup scripts work correctly
- Test cleanup scripts functionality
- Ensure error handling is robust throughout

### 6. Bug Fixes & Improvements
- Fix any issues discovered during review
- Implement necessary improvements for stability
- Optimize performance where applicable
- Ensure proper error messages and logging

## When to Use

- After completing all explicit tasks in a PRP
- Before submitting code for review
- When preparing for production deployment
- As part of regular quality assurance cycles

## Output

- Comprehensive TodoWrite breakdown of all review tasks
- Detailed findings and fixes for each component
- Updated documentation and test results
- Summary of improvements made