# Workspace Detection

**Purpose**: Determine workspace state and check for existing AI-DLC projects

## Step 1: Check for Existing AI-DLC Project
Check if `aidlc-docs/aidlc-state.md` exists:
- If exists: Resume from last phase
- If not exists: Continue with new project assessment

## Step 2: Scan Workspace for Existing Code
Scan for source code files (.java, .py, .js, .ts, .jsx, .tsx, .kt, .go, .rs, .rb, .php, .c, .cpp, .cs, etc.)
Check for build files (pom.xml, package.json, build.gradle, etc.)
Identify workspace root directory (NOT aidlc-docs/)

## Step 3: Determine Next Phase
- **Empty workspace (greenfield)**: Set brownfield=false, next is Requirements Analysis
- **Existing code (brownfield)**: Set brownfield=true
  - If reverse engineering artifacts exist and are current: Skip to Requirements Analysis
  - If artifacts are stale or missing: Next is Reverse Engineering

## Step 4: Create Initial State File
Create `aidlc-docs/aidlc-state.md` with project type, start date, current stage, workspace state.

## Step 5: Present Completion Message
Summarize findings and announce next phase. No user approval required — this is informational only.
