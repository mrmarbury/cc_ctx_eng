# Claude Code Context Engineering Template

This repository contains a comprehensive Claude Code configuration template designed for Context Engineering purposes. It serves as a foundation for enhancing new and existing projects with advanced Claude Code capabilities.

## Project Purpose

This is a **template repository** that provides:
- Advanced Claude Code hooks for security, logging, and notifications
- Comprehensive command library organized by categories
- Security safeguards and best practices
- Extensible configuration for various project types

## Repository Structure

```
.claude/
├── commands/           # Organized slash commands
│   ├── PRPs/          # Problem Resolution Patterns
│   ├── code-quality/  # Code review and refactoring
│   ├── development/   # Git operations and development workflows
│   ├── git-operations/# Git conflict resolution
│   ├── mastery/       # Advanced Claude Code workflows
│   ├── rapid-development/ # Fast development patterns
│   └── typescript/    # TypeScript-specific commands
├── hooks/             # Python-based hooks for automation
│   ├── pre_tool_use.py    # Security and logging before tool execution
│   ├── post_tool_use.py   # Logging after tool execution
│   ├── notification.py    # TTS notifications for user input needed
│   ├── stop.py           # Session completion with TTS
│   └── subagent_stop.py  # Subagent completion notifications
└── settings.json      # Claude Code configuration
```

## Configuration Overview

### Settings (.claude/settings.json)

The configuration includes:
- **Shell**: Zsh with comprehensive permissions
- **Security**: Protections against dangerous operations
- **Hooks**: Automated logging, security, and notifications
- **Permissions**: Granular tool access control

### Hook System

The hook system provides five key lifecycle events:

1. **PreToolUse**: Security validation and pre-execution logging
   - Blocks dangerous `rm -rf` commands
   - Prevents access to `.env` files (allows `.env.sample`)
   - Logs all tool usage to `logs/pre_tool_use.json`

2. **PostToolUse**: Post-execution logging
   - Records tool results in `logs/post_tool_use.json`

3. **Notification**: User input notifications
   - TTS announcements when Claude needs input
   - Supports multiple TTS services (pyttsx3, ElevenLabs, OpenAI)
   - Uses `--notify` flag for activation

4. **Stop**: Session completion
   - Announces completion via TTS
   - Optional transcript copying with `--chat` flag
   - Saves session data to `logs/stop.json`

5. **SubagentStop**: Subagent completion notifications
   - Dedicated TTS for subagent completions
   - Logs subagent activity

### Security Features

- **Command Filtering**: Blocks dangerous `rm -rf` patterns
- **Environment Protection**: Prevents `.env` file access
- **Graceful Failures**: All hooks fail silently to avoid disruption
- **Comprehensive Logging**: Full audit trail of tool usage

## Command Categories

### PRPs (Problem Resolution Patterns)
Advanced patterns for complex feature implementation:
- `prp-base-create.md` - Comprehensive feature research and implementation
- `prp-spec-create.md` - Specification generation
- Task-based execution patterns

### Development Workflows
- `smart-commit.md` - Intelligent git commits
- `create-pr.md` - Pull request automation
- `debug-RCA.md` - Root cause analysis
- `summary-clear.md` - Session summarization and cleanup

### Code Quality
- `review-comprehensive.md` - Thorough code reviews
- `refactor-simple.md` - Refactoring patterns
- `review-staged-unstaged.md` - Git-aware reviews

### Mastery Commands
- `prime.md` - Session initialization with context loading
- `sentient.md` - Advanced AI behavior patterns
- `all_tools.md` - Comprehensive tool demonstrations

## Setup Instructions

### 1. Copy Template to Your Project

```bash
# Clone or copy the .claude directory to your project
cp -r /path/to/cc_ctx_eng/.claude /path/to/your/project/

# Or use as git submodule
git submodule add https://github.com/your-org/cc_ctx_eng.git .claude-template
cp -r .claude-template/.claude .
```

### 2. Install Dependencies

The hooks require Python with `uv` for script execution:

```bash
# Install uv (choose one method)
# Option 1: Using Homebrew (recommended on macOS)
brew install uv

# Option 2: Using official installer
curl -LsSf https://astral.sh/uv/install.sh | sh

# Ensure Python is available (if needed)
# macOS/Linux with Homebrew
brew install python@3.11

# Test hook functionality
uv run .claude/hooks/pre_tool_use.py < /dev/null
```

### 3. Configure Environment (Optional)

For TTS notifications, set up API keys:

```bash
# In your .env or environment
export OPENAI_API_KEY="your-key"           # For OpenAI TTS
export ELEVENLABS_API_KEY="your-key"       # For ElevenLabs TTS
export ANTHROPIC_API_KEY="your-key"        # For completion messages
export ENGINEER_NAME="Your Name"           # For personalized notifications
```

### 4. Customize for Your Project

1. **Update settings.json**: Adjust permissions for your project's needs
2. **Modify hooks**: Customize security rules and logging behavior
3. **Add project-specific commands**: Create commands in appropriate categories
4. **Update validation gates**: Ensure PRP validation commands match your project

## Using Commands

All commands are accessible via slash syntax:

```bash
# Initialize session with project context
/prime

# Create a comprehensive implementation plan
/prp-base-create "user authentication system"

# Smart git commit workflow
/commit "implement user login"

# Comprehensive code review
/review-comprehensive

# Session summary and cleanup
/summary-clear
```

## Best Practices

### Security
- Always use `.env.sample` for template environment files
- Review hook logs regularly for security insights
- Customize dangerous command patterns for your environment

### Development Workflow
1. Start sessions with `/prime` for context loading
2. Use PRP patterns for complex features
3. Leverage code quality commands before commits
4. End sessions with `/summary-clear` for documentation

### Command Development
- Follow existing command structure (frontmatter + markdown)
- Include validation gates that Claude can execute
- Provide comprehensive context in PRPs
- Test commands before adding to production

## Advanced Features

### Parallel Agent Spawning
Many commands support spawning multiple subagents for parallel research and implementation.

### Validation Gates
Commands include executable validation that Claude can run:
- Linting and type checking
- Test execution
- Build verification
- Custom project validations

### Context Engineering
- Rich context passing between agents
- Documentation integration
- Pattern recognition and reuse

## Troubleshooting

### Hook Failures
- Check `logs/` directory for error details
- Ensure `uv` is installed and accessible
- Verify Python script permissions

### TTS Issues
- Ensure API keys are properly set
- Check TTS script availability in `hooks/utils/tts/`
- Verify network connectivity for cloud TTS services

### Command Issues
- Verify command syntax in frontmatter
- Check file permissions
- Ensure required tools are available in the project

## Contributing

When extending this template:
1. Follow existing patterns and structure
2. Document new commands thoroughly
3. Test hooks with various scenarios
4. Update this CLAUDE.md with new features

## Project Context for Claude

**Repository Type**: Claude Code Configuration Template
**Primary Purpose**: Context Engineering and Advanced AI Workflows
**Key Technologies**: Python hooks, Zsh automation, Markdown commands
**Security Level**: High (production-ready with comprehensive safeguards)

**Working with this repo**:
- Focus on configuration and template enhancement
- Maintain security best practices
- Ensure broad compatibility across project types
- Prioritize documentation and ease of adoption

**Development Commands to Run**:
- No specific build process (configuration-based)
- Test hooks: `uv run .claude/hooks/pre_tool_use.py < /dev/null`
- Validate commands: Check markdown syntax and frontmatter

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
feat(commands): add Elixir-specific development workflow

- Implement Elixir standalone specifications with OTP patterns
- Add GenServer and supervision tree task breakdown
- Update command structure for Phoenix framework
- Include fault tolerance patterns in planning

Closes #234
```

### Branch Strategy
- `main`: Production-ready template
- `feature/*`: New features or enhancements
- `fix/*`: Bug fixes
- `docs/*`: Documentation updates

### Commit Process
1. **Review Changes**: Use `git status` and `git diff` to understand what changed
2. **Stage Selectively**: Stage related changes together
3. **Write Clear Messages**: Focus on what and why, not how
4. **Test Before Commit**: Ensure hooks and commands work
5. **Keep Commits Atomic**: One logical change per commit

This repository serves as the foundation for context engineering across multiple projects. All changes should maintain backward compatibility and enhance the template's utility.