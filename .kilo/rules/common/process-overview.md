# AI-DLC Adaptive Workflow Overview

## The Three-Phase Lifecycle
- **INCEPTION PHASE**: Planning and architecture (Workspace Detection + conditional phases + Workflow Planning)
- **CONSTRUCTION PHASE**: Design, implementation, build and test (per-unit design + Code Generation + Build & Test)
- **OPERATIONS PHASE**: Placeholder for future deployment and monitoring workflows

## How It Works
- AI analyzes your request, workspace, and complexity to determine which stages are needed
- These stages always execute: Workspace Detection, Requirements Analysis (adaptive depth), Workflow Planning, Code Generation (per-unit), Build and Test
- All other stages are conditional: Reverse Engineering, User Stories, Application Design, Units Generation, per-unit design stages
- No fixed sequences: Stages execute in the order that makes sense for your specific task

## Stage Descriptions

### INCEPTION PHASE
- Workspace Detection: Analyze workspace state and project type (ALWAYS)
- Reverse Engineering: Analyze existing codebase (CONDITIONAL — Brownfield only)
- Requirements Analysis: Gather and validate requirements (ALWAYS — Adaptive depth)
- User Stories: Create user stories and personas (CONDITIONAL)
- Workflow Planning: Create execution plan (ALWAYS)
- Application Design: High-level component identification and service layer design (CONDITIONAL)
- Units Generation: Decompose into units of work (CONDITIONAL)

### CONSTRUCTION PHASE
- Functional Design: Detailed business logic design per unit (CONDITIONAL, per-unit)
- NFR Requirements: Determine NFRs and select tech stack (CONDITIONAL, per-unit)
- NFR Design: Incorporate NFR patterns and logical components (CONDITIONAL, per-unit)
- Infrastructure Design: Map to actual infrastructure services (CONDITIONAL, per-unit)
- Code Generation: Part 1 — Planning, Part 2 — Generation (ALWAYS, per-unit)
- Build and Test: Build all units and execute comprehensive testing (ALWAYS)

### OPERATIONS PHASE
- Operations: Placeholder for future deployment and monitoring workflows

## Key Principles
- Phases execute only when they add value
- INCEPTION focuses on "what" and "why"
- CONSTRUCTION focuses on "how" plus "build and test"
- Simple changes may skip conditional INCEPTION stages
- Complex changes get full INCEPTION and CONSTRUCTION treatment
