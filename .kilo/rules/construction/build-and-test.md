# Build and Test

**Purpose**: Build all units and execute comprehensive testing

## Prerequisites
- Code Generation must be complete for all units

## Steps

### Step 1: Analyze Testing Requirements
Determine appropriate testing strategy: unit, integration, performance, e2e, contract, security.

### Step 2: Generate Build Instructions
Create `aidlc-docs/construction/build-and-test/build-instructions.md`:
- Prerequisites (build tool, dependencies, env vars)
- Build steps (install deps, configure, build, verify)
- Troubleshooting guide

### Step 3: Generate Unit Test Instructions
Create `aidlc-docs/construction/build-and-test/unit-test-instructions.md`:
- Commands to run all unit tests
- Expected results and coverage targets
- Fix failing tests procedure

### Step 4: Generate Integration Test Instructions
Create `aidlc-docs/construction/build-and-test/integration-test-instructions.md`:
- Test scenarios between units
- Environment setup (docker-compose, services)
- Cleanup procedures

### Step 5: Generate Performance Test Instructions (If Applicable)
Create `aidlc-docs/construction/build-and-test/performance-test-instructions.md`:
- Performance requirements (response time, throughput)
- Load/stress test setup and execution
- Results analysis

### Step 6: Generate Additional Tests (As Needed)
- Contract tests (microservices)
- Security tests (vulnerability scanning)
- E2E tests (complete user workflows)

### Step 7: Generate Summary
Create `aidlc-docs/construction/build-and-test/build-and-test-summary.md`

### Step 8-10: Approval
Present completion message with results summary. End with:
```
✅ **Approve & Continue** — Approve build and test results and proceed to **Operations**
```
Wait for explicit approval. Log in audit.md.
