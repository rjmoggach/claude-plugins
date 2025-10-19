# Spec Workflow Plugin

Complete spec-driven development workflow for creating product feature specifications with automated validation and orchestration.

## Overview

The Spec Workflow plugin provides a systematic approach to creating high-quality product specifications through an agent-orchestrated workflow. It generates requirements, design, and task breakdown documents following standardized templates, with built-in validation at each stage.

## Features

- **Automated Orchestration**: Complete workflow from feature idea to implementation-ready tasks
- **Template-Driven**: Consistent specification structure across all features
- **Multi-Stage Validation**: Dedicated validators for requirements, design, and tasks
- **Code Reuse Analysis**: Identifies existing code to leverage in new features
- **Iterative Refinement**: Validation feedback loop ensures quality
- **Implementation-Ready Output**: Detailed task breakdowns with prompts for each step

## Components

### Agents

#### 1. spec-orchestrator
Coordinates the entire workflow:
- Creates directory structure
- Generates requirements, design, and tasks documents
- Invokes validators at each stage
- Manages iteration cycles
- Provides completion summary

#### 2. spec-requirements-validator
Validates requirements documents for:
- Template structure compliance
- Product vision alignment
- User story quality
- Acceptance criteria completeness
- Non-functional requirements
- Clarity and testability

#### 3. spec-design-validator
Validates design documents for:
- Template structure compliance
- Requirements coverage
- Architecture quality
- Technical standards compliance
- Code reuse opportunities
- Documentation completeness

#### 4. spec-tasks-validator
Validates task breakdowns for:
- Template structure compliance
- Requirements and design alignment
- Code reuse validation
- Task sequencing and dependencies
- Implementation prompt quality
- Testing coverage

### Slash Commands

#### `/spec-create`
Create a complete product feature specification

**Usage:**
```
/spec-create user authentication system
```

#### `/spec-validate`
Validate an existing specification document

**Usage:**
```
/spec-validate .claude/specs/auth/requirements.md
```

### Skills

#### spec-workflow
Automatic detection and execution of spec workflow

**Trigger Patterns:**
- "use spec workflow to create [feature]"
- "create spec for [feature]"
- "generate specification for [feature]"

**Example:**
```
use spec workflow to create our payment processing feature
```

### Templates

#### requirements-template.md
Standard structure for requirements documents:
- Introduction and value proposition
- Product vision alignment
- User stories with acceptance criteria
- Non-functional requirements

#### design-template.md
Standard structure for design documents:
- Overview and architecture
- Technical standards alignment
- Code reuse analysis
- Components and interfaces
- Data models
- Error handling
- Testing strategy

#### tasks-template.md
Standard structure for task breakdowns:
- Numbered, actionable tasks
- File paths for each task
- Leverage references (existing code to reuse)
- Requirements mapping
- Detailed implementation prompts

### Scripts

Helper scripts are available in the skill directory for any custom workflows you develop.

## Installation

1. **Copy plugin to Claude Code plugins directory:**
   ```bash
   cp -r plugins/spec-workflow ~/.claude/plugins/
   ```

2. **Verify installation:**
   ```bash
   ls ~/.claude/plugins/spec-workflow
   ```

The skill will be automatically discovered by Claude Code.

## Usage

### Creating a New Specification

**Option 1: Natural language (recommended)**
```
use spec workflow to create our notification system
```

**Option 2: Slash command**
```
/spec-create notification system
```

**What happens:**
1. Orchestrator creates `.claude/specs/notification-system/` directory
2. Generates `requirements.md` following template
3. Validates requirements (iterates if needed)
4. Generates `design.md` with code reuse analysis
5. Validates design (iterates if needed)
6. Generates `tasks.md` with detailed implementation prompts
7. Validates tasks (iterates if needed)
8. Presents completion summary with document paths

### Validating an Existing Document

```
/spec-validate .claude/specs/notification-system/design.md
```

The appropriate validator will:
- Load relevant templates and context
- Analyze document structure and content
- Provide rating (PASS/NEEDS_IMPROVEMENT/MAJOR_ISSUES)
- List specific issues and improvement suggestions
- Highlight strengths

### Project Structure

After running the workflow, your project will have:

```
.claude/
├── specs/
│   └── {feature-name}/
│       ├── requirements.md  # User stories and acceptance criteria
│       ├── design.md        # Architecture and component design
│       └── tasks.md         # Implementation task breakdown
└── plugins/
    └── spec-workflow/       # This plugin
        ├── agents/
        ├── commands/
        └── skills/
            └── spec-workflow/
                ├── SKILL.md
                ├── templates/
                └── scripts/
```

## Workflow Phases

### Phase 1: Requirements
- Generate requirements.md from template
- Include user stories and acceptance criteria
- Validate for completeness and testability
- Iterate on feedback (max 2 cycles)

### Phase 2: Design
- Generate design.md from template
- Analyze codebase for reuse opportunities
- Create architecture diagrams (Mermaid)
- Validate for technical soundness
- Iterate on feedback (max 2 cycles)

### Phase 3: Tasks
- Generate tasks.md from template
- Break down design into actionable tasks
- Map tasks to requirements
- Include detailed implementation prompts
- Validate for completeness and actionability
- Iterate on feedback (max 2 cycles)

### Phase 4: Completion
- All documents achieve PASS validation
- Summary provided with document paths
- Ready for implementation

## Validation Ratings

- **PASS**: Document meets all quality standards, ready to proceed
- **NEEDS_IMPROVEMENT**: Minor issues requiring targeted fixes
- **MAJOR_ISSUES**: Significant problems requiring substantial revision

## Best Practices

1. **Start with context**: Provide clear feature description and any existing context
2. **Trust the workflow**: Let the orchestrator manage the process
3. **Review validation feedback**: Validators provide specific, actionable guidance
4. **Iterate strategically**: Address feedback systematically
5. **Leverage existing code**: Ensure design and tasks reference code reuse opportunities
6. **Keep tasks focused**: Each task should have a single, clear purpose
7. **Test thoroughly**: Include comprehensive testing tasks in breakdown

## Customization

### Custom Templates
Replace templates in `templates/` directory to customize output structure

### Custom Validators
Modify agent prompts in `agents/` directory to adjust validation criteria

### Custom Workflows
Extend `spec-orchestrator.md` to add additional workflow phases

## Troubleshooting

**Templates not found:**
- Ensure plugin is installed in `.claude/plugins/spec-workflow/`
- Check template files exist in `templates/` directory

**Validation fails repeatedly:**
- Review validation feedback carefully
- Consult user if issues cannot be resolved automatically
- Consider adjusting validation criteria if too strict

**Scripts not working:**
- Ensure scripts have execute permissions (macOS/Linux)
- Check file paths are absolute, not relative
- Verify PowerShell execution policy (Windows)

## Examples

### Example 1: E-commerce Feature
```
use spec workflow to create our shopping cart feature
```

Output:
- `.claude/specs/shopping-cart/requirements.md`
- `.claude/specs/shopping-cart/design.md`
- `.claude/specs/shopping-cart/tasks.md`

### Example 2: Validation Check
```
/spec-validate .claude/specs/shopping-cart/design.md
```

Output:
- Validation rating
- Specific issues found
- Improvement suggestions
- Identified strengths

## Contributing

Improvements and extensions welcome:
- Additional validator criteria
- New template sections
- Enhanced orchestration logic
- Additional helper scripts

## License

MIT License - see LICENSE file for details

## Support

For issues, questions, or feature requests, please open an issue in the repository.

---

**Version:** 1.0.0
**Last Updated:** 2025-10-19
**Requires:** Claude Code CLI
