# Question Format Guide

## MANDATORY: Never Ask Questions in Chat
ALL questions must be placed in dedicated `.md` files, never directly in chat.

## Question File Format

### File Naming Convention
Use descriptive names: `{phase-name}-questions.md`
Examples: `requirements-questions.md`, `story-planning-questions.md`

### Question Structure
Every question must include meaningful options plus "Other" as the last option:

## Question [Number]
[Clear, specific question text]

A) [First meaningful option]

B) [Second meaningful option]

[...additional options as needed...]

X) Other (please describe after [Answer]: tag below)

[Answer]:

### Critical Rules
- "Other" is MANDATORY as the LAST option for every question
- Only include meaningful options — don't make up options to fill slots
- Use as many or as few options as make sense (minimum 2 + Other)
- Each option must be separated by a blank line for CommonMark compatibility

### Multiple Choice Guidelines
- Minimum: 2 meaningful options + "Other"
- Typical: 3-4 meaningful options + "Other"
- Maximum: 5 meaningful options + "Other"
- Make options mutually exclusive
- Cover the most common scenarios
- Be specific and clear

### Contradiction and Ambiguity Detection
After reading user responses, check for:
- Scope mismatch: "Bug fix" but "Entire codebase affected"
- Risk mismatch: "Low risk" but "Breaking changes"
- Timeline mismatch: "Quick fix" but "Multiple subsystems"
- Impact mismatch: "Single component" but "Significant architecture changes"

### Clarification Workflow
1. Detect contradictions/ambiguities
2. Create clarification question file
3. Inform user and wait for answers
4. Re-validate after clarifications
5. Only proceed when all contradictions are resolved
