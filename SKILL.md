---
name: x-claude-ideas
description: Search X (Twitter) and Reddit for the latest Claude Code posts and ideas. Use when the user wants to check for new Claude ideas, tips, or discussions.
---

# Claude Ideas Scanner

Search X (Twitter) and Reddit for the latest Claude Code posts and ideas, evaluate them for actionable improvements, and offer to implement the good ones.

## Execution Steps

### 1. Get Chrome Tab Context
Use `mcp__claude-in-chrome__tabs_context_mcp` with `createIfEmpty: true` to ensure a tab is available.

### 2. Search X (Twitter)
Navigate to `https://x.com/search?q=claude%20code&src=typed_query&f=live` for latest posts.
- Wait 2-3 seconds for results to load
- Take a screenshot
- Scroll down and capture more posts (2-3 scrolls)

### 3. Search Reddit
Navigate to Reddit and check these subreddits for Claude Code discussions:

**Primary subreddits:**
- `https://www.reddit.com/r/ClaudeAI/new/` - Main Claude community
- `https://www.reddit.com/r/ClaudeAI/search/?q=claude%20code&sort=new` - Claude Code specific

**Also worth checking:**
- `https://www.reddit.com/r/LocalLLaMA/search/?q=claude%20code&sort=new` - Technical discussions
- `https://www.reddit.com/r/ChatGPTCoding/search/?q=claude%20code&sort=new` - Coding workflows

For each subreddit:
- Take a screenshot
- Scroll to see more posts
- Note post titles and upvote counts (indicates quality)

### 4. Analyze Posts for Actionable Ideas
Review each post from both platforms and categorize:

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

**Reddit-specific signals:**
- High upvote counts suggest valuable content
- Comments often contain refined versions of tips
- "Pro tip" or "TIL" posts often have actionable content

### 5. Present Findings
Format the output as:

```
## Claude Ideas Scan Results

### From X (Twitter)

#### Actionable Ideas Found
1. **[Idea Title]** - @handle
   - What: [Brief description]
   - How to implement: [Specific steps]
   - Effort: Low/Medium/High

### From Reddit

#### Actionable Ideas Found
1. **[Idea Title]** - u/username (r/subreddit, X upvotes)
   - What: [Brief description]
   - How to implement: [Specific steps]
   - Effort: Low/Medium/High

### Other Interesting Posts
- [Summary of non-actionable but interesting posts]

### Would you like me to implement any of these?
[List the implementable ideas with numbers for easy selection]
```

### 6. Offer Implementation
After presenting findings, use AskUserQuestion to ask:
- "Would you like me to implement any of these ideas?"
- Provide options for each actionable idea found
- Include "None" and "All applicable" options

### 7. Implement Selected Ideas
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

- `/x-claude-ideas` - Search both X and Reddit for "claude code" posts
- `/x-claude-ideas tips` - Search for "claude code tips"
- `/x-claude-ideas mcp` - Search for "claude code mcp"
- `/x-claude-ideas hooks` - Search for "claude code hooks"

## Prerequisites

- Claude Code with `--chrome` flag
- [Claude in Chrome extension](https://claude.com/chrome) installed
- Logged into X.com in Chrome (for X searches)

## Installation

Copy `SKILL.md` to your Claude Code skills directory:

```bash
# Create skill directory
mkdir -p ~/.claude/skills/x-claude-ideas

# Copy the skill file
cp SKILL.md ~/.claude/skills/x-claude-ideas/
```

Then restart Claude Code to activate the skill.
