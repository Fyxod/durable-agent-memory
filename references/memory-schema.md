# Memory schema patterns

Use only files justified by project complexity. Names may follow existing
project conventions.

## Index

Purpose, authoritative project roots, file map, memory contract, current short
status, and how to resume. Keep this cheap to read.

## User directives

Record durable scope, priorities, constraints, permission boundaries, required
identity/authorship, preservation rules, output requirements, and later changes
with dates. Quote or precisely paraphrase consequential authorization.

## Current state

Lead with the newest established conclusion. Include:

- what is proven;
- what is partial or merely mechanistic;
- what failed or remains unsupported;
- exact evidence/run/commit paths;
- current operational state;
- active blockers.

Keep historical detail elsewhere and link it.

## Decision log

Append dated decisions with rationale, alternatives closed or retained,
evidence used, and downstream consequence. Preserve reversals as new entries.

## Work or experiment ledger

One record per meaningful unit: identifier, question, inputs/protocol, status,
terminal marker, result class, confounds, evidence paths, and follow-up. Exact
mirrors are not independent experiments.

## Next checkpoint

State the last terminal checkpoint and one exact next bounded action. Include
frozen inputs/configs, success/failure gates, stop conditions, and pointers
needed to resume. Clearly label proposed work that has not begun.

## Source map

Map claims to local artifacts and primary external sources. Record immutable
revisions/hashes when reproducibility matters. Do not copy secrets or gated
credentials.

## Optional specialized records

Use dedicated files for a large completed phase, architecture audit, risk
register, report lineage, corpus coverage manifest, or research-value map when
that detail would overwhelm current state.

## Machine-readable staging

Large inventories, duplicate maps, or raw audit tables may live in a staging
area and be compressed for Git. Keep a human-readable synthesis and document
which raw files are intentionally local. Do not delete source data merely to
make memory smaller.
