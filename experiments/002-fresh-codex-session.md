Experiment 002 — Fresh Codex Session Context Recovery

Date: 2026-08-16
Status: Completed
Result: Success

Objective

Determine whether a fresh OpenAI Codex session can reconstruct the Codex Context Memory project accurately after the path, instruction, and state-consistency repairs prompted by Experiment 001.

Test conditions

- The Codex session had no access to the conversation that created or repaired the memory architecture.
- The session was instructed to derive its answer entirely from the repository.
- It was instructed to read repository instructions and all memory files.
- It was instructed not to modify repository files.
- The repository state under test was `main` after pull request #1, with head commit `ea1185d3663752df0d8347c4296e49e77d513c03`.

Test prompt

The fresh session was asked to reconstruct:

1. the problem the project is solving;
2. why OpenAI Codex is the primary target;
3. the current development stage;
4. architectural decisions future agents must preserve;
5. the next work item;
6. the responsibilities of the five memory files;
7. the repository files used; and
8. contradictions, stale information, missing files, or design weaknesses.

It was also asked to state explicitly whether Experiment 001 was complete, whether CLI automation or Claude Code compatibility existed, and whether all required memory files were present at their documented paths.

Expected behavior

A successful run should:

- discover all five memory files through their canonical paths;
- reconstruct the project purpose and Codex-first rationale;
- report the current phase and immediate next action accurately;
- distinguish implemented manual behavior from planned automation;
- recognize Experiment 001 as completed;
- find no current path, milestone, or experiment-status contradiction; and
- require no additional project explanation from the maintainer.

Observed behavior

The fresh session reconstructed the project from repository context alone. It read every tracked repository file and inspected the branch, Git status, tracked tree, canonical memory paths, experiment directory, nested-directory state, internal references, and the path-repair commit.

It correctly reported that:

- the project addresses context loss between coding-agent sessions;
- the solution is a repository-native, Markdown-based memory layer;
- Codex is the primary target so a concrete workflow can be validated before broader compatibility work;
- the project remains in Foundation — v0.1 manual workflow validation;
- Experiment 001 was completed with a partial-success result;
- all five required memory files exist directly under `memory/`;
- `memory/memory/` no longer exists;
- CLI automation, automatic validation, and stale-memory detection are not implemented;
- Claude Code compatibility is not implemented;
- Experiment 002 was the immediate next repository action; and
- the six accepted architectural decisions remain the controlling design constraints.

Success-criteria assessment

- Required files discovered at documented paths: PASS
- Project purpose and Codex-first rationale recovered: PASS
- Current phase and immediate next action reported accurately: PASS
- Implemented behavior distinguished from planned automation: PASS
- Experiment 001 status reported accurately: PASS
- Path consistency: PASS
- Milestone and cross-file status consistency: PASS
- Recovery without previous conversation: PASS

Current contradictions

No material contradiction was found among `memory/CURRENT_STATE.md`, `memory/TASKS.md`, and `memory/HANDOFF.md`. Historical defects described by Experiment 001 were correctly treated as dated evidence rather than current state.

Minor weaknesses discovered

1. README layer description

`README.md` says the project uses “four main layers of memory” even though its canonical file list also includes task and handoff responsibilities. The path list is correct, but the layer explanation incompletely represents the responsibility-separated model.

2. Mutable state in durable memory

`memory/PROJECT_MEMORY.md` contains a `Current stage` field even though the current phase is formally owned by `memory/CURRENT_STATE.md`. The values currently agree, but this creates an avoidable future drift risk.

These weaknesses did not prevent accurate recovery and are not current status contradictions. They should be corrected before the next workflow experiment.

Remaining design limitations

- Memory maintenance and consistency checks remain manual.
- There is no automated stale-memory, schema, or broken-link detection.
- Evidence is limited to this repository and two fresh-session experiments.
- Token cost and context-loading efficiency have not been measured.
- The workflow still depends on agents following `AGENTS.md`.

Conclusion

Experiment 002 succeeded.

The repairs made after Experiment 001 allowed a fresh Codex session to discover the canonical memory structure, reconstruct the project accurately, distinguish planned work from implemented behavior, and find no material current-state contradiction.

This provides stronger evidence that the manual v0.1 architecture can support fresh-session context recovery. It does not prove automated consistency, cross-repository portability, or reliable memory updates after real implementation work.

Changes made as a result

- Added this experiment record.
- Updated `memory/CURRENT_STATE.md` to mark Experiment 002 successful.
- Updated `memory/TASKS.md` to complete the Experiment 002 checklist and track the two minor documentation weaknesses.
- Updated `memory/HANDOFF.md` with the next continuation point.

Next action

Correct the README layer description and remove or reframe the mutable current-stage field in `PROJECT_MEMORY.md`. Then test whether a fresh Codex session follows the memory update procedure after completing real work.
