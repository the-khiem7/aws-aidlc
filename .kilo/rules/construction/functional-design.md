# Functional Design

**Purpose**: Detailed business logic design per unit (technology-agnostic)

## Prerequisites
- Units Generation must be complete
- Application Design recommended
- Execution plan must indicate Functional Design should execute

## Steps

### Step 1: Analyze Unit Context
Read unit definition and assigned stories from inception artifacts.

### Step 2-4: Create Plan with Questions
Evaluate categories: Business Logic Modeling, Domain Model, Business Rules, Data Flow, Integration Points, Error Handling, Business Scenarios, Frontend Components (if applicable)

### Step 5: Collect and Analyze Answers
Wait for ALL [Answer]: tags. Review for vague/ambiguous responses. Create follow-up questions if needed. Resolve ALL ambiguities.

### Step 6: Generate Artifacts
- `business-logic-model.md` — Core algorithms, data transformations, workflows
- `business-rules.md` — Decision rules, validation logic, constraints
- `domain-entities.md` — Entity relationships, data structures
- `frontend-components.md` (if applicable) — Component hierarchy, props, state, user interactions

### Step 7-9: Approval
Present completion message: Completion Announcement → AI Summary → Review Required (Request Changes / Continue to Next Stage)
Wait for explicit approval. Log in audit.md.
