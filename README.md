# Durable Agent Memory

> A lightweight memory protocol for long-running AI agents.

AI agents lose context. Sessions end, agents change, experiments fail midway, and important decisions get buried in old conversations.

**Durable Agent Memory** gives agents a structured, evidence-backed way to preserve project state across context loss, interruptions, and handoffs.

## What it does

- **Preserves project state** across sessions and agents
- **Tracks decisions, failures, hypotheses, and next steps**
- **Links claims to evidence** such as files, commits, run IDs, and artifacts
- **Supports safe resumption** by reconciling memory with the actual workspace
- **Validates memory structure** with a read-only Python validator

## Operating modes

| Mode | Purpose |
|---|---|
| **Bootstrap** | Create memory for an existing project |
| **Update** | Record new decisions, evidence, failures, or progress |
| **Resume** | Recover the live state after context loss or handoff |
| **Audit** | Check for stale claims, broken references, or memory drift |

## Example structure

```text
project-memory/
├── README.md
├── USER_DIRECTIVES.md
├── CURRENT_STATE.md
├── DECISION_LOG.md
└── NEXT_CHECKPOINT.md
```

Memory stays compact and points back to the real project rather than trying to replace it.

> **The workspace is the source of truth. Memory is the index.**

## Validation

```bash
python scripts/validate_memory.py project-memory/ --strict
```

The validator checks memory structure, broken links, missing core files, unsafe paths, and other common issues.

## Repository

```text
├── SKILL.md
├── agents/
├── references/
└── scripts/
    └── validate_memory.py
```

Built for long-running development, research, and multi-agent workflows where losing the context should not mean losing the project.
