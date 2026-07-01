# Units Generation

**Purpose**: Decompose the system into manageable units of work
**Definition**: A unit of work is a logical grouping of stories for development purposes

## Prerequisites
- Application Design stage REQUIRED
- User Stories recommended
- Execution plan must indicate Units Generation should execute

## PART 1: PLANNING

### Step 1-4: Create Unit of Work Plan
Generate plan with checkboxes. Evaluate question categories:
- Story Grouping, Dependencies, Team Alignment, Technical Considerations, Business Domain, Code Organization

### Step 5-10: Questions, Answers, Approval
Use [Answer]: tags. Analyze for ambiguities. Resolve ALL.
Get explicit user approval before generation.

## PART 2: GENERATION

### Step 12-19: Generate Artifacts
- `unit-of-work.md` — Unit definitions and responsibilities
- `unit-of-work-dependency.md` — Dependency matrix
- `unit-of-work-story-map.md` — Story-to-unit mapping
- Greenfield only: Document code organization strategy

Complete all steps. Present completion message. Wait for explicit approval.

## Critical Rules
- NO HARDCODED LOGIC: Only execute what's written in the plan
- FOLLOW PLAN EXACTLY: Do not deviate from the step sequence
- UPDATE CHECKBOXES: Mark [x] immediately after completing each step
- USE APPROVED APPROACH: Follow the decomposition methodology from Planning
