# Session Continuity

## Welcome Back Prompt
When a user returns to continue work on an existing AI-DLC project, present:

**Welcome back! I can see you have an existing AI-DLC project in progress.**

Based on your aidlc-state.md, here's your current status:
- **Project**: [project-name]
- **Current Phase**: [INCEPTION/CONSTRUCTION/OPERATIONS]
- **Current Stage**: [Stage Name]
- **Last Completed**: [Last completed step]
- **Next Step**: [Next step to work on]

**What would you like to work on today?**

A) Continue where you left off ([Next step description])
B) Review a previous stage ([Show available stages])

[Answer]:

## Session Continuity Rules
1. Always read `aidlc-docs/aidlc-state.md` first
2. Parse current status from the workflow file
3. Load previous stage artifacts before resuming:
   - Reverse Engineering: architecture.md, code-structure.md, api-documentation.md
   - Requirements: requirements.md, requirement-verification-questions.md
   - User Stories: stories.md, personas.md, story-generation-plan.md
   - Application Design: components.md, component-methods.md, services.md
   - Units: unit-of-work.md, unit-of-work-dependency.md, unit-of-work-story-map.md
   - Per-Unit Design: artifacts under `aidlc-docs/construction/{unit-name}/`
   - Code Stages: ALL previous artifacts + code files
4. Adapt options based on architectural choice and current phase
5. Show specific next steps rather than generic descriptions
6. Log the continuity prompt in audit.md with timestamp
7. Place all questions in .md files, never in chat
