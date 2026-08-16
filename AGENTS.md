# Codex Context Memory — Agent Instructions

These instructions apply to the entire repository. They define how agents recover context, judge repository truth, and maintain the memory system.

## Project scope

This repository is a Codex-first, repository-based memory framework. Version 0.1 is intentionally manual: Markdown files and Git history are the implementation. Do not describe a CLI, automatic memory updates, stale-memory detection, or Claude Code compatibility as implemented unless corresponding code and validation exist in the repository.

## Required startup procedure

Before answering a repository-context question or making a change:

1. Inspect the current branch, repository tree, and relevant code or configuration.
2. Read `AGENTS.md`.
3. Read `memory/PROJECT_MEMORY.md` for durable purpose and architecture.
4. Read `memory/CURRENT_STATE.md` for the current milestone, completed work, limitations, and next action.
5. Read `memory/TASKS.md` for the actionable roadmap.
6. Read `memory/HANDOFF.md` when continuing recent work.
7. Read `memory/DECISIONS.md` before changing architecture, scope, file responsibilities, or tool targeting.
8. Read relevant records under `experiments/` when evaluating validation claims.

For a memory-system audit or fresh-session recovery test, read all files listed above before drawing conclusions.

## Required layout

```text
AGENTS.md
memory/
├── PROJECT_MEMORY.md
├── CURRENT_STATE.md
├── DECISIONS.md
├── TASKS.md
└── HANDOFF.md
```

Do not create a second memory source under another path. If a required file is missing or misplaced:

- inspect the repository tree and Git history before assuming it was never created;
- do not silently create a duplicate;
- report the discrepancy;
- repair it only when the active task authorizes repository changes; and
- verify that the canonical path contains the intended content and the obsolete path no longer exists.

## Source-of-truth precedence

Use the precedence defined in `memory/PROJECT_MEMORY.md`:

1. repository code, configuration, file layout, and current Git state;
2. `AGENTS.md`;
3. accepted decisions in `memory/DECISIONS.md`;
4. durable architecture in `memory/PROJECT_MEMORY.md`;
5. current status in `memory/CURRENT_STATE.md`;
6. recent-session context in `memory/HANDOFF.md`;
7. prior conversation.

`memory/TASKS.md` is a plan, not proof that work is complete. A checked task must agree with repository reality and `memory/CURRENT_STATE.md`. If sources conflict, verify the repository, follow the higher-precedence source, and correct stale lower-precedence memory when the task permits.

## File ownership

| File | Owns | Must not become |
| --- | --- | --- |
| `AGENTS.md` | Agent workflow, precedence, validation, and update rules | Project status or a feature roadmap |
| `memory/PROJECT_MEMORY.md` | Durable purpose, architecture, concepts, and long-term constraints | A session log or changing checklist |
| `memory/CURRENT_STATE.md` | Present phase, verified capabilities, limitations, and immediate next action | A complete history or speculative roadmap |
| `memory/DECISIONS.md` | Accepted architectural decisions and rationale | A task list or casual notes |
| `memory/TASKS.md` | Actionable completed, current, blocked, and future work | Evidence that unchecked code exists |
| `memory/HANDOFF.md` | Concise context needed by the next session | An append-only diary or duplicate project overview |
| `experiments/*.md` | Dated validation method, evidence, result, and follow-up | Current status that silently changes with later work |

To minimize drift, store each frequently changing fact in one primary location:

- current milestone and immediate next action: `memory/CURRENT_STATE.md`;
- detailed work checklist: `memory/TASKS.md`;
- next-session continuation notes: `memory/HANDOFF.md`.

Other files should link to those facts rather than copy detailed status.

## Memory update rules

After meaningful work, update only the files whose owned information changed:

- Update `CURRENT_STATE.md` when capabilities, phase, limitations, validation status, or the immediate next action changes.
- Update `TASKS.md` when work is completed, reprioritized, added, or blocked.
- Replace stale material in `HANDOFF.md` with the smallest useful continuation context.
- Update `PROJECT_MEMORY.md` only for durable project knowledge.
- Add or amend a decision in `DECISIONS.md` only for a durable architectural choice with meaningful alternatives.
- Add a new experiment record for a new validation run. Preserve earlier results as historical evidence; correct them only to fix factual or formatting errors.

Do not update memory mechanically. A documentation-only change can still require state updates, while a trivial edit may require none.

## Stale-memory and conflict handling

Treat memory as stale when it names nonexistent paths, marks repository-visible work incorrectly, contradicts a higher-precedence source, or presents planned work as implemented. When stale memory is found:

1. identify the repository evidence;
2. state which memory entries conflict;
3. determine the canonical owner for each fact;
4. update or remove duplicates within the authorized scope; and
5. record unresolved ambiguity in `CURRENT_STATE.md` or `HANDOFF.md` rather than guessing.

Repository reality overrides memory, but agents should repair stale memory so later sessions do not repeat the same error.

## Validation before completion

Before declaring a task complete:

- inspect the final tree and confirm all referenced paths exist;
- compare `CURRENT_STATE.md`, `TASKS.md`, and `HANDOFF.md` for milestone and next-action consistency;
- confirm accepted decisions were preserved;
- distinguish implemented, manually validated, planned, and blocked work;
- inspect the final diff and confirm it contains only intended files;
- run relevant tests or checks when code changes; and
- report any unverified claim or remaining weakness.

For documentation-only memory changes, the minimum validation is path verification, cross-file consistency review, and diff-scope review.

## Git and security rules

- Use focused branches, commits, and pull requests for nontrivial work.
- Do not mix unrelated cleanup with the active task.
- Never store credentials, tokens, private keys, personal secrets, or copied private conversation history in memory files.
- Prefer concise summaries and repository references over raw logs or full transcripts.

## Completion report

At handoff, summarize:

- files changed;
- contradictions resolved;
- checks performed;
- remaining weaknesses; and
- the single next action.
