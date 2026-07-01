# Workflow Planning

**Purpose**: Determine which phases to execute and create comprehensive execution plan
**Always Execute**

## Step 1: Load All Prior Context
Load reverse engineering artifacts, requirements, user stories (if executed).

## Step 2: Detailed Scope and Impact Analysis
- Transformation scope detection (brownfield): architecture, infrastructure changes, cross-package impact
- Change impact: user-facing, structural, data model, API, NFR
- Component relationship mapping with dependency graph
- Risk assessment: Low/Medium/High/Critical

## Step 3: Phase Determination
Determine which stages to EXECUTE or SKIP with rationale.

## Step 4: Multi-Module Coordination (Brownfield)
Analyze dependencies, determine update strategy (sequential/parallel/hybrid).

## Step 5: Generate Workflow Visualization
Create Mermaid flowchart with proper styling:
- Always execute: Green (#4CAF50)
- Conditional execute: Orange (#FFA726)
- Skip: Gray (#BDBDBD)
- Start/End: Purple (#CE93D8)

## Step 6: Create Execution Plan Document
Save as `aidlc-docs/inception/plans/execution-plan.md`

## Step 7: Initialize State Tracking
Update aidlc-state.md with all stages and their EXECUTE/SKIP status.

## Step 8: Present Plan to User
Format: Completion Announcement → Detailed Analysis → Recommended Plan (execute/skip with rationale) → Review Required + What's Next (Request Changes / Add Skipped Stages / Approve & Continue)
Wait for explicit user approval.
