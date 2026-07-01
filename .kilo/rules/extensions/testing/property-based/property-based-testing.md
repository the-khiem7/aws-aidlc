# Property-Based Testing Rules

**Extension**: Property-Based Testing
**Status**: Enforced when user opts in during Requirements Analysis

## Mandatory PBT Rules

### When to Use Property-Based Tests
Use property-based testing for:
- Pure functions: Functions where output depends only on input (no side effects)
- Serialization/deserialization round-trips: JSON, XML, Protocol Buffers, etc.
- Data transformations: Mappers, converters, validators
- Stateful systems: State machines, database operations, CRUD operations
- Invariant checking: Properties that must always hold true
- Business logic: Rules, calculations, decision logic

### Framework Selection
- **JavaScript/TypeScript**: fast-check, jsverify
- **Java**: jqwik, quickcheck, junit-quickcheck
- **Python**: Hypothesis
- **Go**: rapid, gopter, testing/quick
- **Rust**: proptest, quickcheck
- **C#**: FsCheck
- **Kotlin**: Kotest property testing, kqwik

### Test Structure Requirements
Each PBT test must define:
1. **Properties**: Invariants that must hold for ALL inputs
2. **Generators**: Custom generators for domain-specific types (not just primitives)
3. **Shrinking**: Allow the framework to shrink failing cases to minimal counterexamples

### Minimum Property Categories
For any function or module under PBT, cover these property categories:
- **Idempotence**: Running the operation twice produces the same result
- **Invariance**: Certain properties remain unchanged by operations
- **Inverse**: Operations have an inverse that restores original state
- **Oracle**: Compare against a known-correct (possibly slower) implementation
- **Metamorphic**: Related inputs produce predictably related outputs
- **Stateful**: State transitions maintain valid system states

### Code Review Gates
- Code submitted as "opting for PBT" must include PBT tests before merge
- PBT tests must achieve coverage of at least 80% of the targeted pure functions
- Shrinking must produce minimal counterexamples for any failing property
