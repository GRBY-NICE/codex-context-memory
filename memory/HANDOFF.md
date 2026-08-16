Session Handoff

«Last updated: 2026-08-16»

This file provides a concise handoff for the next Codex session.

It is temporary operational context.

Do not treat this file as permanent project history.

For durable project knowledge, use "PROJECT_MEMORY.md".

For architectural reasoning, use "DECISIONS.md".

For the latest overall project status, use "CURRENT_STATE.md".

Session objective

Establish the minimum persistent memory architecture for Codex Context Memory.

Work completed

The repository now has the core manual memory structure:

README.md
AGENTS.md

memory/
├── PROJECT_MEMORY.md
├── CURRENT_STATE.md
├── DECISIONS.md
├── TASKS.md
└── HANDOFF.md

The project has established:

- Codex as the primary agent target
- Claude Code as a secondary compatibility target
- repository-based persistent context
- Markdown as the initial memory format
- separation between durable memory and temporary state
- architectural decision tracking
- explicit task tracking
- session-to-session handoff rules

Important decisions

Before changing the memory architecture, review:

"memory/DECISIONS.md"

Important accepted decisions currently include:

- memory lives inside the repository
- Markdown is the primary memory format
- Codex is the primary agent target
- memory is separated by responsibility
- full conversation transcripts are not persistent memory
- repository reality overrides stale memory

Current state

The manual memory architecture is now structurally complete.

However, it has not yet been validated through a fresh Codex session.

Do not describe the framework as proven or production-ready.

Immediate next step

Run the first fresh-session Codex memory experiment.

The experiment should determine whether Codex can recover project context without access to the conversation that created these files.

Suggested experiment

Open a fresh Codex session with access to this repository.

Do not manually explain the project.

Ask Codex:

«Read the repository instructions and memory files. Without making any changes, tell me:

1. What is this project trying to solve?
2. Why is Codex the primary target?
3. What is the current development stage?
4. What architectural decisions must be preserved?
5. What should be worked on next?
6. Which files did you use to reconstruct this context?»

Compare the response with the repository memory.

Success criteria

The experiment succeeds if Codex can correctly identify:

- the persistent context problem
- the Codex-first design
- the repository-based memory architecture
- the current v0.1 stage
- the major architectural decisions
- the next development task
- the difference between durable memory and temporary state

Codex should reach these conclusions from repository context rather than additional explanation from the user.

Failure cases to record

Record a failure if Codex:

- ignores "AGENTS.md"
- misses important memory files
- treats planned CLI features as already implemented
- confuses "CURRENT_STATE.md" with durable memory
- ignores architectural decisions
- cannot determine the next task
- requires the user to explain information already stored in memory
- invents project capabilities
- loads unnecessary context without reason

After the experiment

Do not simply mark the experiment complete.

Record what actually happened.

Create an experiment document such as:

"experiments/001-fresh-codex-session.md"

It should include:

- experiment goal
- environment
- prompt used
- expected behavior
- observed behavior
- failures
- useful observations
- changes made as a result
- conclusion

If the experiment reveals a design problem:

1. update the relevant implementation or memory rule
2. update "CURRENT_STATE.md"
3. create a new decision entry if architecture changes
4. update "TASKS.md"
5. refresh this handoff

Files the next session should inspect

Start with:

1. "AGENTS.md"
2. "memory/PROJECT_MEMORY.md"
3. "memory/CURRENT_STATE.md"

Then inspect:

4. "memory/DECISIONS.md"
5. "memory/TASKS.md"

Use this handoff only for the immediate continuation context.

Known limitations

The framework is currently manual.

There is no CLI.

There is no automatic synchronization.

There is no stale-memory detector.

There is no automated validation.

There is no completed Claude Code compatibility layer.

There are no benchmark results yet.

These limitations are intentional at this stage and should not be hidden.

Handoff rule

Replace or substantially rewrite this file when the immediate continuation context changes.

Do not endlessly append old session handoffs.

Git history already preserves previous versions.

The purpose of this file is to answer one question:

«What does the next coding-agent session need to know to continue safely?»