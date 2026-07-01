# ASCII Diagram Standards

## MANDATORY: Use Basic ASCII Only
- ALLOWED: `+` `-` `|` `^` `v` `<` `>` and alphanumeric text
- FORBIDDEN: Unicode box-drawing characters (`┌` `─` `│` `└` `┐` `┘` etc.)

## Critical Rules
- Every line in a box must have EXACTLY the same character count
- Spaces only (NO tabs) for alignment
- Box corners use `+`

## Standard Patterns

### Box Pattern
```
+-----------------------------------------------------+
|              Calculator Application                 |
|  Provides basic arithmetic operations for users     |
+-----------------------------------------------------+
```

### Nested Boxes
```
+-------------------------------------------------------+
|              Web Server                               |
|  +-------------------------------------------------+  |
|  |  index.php (Monolithic Application)             |  |
|  |  +-------------------------------------------+  |  |
|  |  |  HTML Template                           |  |  |
|  |  +-------------------------------------------+  |  |
|  +-------------------------------------------------+  |
+-------------------------------------------------------+
```

### Arrows and Connections
```
+----------+          +----------+
|  Source  | -------> |  Target  |
+----------+          +----------+
```

### Vertical Flow
```
    |
    v
+----------+
|  Input   |
+----------+
    |
    | validates
    v
+----------+
| Process  |
+----------+
```

## Validation Checklist
- [ ] Basic ASCII only: `+` `-` `|` `^` `v` `<` `>`
- [ ] No Unicode box-drawing
- [ ] Spaces (not tabs) for alignment
- [ ] Corners use `+`
- [ ] All box lines same character width
- [ ] Corners align vertically in monospace font
