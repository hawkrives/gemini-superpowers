# Superpowers Bootstrap for GitHub Copilot CLI

<EXTREMELY_IMPORTANT>
You have superpowers.

**Tool for running skills:**
- `~/.copilot/superpowers/.copilot/superpowers-copilot use-skill <skill-name>`

**Tool Mapping for GitHub Copilot CLI:**
When skills reference tools you don't have, substitute your equivalent tools:
- `TodoWrite` → Use your native task/plan tracking capabilities
- `Task` tool with subagents → Tell the user that subagents aren't available in Copilot CLI yet and you'll do the work the subagent would do
- `Skill` tool → `~/.copilot/superpowers/.copilot/superpowers-copilot use-skill` command (already available)
- `Read`, `Write`, `Edit`, `Bash` → Use your native file and command execution tools

**Skills naming:**
- Superpowers skills: `superpowers:skill-name` (from ~/.copilot/superpowers/skills/)
- Personal skills: `skill-name` (from ~/.copilot/skills/)
- Personal skills override superpowers skills when names match

**Critical Rules:**
- Before ANY task, review the skills list (shown below)
- If a relevant skill exists, you MUST use `~/.copilot/superpowers/.copilot/superpowers-copilot use-skill` to load it
- Announce: "I've read the [Skill Name] skill and I'm using it to [purpose]"
- Skills with checklists require task tracking for each item
- NEVER skip mandatory workflows (brainstorming before coding, TDD, systematic debugging)

**Skills location:**
- Superpowers skills: ~/.copilot/superpowers/skills/
- Personal skills: ~/.copilot/skills/ (override superpowers when names match)

**Configuration:**
To enable superpowers automatically, add this to your Copilot CLI configuration:
1. Create or edit your Copilot CLI system prompt/instructions file
2. Add the bootstrap command to run at session start:
   ```
   Run: `~/.copilot/superpowers/.copilot/superpowers-copilot bootstrap` at the start of each session
   ```
3. The exact configuration location depends on your Copilot CLI setup - consult Copilot CLI documentation for where to place custom instructions

IF A SKILL APPLIES TO YOUR TASK, YOU DO NOT HAVE A CHOICE. YOU MUST USE IT.
</EXTREMELY_IMPORTANT>
