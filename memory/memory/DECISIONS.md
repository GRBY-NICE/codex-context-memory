Architecture Decisions

This file records durable architectural and technical decisions for Codex Context Memory.

The purpose is not to record every implementation detail.

A decision belongs here when future maintainers or coding agents may reasonably ask:

«Why was the project designed this way?»

Decision format

Use the following structure for new decisions:

## DEC-XXX — Decision title

**Date:** YYYY-MM-DD  
**Status:** Proposed | Accepted | Superseded | Rejected

### Context

What problem required a decision?

### Decision

What was decided?

### Rationale

Why was this option selected?

### Alternatives considered

What other approaches were considered?

### Consequences

What tradeoffs or constraints does this decision introduce?

---

Accepted Decisions

DEC-001 — Use repository-based memory

Date: 2026-08-16
Status: Accepted

Context

Coding agents frequently work across multiple sessions.

Conversation history may be unavailable, incomplete, difficult to inspect, or disconnected from the current state of the repository.

The project needs a persistent context layer that survives individual coding sessions.

Decision

Persistent project memory will be stored inside the repository.

Memory will live alongside the code instead of depending entirely on external conversation history or an external memory service.

Rationale

Repository-based memory provides several advantages:

- survives individual agent sessions
- travels with the project
- can be reviewed by humans
- can be versioned with Git
- works across different development environments
- does not depend on a proprietary memory backend
- allows Codex to inspect context using normal repository access

Alternatives considered

External memory service

A database or hosted service could provide more advanced retrieval.

Rejected for the initial architecture because it introduces infrastructure, authentication, synchronization, and portability concerns.

It may be explored later as an optional extension.

Conversation history only

Rejected because project continuity should not depend on access to previous conversations.

Git history only

Git provides implementation history but does not reliably preserve intent, blockers, current priorities, or architectural reasoning in a concise form.

Consequences

Memory files must be maintained alongside the repository.

Stale memory becomes a possible failure mode.

Future tooling should therefore help detect inconsistencies between repository state and recorded memory.

---

DEC-002 — Markdown is the primary memory format

Date: 2026-08-16
Status: Accepted

Context

The project needs a storage format that can be read and edited by:

- developers
- Codex
- other coding agents
- GitHub
- ordinary text editors

Decision

Markdown will be the primary human-facing memory format.

Rationale

Markdown is:

- human-readable
- Git-friendly
- portable
- easy for coding agents to interpret
- easy to review in pull requests
- supported by GitHub
- independent of specialized software

It also keeps the initial implementation lightweight.

Alternatives considered

JSON

Useful for strict machine-readable structures but less comfortable for long-form reasoning and human editing.

YAML

More readable than JSON but still introduces structural sensitivity and is less suitable for narrative architectural context.

SQLite

Powerful for structured retrieval but unnecessary for the initial manual framework.

Consequences

The first version of the system will prioritize readability over strict schemas.

Machine-readable metadata may later be added without replacing Markdown as the primary interface.

---

DEC-003 — Codex is the primary agent target

Date: 2026-08-16
Status: Accepted

Context

Different coding agents use different instruction files and context-management conventions.

Trying to optimize equally for every coding agent from the beginning would make the architecture harder to evaluate.

Decision

OpenAI Codex will be the primary design target.

Claude Code will be supported as a secondary compatibility target.

Rationale

A clear primary target allows the project to develop concrete workflows instead of becoming a generic collection of prompts.

The project can first evaluate:

- Codex session startup
- repository instruction loading
- persistent project state
- long-running tasks
- agent handoffs
- context efficiency

Compatibility can then be built around a stable shared memory model.

Alternatives considered

Fully agent-neutral design

Rejected for the initial version because it risks optimizing for theoretical portability instead of practical workflows.

Separate Codex and Claude Code memory systems

Rejected because duplicate memory stores could drift and contradict one another.

Consequences

Documentation and examples should demonstrate Codex first.

Compatibility features should not weaken the Codex workflow.

---

DEC-004 — Separate memory by responsibility

Date: 2026-08-16
Status: Accepted

Context

A single large memory file is simple initially but becomes increasingly difficult to maintain as a project grows.

Long-term architecture, temporary state, tasks, and session notes have different lifetimes.

Decision

Persistent context will be separated into focused files:

AGENTS.md
memory/
├── PROJECT_MEMORY.md
├── CURRENT_STATE.md
├── DECISIONS.md
├── TASKS.md
└── HANDOFF.md

Rationale

Different information has different lifetimes.

For example:

"PROJECT_MEMORY.md" may remain valid for months.

"CURRENT_STATE.md" may change several times per day.

"HANDOFF.md" may become obsolete after the next session.

Separating these responsibilities makes it possible for an agent to load only the context relevant to a task.

Alternatives considered

One MEMORY.md file

Simpler but likely to become large, repetitive, and difficult to keep current.

One file per session

Provides detailed history but can create excessive context and make retrieval difficult.

Consequences

Agents must understand which file should contain each type of information.

The rules in "AGENTS.md" define these responsibilities.

---

DEC-005 — Do not store full conversation history

Date: 2026-08-16
Status: Accepted

Context

One possible approach to persistent agent memory is storing complete conversations.

However, full transcripts contain large amounts of temporary discussion, repeated explanations, abandoned ideas, and irrelevant context.

Decision

Codex Context Memory will preserve distilled project knowledge rather than full conversation transcripts.

Rationale

Persistent memory should answer:

- What matters now?
- What has been decided?
- What constraints must remain?
- What work is unfinished?
- What should happen next?

It should not attempt to reproduce every interaction that produced those facts.

Alternatives considered

Store complete transcripts

Rejected as the default because it increases context size and makes important information harder to identify.

Store AI-generated conversation summaries

Potentially useful, but summaries should ultimately be converted into the appropriate structured memory layer.

Consequences

Some historical detail will intentionally be discarded.

Important reasoning must therefore be preserved explicitly in "DECISIONS.md".

---

DEC-006 — Repository reality overrides memory

Date: 2026-08-16
Status: Accepted

Context

Persistent memory can become stale.

An agent may encounter a memory entry that no longer matches the actual implementation.

Decision

Current repository code and configuration take precedence over memory summaries when they clearly conflict.

Rationale

Memory describes the project.

It is not the project itself.

Allowing stale memory to override observable implementation would create a dangerous feedback loop where agents preserve incorrect assumptions.

Required behavior

When a conflict is discovered:

1. inspect the relevant implementation
2. verify which source is current
3. correct stale memory
4. preserve important architectural changes in the decision log when appropriate

Consequences

Future automated tooling should include stale-memory detection and validation where practical.

---

Decision lifecycle

Decisions should not normally be deleted.

If an accepted decision becomes obsolete, mark it:

"Superseded"

Then reference the newer decision.

Example:

**Status:** Superseded by DEC-012

The new decision should explain why the previous approach changed.

This preserves architectural history for both human maintainers and coding agents.

Agent instruction

Before making a repository-wide architectural change, Codex should inspect this file.

After making a meaningful architectural decision, Codex should update this file when the reasoning will matter to future sessions.

Do not add decisions merely to make the log appear active.

Every recorded decision should represent a real project choice.