# Installing Superpowers for GitHub Copilot CLI

Quick setup to enable superpowers skills in GitHub Copilot CLI.

## Quick Install

Run these commands to install superpowers:

```bash
# Clone superpowers repository
git clone https://github.com/hawkrives/gemini-superpowers.git ~/.copilot/superpowers

# Create personal skills directory
mkdir -p ~/.copilot/skills
```

## Configuration

### Option 1: Manual Bootstrap (Recommended for Testing)

Before starting work on a task, run the bootstrap command:

```bash
~/.copilot/superpowers/.copilot/superpowers-copilot bootstrap
```

This will:
- Show available skills
- Load the `using-superpowers` skill
- Check for updates
- Display usage instructions

### Option 2: Automatic Bootstrap (If Supported)

If your Copilot CLI setup supports custom configuration or system prompts:

1. Locate your Copilot CLI configuration directory or system prompt file
2. Add an instruction to run the bootstrap at session start:
   ```
   At the start of each session, run: ~/.copilot/superpowers/.copilot/superpowers-copilot bootstrap
   ```

**Note:** The exact configuration method depends on your Copilot CLI version and setup. Consult the official Copilot CLI documentation for custom instructions support.

## Verification

Test the installation by running:

```bash
~/.copilot/superpowers/.copilot/superpowers-copilot help
```

You should see the help output with available commands.

Test skill loading:

```bash
~/.copilot/superpowers/.copilot/superpowers-copilot list
```

This should display all available skills.

## Usage Examples

### Loading a Skill

Load the brainstorming skill before design work:

```bash
~/.copilot/superpowers/.copilot/superpowers-copilot use-skill superpowers:brainstorming
```

### Searching for Skills

Find skills related to testing:

```bash
~/.copilot/superpowers/.copilot/superpowers-copilot search testing
```

### Listing All Skills

See all available skills:

```bash
~/.copilot/superpowers/.copilot/superpowers-copilot list
```

## Creating Personal Skills

Create your own skills in `~/.copilot/skills/`:

1. Create a directory for your skill:
   ```bash
   mkdir -p ~/.copilot/skills/my-custom-skill
   ```

2. Create a `SKILL.md` file with frontmatter:
   ```markdown
   ---
   name: My Custom Skill
   description: A brief description of what this skill does
   when_to_use: When you need to accomplish X
   ---
   
   # Your skill content here
   
   Instructions and guidance for using this skill...
   ```

3. Use your skill:
   ```bash
   ~/.copilot/superpowers/.copilot/superpowers-copilot use-skill my-custom-skill
   ```

Personal skills override superpowers skills with the same name.

## Updating Superpowers

To update to the latest version:

```bash
cd ~/.copilot/superpowers
git pull
```

The bootstrap command will notify you when updates are available.

## Troubleshooting

### Command not found

Make sure the script is executable:

```bash
chmod +x ~/.copilot/superpowers/.copilot/superpowers-copilot
```

### Skills not found

Verify the directories exist:

```bash
ls -la ~/.copilot/superpowers/skills/
ls -la ~/.copilot/skills/
```

If the superpowers skills directory is empty, you may need to re-clone:

```bash
rm -rf ~/.copilot/superpowers
git clone https://github.com/hawkrives/gemini-superpowers.git ~/.copilot/superpowers
```

### Git fetch timeout

If you see timeout errors during bootstrap, this is normal if you're offline or have slow connectivity. The bootstrap will continue without checking for updates.

### Skills not loading in Copilot CLI

Currently, GitHub Copilot CLI may not have native support for custom instruction files or automatic bootstrap. In this case:

1. Run the bootstrap manually before each session
2. Copy the output and provide it as context to Copilot CLI
3. Check for Copilot CLI updates that may add configuration support

## Directory Structure

```
~/.copilot/
├── superpowers/          # Cloned repository
│   ├── .copilot/
│   │   ├── superpowers-copilot  # Main script
│   │   ├── superpowers-bootstrap.md
│   │   └── INSTALL.md (this file)
│   └── skills/           # Pre-built superpowers skills
│       ├── brainstorming/
│       ├── test-driven-development/
│       ├── systematic-debugging/
│       └── ...
└── skills/               # Your personal skills
    └── my-custom-skill/
        └── SKILL.md
```

## Additional Resources

- **Project Homepage**: https://github.com/hawkrives/gemini-superpowers
- **Blog Post**: https://blog.fsck.com/2025/10/09/superpowers/
- **Skills Documentation**: See individual SKILL.md files in `~/.copilot/superpowers/skills/`

## Support

For issues or questions:
- Open an issue: https://github.com/hawkrives/gemini-superpowers/issues
- Check existing skills for examples
- Review the `writing-skills` skill for creating new skills
