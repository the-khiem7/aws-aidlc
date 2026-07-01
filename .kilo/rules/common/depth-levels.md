# Adaptive Depth

## Core Principle
When a stage executes, ALL its defined artifacts are created. The "depth" refers to the level of detail and rigor within those artifacts, which adapts to the problem's complexity.

## Stage Selection vs Detail Level
- **Workflow Planning** decides: EXECUTE or SKIP for each stage
- **If EXECUTE**: Stage runs and creates ALL its defined artifacts
- **If SKIP**: Stage doesn't run at all
- **Detail level** adapts: Simple problems get concise artifacts, complex problems get comprehensive artifacts

## Factors Influencing Detail Level
1. Request Clarity — How clear and complete is the user's request?
2. Problem Complexity — How intricate is the solution space?
3. Scope — Single file, component, multiple components, or system-wide?
4. Risk Level — What's the impact of errors or omissions?
5. Available Context — Greenfield vs brownfield, existing documentation
6. User Preferences — Has user expressed preference for brevity or detail?

## Guiding Principle
Create exactly the detail needed for the problem at hand — no more, no less.
Don't artificially inflate simple problems with unnecessary detail.
Don't shortchange complex problems by omitting critical detail.
