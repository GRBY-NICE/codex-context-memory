# Handoff

## Current objective

Validate the corrected and synchronized v0.1 memory workflow in a fresh Codex session.

## Latest completed work

- Experiment 001 was recorded as a partial success in `experiments/001-fresh-codex-session.md`.
- `memory/DECISIONS.md` and `memory/HANDOFF.md` were moved out of the unintended `memory/memory/` directory in commit `155228a0ab8dc054850a263b0a9b78542038dab7`.
- `AGENTS.md` now defines startup order, source precedence, file ownership, missing-file handling, stale-memory handling, update rules, validation, Git discipline, and security.
- `memory/CURRENT_STATE.md`, `memory/TASKS.md`, and this handoff now agree that the complete manual file structure exists and Experiment 002 is next.

## What the next session must do

1. Start with no prior conversation context.
2. Follow the startup procedure in `AGENTS.md` and read all five files under `memory/`.
3. Reconstruct the project context and compare it with the Experiment 002 success criteria in `memory/CURRENT_STATE.md`.
4. Record the run as `experiments/002-fresh-codex-session.md`.
5. Update `CURRENT_STATE.md`, `TASKS.md`, and `HANDOFF.md` from the recorded evidence.

## Guardrails

- Treat repository reality as authoritative when memory conflicts.
- Do not recreate files under `memory/memory/`.
- Do not claim automated validation or stale-memory detection exists.
- Do not begin CLI implementation or Claude Code compatibility before Experiment 002 evidence is recorded.
- Preserve accepted decisions in `memory/DECISIONS.md` unless a new explicit decision supersedes one.

## Remaining weaknesses

- Consistency enforcement is manual.
- Only Experiment 001 has been recorded.
- No second-repository validation or token-cost measurement exists.
- The process depends on agents following `AGENTS.md`.

## Key references

- Durable architecture: `memory/PROJECT_MEMORY.md`
- Current status and success criteria: `memory/CURRENT_STATE.md`
- Accepted decisions: `memory/DECISIONS.md`
- Work queue: `memory/TASKS.md`
- Previous evidence: `experiments/001-fresh-codex-session.md`
