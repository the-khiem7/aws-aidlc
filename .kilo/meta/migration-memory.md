# Migration Memory: Kiro CLI → Kilo Code Port

**Purpose**: Record why and how `.kiro/` was ported to `.kilo/`. This file is NOT loaded by any `kilo.jsonc` instructions glob — it exists solely as a memory anchor.

## Timeline

- **2026-07-01**: Explored `.kiro/` structure (steering/core-workflow.md + 29 rule detail files under `aws-aidlc-rule-details/`).
- **2026-07-01**: Fetched Kilo Code docs (CLI, Custom Rules, Custom Modes, Customize overview).
- **2026-07-01**: Created `.kilo/` port: 4 agents, 29 rule files, `kilo.jsonc`.
- **2026-07-01**: Review + fixes (permissions, audit append, extension enforcement, opt-in glob).

## Why the Port Exists

The Kiro CLI AI-DLC workflow (`core-workflow.md`) is a procedural script for one persistence model. Kilo Code has a different architecture — static prompt assembly via `instructions` globs, YAML-frontmatter agent definitions, and `user-switch` mode handoffs instead of runtime control flow.

Mapping 1:1 preserves the workflow semantics across platforms.

## Key Differences Between Kiro and Kilo

| Aspect | Kiro CLI | Kilo Code |
|---|---|---|
| Execution model | Runtime scripting (one long prompt, one mode) | Static prompt assembly (instructions loaded upfront) |
| Phase transitions | Procedural — script says "now do X" | Manual — user switches agent modes |
| Extension loading | "Scan dir → show opt-in → load on demand" at runtime | `*.opt-in.md` trick: glob loads lightweight prompts, agent `read`s full file on demand |
| Single vs split | One `core-workflow.md` file | 4 agent files (`aidlc.md` + `inception.md` + `construction.md` + `operations.md`) |
| Extension enforcement | Script checks for missing opt-in files at runtime | Agent prompt contains fallback rule |
| Permissions model | N/A (script has full access) | `kilo.jsonc` + agent frontmatter (last-match-wins) |

## Architectural Decisions

1. **Steering/core-workflow.md → agent prompt, not rules**: The orchestrator became the `aidlc.md` agent prompt. The subagents (`inception.md`, `construction.md`, `operations.md`) are placeholders for `mode: subagent` delegation.

2. **Permission split removed**: After review, `permission:` was removed from `aidlc.md` frontmatter entirely. All permissions live in `kilo.jsonc:32-59`.

3. **Extension glob narrowed**: Changed from `extensions/**/*.md` to `extensions/**/*.opt-in.md` in `kilo.jsonc:8`. Full `.md` files are loaded on demand via `read` tool.

4. **Deferred loading via agent instruction**: The `aidlc.md` agent is instructed to `read` full extension rule files when user opts in (line 81). This is a convention, not enforced by Kilo's runtime.

5. **Audit append-only instruction**: Added explicit append-vs-overwrite guidance (lines 116-117) with correct/incorrect tool usage examples, ported from `core-workflow.md:497-507`.

## Files Created (34 files + 1 config)

- `kilo.jsonc` — config: instructions globs, 4 agents, permissions
- `.kilo/agents/aidlc.md` — main orchestrator (port of core-workflow.md)
- `.kilo/agents/inception.md` — inception subagent placeholder
- `.kilo/agents/construction.md` — construction subagent placeholder
- `.kilo/agents/operations.md` — operations subagent placeholder
- `.kilo/rules/common/` — 11 files
- `.kilo/rules/inception/` — 7 files
- `.kilo/rules/construction/` — 6 files
- `.kilo/rules/operations/` — 1 file
- `.kilo/rules/extensions/security/baseline/` — 2 files (opt-in + full)
- `.kilo/rules/extensions/testing/property-based/` — 2 files (opt-in + full)

## Caveats

- User must manually switch agent modes (aidlc → inception → construction → operations). No automated handoff.
- Extension opt-in is a convention in the agent prompt, not enforced by the runtime. An agent ignoring its own prompt would load all rules eagerly.
- `.opt-in.md` pattern is Kilo-specific — no other tool uses this convention.
