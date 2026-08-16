Project Memory

This file contains durable project knowledge for Codex Context Memory.

It should store facts that are expected to remain useful across many sessions.

Temporary progress, active tasks, blockers, and short-term notes belong in "CURRENT_STATE.md", not here.

Project identity

Name: Codex Context Memory

Primary target: OpenAI Codex

Secondary compatibility target: Claude Code

Project type: Open-source persistent context and memory framework for AI coding agents

Current stage: Early architecture and documentation phase

Project purpose

Codex Context Memory exists to solve a common problem in long-running AI-assisted software development:

important context is often lost, fragmented, or repeatedly re-explained between coding sessions.

The project provides a lightweight, Git-friendly, human-readable memory layer that allows Codex to recover important project context directly from the repository.

The system should reduce dependence on hidden chat history and make project state easier to inspect by both humans and coding agents.

Core principles

The project follows these principles:

1. Codex-first design
2. Human-readable memory
3. Git-friendly storage
4. Minimal dependencies
5. Explicit context hierarchy
6. Small and focused memory files
7. Clear separation between durable and temporary context
8. Compatibility without duplicate sources of truth
9. Easy adoption in existing repositories
10. Memory should support work, not become additional maintenance burden

Memory architecture

The shared memory layer currently consists of:

"AGENTS.md"

Repository-level instructions for coding agents.

Responsible for:

- startup behavior
- context loading order
- coding rules
- memory update rules
- end-of-session procedures

"memory/PROJECT_MEMORY.md"

Long-term project knowledge.

Responsible for:

- project purpose
- architecture
- permanent constraints
- stable conventions
- long-lived compatibility requirements

"memory/CURRENT_STATE.md"

Short-term operational state.

Responsible for:

- current progress
- active implementation
- blockers
- incomplete work
- next recommended action

"memory/DECISIONS.md"

Long-term technical decision history.

Responsible for:

- architectural decisions
- important technical tradeoffs
- superseded decisions
- rationale that future agents should preserve

"memory/TASKS.md"

Actionable project work.

Responsible for:

- planned work
- priorities
- concrete implementation tasks
- completion tracking

"memory/HANDOFF.md"

Session continuation context.

Responsible for:

- work completed during the latest session
- unfinished work
- important files
- warnings
- immediate next steps

Source-of-truth philosophy

The repository itself is the source of truth.

Memory files must never override clearly observable facts in current source code or configuration.

When memory conflicts with the implementation:

1. inspect the implementation
2. determine whether the memory is stale
3. update the memory if necessary
4. preserve important historical decisions in "DECISIONS.md"

Memory exists to summarize project reality, not replace it.

Context hierarchy

The intended context hierarchy is:

1. current repository code and configuration
2. explicit agent instructions
3. recorded technical decisions
4. durable project memory
5. current operational state
6. handoff notes
7. conversational context

This hierarchy is intended to reduce accidental dependence on stale chat history.

Codex integration philosophy

Codex should be able to enter the repository and quickly determine:

- what the project does
- what rules it must follow
- what has already been decided
- what state the project is currently in
- what work remains
- what should happen next

The system should avoid requiring one extremely large instruction file.

Context should instead be separated by purpose and loaded only when relevant.

Claude Code compatibility

Claude Code is a secondary compatibility target.

Compatibility should not create a separate memory system.

If a "CLAUDE.md" compatibility layer is introduced, it should point to or reuse the same shared memory files.

The project should avoid maintaining two competing sources of truth for Codex and Claude Code.

Planned technical direction

The project may evolve from a file-based framework into a small CLI tool.

Potential commands include:

codex-memory init
codex-memory status
codex-memory update
codex-memory handoff
codex-memory validate

Potential future capabilities include:

- automatic memory initialization
- template generation
- Git-aware project state detection
- memory consistency validation
- context compaction
- session handoff generation
- architecture decision helpers
- stale-memory detection
- repository health checks
- Claude Code compatibility generation

These are planned directions, not implemented features.

Storage model

The initial storage format is Markdown.

Reasons:

- easy for humans to read
- easy for coding agents to parse
- easy to review in Git
- no database required
- portable across platforms
- simple to integrate into existing repositories

Structured formats such as JSON or YAML may be introduced later for machine-readable metadata, but Markdown should remain a first-class interface.

Non-goals

The project is not intended to:

- permanently store full conversation histories
- copy entire codebases into memory files
- replace Git
- replace issue trackers
- replace documentation
- provide hidden or opaque agent memory
- claim to be an official OpenAI memory implementation

The project is community-built and independent.

Naming conventions

Use the term memory for structured repository context that persists across sessions.

Use current state for temporary implementation status.

Use handoff for continuation information between working sessions.

Use decision for durable architectural or technical choices.

Avoid ambiguous terms such as "brain", "internal memory", or "hidden memory" in technical documentation unless explaining concepts.

Documentation style

Documentation should be:

- concise
- practical
- example-driven
- technically accurate
- explicit about implemented versus planned features

Avoid claiming features that do not yet exist.

Security and privacy principles

Memory files must not encourage storing:

- API keys
- access tokens
- passwords
- private credentials
- sensitive personal information

Future tooling should provide warnings or validation for obvious secrets where practical.

Long-term success criteria

The project is successful if a developer can:

1. add the framework to a repository
2. open a fresh Codex session
3. allow Codex to recover meaningful context from repository files
4. continue work without manually re-explaining major project history
5. review and correct the agent's memory using ordinary Git workflows

The memory system should remain understandable even without specialized software.