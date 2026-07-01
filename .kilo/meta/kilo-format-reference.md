# Kilo Code Format Reference

## Agent Files (`agents/*.md`)

### YAML Frontmatter Fields

```yaml
---
description: Short description shown in agent switcher
mode: primary | subagent | ask | plan
color: "#RRGGBB"        # sidebar accent color (optional)
groups: []              # optional group membership
permission:             # optional — overrides kilo.jsonc per agent
  read: allow
  bash:
    "*": ask
    "git *": allow
---
```

### Permission Precedence

If both `kilo.jsonc` permissions and agent frontmatter permissions are present, **agent frontmatter takes precedence** (overrides matching keys). Remove `permission:` from agent frontmatter to inherit globally from `kilo.jsonc`.

Rules in `kilo.jsonc` follow **last-match-wins** ordering. Common pattern: put the catch-all `"*": "ask"` first, then specific allows:

```json
"bash": {
  "*": "ask",
  "git *": "allow",
  "npm *": "ask",
  "npm install": "allow"
}
```

`npm install` matches both `npm *` (ask) and `npm install` (allow) — `allow` wins because it's last.

### Behavior of Each Mode

| Mode | Behavior |
|---|---|
| `primary` | Listed in sidebar. Can be activated by user. Can use subagents. |
| `subagent` | Not shown in sidebar. Only accessible via `mode` delegation from a primary agent's YAML. |
| `ask` | Listed in sidebar. Always asks user before taking actions. |
| `plan` | Listed in sidebar. Plans before acting. |

## Instructions Loading (`kilo.jsonc`)

All files matched by `instructions` globs are **loaded at startup into the system prompt**. There is no lazy loading, no conditional loading, no runtime file scanning in the loading phase. Everything is baked before the agent starts.

```json
"instructions": [
  ".kilo/rules/common/*.md",
  ".kilo/rules/extensions/**/*.opt-in.md"
]
```

### Consequences

- **No runtime control flow**: The agent cannot `include()` or `require()` another rule file. To simulate deferred loading, the agent must use the `read` tool on demand — but the instruction content is still in system prompt context.
- **The `.opt-in.md` pattern**: Place a lightweight prompt in `*.opt-in.md` (matched by glob), and keep full rules in `*.md` (not matched). Agent reads the full file via `read` only after user opts in. This is a userland convention, not a Kilo runtime feature.
- **Globs outside `rules/` are safe**: Only paths in the `instructions` array are loaded. A file at `.kilo/migration-memory.md` is never loaded unless explicitly added.
- **Extension rule consequence**: Extensions that are always enforced must still have a `*.md` file under `extensions/`. They are loaded via the agent's `read` instruction, or explicitly added to the `instructions` array if eager loading is acceptable.

## Permission Rules (`kilo.jsonc:permission`)

```json
"permission": {
  "*": "ask",           # catch-all for all tools
  "read": "allow",      # tool-level override (applies to all read tool usage)
  "glob": "allow",
  "grep": "allow",
  "bash": {             # bash sub-commands by pattern match
    "*": "ask",
    "git *": "allow",
    "rm *": "deny"
  },
  "edit": {
    "aidlc-docs/**": "allow",
    "*": "ask"
  },
  "write": {
    "aidlc-docs/**": "allow",
    "*": "ask"
  }
}
```

Available verbs: `allow`, `ask`, `deny`.

Tool-level keys (`read`, `glob`, `grep`) apply to the entire tool — they cannot be scoped by path. Bash and file tool permissions use glob patterns on the command/file argument.

**`"*": "ask"`** is the catch-all for all tools, including any not explicitly listed. Always put it first.

## Permission Precedence (Agent vs Config)

1. If the agent's YAML frontmatter has a `permission:` block, it is used INSTEAD of the global `kilo.jsonc` permission for that agent.
2. If the agent has no `permission:` block, the global `kilo.jsonc` permission applies.
3. There is no merge — it's one or the other.

## How Instructions Are Composed

```
kilo.jsonc
├── instructions globs → matched files → concatenated into system prompt
├── agent definitions → each agent gets its own system prompt
│   └── agent_name.md frontmatter → YAML metadata
│   └── agent_name.md body → appended after instructions
```

The effective system prompt for a given agent is:

```
[content of all instruction files matched by globs]
[content of the agent's .md file body]
```

## Subagent Delegation

A primary agent can delegate to a subagent by referencing its mode name:

```yaml
---
mode: primary
---
```

In the prompt: `Use mode=inception to delegate architecture work to the Inception subagent.`

Effect: Kilo pauses the primary agent's conversation and starts a new sub-conversation with the subagent's system prompt. The subagent's output is returned to the primary when done.

**Limitation**: The user must explicitly trigger the switch. There is no automatic `await subagent.run()` — the primary agent can only *recommend* the user switch.
