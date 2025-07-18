---
name: commit
description: Analyze changes and create a smart git commit
arguments: "Additional instructions for the commit"
---

additional instructions = $ARGUMENTS

type = "feat", "fix", "docs", "style", "refactor", "perf", "test", "chore"

# Smart Git CommitPRPs/ai_docs

Please help me create a git commit by:

1. First, check the current git status and analyze what changed:

```bash
git status
git diff --staged
```

2. If no files are staged, show me the changes and help me decide what to stage:

```bash
git diff
git status -s
```

3. Based on the changes, suggest:

- The appropriate commit type (feat/fix/docs/style/refactor/perf/test/chore)
- A concise, descriptive commit message following conventional commits
- If the changes are complex, suggest breaking into multiple commits

**CRITICAL**: Never include references to Claude Code, AI assistance, or automated generation in commit messages.

4. The commit format should be:

```
<type>(<scope>): <subject>

<body>

<footer>
```

**Example:**
```
feat(auth): implement JWT authentication system

- Add JWT token generation and validation
- Implement secure password hashing with bcrypt
- Create authentication middleware for protected routes
- Add user session management with Redis

Closes #156
```

**Types:** feat, fix, docs, style, refactor, test, chore

5. After showing me the suggested commit message, ask if I want to:

- Use it as-is
- Modify it
- Add more details to the body
- Stage different files

6. Once approved, create the commit and show me the result.

7. Finally, ask if I want to push or create a PR.
