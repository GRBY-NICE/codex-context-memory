# Project Tasks

## Current milestone

Close the minor documentation weaknesses found by Experiment 002, then test memory updates after real work.

## Foundation

- [x] Create the public repository and base structure.
- [x] Add `README.md`.
- [x] Define the Codex-first direction.
- [x] Add `AGENTS.md`.
- [x] Add `memory/PROJECT_MEMORY.md`.
- [x] Add `memory/CURRENT_STATE.md`.
- [x] Add `memory/DECISIONS.md`.
- [x] Add `memory/TASKS.md`.
- [x] Add `memory/HANDOFF.md`.
- [x] Record the initial architectural decisions.
- [x] Correct the unintended nested paths for `DECISIONS.md` and `HANDOFF.md`.

## Experiment 001 follow-up

- [x] Record Experiment 001 as a partial success.
- [x] Synchronize completed foundation work in `CURRENT_STATE.md` and `TASKS.md`.
- [x] Refresh `HANDOFF.md` so it no longer claims Experiment 001 is pending.
- [x] Strengthen `AGENTS.md` with operational recovery and maintenance rules.
- [x] Define manual path, consistency, and diff-scope validation.
- [x] Reduce duplicated frequently changing state.

## Experiment 002

- [x] Open a fresh Codex session with no prior conversation.
- [x] Ask it to read repository instructions and all memory files.
- [x] Verify that it discovers all canonical paths.
- [x] Verify recovery of project purpose and Codex-first rationale.
- [x] Verify accurate reporting of current phase, implemented capabilities, limitations, and next action.
- [x] Verify that it distinguishes durable memory from current state and handoff context.
- [x] Verify that it finds no path, milestone, or experiment-status contradictions.
- [x] Record the result in `experiments/002-fresh-codex-session.md`.
- [x] Update memory files from the experiment evidence.

## Experiment 002 follow-up

- [ ] Update the README layer explanation so it represents task and handoff responsibilities as well as the four conceptual layers.
- [ ] Remove or reframe the mutable `Current stage` field in `PROJECT_MEMORY.md`; keep current phase canonical in `CURRENT_STATE.md`.

## Remaining v0.1 validation

- [ ] Test whether a fresh Codex session follows the memory update procedure after completing real work.
- [ ] Run the workflow in a second repository.
- [ ] Measure prompt and memory token cost.
- [ ] Document failure cases and recovery guidance.

## Documentation

- [ ] Write `docs/codex-memory-guide.md`.
- [ ] Write `docs/memory-architecture.md`.
- [ ] Add a complete Codex workflow example.
- [ ] Document the memory lifecycle.
- [ ] Document stale-memory risks.
- [ ] Add security guidance.
- [ ] Add contribution guidance.

## Claude Code compatibility

Deferred until the remaining v0.1 validation and documentation work is complete. Fresh-session recovery success alone does not authorize this work. Any future adapter must reuse the shared Markdown memory source rather than create a competing architecture.

- [ ] Research Claude Code project-instruction behavior.
- [ ] Define the minimum useful `CLAUDE.md` adapter.
- [ ] Map Claude Code instructions to the shared memory layer.
- [ ] Create a Claude Code example.
- [ ] Test the same project memory with Codex and Claude Code.
- [ ] Document differences between the two workflows.

## v0.2 — Templates and validation

Do not begin until v0.1 has repeatable validation evidence.

### Templates

- [ ] Create a reusable `AGENTS.md` template.
- [ ] Create project-memory, current-state, decision-log, task, and handoff templates.

### Validation

- [ ] Define required memory files in a machine-checkable form.
- [ ] Detect missing files, malformed structure, and obviously empty sections.
- [ ] Explore stale-memory detection.
- [ ] Add basic automated tests.

### Example repositories

- [ ] Create minimal, small-application, and long-running-project examples.
- [ ] Document memory changes across multiple sessions.

## v0.3 — CLI prototype

Do not begin implementation until the v0.1 and v0.2 evidence supports the command design.

### Proposed commands

- [ ] Design `codex-memory init` to detect the repository root, generate missing memory files, avoid overwrites, and generate or extend `AGENTS.md`.
- [ ] Design `codex-memory status` to show available files, modification times, missing files, the current milestone, and the immediate next task.
- [ ] Design `codex-memory validate` to detect structural problems, broken references, conflicting metadata, and likely secrets, with useful exit codes.
- [ ] Design `codex-memory update` around verified repository changes without inventing state.
- [ ] Design `codex-memory handoff` to draft concise continuation context while preserving unresolved work.

## Future research

These are research directions, not committed or implemented features.

- [ ] Git-diff-aware memory updates.
- [ ] Commit-aware context reconstruction.
- [ ] Issue and pull-request context integration.
- [ ] Memory relevance scoring and context-budget management.
- [ ] Automatic context compaction.
- [ ] Stale-memory scoring.
- [ ] Multi-agent handoff.
- [ ] Memory quality benchmarks and token-usage comparisons.
- [ ] Repository-scale experiments.

## Immediate next task

Correct the two minor documentation weaknesses found by Experiment 002. Then run the real-work memory-update validation before starting CLI work or Claude Code compatibility.
