---
name: durable-project-memory
description: Maintain compact, evidence-backed project memory for long-running work that must survive context loss, agent handoffs, interruptions, or multi-stage research and implementation. Use when a user asks to create, update, audit, or resume from durable project memory; do not activate for ordinary short tasks that need no persistent handoff.
---

# Durable Project Memory

Build memory that lets a future agent recover the project's actual state without
re-reading the whole workspace or trusting stale prose.

## Core contract

- Treat the workspace and primary artifacts as ground truth. Memory is a
  verified index and synthesis, not an alternative source of truth.
- Preserve history. Supersede outdated conclusions with dated entries or a
  clear current-state section; do not silently rewrite what was previously
  believed or erase failed work.
- Separate facts, interpretations, decisions, open hypotheses, planned work,
  and user instructions. Do not promote internal diagnostics, successful
  commands, or completed runners into user-visible or project outcomes without
  the relevant outcome evidence.
- Point material claims to stable local paths, run IDs, commits, hashes, issue
  IDs, or authoritative sources. Say when evidence is missing or only inferred.
- Keep secrets, credentials, personal access tokens, and sensitive raw data out
  of memory and Git. Record safe provenance and access requirements instead.
- Do not infer permission to create a repository, push, publish, upload raw
  transcripts, or mutate external systems. Do those only when authorized.

## Choose the operating mode

1. **Bootstrap:** inspect the project and create memory for the first time.
2. **Update:** record new instructions, decisions, evidence, failures, or a
   completed stage without re-auditing everything.
3. **Resume:** reconstruct the live task after context loss or handoff, then
   reconcile memory against the current workspace before acting.
4. **Audit:** check memory for drift, unsupported claims, missing paths,
   contradictions, excessive size, or unsafe content.

Read [references/maintenance-modes.md](references/maintenance-modes.md) for the
selected mode. Do not load mode details that are irrelevant to the request.

## Establish the memory boundary

Use a user-specified location. Otherwise choose a discoverable, project-local
directory such as `project-memory/` or `codex_memory/`. If a memory directory
already exists, inspect and reuse or update it; never replace it. If the
requested location conflicts with unrelated existing content, ask before
choosing a different location. Inspect repository instructions and existing
memory first.

Before bootstrapping, inventory the relevant roots, repository state, current
task history, active processes/runs, and authoritative output locations. When
large trees contain mirrors, record every requested path but content-deduplicate
exact mirrors rather than treating them as independent evidence.

Use the smallest structure that supports reliable continuation. A mature,
multi-stage project commonly benefits from:

- an index;
- durable user directives and authorization boundaries;
- current established state and limitations;
- an append-only decision log;
- an experiment/work ledger;
- an exact next checkpoint;
- a source/provenance map.

These filenames are conventions, not universal requirements. Read
[references/memory-schema.md](references/memory-schema.md) when bootstrapping or
restructuring memory.

## Update at material boundaries

Update memory when any of these changes what a future agent should do or
believe:

- a user adds or changes scope, constraints, permissions, identity, or delivery
  requirements;
- a protocol, architecture, design, or evaluation rule is frozen;
- a meaningful stage succeeds, fails, is invalidated, or is interrupted;
- evidence changes the current conclusion or closes/reopens a direction;
- an external dependency, license, access condition, or blocker is discovered;
- a reproducible handoff, commit, report, or publication checkpoint is created.

Do not turn every tool call into memory. Prefer coherent milestone updates.
Record exact interruption state before recovery, and keep failed/superseded runs
addressable. For evidence classification and recovery records, read
[references/evidence-and-handoffs.md](references/evidence-and-handoffs.md).

## Resume safely

On resume, read the index, directives, current state, decision log tail, and
next checkpoint. Then inspect the actual workspace, repository status, terminal
markers, active processes, available resources, and newest task history.
Reconcile discrepancies explicitly. Do not rerun a stage merely because memory
says it was pending if a terminal artifact now exists; do not trust a claimed
completion if its artifacts are absent or changed.

End a working session with an exact handoff: what is established, what remains
uncertain, the last valid artifact/commit/run, the next bounded action, and the
conditions that would change that action.

## Keep memory usable

- Summarize raw logs and transcripts; retain or link raw provenance only when
  it has future evidentiary value or the user requests it.
- Use dates and stable identifiers. Prefer links over duplicating large data.
- Keep current-state files concise by moving completed detail to dedicated
  records while retaining a short current conclusion.
- Check links and structure with
  `scripts/validate_memory.py <memory-dir> --strict` when the conventional
  index/schema is used. This validator is diagnostic and must not rewrite
  memory. Its default mode permits schema warnings; it does not prove semantic
  claim consistency or absence of secrets, which still require manual review.
- Commit coherent memory milestones when the memory is already authorized for
  Git. Use the user's required identity, avoid credentials, and verify the
  intended paths before staging. Push only when authorized and technically
  available.

Report material memory changes in the final handoff: location, main conclusion,
next checkpoint, validation result, and commit/push status if applicable.
