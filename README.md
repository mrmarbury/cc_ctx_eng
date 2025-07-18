# Claude Code Context Engineering Template

A comprehensive template repository for enhancing projects with advanced Claude Code capabilities through Context Engineering patterns, security safeguards, and structured development workflows.

## What is Context Engineering?

Context Engineering is the practice of designing and implementing systems that provide AI assistants with rich, structured context about your project, enabling more accurate, consistent, and effective assistance. This repository provides a complete framework for:

- **Structured Documentation**: Standardized formats for PRDs, planning documents, and task breakdowns
- **Security-First Approach**: Automated safeguards against dangerous operations
- **Workflow Optimization**: Streamlined development processes with built-in quality gates
- **Project Intelligence**: Self-documenting systems that Claude can understand and work with effectively

## Quick Start

### Option 1: Use as Template (Recommended for New Projects)

```bash
# Create new project from template
git clone https://github.com/mrmarbury/cc_ctx_eng.git my-new-project
cd my-new-project
rm -rf .git
git init
git add .
git commit -m "Initial commit from Context Engineering template"

# Install dependencies
brew install uv python@3.11

# Test hook functionality
uv run .claude/hooks/pre_tool_use.py < /dev/null
```

### Option 2: Copy to Existing Project

```bash
# Copy .claude directory to existing project
cp -r /path/to/cc_ctx_eng/.claude /path/to/your/existing/project/

# Install dependencies
cd /path/to/your/existing/project
brew install uv python@3.11

# Test setup
uv run .claude/hooks/pre_tool_use.py < /dev/null
```

### Option 3: Git Submodule (Advanced)

```bash
# Add as submodule
git submodule add https://github.com/your-org/cc_ctx_eng.git .claude-template
cp -r .claude-template/.claude .
```

## Repository Structure

```
.claude/
├── commands/              # Slash commands organized by category
│   ├── development/       # Core development workflows
│   ├── PRPs/             # Problem Resolution Patterns
│   ├── code-quality/     # Code review and refactoring
│   ├── git-operations/   # Git workflow automation
│   ├── mastery/          # Advanced Claude workflows
│   ├── rapid-development/ # Fast development patterns
│   ├── typescript/       # TypeScript-specific commands
│   └── Elixir/           # Elixir/Phoenix-specific commands
├── hooks/                # Python automation hooks
│   ├── pre_tool_use.py   # Security and logging before tool execution
│   ├── post_tool_use.py  # Logging after tool execution
│   ├── notification.py   # TTS notifications for user input
│   ├── stop.py          # Session completion with TTS
│   └── subagent_stop.py # Subagent completion notifications
└── settings.json         # Claude Code configuration
```

## Core Features

### 🔒 Security Safeguards

- **Dangerous Command Prevention**: Blocks `rm -rf` and similar destructive operations
- **Environment Protection**: Prevents access to `.env` files (allows `.env.sample`)
- **Graceful Failure**: All hooks fail silently to avoid disrupting workflow
- **Comprehensive Logging**: Full audit trail of all tool usage

### 🚀 Development Workflows

#### 4-Step Planning Process

1. **`/create-prd`** - Product Requirements Document
2. **`/create-claude-md`** - Project-specific Claude documentation
3. **`/create-planning`** - Technical architecture and implementation strategy
4. **`/create-tasks`** - Milestone-based task breakdown

#### Standalone Specification Workflow

- **`/prp-spec-create`** - Create standalone specifications with checkboxes
- **`/prp-spec-execute`** - Execute specifications with progress tracking

### 🔧 Language-Specific Commands

#### Elixir/Phoenix Development

- **`/Elixir:create-spec`** - Elixir standalone specifications with OTP patterns
- **`/Elixir:create-prd`** - Elixir PRDs with supervision tree architecture
- **`/Elixir:create-claude-md`** - Elixir development guide with GenServer patterns
- **`/Elixir:create-planning`** - OTP architecture and Phoenix framework planning
- **`/Elixir:create-tasks`** - Elixir task breakdown with fault tolerance focus

### 🎯 Quality Assurance

- **Code Review Standards**: Comprehensive review checklists
- **Testing Requirements**: 80%+ coverage targets, validation gates
- **Documentation Standards**: Mandatory review and documentation for all tasks
- **Task Management**: Checkbox-based progress tracking

## Commands Reference

### Core Development Commands

#### `/Elixir:create-prd "Project Description"`

Creates comprehensive Elixir Product Requirements Document with OTP architecture, Phoenix patterns, and fault tolerance design.

**Example:**

```bash
/Elixir:create-prd "Phoenix LiveView dashboard with real-time GenServer analytics"
```

**Output:** `PRD.md` with Elixir-specific project specification including supervision trees

#### `/Elixir:create-claude-md "Tech Stack"`

Generates Elixir project-specific CLAUDE.md with OTP development guidelines, GenServer patterns, and Phoenix best practices.

**Example:**

```bash
/Elixir:create-claude-md "Phoenix LiveView with OTP supervision tree"
```

**Output:** `CLAUDE.md` with Elixir/Phoenix-specific guidance (backs up existing file)

#### `/Elixir:create-planning "Focus Area"`

Creates detailed PLANNING.md with OTP architecture, supervision tree design, and Phoenix framework implementation strategy.

**Example:**

```bash
/Elixir:create-planning "OTP supervision tree with GenServer patterns"
```

**Output:** `PLANNING.md` with comprehensive Elixir technical planning

#### `/Elixir:create-tasks "Milestone Focus"`

Generates milestone-based TASKS.md with Elixir-specific task breakdown focusing on OTP patterns and Phoenix development.

**Example:**

```bash
/Elixir:create-tasks "OTP foundation"
```

**Output:** `TASKS.md` with GenServer, supervision, and Phoenix task breakdown

### Standalone Specification Commands

#### `/Elixir:create-spec "Specification"`

Creates standalone Elixir specification document with checkbox-based task tracking and OTP patterns.

**Example:**

```bash
/Elixir:create-spec "Implement distributed task queue with GenServer workers and supervision"
```

**Output:** `PRPs/elixir_spec_distributed_queue.md`

#### `/prp-spec-create "Specification"`

Creates standalone specification document with checkbox-based task tracking (language-agnostic).

**Example:**

```bash
/prp-spec-create "Migrate legacy authentication system to OAuth 2.0"
```

**Output:** `PRPs/prp_spec_oauth_migration.md`

#### `/prp-spec-execute "PRP File"`

Executes standalone specification with progress tracking.

**Example:**

```bash
/prp-spec-execute "PRPs/prp_spec_oauth_migration.md"
```

### Git and Development Commands

#### `/smart-commit "Additional Instructions"`

Analyzes changes and creates intelligent git commits with conventional commit format.

**Example:**

```bash
/smart-commit "focus on authentication changes"
```

#### `/create-pr`

Creates pull request with comprehensive description and testing checklist.

#### `/summary-clear "Context"`

Summarizes session accomplishments in CLAUDE.md and clears the session.

**Example:**

```bash
/summary-clear "implemented user authentication system"
```

### Code Quality Commands

#### `/review-comprehensive`

Performs thorough code review with architecture, security, and performance analysis.

#### `/review-staged-unstaged`

Reviews both staged and unstaged changes with git-aware analysis.

#### `/refactor-simple`

Guides through simple refactoring with quality improvements.

### Mastery Commands

#### `/prime`

Initializes session with project context by analyzing codebase structure and README.

#### `/sentient`

Advanced AI behavior patterns for complex problem-solving.

#### `/all_tools`

Demonstrates comprehensive tool usage and capabilities.

## Hook System

### Security and Logging Hooks

#### Pre-Tool Use Hook

- **File**: `.claude/hooks/pre_tool_use.py`
- **Purpose**: Security validation and pre-execution logging
- **Features**:
  - Blocks dangerous `rm -rf` commands
  - Prevents `.env` file access
  - Logs all tool usage

#### Post-Tool Use Hook

- **File**: `.claude/hooks/post_tool_use.py`
- **Purpose**: Post-execution logging and audit trail
- **Features**: Records tool results and outcomes

### Notification Hooks

#### Notification Hook

- **File**: `.claude/hooks/notification.py`
- **Purpose**: TTS notifications when Claude needs user input
- **Features**:
  - Multiple TTS service support (pyttsx3, ElevenLabs, OpenAI)
  - Personalized notifications with engineer name
  - Configurable via `--notify` flag

#### Stop Hook

- **File**: `.claude/hooks/stop.py`
- **Purpose**: Session completion announcements
- **Features**:
  - TTS completion messages
  - Transcript copying with `--chat` flag
  - LLM-generated completion messages

#### Subagent Stop Hook

- **File**: `.claude/hooks/subagent_stop.py`
- **Purpose**: Subagent completion notifications
- **Features**: Dedicated TTS for subagent work completion

### Environment Variables

```bash
# Optional TTS configuration
export OPENAI_API_KEY="your-key"           # For OpenAI TTS
export ELEVENLABS_API_KEY="your-key"       # For ElevenLabs TTS
export ANTHROPIC_API_KEY="your-key"        # For completion messages
export ENGINEER_NAME="Your Name"           # For personalized notifications
```

## Configuration

### Settings.json Structure

```json
{
  "shell": "/bin/zsh",
  "permissions": {
    "allow": [
      "Zsh(mkdir:*)",
      "Zsh(uv:*)",
      "Write",
      "Edit",
      "Zsh(npm:*)",
      "Zsh(test:*)"
    ],
    "deny": []
  },
  "hooks": {
    "PreToolUse": [
      {
        "matcher": "",
        "hooks": [
          {
            "type": "command",
            "command": "uv run .claude/hooks/pre_tool_use.py"
          }
        ]
      }
    ],
    "PostToolUse": [
      {
        "matcher": "",
        "hooks": [
          {
            "type": "command",
            "command": "uv run .claude/hooks/post_tool_use.py"
          }
        ]
      }
    ],
    "Notification": [
      {
        "matcher": "",
        "hooks": [
          {
            "type": "command",
            "command": "uv run .claude/hooks/notification.py --notify"
          }
        ]
      }
    ],
    "Stop": [
      {
        "matcher": "",
        "hooks": [
          {
            "type": "command",
            "command": "uv run .claude/hooks/stop.py --chat"
          }
        ]
      }
    ],
    "SubagentStop": [
      {
        "matcher": "",
        "hooks": [
          {
            "type": "command",
            "command": "uv run .claude/hooks/subagent_stop.py"
          }
        ]
      }
    ]
  }
}
```

## Usage Examples

### Example 1: Starting a New Phoenix LiveView Application

```bash
# Step 1: Create comprehensive Elixir PRD
/Elixir:create-prd "Real-time chat application with Phoenix LiveView and OTP supervision"

# Step 2: Generate Elixir development guide
/Elixir:create-claude-md "Phoenix LiveView with GenServer state management"

# Step 3: Create OTP architecture planning
/Elixir:create-planning "OTP supervision tree with real-time features"

# Step 4: Break down into Elixir tasks
/Elixir:create-tasks "OTP foundation"

# Step 5: Start development with context
/prime
```

### Example 2: Adding Feature to Existing Elixir Project

```bash
# Initialize with context
/prime

# Create standalone Elixir specification
/Elixir:create-spec "Add distributed caching with ETS and GenServer pooling"

# Execute specification with OTP patterns
/prp-spec-execute "PRPs/elixir_spec_distributed_cache.md"
```

### Example 3: Building Phoenix API with Real-time Features

```bash
# Create Elixir-specific PRD for API
/Elixir:create-prd "Phoenix API with WebSocket channels and PubSub for IoT device management"

# Generate Elixir development guide
/Elixir:create-claude-md "Phoenix API with Channels and OTP workers"

# Create supervision tree architecture
/Elixir:create-planning "distributed system with fault tolerance"

# Break down into GenServer and Channel tasks
/Elixir:create-tasks "Phoenix API with real-time features"
```

## Best Practices

### Context Engineering Principles

1. **Start with Context**: Always begin sessions with `/prime` to load project context
2. **Document Everything**: Use the 4-step planning process for comprehensive documentation
3. **Iterate Intelligently**: Use specification workflows for focused improvements
4. **Maintain Quality**: Leverage built-in review and testing standards

### Development Workflow

1. **Session Initialization**: `/prime` to understand project structure
2. **Task Planning**: Use appropriate planning commands for your project type
3. **Implementation**: Follow task breakdowns with checkbox tracking
4. **Quality Assurance**: Use review commands before commits
5. **Session Completion**: `/summary-clear` to document progress

### Security Guidelines

- Always use `.env.sample` for template environment files
- Review hook logs regularly for security insights
- Test dangerous operations in safe environments first
- Keep hooks updated and monitor for security patches

## Troubleshooting

### Common Issues

#### Hook Failures

```bash
# Check logs for details
ls -la logs/

# Verify uv installation
uv --version

# Test hook manually
uv run .claude/hooks/pre_tool_use.py < /dev/null
```

#### Permission Issues

```bash
# Check file permissions
ls -la .claude/hooks/

# Fix permissions if needed
chmod +x .claude/hooks/*.py
```

#### TTS Issues

```bash
# Check environment variables
echo $OPENAI_API_KEY
echo $ELEVENLABS_API_KEY

# Test TTS manually
uv run .claude/hooks/notification.py --notify
```

### Getting Help

- **Documentation**: Check `CLAUDE.md` in your project for project-specific guidance
- **Command Help**: Use `/help` for Claude Code assistance
- **Issues**: Report problems at https://github.com/anthropics/claude-code/issues

## Advanced Usage

### Custom Commands

Create custom commands by adding `.md` files to `.claude/commands/`:

```markdown
---
name: my-custom-command
description: My custom development workflow
arguments: "Project context"
---

# My Custom Command

## Context: $ARGUMENTS

[Command implementation here]
```

### Hook Customization

Modify hooks in `.claude/hooks/` to customize behavior:

```python
# Example: Custom validation in pre_tool_use.py
def custom_validation(tool_name, tool_input):
    # Add your custom logic here
    return True
```

### Environment-Specific Configuration

Create environment-specific settings:

```bash
# Development
cp .claude/settings.json .claude/settings.dev.json

# Production
cp .claude/settings.json .claude/settings.prod.json
```

## Contributing

### Adding New Commands

1. Create command file in appropriate category directory
2. Follow existing command structure and conventions
3. Include comprehensive examples and validation
4. Test thoroughly before committing

### Improving Hooks

1. Follow Python best practices
2. Maintain graceful failure patterns
3. Add comprehensive logging
4. Test with various scenarios

### Documentation Updates

1. Update README.md for new features
2. Maintain CLAUDE.md template accuracy
3. Include practical examples
4. Keep troubleshooting section current

## License

This template is provided as-is for enhancing development workflows with Claude Code. Modify and adapt as needed for your projects.

---

**Happy Context Engineering!** 🚀

This template provides the foundation for building intelligent, self-documenting projects that work seamlessly with Claude Code. Start with the basic workflows and gradually adopt advanced patterns as your team becomes comfortable with Context Engineering principles.

This repo is an amalgamation of the following repos and ideas:

- https://github.com/shizonic/claude-code-guide
- https://github.com/shizonic/PRPs-agentic-eng
- https://github.com/disler/claude-code-hooks-mastery
- https://www.youtube.com/watch?v=OZej8sdVCP0
- https://www.youtube.com/watch?v=QgA55EnmUp4

