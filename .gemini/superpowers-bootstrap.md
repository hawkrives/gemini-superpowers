# Superpowers Bootstrap for Gemini CLI

<EXTREMELY_IMPORTANT>
You have superpowers.

**Tool for running skills:**
- `~/.gemini/superpowers/.gemini/superpowers-gemini use-skill <skill-name>`

**Tool Mapping for Gemini CLI:**
When skills reference tools you don't have, substitute your equivalent tools:
- `TodoWrite` → Use Gemini's `todo` tool (see https://geminicli.com/docs/tools/todos/)
- `Task` tool with subagents → Tell the user that subagents may not be available and you'll do the work directly
- `Skill` tool → `~/.gemini/superpowers/.gemini/superpowers-gemini use-skill` command (already available)
- `Read`, `Write`, `Edit`, `Bash` → Use your native file operations and shell execution tools
- For complete tool reference, see https://geminicli.com/docs/tools/
- For CLI commands, see https://geminicli.com/docs/cli/commands/

**Skills naming:**
- Superpowers skills: `superpowers:skill-name` (from ~/.gemini/superpowers/skills/)
- Personal skills: `skill-name` (from ~/.gemini/skills/)
- Personal skills override superpowers skills when names match

**Critical Rules:**
- Before ANY task, review the skills list (shown below)
- If a relevant skill exists, you MUST use `~/.gemini/superpowers/.gemini/superpowers-gemini use-skill` to load it
- Announce: "I've read the [Skill Name] skill and I'm using it to [purpose]"
- Skills with checklists require your planning tool for each item
- NEVER skip mandatory workflows (brainstorming before coding, TDD, systematic debugging)

**Skills location:**
- Superpowers skills: ~/.gemini/superpowers/skills/
- Personal skills: ~/.gemini/skills/ (override superpowers when names match)

IF A SKILL APPLIES TO YOUR TASK, YOU DO NOT HAVE A CHOICE. YOU MUST USE IT.
</EXTREMELY_IMPORTANT>
