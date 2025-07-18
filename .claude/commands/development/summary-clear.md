---
name: summary-clear
description: Summarize session accomplishments in CLAUDE.md and clear the session
arguments: "Optional context about what was accomplished"
---

additional_context = $ARGUMENTS

# Session Summary and Clear

Please help me wrap up this session by:

1. **Analyze what was accomplished during this session:**
   - Review the conversation history and identify key tasks completed
   - Note any files created, modified, or analyzed
   - Highlight important decisions or discoveries made
   - Include any issues resolved or features implemented

2. **Update CLAUDE.md with a summary:**
   - Add a new entry with today's date and session summary
   - Include the key accomplishments in a clear, concise format
   - Mention any important context or decisions for future reference
   - If additional context was provided: $additional_context

3. **Execute the clear command:**
   - After updating CLAUDE.md, run `/clear` to clear the session

The summary should be professional and helpful for future sessions, focusing on what was actually completed rather than what was discussed.