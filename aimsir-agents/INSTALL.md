# Aimsir agents: install

Contents: 8 subagent files (agents/) and 1 slash command (commands/aimsir-relay.md).

## Option A: paste this prompt into Claude Code on your machine
Unzip the bundle somewhere (for example ~/Downloads/aimsir-agents), open Claude Code, and paste:

---
Install the Aimsir agent bundle at ~/Downloads/aimsir-agents for all projects (user level).

1. List the files in ~/Downloads/aimsir-agents/agents and ~/Downloads/aimsir-agents/commands and show me the list.
2. Read each file and confirm that (a) no agent's tools line includes any QuickBooks tool other than the read-only reporting tools, and (b) only aimsir-budget-analyst and aimsir-grants-financial-manager have any QuickBooks tools at all. Tell me the result before copying anything.
3. Check whether ~/.claude/agents or ~/.claude/commands already contain files with the same names. If so, do not overwrite; show me the conflicts and ask.
4. After I say "ok", copy agents/*.md to ~/.claude/agents/ and commands/aimsir-relay.md to ~/.claude/commands/.
5. Do not edit any file's contents. Do not run anything else.
6. Then tell me to restart Claude Code, and to run /agents and /mcp to confirm the eight agents and the QuickBooks tool names.
---

## Option B: manual
mkdir -p ~/.claude/agents ~/.claude/commands
cp agents/*.md ~/.claude/agents/
cp commands/aimsir-relay.md ~/.claude/commands/
Restart Claude Code.

## Verify
- /agents lists all eight aimsir-* agents.
- /mcp shows the QuickBooks tools. If the tool names in the two finance agents' tools line (for example mcp__Intuit_QuickBooks__...) do not match what /mcp shows on your machine, edit that line to the exact names. Until fixed, those agents will run without QuickBooks.
- First test: /aimsir-relay money

## Notes
- Subagents cannot call other subagents, so the relay is a slash command run by your main session.
- Edit one file to change an agent; keep the saved Claude skills and these files in step manually.
