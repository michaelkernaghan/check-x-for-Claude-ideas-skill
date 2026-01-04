---
name: x-claude-ideas
description: Search X (Twitter) for the latest Claude Code posts and ideas. Use when the user wants to check for new Claude ideas, tips, or discussions.
---

# Claude Ideas Scanner

Search X (Twitter) for the latest Claude Code posts and ideas, evaluate them for actionable improvements, and offer to implement the good ones.

## Execution Steps

### 1. Get Chrome Tab Context
Use `mcp__claude-in-chrome__tabs_context_mcp` with `createIfEmpty: true` to ensure a tab is available.

### 2. Search X (Twitter)
Navigate to `https://x.com/search?q=claude%20code&src=typed_query&f=live` for latest posts.
- Wait 2-3 seconds for results to load
- Take a screenshot
- Scroll down and capture more posts (2-3 scrolls)

### 3. Analyze Posts for Actionable Ideas
Review posts and categorize:

**Look for these types of actionable ideas:**
- Configuration tips (CLAUDE.md, settings, hooks)
- Workflow improvements (skills, slash commands, MCP servers)
- Prompt techniques or patterns
- New features or flags to try
- Integration ideas (Chrome, IDE, tools)
- Performance tips (context management, token usage)

**Filter out:**
- General praise without specifics
- Questions without answers
- Off-topic or unrelated posts
- Ideas already implemented in our setup

### 4. Present Findings
Format the output as:

```
## Claude Ideas Scan Results

### Actionable Ideas Found
1. **[Idea Title]** - @handle
   - What: [Brief description]
   - How to implement: [Specific steps]
   - Effort: Low/Medium/High

### Other Interesting Posts
- [Summary of non-actionable but interesting posts]

### Would you like me to implement any of these?
[List the implementable ideas with numbers for easy selection]
```

### 5. Offer Implementation
After presenting findings, use AskUserQuestion to ask:
- "Would you like me to implement any of these ideas?"
- Provide options for each actionable idea found
- Include "None" and "All applicable" options

### 6. Implement Selected Ideas
If user selects ideas to implement:
- Create/modify CLAUDE.md rules
- Add new skills
- Update settings
- Configure hooks
- Set up MCP servers
- Whatever is needed for the selected idea

## Example Ideas to Look For

- "I added a rule to CLAUDE.md that..."
- "This hook saves me time..."
- "Try using plan mode for..."
- "MCP server for X is amazing..."
- "Set up a skill that..."
- "The --flag does..."
- "Context window tip:..."
- "Pro tip: Claude Code can..."
- "TIL you can use Claude Code to..."

## Example Usage

- `/x-claude-ideas` - Search X for "claude code" posts
- `/x-claude-ideas tips` - Search for "claude code tips"
- `/x-claude-ideas mcp` - Search for "claude code mcp"
- `/x-claude-ideas hooks` - Search for "claude code hooks"

## Prerequisites

- Claude Code with `--chrome` flag
- [Claude in Chrome extension](https://claude.com/chrome) installed
- Logged into X.com in Chrome
