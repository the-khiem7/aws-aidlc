# Application Design

**Purpose**: High-level component identification and service layer design

## Prerequisites
- Workspace Detection must be complete
- Requirements Analysis recommended
- User Stories recommended
- Execution plan must indicate Application Design should execute

## Step-by-Step Execution

### 1. Analyze Context
Read requirements.md, stories.md. Identify key business capabilities.

### 2. Create Application Design Plan
Generate plan with checkboxes for components, methods, services, dependencies.

### 3. Generate Mandatory Artifacts
- `components.md` — Component definitions and responsibilities
- `component-methods.md` — Method signatures (detailed business rules come later in Functional Design)
- `services.md` — Service definitions and orchestration patterns
- `component-dependency.md` — Dependency matrix and communication patterns
- `application-design.md` — Consolidated design document

### 4. Generate Context-Appropriate Questions
Evaluate categories: Component Identification, Component Methods, Service Layer Design, Component Dependencies, Design Patterns
Default to asking when in doubt.

### 5-7. Questions and Answers
Store plan in `aidlc-docs/inception/plans/application-design-plan.md`
Use [Answer]: tags. Wait for ALL answers.

### 8-9. Analyze and Follow-up
Review for vague/ambiguous/contradictory answers. Create follow-up questions. Resolve ALL ambiguities.

### 10. Generate Design Artifacts
Execute approved plan to create all design artifacts.

### 11-15. Approval
Present completion message with Review Required + What's Next.
Wait for explicit approval. Log in audit.md.
