## Purpose

This file stores durable, cross-cutting guidance only.

Do not store:
- snapshots of current implementation state
- temporary migration status
- feature-specific wiring details
- notes likely to change as code evolves

If a note is likely to go stale, it does not belong here.

## Durable Preferences

- Prefer elegant minimalism in architecture and implementation.
- Keep functions pure and redirection minimal.
- Protect module boundaries; avoid leaking DB or unrelated module knowledge across layers.
- For Agent V3 voice work, keep `orchestrate-sandbox` voice-agnostic; put voice-specific logic in adapters (webhooks/tools/activities).
- For sandbox-vs-legacy Vapi splits, prefer new sandbox-specific adapter files and reuse only runtime-agnostic voice/Vapi helpers.
- Design for modularity and testability first.
- For larger UI surfaces, prefer container/view splits (stateful container, pure presentational view).
- Prefer typed contracts over heuristic parsing when behavior crosses module boundaries.
- Favor compile-time contract enforcement first; runtime checks are secondary.
- Prefer extending and reusing existing nearby types before introducing new parallel type declarations.
- For systems not yet in production, prefer direct simplification over phased rollout unless explicitly requested.
- For major feature rewrites, prefer blank-slate cleanup (full removal of old paths) before introducing replacement implementations.
- For architectural refactors, prefer TDD (failing test, implementation, refactor).
- For architectural refactors, prefer hard cutover over compatibility layers unless explicitly requested.
- Treat behavior as I/O contracts (stable inputs, outputs, side effects) so internals can evolve safely.
- For long-running contract scripts, enforce a hard wall-clock timeout so hangs fail fast.
- For Oracle CLI usage, allow up to 60 minutes for a run and do not start a second run while the first is still active.
- For sandbox contract runs, default to live contract scenarios only and skip helper/spec tests unless explicitly requested.
- Keep one canonical plan artifact per topic when planning.
- For sandbox runtime design, treat Modal image snapshots and mounted S3 state as separate persistence layers; snapshots do not capture mounted-file content.
- For sandbox rerun checkpoints with large mostly-immutable files, prefer local-mirror + snapshot + restore over per-checkpoint mounted-prefix duplication when snapshot economics are favorable.
- For sandbox run-log replay, treat the sandbox-local log mirror as authoritative for in-instance resume and only seed from mounted state when local is empty, since mounted log writes can fail or lag.
- For mounted sandbox run logs, avoid direct append (`>>`) to mounted paths; append to local `/tmp/.sandbox/log.ndjson` and mirror with full-file copy/overwrite.
- For sandbox restarts/recycles, seed `/tmp/.sandbox/log.ndjson` from durable run storage at sandbox start so cross-sandbox run-log history survives mount lag/stale local mirrors.
- For sandbox append helpers, chunk large append payloads and pass through timeout settings; single huge append commands can fail in Modal exec.
- For AI SDK message persistence/replay, preserve schema shape exactly (omit undefined object fields instead of coercing them to null) so resumed tool-call transcripts remain parseable and provider-compatible.
- For sandbox computer-use subagents, treat incoming `resumeCursor` values as untrusted model/runtime input and canonicalize root step IDs to DB-safe UUIDs at the backend boundary before querying `flow_run_steps`.
- For sandbox computer-use subagents, treat unchanged replay cursors across consecutive `running + needsMoreWork` completions as a no-progress signal and avoid auto-rerun loops from orchestration.
- For sandbox computer-use orchestration, treat `currentReplayId` as replay-segment scoped (it may remain unchanged across multiple valid iterations); do not use replay-ID changes as the only progress signal.
- In sandbox tool-definition modules, avoid eager imports of integration-heavy runtime modules (for example DB-backed services); prefer lazy runtime imports inside tool execution paths to keep unit tests isolated from env/bootstrap side effects.
- For sandbox subagents queued while a run is blocked for human-action wait, do not assume `sandboxId` is available at enqueue time; hydrate missing payload `sandboxId` from the current sandbox when subagent execution starts.
- For sandbox subagents resumed after a sandbox recycle, treat queued payload `sandboxId` values as potentially stale and resolve subagent execution against the current active sandbox.
- For sandbox orchestration work, prioritize explicit parity checks vs legacy behavior and prefer typed inter-agent timeline contracts over notice-text heuristics in `log.ndjson`.
- For sandbox run logs, treat each entry as a typed contract that must support both deterministic agent-state reconstruction and frontend performance/timeline rendering without text-parsing heuristics.
- For sandbox run-log persistence, prefer explicit adapter boundaries: one function for live sandbox append, one for offline S3 append, and one selector that routes by sandbox liveness.
- For sandbox resume reliability, carry inbound-input notices on wake signals (for example `inputsAvailable`) so replay can restore pending user inputs even if run-log persistence races during sandbox suspend/teardown.
- For sandbox files appended during a run, define append-target paths on the run manifest and reference manifest entries across modules instead of standalone path constants.
- For ingestion-quality work, prefer iterative experiment loops where an LLM judges Markdown against source visuals and each experiment attempt is tracked with explicit status notes.
- Treat inbound provider deliveries as at-least-once: duplicate message IDs are expected and duplicate deliveries must be idempotent (no new-input signaling for already-attached entities).
- Prefer local development ports 7000 (frontend) and 7001 (API) unless specified otherwise.
- For the personal tools repo, keep a root index page that links out to each individual tool/page.
- For personal tools that ingest copied logs/transcripts, prefer tolerant JSON5-style parsing over strict JSON-only parsing.
- Prefer manual invocation of `.claude/hooks/setup-worktree.sh`; do not auto-run it on Claude `SessionStart`.

## Note Hygiene

- Add only guidance that should still hold months from now.
- Keep notes generic enough to apply across features.
- Rewrite or remove notes that no longer meet the durability bar.
