# Evidence, interruption, and handoff discipline

## Claim classes

Label conclusions at the correct level:

- **implemented:** code/config exists, but meaningful runtime validation may not;
- **smoke-validated:** basic execution, determinism, gradients, or invariants
  pass;
- **internal movement:** a loss/activation/score changed without endpoint proof;
- **partial endpoint:** a visible or product outcome weakened but did not meet
  the strict gate;
- **controlled success:** the declared endpoint passed and relevant controls did
  not reproduce it;
- **replicated/generalized:** a separately frozen test passed across the stated
  held-out dimensions;
- **null/failed/invalid:** distinguish a valid negative result from a broken or
  confounded run.

Adapt these names to the project, but retain the separation between execution,
internal diagnostics, endpoint outcomes, and generalization.

## Evidence record

For a material run or delivery, preserve as applicable:

- resolved config and immutable dependency/model revisions;
- input/source hashes and selection rules;
- code/commit hash;
- history/logs and checkpoints;
- controls and evaluation contract;
- terminal `DONE`, `FAILED`, or `INVALID` marker;
- exact output/report paths;
- visual/manual review provenance;
- honest conclusion and limitations.

## Interrupted work

When a process disappears or a stage is interrupted:

1. Inspect active processes and existing terminal markers.
2. Do not overwrite or automatically label the partial directory successful.
3. Record the last complete unit, counts, state/config hashes, and whether any
   endpoint output was generated or viewed.
4. Prefer append-only recovery from a validated deterministic prefix or saved
   checkpoint. Freeze a recovery contract before resuming when chronology or
   selection leakage matters.
5. If recovery changes the scientific protocol, treat it as a new run rather
   than silent continuation.

## Handoff record

An exact handoff answers:

- What is the latest valid conclusion?
- Which artifact, run, branch, or commit proves it?
- What is still uncertain or blocked?
- What process, if any, is currently active?
- What precise action should happen next?
- Which frozen rule or observation would stop or change that action?
- Which files are local-only, uncommitted, or unpushed?

Avoid vague instructions such as “continue experimenting.” A future agent
should be able to resume without outcome-driven improvisation.
