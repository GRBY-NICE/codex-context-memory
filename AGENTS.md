Codex Context Memory

A lightweight persistent memory and context-management framework for OpenAI Codex, with optional Claude Code compatibility.

Why this project exists

AI coding agents are highly capable, but long-running projects often suffer from one recurring problem: context disappears between sessions.

Important architectural decisions, implementation constraints, unfinished work, and project state can become scattered across chats, commits, issues, and local notes.

Codex Context Memory provides a simple file-based memory layer that helps coding agents recover project context quickly and continue work with less repetition.

Core idea

The framework separates project context into a few small, structured files:

- "AGENTS.md" — instructions, coding rules, workflow constraints, and agent behavior
- "memory/PROJECT_MEMORY.md" — long-term project knowledge
- "memory/CURRENT_STATE.md" — current progress, active work, blockers, and next steps
- "memory/DECISIONS.md" — important technical and architectural decisions
- "memory/TASKS.md" — open work and priorities
- "memory/HANDOFF.md" — session-to-session handoff notes

Instead of relying on one large prompt, the agent reads only the memory relevant to the current task.

Primary target: OpenAI Codex

This project is designed primarily around Codex workflows.

Typical use cases include:

- long-running software projects
- repository maintenance
- multi-session coding tasks
- architecture preservation
- implementation handoffs
- refactoring across large codebases
- repeated Codex sessions on the same repository

Claude Code compatibility is treated as an optional interoperability layer, not the primary target.

Memory model

The project uses four main layers of memory.

1. Rules memory

Stored in "AGENTS.md".

Contains:

- coding conventions
- repository rules
- testing requirements
- file ownership rules
- agent behavior
- memory update instructions

2. Long-term project memory

Stored in "memory/PROJECT_MEMORY.md".

Contains:

- project goals
- architecture
- major components
- permanent constraints
- important conventions

3. Current working state

Stored in "memory/CURRENT_STATE.md".

Contains:

- current implementation status
- active task
- blockers
- incomplete work
- next recommended action

4. Decision history

Stored in "memory/DECISIONS.md".

Contains major technical decisions and the reasons behind them.

Example workflow

At the beginning of a Codex session:

1. Read "AGENTS.md"
2. Read "memory/PROJECT_MEMORY.md"
3. Read "memory/CURRENT_STATE.md"
4. Read task-specific decision records if needed
5. Continue implementation

At the end of a meaningful task:

1. Update "memory/CURRENT_STATE.md"
2. Record important architectural decisions
3. Update project memory only when long-term facts changed
4. Leave a concise handoff for the next session

Design goals

Codex Context Memory aims to be:

- simple
- transparent
- human-readable
- Git-friendly
- model-agnostic where useful
- Codex-first
- easy to adopt in existing repositories

Planned features

- reusable memory templates
- Codex-oriented "AGENTS.md" templates
- automatic project memory initialization
- Git-aware memory updates
- session handoff generation
- decision log helpers
- context compaction
- optional Claude Code compatibility
- CLI tooling

Planned CLI direction:

codex-memory init
codex-memory status
codex-memory update
codex-memory handoff

Status

Early-stage open-source project.

The current focus is defining a practical memory architecture for persistent Codex workflows before introducing heavier automation.

Contributing

Ideas, issues, examples, and real-world workflow feedback are welcome.

The most useful contributions are examples of where coding agents lose important context during long-running repository work.

License

MIT