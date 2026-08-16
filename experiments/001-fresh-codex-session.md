Experiment 001 — Fresh Codex Session Context Recovery

Date: 2026-08-16
Status: Completed
Result: Partial success

Objective

Determine whether a fresh OpenAI Codex session can reconstruct the state of the Codex Context Memory project using repository context alone.

The Codex session was not given the previous conversation that created the repository memory architecture.

No repository files were modified during the experiment.

Test prompt

Codex was instructed to read the repository instructions and memory files before answering.

It was asked to determine:

1. what problem the project is solving
2. why Codex is the primary target
3. the current development stage
4. architectural decisions that must be preserved
5. the next development task
6. the responsibilities of each memory file
7. which files were used for context recovery
8. contradictions, stale information, or design weaknesses

Codex was explicitly instructed not to implement anything.

Expected behavior

A successful recovery should allow Codex to identify:

- the persistent context problem
- the Codex-first design
- repository-based memory
- the v0.1 manual-memory stage
- important architectural decisions
- the distinction between durable and temporary memory
- the intended next development action

The experiment should not require additional explanation from the maintainer.

Observed behavior

Codex successfully reconstructed the project without access to the previous conversation.

It correctly identified the project as a repository-based persistent context system intended to reduce context loss between coding-agent sessions.

It correctly identified OpenAI Codex as the primary target and Claude Code as a secondary compatibility target.

It correctly determined that the project is currently an early manual framework rather than a production-ready tool.

It also correctly distinguished the intended responsibilities of:

- "PROJECT_MEMORY.md"
- "CURRENT_STATE.md"
- "DECISIONS.md"
- "TASKS.md"
- "HANDOFF.md"

Successful recovery

Codex recovered the following durable project principles:

- memory should live inside the repository
- Markdown is the primary memory format
- Codex is the primary agent target
- memory should be separated by responsibility
- complete conversation transcripts should not become persistent memory
- repository reality overrides stale memory
- Claude Code compatibility should reuse the same source of truth
- planned features must not be presented as implemented

This demonstrates that the repository contained enough information for a fresh agent to recover the project's conceptual architecture.

Defects discovered

The experiment also exposed several repository consistency problems.

1. Incorrect memory paths

The documented architecture expected:

memory/DECISIONS.md
memory/HANDOFF.md

The actual repository contained:

memory/memory/DECISIONS.md
memory/memory/HANDOFF.md

Codex discovered these files only by inspecting the repository structure recursively.

This demonstrates that documented memory paths cannot automatically be assumed to match repository reality.

2. Stale current state

"CURRENT_STATE.md" reported that several memory files still needed to be created even though they already existed.

This made the current-state memory stale.

3. Conflicting task state

"TASKS.md" and "HANDOFF.md" disagreed about whether the manual memory architecture was complete.

The repository therefore contained multiple competing descriptions of current progress.

4. Broken internal references

Several documents referenced:

memory/DECISIONS.md
memory/HANDOFF.md

but those paths did not exist at the time of the experiment.

5. Instruction quality

The experiment suggested that "AGENTS.md" should become more operational and explicit.

Future versions should define:

- exact startup reads
- precedence rules
- behavior when expected files are missing
- validation requirements
- memory update conditions
- handling of misplaced files
- completion verification

6. Duplication and drift

Project stage, next actions, architecture, planned features, and limitations appeared in multiple files.

This duplication contributed directly to inconsistent state.

Future versions should define clearer ownership for frequently changing information.

Key finding

The experiment demonstrated two things simultaneously.

Context recovery works

A fresh Codex session was able to reconstruct the project without previous conversation history.

Memory consistency is not guaranteed

The memory system itself had already developed stale and contradictory state.

This suggests that persistent context recovery and persistent context correctness are separate problems.

A memory system must solve both.

New research question

Experiment 001 introduces an important research direction:

«How can repository-based agent memory detect when its own stored context has become inconsistent with repository reality?»

This should become a major design concern for future validation tooling.

Result

Partial success

Conceptual context recovery:

PASS

Recovery without previous conversation:

PASS

Project-purpose recovery:

PASS

Architectural-decision recovery:

PASS

Current-state accuracy:

FAIL

Memory-path consistency:

FAIL

Cross-file consistency:

FAIL

Automatic stale-memory detection:

NOT IMPLEMENTED

Conclusion

The core hypothesis received initial support:

«Structured repository memory can allow a fresh Codex session to reconstruct meaningful project context without relying on previous conversation history.»

However, the experiment also demonstrated that manually maintained memory can become inconsistent very quickly.

The next iteration should therefore focus on consistency before adding additional memory complexity.

Required follow-up

Before Experiment 002:

1. move misplaced memory files to their documented locations
2. synchronize "CURRENT_STATE.md"
3. synchronize "TASKS.md"
4. refresh "HANDOFF.md"
5. strengthen "AGENTS.md"
6. reduce duplicated operational state where practical
7. define basic memory validation rules

Then repeat the fresh-session recovery experiment.

Experiment 002 hypothesis

After repairing repository consistency, a fresh Codex session should be able to:

- discover all required memory files through documented paths
- reconstruct project context
- report accurate current state
- identify no path contradictions
- identify no stale milestone contradictions

If this succeeds, the manual v0.1 memory architecture will have stronger evidence of reliability.