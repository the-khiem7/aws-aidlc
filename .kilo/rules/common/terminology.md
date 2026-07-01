# AI-DLC Terminology Glossary

## Core Terminology

### Phase vs Stage
- **Phase**: One of the three high-level lifecycle phases (INCEPTION, CONSTRUCTION, OPERATIONS)
- **Stage**: An individual workflow activity within a phase

### Three-Phase Lifecycle

**INCEPTION PHASE** — Planning & Architecture (WHAT and WHY)
Stages: Workspace Detection (ALWAYS), Reverse Engineering (CONDITIONAL), Requirements Analysis (ALWAYS), User Stories (CONDITIONAL), Workflow Planning (ALWAYS), Application Design (CONDITIONAL), Units Generation (CONDITIONAL)

**CONSTRUCTION PHASE** — Design, Implementation & Test (HOW)
Stages: Functional Design (CONDITIONAL), NFR Requirements (CONDITIONAL), NFR Design (CONDITIONAL), Infrastructure Design (CONDITIONAL), Code Generation (ALWAYS), Build and Test (ALWAYS)

**OPERATIONS PHASE** — Deployment & Monitoring
Stages: Operations (PLACEHOLDER)

### Application Design Terms
- **Component**: A functional unit with specific responsibilities
- **Method**: A function or operation within a component with defined business rules
- **Business Rule**: Logic that governs method behavior and validation
- **Service**: Orchestration layer that coordinates business logic across components
- **Component Dependency**: Relationship and communication pattern between components

### Architecture Terms
- **Unit of Work**: Logical grouping of stories for development purposes
- **Service**: Independently deployable component in microservices architecture
- **Module**: Logical grouping of functionality within a single service or monolith
- **Component**: Reusable building block within a service or module

### Depth Levels
- **Minimal**: Quick, focused execution for simple changes
- **Standard**: Normal depth with standard artifacts for typical projects
- **Comprehensive**: Full depth with all artifacts for complex/high-risk projects

### Artifact Types
- **Plans**: Documents with checkboxes and questions (in `aidlc-docs/plans/`)
- **Artifacts**: Generated outputs from executing plans (in `aidlc-docs/` subdirectories)
- **State Files**: `aidlc-state.md` (overall progress) and `audit.md` (complete audit trail)

### Common Abbreviations
- **AI-DLC**: AI-Driven Development Life Cycle
- **NFR**: Non-Functional Requirements
- **UOW**: Unit of Work
