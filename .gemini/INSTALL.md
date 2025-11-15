# Superpowers for Gemini CLI - Installation Guide

This guide will help you install the Superpowers skills system for Gemini CLI.

## ⚠️ Security Notice

This installation will:
- Clone the Superpowers repository to `~/.gemini/superpowers`
- Create/modify `~/.gemini/AGENT.md` with bootstrap instructions
- Make the `superpowers-gemini` script executable

**You are downloading and executing code, and modifying your agent's startup configuration.**

If you're comfortable with this, proceed with the installation.

## Quick Install

Run these commands in your terminal:

```bash
# Create .gemini directory if it doesn't exist
mkdir -p ~/.gemini

# Clone superpowers repository
git clone https://github.com/hawkrives/gemini-superpowers.git ~/.gemini/superpowers

# Make script executable (should already be executable)
chmod +x ~/.gemini/superpowers/.gemini/superpowers-gemini

# Create personal skills directory
mkdir -p ~/.gemini/skills

# Add bootstrap to AGENT.md
cat >> ~/.gemini/AGENT.md <<'BOOTSTRAP'

## Superpowers System

You have superpowers. Superpowers teach you new skills and capabilities.

RIGHT NOW run: `~/.gemini/superpowers/.gemini/superpowers-gemini bootstrap` 
and follow the instructions it returns.

BOOTSTRAP
```

## Manual Installation

### 1. Clone the Repository

```bash
mkdir -p ~/.gemini
git clone https://github.com/hawkrives/gemini-superpowers.git ~/.gemini/superpowers
```

### 2. Verify Script is Executable

The script should already be executable, but you can verify:

```bash
chmod +x ~/.gemini/superpowers/.gemini/superpowers-gemini
```

### 3. Create Personal Skills Directory

```bash
mkdir -p ~/.gemini/skills
```

### 4. Add Bootstrap to AGENT.md

Edit or create `~/.gemini/AGENT.md` and add:

```markdown
## Superpowers System

You have superpowers. Superpowers teach you new skills and capabilities.

RIGHT NOW run: `~/.gemini/superpowers/.gemini/superpowers-gemini bootstrap` 
and follow the instructions it returns.
```

## Verification

Test the installation:

```bash
~/.gemini/superpowers/.gemini/superpowers-gemini bootstrap
```

You should see:
- A welcome message
- Tool mapping instructions
- A list of available skills
- Usage instructions

## Usage

Once installed, Gemini CLI will automatically run the bootstrap command on startup.

### Available Commands

```bash
# Show bootstrap and list all skills
~/.gemini/superpowers/.gemini/superpowers-gemini bootstrap

# List all available skills
~/.gemini/superpowers/.gemini/superpowers-gemini list

# Load a specific skill
~/.gemini/superpowers/.gemini/superpowers-gemini use-skill brainstorming

# Search for skills
~/.gemini/superpowers/.gemini/superpowers-gemini search debugging
```

### How Gemini Will Use Skills

When you start a conversation, Gemini will:
1. See the bootstrap instructions
2. Run the bootstrap command
3. Review the list of available skills
4. Load and follow relevant skills before starting work

For example, if you ask Gemini to "help me debug this code", it should:
1. Search for debugging skills
2. Load the `systematic-debugging` skill
3. Follow its 4-phase debugging process

## Creating Your Own Skills

Create personal skills in `~/.gemini/skills/`:

```bash
# Create a new skill
mkdir -p ~/.gemini/skills/my-custom-skill
cat > ~/.gemini/skills/my-custom-skill/SKILL.md <<'EOF'
# My Custom Skill

This skill teaches Gemini how to...

## When to Use This Skill

Use this skill when...

## Process

1. First step...
2. Second step...
3. Final step...
EOF
```

Personal skills automatically override Superpowers skills with the same name.

## Updating

To update Superpowers skills:

```bash
cd ~/.gemini/superpowers
git pull origin main
```

## Available Skills

After installation, you'll have access to:

**Testing Skills:**
- test-driven-development
- condition-based-waiting
- testing-anti-patterns

**Debugging Skills:**
- systematic-debugging
- root-cause-tracing
- verification-before-completion
- defense-in-depth

**Collaboration Skills:**
- brainstorming
- writing-plans
- executing-plans
- dispatching-parallel-agents
- requesting-code-review
- receiving-code-review
- using-git-worktrees
- finishing-a-development-branch
- subagent-driven-development

**Meta Skills:**
- writing-skills
- sharing-skills
- testing-skills-with-subagents
- using-superpowers

## Troubleshooting

### Script not found

Make sure the script path is correct:

```bash
ls -la ~/.gemini/superpowers/.gemini/superpowers-gemini
```

### No skills listed

Verify the superpowers repository was cloned:

```bash
ls ~/.gemini/superpowers/skills/
```

### AGENT.md not loading

Check that Gemini CLI supports the `~/.gemini/AGENT.md` file. Some versions may use different configuration methods.

## Philosophy

Superpowers teaches systematic approaches to common engineering tasks:

- **Test-Driven Development** - Write tests first, always
- **Systematic over ad-hoc** - Process over guessing
- **Complexity reduction** - Simplicity as primary goal
- **Evidence over claims** - Verify before declaring success
- **Domain over implementation** - Work at problem level, not solution level

## Support

- **Original Superpowers**: https://github.com/obra/superpowers
- **Gemini CLI Port**: https://github.com/hawkrives/gemini-superpowers
- **Issues**: Open an issue on the gemini-superpowers repository

## License

This port maintains the same MIT license as the original Superpowers project.
