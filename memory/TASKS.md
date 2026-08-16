Project Tasks

This file tracks actionable work for Codex Context Memory.

Tasks should represent real work that can be completed, reviewed, tested, or discussed.

Current milestone

v0.1 — Manual Memory Framework

Goal:

Build and validate the minimum repository-based persistent memory workflow for OpenAI Codex.

Foundation

- [x] Create public repository
- [x] Create project README
- [x] Define Codex-first direction
- [x] Create "AGENTS.md"
- [x] Create "PROJECT_MEMORY.md"
- [x] Create "CURRENT_STATE.md"
- [x] Create "DECISIONS.md"
- [x] Create "TASKS.md"
- [ ] Create "HANDOFF.md"

Codex validation

- [ ] Open the repository in a fresh Codex session
- [ ] Ask Codex to recover project purpose using repository context
- [ ] Ask Codex to identify the current project state
- [ ] Ask Codex to identify the next development task
- [ ] Verify that Codex distinguishes durable memory from current state
- [ ] Test whether Codex follows the memory update procedure
- [ ] Record observed context failures
- [ ] Document the first real Codex memory experiment

Documentation

- [ ] Add "docs/codex-memory-guide.md"
- [ ] Add "docs/memory-architecture.md"
- [ ] Add a complete Codex workflow example
- [ ] Explain memory lifecycle
- [ ] Explain stale-memory risks
- [ ] Document security guidance
- [ ] Add contribution guidelines

Claude Code compatibility

Do not begin this work until the basic Codex workflow has been tested.

- [ ] Research Claude Code project instruction behavior
- [ ] Define "CLAUDE.md" compatibility strategy
- [ ] Map Claude Code instructions to the shared memory layer
- [ ] Create a Claude Code example
- [ ] Test the same project memory with Codex and Claude Code
- [ ] Document differences between the two workflows

---

v0.2 — Templates and Validation

Goal:

Make the framework easy to add to another repository.

Templates

- [ ] Create reusable "AGENTS.md" template
- [ ] Create project memory template
- [ ] Create current state template
- [ ] Create decision log template
- [ ] Create task template
- [ ] Create handoff template

Validation

- [ ] Define required memory files
- [ ] Detect missing memory files
- [ ] Detect malformed memory structure
- [ ] Detect obviously empty memory sections
- [ ] Explore stale-memory detection
- [ ] Add basic automated tests

Example repositories

- [ ] Create minimal example
- [ ] Create small application example
- [ ] Create long-running project example
- [ ] Document memory changes across multiple sessions

---

v0.3 — CLI Prototype

Goal:

Reduce the manual work required to maintain the memory system.

Proposed command interface:

codex-memory init
codex-memory status
codex-memory validate
codex-memory update
codex-memory handoff

"codex-memory init"

- [ ] Detect repository root
- [ ] Generate memory directory
- [ ] Generate initial memory files
- [ ] Avoid overwriting existing files
- [ ] Generate or extend "AGENTS.md"

"codex-memory status"

- [ ] Display available memory files
- [ ] Display last modification times
- [ ] Identify missing required files
- [ ] Show current milestone
- [ ] Show immediate next task

"codex-memory validate"

- [ ] Validate expected file structure
- [ ] Detect broken references
- [ ] Detect conflicting metadata where possible
- [ ] Warn about likely secrets in memory
- [ ] Return useful exit codes for automation

"codex-memory handoff"

- [ ] Inspect current project state
- [ ] Generate a structured handoff draft
- [ ] Preserve unresolved work
- [ ] Reference relevant files
- [ ] Avoid copying large source files into memory

---

Future research

These are research directions, not committed features.

- [ ] Git diff aware memory updates
- [ ] Commit-aware context reconstruction
- [ ] Issue and pull request context integration
- [ ] Memory relevance scoring
- [ ] Context budget management
- [ ] Automatic context compaction
- [ ] Stale-memory scoring
- [ ] Multi-agent handoff
- [ ] Memory quality benchmarks
- [ ] Token usage comparison
- [ ] Repository-scale experiments

Evaluation questions

The project should eventually produce evidence for questions such as:

1. Does structured repository memory reduce repeated context explanation?
2. Can a fresh Codex session correctly recover project state?
3. Which memory files provide the highest value?
4. How much repository memory should be loaded at startup?
5. When does memory become stale?
6. Can Codex reliably maintain its own project memory?
7. How much context can be removed without reducing task performance?
8. Can Codex and Claude Code safely share the same persistent memory layer?

Task rules

When adding tasks:

- make them concrete
- make them testable when possible
- avoid vague tasks such as "improve memory"
- do not mark work complete before verifying it
- move durable conclusions into project memory or decisions

When a task changes project architecture, review "DECISIONS.md".

When completing meaningful work, update "CURRENT_STATE.md".

Immediate next task

Create:

"memory/HANDOFF.md"

After the manual memory architecture is complete, perform the first fresh-session Codex experiment.