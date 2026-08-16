# Project Tasks

## Current milestone

Validate the corrected v0.1 manual memory workflow with Experiment 002.

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

- [ ] Open a fresh Codex session with no prior conversation.
- [ ] Ask it to read repository instructions and all memory files.
- [ ] Verify that it discovers all canonical paths.
- [ ] Verify recovery of project purpose and Codex-first rationale.
- [ ] Verify accurate reporting of current phase, implemented capabilities, limitations, and next action.
- [ ] Verify that it distinguishes durable memory from current state and handoff context.
- [ ] Verify that it finds no path, milestone, or experiment-status contradictions.
- [ ] Record the result in `experiments/002-fresh-codex-session.md`.
- [ ] Update memory files from the experiment evidence.

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

Blocked until the basic Codex workflow has passed fresh-session validation. This work must reuse the shared Markdown memory source rather than create a competing architecture.

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

Run Experiment 002 and record its evidence before starting CLI work or Claude Code compatibility.
