# Installation Guide

## Quick Install

1. **Copy plugin to your Claude Code plugins directory:**
   ```bash
   cp -r plugins/spec-workflow ~/.claude/plugins/
   ```

2. **Restart Claude Code** (if already running)

3. **Verify installation:**
   ```bash
   # The skill should now be available
   ls ~/.claude/plugins/spec-workflow/skills/spec-workflow/SKILL.md
   ```

## Usage

Once installed, you can use the spec workflow in multiple ways:

### Natural Language (Recommended)
```
use spec workflow to create our user authentication feature
```

### Slash Commands
```
/spec-create notification system
/spec-validate .claude/specs/auth/requirements.md
```

## What Gets Installed

- **1 Skill** (`spec-workflow`) - Automatic workflow detection
- **4 Agents** - Orchestrator and 3 validators
- **2 Commands** - `/spec-create` and `/spec-validate`
- **3 Templates** - Requirements, design, and tasks templates
- **Helper Scripts** - Utility scripts for custom workflows

## Verification

Ask Claude:
```
What Skills are available?
```

You should see "Spec Workflow" listed.

## Next Steps

Try creating your first spec:
```
use spec workflow to create our test feature
```

See [README.md](README.md) for complete documentation.
