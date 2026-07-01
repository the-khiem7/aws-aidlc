# Reverse Engineering

**Purpose**: Analyze existing codebase and generate comprehensive design artifacts
**Execute when**: Brownfield project detected
**Skip when**: Greenfield project

## Step 1: Multi-Package Discovery
- Scan all packages, relationships, types (Application, CDK, Models, Clients, Tests)
- Understand business context and transactions
- Discover infrastructure (CDK, Terraform, CloudFormation)
- Discover build systems, service architecture, code quality indicators

## Step 2-8: Generate Artifacts in `aidlc-docs/inception/reverse-engineering/`
- `business-overview.md` — Business context diagram, transactions, dictionary
- `architecture.md` — System overview, component descriptions, data flow, infrastructure
- `code-structure.md` — Build system, key classes/modules, design patterns, file inventory
- `api-documentation.md` — REST APIs, internal APIs, data models
- `component-inventory.md` — All packages with counts
- `technology-stack.md` — Languages, frameworks, infrastructure, tools
- `dependencies.md` — Internal and external dependencies with diagrams
- `code-quality-assessment.md` — Test coverage, quality indicators, technical debt
- `reverse-engineering-timestamp.md` — Analysis date for staleness tracking

## Step 9: Update State Tracking
Mark Reverse Engineering complete in aidlc-state.md

## Step 10: Present Completion Message
Wait for explicit user approval before proceeding to Requirements Analysis.
