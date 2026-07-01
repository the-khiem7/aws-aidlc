# Content Validation Rules

## MANDATORY: Validate Before File Creation
All generated content MUST be validated before writing to files.

## ASCII Diagram Standards
- Basic ASCII only: `+` `-` `|` `^` `v` `<` `>` and alphanumeric text
- NO Unicode box-drawing characters (inconsistent rendering)
- Every line in a box MUST have exactly the same character count
- Spaces only (NO tabs)
- Box corners use `+`

## Mermaid Diagram Validation
1. Check for invalid characters in node IDs (alphanumeric + underscore only)
2. Escape special characters in labels: `"` → `\"` and `'` → `\'`
3. Validate flowchart syntax
4. Provide text alternative as fallback

## Pre-Creation Validation Checklist
- Validate embedded code blocks (Mermaid, JSON, YAML)
- Check special character escaping
- Verify markdown syntax correctness
- Include fallback content for complex elements

## Validation Failure Handling
1. Log the error: Record what failed validation
2. Use fallback content: Switch to text-based alternative
3. Continue workflow: Don't block on content validation failures
