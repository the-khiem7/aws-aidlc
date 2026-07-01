# Requirements Analysis (Adaptive)

**Role**: Assume the role of a product owner

## Prerequisites
- Workspace Detection must be complete
- Reverse Engineering must be complete (if brownfield)

## Execution Steps

### Step 1: Load Reverse Engineering Context (if available)
Load architecture.md, component-inventory.md, technology-stack.md

### Step 2: Analyze User Request (Intent Analysis)
- Clarity: Clear / Vague / Incomplete
- Type: New Feature / Bug Fix / Refactoring / Upgrade / Migration / Enhancement / New Project
- Scope: Single File / Single Component / Multiple Components / System-wide / Cross-system
- Complexity: Trivial / Simple / Moderate / Complex

### Step 3: Determine Requirements Depth
- Minimal: Clear, simple request
- Standard: Needs clarification, normal complexity
- Comprehensive: Complex, high-risk, multiple stakeholders

### Step 4: Assess Current Requirements
Analyze what the user has provided, convert non-markdown to markdown.

### Step 5: Thorough Completeness Analysis
Evaluate ALL areas: Functional, NFR, User Scenarios, Business Context, Technical Context, Quality Attributes.
When in doubt, ask questions.

### Step 5.1: Extension Opt-In Prompts
Present opt-in questions from loaded `.opt-in.md` files. Record enablement status in aidlc-state.md.
Load full rules for opted-in extensions.

### Step 6: Generate Clarifying Questions
Create `aidlc-docs/inception/requirements/requirement-verification-questions.md`
Use multiple choice format with [Answer]: tags. Keep asking until ambiguity is resolved.

**GATE**: DO NOT proceed until ALL questions are answered and validated.

### Step 7: Generate Requirements Document
Create `aidlc-docs/inception/requirements/requirements.md` with intent analysis, functional and non-functional requirements.

### Step 8: Update State Tracking

### Step 9: Present Completion Message
Format: Completion Announcement → AI Summary → Review Required + What's Next (Request Changes / Add User Stories / Approve & Continue)
Wait for explicit user approval.
