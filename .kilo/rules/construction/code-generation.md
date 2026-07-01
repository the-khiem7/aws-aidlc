# Code Generation

**Purpose**: Generate code for each unit of work through planning and execution
**Note**: For brownfield projects, "generate" means modify existing files when appropriate.

## PART 1: PLANNING

### Step 1: Analyze Unit Context
Read unit design artifacts, story map, identify dependencies.

### Step 2: Create Detailed Plan
Document exact paths (never aidlc-docs/). Create numbered steps with checkboxes:
- Project Structure Setup (greenfield only)
- Business Logic Generation + Unit Testing + Summary
- API Layer Generation + Unit Testing + Summary
- Repository Layer Generation + Unit Testing + Summary
- Frontend Components Generation + Testing + Summary (if applicable)
- Database Migration Scripts (if data models exist)
- Documentation Generation
- Deployment Artifacts Generation

### Step 3-7: Approval
Save plan as `aidlc-docs/construction/plans/{unit-name}-code-generation-plan.md`
Wait for explicit user approval before generation.

## PART 2: GENERATION

### Step 10-16: Execute Plan
- Load plan, execute each step in order
- Brownfield: Modify in-place (no `ClassName_modified.java`)
- Greenfield: Create new files following structure patterns
- Add `data-testid` attributes to UI elements
- Mark [x] immediately after each step

### Completion
Present completion message with modified/created files listed.
Wait for explicit approval. Log in audit.md.

## Critical Rules
- Application code: Workspace root ONLY (NEVER aidlc-docs/)
- Documentation: aidlc-docs/ only (markdown summaries)
- Brownfield: Modify in-place, verify no duplicates
- NO HARDCODED LOGIC: Only execute what's in the plan
- FOLLOW PLAN EXACTLY: Do not deviate from the step sequence
