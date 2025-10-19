---
description: Validate existing requirements, design, or tasks document
---

You are validating an existing specification document.

## Your Task

Use the appropriate validator agent to validate the specified document type.

## Instructions

1. **Identify document type**: Determine if validating requirements, design, or tasks
2. **Identify document path**: Get the path to the document to validate
3. **Invoke appropriate validator**:

### For Requirements Validation
Use the **spec-requirements-validator** agent:
```
Validate the requirements document at: {path}

Load the requirements template and product context (if available), then provide comprehensive validation feedback on:
- Template structure compliance
- Product vision alignment
- User stories quality
- Acceptance criteria completeness
- Non-functional requirements
- Clarity and testability

Provide rating (PASS/NEEDS_IMPROVEMENT/MAJOR_ISSUES) and specific feedback.
```

### For Design Validation
Use the **spec-design-validator** agent:
```
Validate the design document at: {path}

Load the design template and requirements document, then provide comprehensive validation feedback on:
- Template structure compliance
- Requirements coverage
- Architecture quality
- Technical standards compliance
- Code reuse and integration
- Documentation completeness

Provide rating (PASS/NEEDS_IMPROVEMENT/MAJOR_ISSUES) and specific feedback.
```

### For Tasks Validation
Use the **spec-tasks-validator** agent:
```
Validate the tasks document at: {path}

Load the tasks template, requirements, and design documents, then provide comprehensive validation feedback on:
- Template structure compliance
- Requirements coverage
- Design alignment
- Code reuse validation
- Task sequencing
- Implementation prompts quality
- Actionability and testing coverage

Provide rating (PASS/NEEDS_IMPROVEMENT/MAJOR_ISSUES) and specific feedback.
```

4. **Present validation results**: Show the user the validator's feedback

## Example Usage

User: "/spec-validate .claude/specs/auth/requirements.md"
User: "validate the design document for the auth feature"

## Notes

- Validators are read-only - they provide feedback but don't modify files
- Use validation feedback to iterate and improve documents
- All documents should achieve PASS rating before implementation
