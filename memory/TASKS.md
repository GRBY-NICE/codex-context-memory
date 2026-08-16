# Project Tasks

## Current milestone

Validate the corrected v0.1 manual memory workflow with Experiment 002.

## Foundation

- [x] Create repository structure.
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
- [ ] Add a complete workflow example.
- [ ] Document the memory lifecycle.
- [ ] Document stale-memory risks.
- [ ] Add security guidance.
- [ ] Add contribution guidance.

## Claude Code compatibility

Blocked until the basic Codex workflow has passed fresh-session validation.

- [ ] Research the minimum useful `CLAUDE.md` adapter.
- [ ] Keep the Markdown memory files as the shared source of truth.
- [ ] Avoid creating a separate Claude-only memory architecture.

## v0.2 automation

Do not begin until v0.1 has repeatable validation evidence.

- [ ] Design CLI commands.
- [ ] Add Git-aware change detection.
- [ ] Add memory compaction.
- [ ] Add stale-memory warnings.
- [ ] Add a memory diff view.
- [ ] Add validation for missing or broken references.
- [ ] Add secret scanning.

## v0.3 packaging

- [ ] Add global installation.
- [ ] Add project initialization.
- [ ] Add migration support.
- [ ] Add package documentation.

## Immediate next task

Run Experiment 002 and record its evidence before starting CLI work or Claude Code compatibility.
