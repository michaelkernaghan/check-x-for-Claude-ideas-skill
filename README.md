# X Claude Ideas Scanner

A Claude Code skill that searches X (Twitter) for the latest Claude Code posts, evaluates them for actionable ideas, and offers to implement them.

## What It Does

1. Opens X.com in Chrome (via Claude Code's browser automation)
2. Searches for "claude code" posts (latest)
3. Analyzes posts for actionable tips and ideas
4. Presents findings categorized by type
5. Offers to implement selected ideas directly

## Example Ideas It Looks For

- CLAUDE.md configuration tips
- Workflow improvements (skills, hooks, MCP servers)
- New features or flags to try
- Performance tips (context management)
- Integration ideas

## Prerequisites

- [Claude Code](https://claude.com/claude-code) CLI
- [Claude in Chrome extension](https://claude.com/chrome)
- Run Claude Code with `--chrome` flag: `claude --chrome`
- Be logged into X.com in Chrome

## Installation

```bash
# Clone the repo
git clone https://github.com/michaelkernaghan/check-x-for-Claude-ideas-skill.git

# Create skill directory (if it doesn't exist)
mkdir -p ~/.claude/skills/x-claude-ideas

# Copy the skill file
cp check-x-for-Claude-ideas-skill/SKILL.md ~/.claude/skills/x-claude-ideas/

# Restart Claude Code
```

## Usage

```
/x-claude-ideas              # Search for "claude code" posts
/x-claude-ideas tips         # Search for "claude code tips"
/x-claude-ideas mcp          # Search for "claude code mcp"
/x-claude-ideas hooks        # Search for "claude code hooks"
```

## Output Example

```
## X Claude Ideas Scan Results

### Actionable Ideas Found

1. **Activity Page for Context Costs** - @codewithimanshu
   - What: Use the Activity page to monitor token usage
   - How to implement: Add monitoring rule to CLAUDE.md
   - Effort: Low

### Would you like me to implement any of these?
```

## License

MIT
