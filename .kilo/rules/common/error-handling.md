# Error Handling and Recovery Procedures

## Error Severity Levels
- **Critical**: Workflow cannot continue (missing files, system errors)
- **High**: Stage cannot complete (incomplete answers, contradictory responses)
- **Medium**: Stage can continue with workarounds (optional artifacts missing)
- **Low**: Minor issues that don't block progress (formatting inconsistencies)

## General Error Handling
1. Identify the error clearly
2. Assess impact (blocking or workaround possible)
3. Communicate to user with options
4. Offer clear resolution steps
5. Document in audit.md

## Recovery Procedures

### Partial Stage Completion
1. Load the stage plan file
2. Identify last completed step (last [x] checkbox)
3. Resume from next uncompleted step
4. Verify all prior steps are complete

### Corrupted State File
1. Create backup: aidlc-state.md.backup
2. Ask user which stage they're on
3. Regenerate state file from scratch
4. Mark completed stages based on existing artifacts
5. Resume from current stage

### Missing Artifacts
1. Identify which artifacts are missing
2. Determine if they can be regenerated
3. If yes: Return to that stage, regenerate
4. If no: Ask user to provide information manually
5. Document the gap in audit.md

### User Wants to Restart Stage
1. Confirm user wants to restart (data will be lost)
2. Archive existing artifacts: {artifact}.backup
3. Reset stage status in aidlc-state.md
4. Clear stage checkboxes in plan files
5. Re-execute stage from beginning

## Logging Format
```markdown
## Error — [Stage Name]
**Timestamp**: [ISO timestamp]
**Error Type**: [Critical/High/Medium/Low]
**Description**: [What went wrong]
**Cause**: [Why it happened]
**Resolution**: [How it was resolved]
**Impact**: [Effect on workflow]
```
