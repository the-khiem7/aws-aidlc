# Mid-Workflow Changes and Stage Management

## Types of Changes

### 1. Adding a Skipped Stage
1. Confirm request with user
2. Check dependencies are complete
3. Update execution plan with rationale
4. Mark stage as "PENDING" in aidlc-state.md
5. Execute stage following normal process
6. Log change in audit.md

### 2. Skipping a Planned Stage
1. Confirm request and warn about impact
2. Get explicit confirmation
3. Mark stage as "SKIPPED" with reason
4. Adjust later stages that may need manual setup
5. Log change in audit.md

### 3. Restarting Current Stage
Offer options: Modify existing artifacts or complete restart.
If restart: Archive artifacts, reset checkboxes, re-execute.

### 4. Restarting Previous Stage
Assess impact on all dependent stages, warn user about full impact,
get explicit confirmation, archive affected artifacts, reset stages.

### 5. Changing Stage Depth
Confirm request, update execution plan, adjust approach, inform user of new timeline.

### 6. Pausing Workflow
Complete current step, update checkboxes and state, provide resume instructions.

### 7. Changing Architectural Decision
Explain impact based on current progress (early vs late in workflow),
recommend approach, get confirmation, execute changes.

### 8. Adding/Removing Units
Assess which units have completed design/code, explain consequences,
update unit artifacts, reset affected units for redesign.

## General Guidelines
- Always confirm before destructive changes
- Explain impact before user decides
- Offer alternatives when possible
- Archive before making changes
- Keep all tracking files in sync
- Log thoroughly for audit trail
