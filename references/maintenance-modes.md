# Maintenance modes

Read only the section matching the current request.

## Bootstrap

1. Locate project instructions, repositories, current task history, relevant
   roots, authoritative outputs, and any previous memory or transcripts.
2. Inventory before interpreting. Record requested paths, file counts/sizes,
   repositories, run markers, and exact mirrors. Use hashes or content-aware
   comparison when a duplicate would otherwise be mistaken for replication.
3. Read high-value entrypoints first—README files, configs, manifests, reports,
   terminal markers, experiment scripts, and version history—then trace claims
   into their underlying artifacts.
4. Create the smallest useful memory schema. Start current conclusions only
   after evidence review; mark review limits honestly.
5. Validate paths and index links. If Git publication is authorized, inspect
   staged paths, file sizes, and secret exposure before the first commit.

## Update

1. Identify what materially changed since the last memory entry.
2. Update directives first when the user changed scope or authorization.
3. Add a dated decision/evidence entry. Update current state and next checkpoint
   only when the new evidence actually changes them.
4. Preserve the prior conclusion in history; explain why the current conclusion
   supersedes it.
5. Check that new claims cite existing artifacts and that planned work is not
   phrased as completed work.

## Resume

1. Read the index, directives, current state, recent decision-log tail, and
   exact next checkpoint.
2. Inspect current repository status, newest run directories and terminal
   markers, process/GPU state when relevant, disk, and the newest task history.
3. Compare memory with reality. Record drift such as a completed run still
   described as active, a changed hash, uncommitted evidence, or an interrupted
   process.
4. Resume from validated artifacts/checkpoints. Never overwrite an interrupted
   run merely to make the memory narrative simpler.

## Audit

Check:

- index links and referenced local paths;
- claims without evidence identifiers;
- contradictions between current state, ledger, and decision log;
- proposals described as results;
- stale next steps after a terminal run;
- unrecorded interruptions/recoveries;
- credentials, tokens, private URLs, or excessive sensitive data;
- large raw logs that should be linked/compressed rather than loaded by default;
- Git status and unpushed material evidence when publication was authorized.

An audit reports issues and makes only scope-authorized corrections. It does
not publish, delete, or rewrite history without permission.
