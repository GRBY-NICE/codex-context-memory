Current State

«Last updated: 2026-08-16»

This file describes the current operational state of Codex Context Memory.

Unlike "PROJECT_MEMORY.md", this document is expected to change frequently as development progresses.

Current phase

Phase: Foundation / v0.1 design

The project is currently establishing the first version of its persistent context architecture.

The immediate goal is to create a complete minimal memory system that can be tested with real Codex workflows before building automation around it.

Completed

The following foundation work has been completed:

- Public GitHub repository created
- Initial project README created
- Codex-first project direction defined
- "AGENTS.md" agent instructions created
- Memory hierarchy defined
- Long-term "PROJECT_MEMORY.md" created
- Claude Code compatibility established as a secondary project goal
- Markdown selected as the initial memory storage format

Current architecture

The intended repository memory structure is:

AGENTS.md

memory/
├── PROJECT_MEMORY.md
├── CURRENT_STATE.md
├── DECISIONS.md
├── TASKS.md
└── HANDOFF.md

Currently implemented:

AGENTS.md
memory/PROJECT_MEMORY.md
memory/CURRENT_STATE.md

Still to be added:

memory/DECISIONS.md
memory/TASKS.md
memory/HANDOFF.md

Current focus

Complete the minimum viable memory architecture.

The next files should define:

1. architectural decision records
2. actionable task tracking
3. session handoff behavior

After these files exist, the memory workflow should be tested manually using a fresh Codex session.

Active work

Memory architecture

Status: In progress

Goal:

Create a small set of repository files that allows a fresh Codex session to reconstruct enough project context to continue meaningful work.

Codex workflow

Status: Designing

The intended session workflow is:

Start Codex session
        ↓
Read AGENTS.md
        ↓
Read PROJECT_MEMORY.md
        ↓
Read CURRENT_STATE.md
        ↓
Read relevant decisions/tasks
        ↓
Perform work
        ↓
Validate changes
        ↓
Update CURRENT_STATE
        ↓
Write HANDOFF if necessary

Claude Code compatibility

Status: Planned

Claude Code support will be introduced only after the Codex-first memory workflow is functional.

The compatibility layer should reuse the same memory files instead of creating an independent memory database.

Not implemented yet

The following features are ideas or planned work and must not be described as completed functionality:

- CLI
- automatic memory updates
- Git-aware state detection
- context compaction
- stale-memory detection
- automatic handoff generation
- memory validation
- secret detection
- Claude Code adapter
- installation command
- package distribution

Known limitations

The current system is entirely file-based and manually maintained.

There is currently no automated mechanism to determine whether memory is stale.

There is currently no validation that agents actually update memory after completing work.

The architecture has not yet been tested across multiple real-world repositories.

Token usage and context-loading efficiency have not yet been benchmarked.

Questions to validate

The project should eventually test:

- How much context does Codex actually need at session startup?
- Which memory files should always be loaded?
- Which files should be loaded only when relevant?
- When should Codex update memory?
- How can stale memory be detected?
- How much duplication between memory and documentation is acceptable?
- Can Git history help reconstruct missing context?
- Does structured memory reduce repeated explanations between sessions?
- How well can the same memory layer support Claude Code?
- At what repository size does manual memory management become inconvenient?

Next milestone

v0.1 — Manual Memory Framework

The first milestone should provide a complete manual persistent-memory workflow.

Required components:

- [x] README
- [x] AGENTS instructions
- [x] Project memory
- [x] Current state
- [ ] Decision log
- [ ] Task tracker
- [ ] Session handoff
- [ ] Codex usage example
- [ ] Claude Code compatibility documentation
- [ ] Manual workflow test

Immediate next action

Create:

"memory/DECISIONS.md"

The first decision record should document why the project uses:

repository-based Markdown memory instead of an external database.

This will also provide a concrete example of how architectural decisions should be preserved.

Maintainer note

Keep this file short enough that a new Codex session can understand current project status quickly.

When work progresses:

- move durable facts into "PROJECT_MEMORY.md"
- preserve important architectural choices in "DECISIONS.md"
- remove obsolete temporary information
- update the immediate next action

Do not turn this file into a permanent chronological development log.