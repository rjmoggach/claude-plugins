---
description: Create a complete product feature specification using the spec-driven workflow
---

You are initiating the spec-driven development workflow to create a complete product feature specification.

## Your Task

Use the **spec-orchestrator** agent to create a comprehensive specification for the feature described by the user.

## Instructions

1. **Understand the feature request**: Analyze what the user wants to build
2. **Invoke the orchestrator**: Use the Task tool to launch the spec-orchestrator agent with the following prompt:

```
Create a complete specification for the following feature: {user's feature description}

Follow the complete spec-driven workflow:
1. Create requirements.md with clear user stories and acceptance criteria
2. Validate requirements using spec-requirements-validator
3. Create design.md with architecture, components, and code reuse analysis
4. Validate design using spec-design-validator
5. Create tasks.md with detailed implementation tasks
6. Validate tasks using spec-tasks-validator
7. Iterate on validation feedback until all documents pass
8. Provide completion summary with document paths

Feature context provided by user: {include any additional context the user mentioned}
```

3. **Present results**: Once the orchestrator completes, show the user:
   - Paths to created documents
   - Brief summary of what was created
   - Validation status
   - Next steps (review or begin implementation)

## Example Usage

User: "use spec workflow to create our user authentication feature"

Your response:
```
I'll create a complete specification for the user authentication feature using the spec-driven workflow.

[Invoke spec-orchestrator agent with appropriate prompt]

[Present results when orchestrator completes]
```

## Notes

- The orchestrator will handle all document creation and validation
- You just need to invoke it with the right context and present results
- The user may also invoke this with `/spec-create {feature-name}`
