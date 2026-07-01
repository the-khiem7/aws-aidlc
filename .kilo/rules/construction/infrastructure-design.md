# Infrastructure Design

**Purpose**: Map logical software components to actual infrastructure choices

## Prerequisites
- Functional Design must be complete for the unit
- NFR Design recommended
- Execution plan must indicate Infrastructure Design should execute

## Steps

### Step 1: Analyze Design Artifacts
Read functional design and NFR design. Identify logical components needing infrastructure.

### Step 2-4: Create Plan with Questions
Evaluate categories: Deployment Environment, Compute Infrastructure, Storage Infrastructure, Messaging Infrastructure, Networking Infrastructure, Monitoring Infrastructure, Shared Infrastructure

### Step 5: Collect and Analyze Answers
Wait for ALL [Answer]: tags. Review for ambiguities. Create follow-up questions if needed.

### Step 6: Generate Artifacts
- `infrastructure-design.md` — Service mapping (AWS/Azure/GCP/on-premise)
- `deployment-architecture.md` — Deployment environment architecture
- `shared-infrastructure.md` (if applicable) — Infrastructure sharing strategy

### Step 7-9: Approval
Present completion message. Wait for explicit approval. Log in audit.md.
