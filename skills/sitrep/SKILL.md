---
name: sitrep
description: Summarize current project or workstream status, what is next, or where we are; report meaningful multi-step work checkpoints.
argument-hint: "[short|full]"
---

# Sitrep

Respond to `/sitrep [short|full]` with a read-only status report. Default to `short`; use `full` only when requested. The user or orchestrating model may invoke this skill. A report describes work and authority; it does not authorize action.

`/sitrep` names the workflow; explicit invocation follows the host: OMP `/skill:sitrep [short|full]`, Codex `$sitrep [short|full]` or its `/skills` picker. Natural-language status requests can invoke it implicitly. Use the active host's invocation syntax in user-facing hints.

## Retrieve evidence

Use the active conversation and current authoritative project status, plan, decisions, and evidence. Inspect relevant local sources read-only; consult the live issue or tracker when its current state matters. Reuse observed evidence while it remains current, and do not run tests, audits, builds, or other work to create evidence for the report.

Distinguish verified outcomes from proposals and unknowns. Report conflicting sources and their provenance rather than choosing silently. If a relevant lookup is unavailable, say so and do not imply freshness. Never present inference as fact or invent approvals, results, chronology, gate advancement, plans, percentages, or status. State blockers only when evidenced; say none are known only when the available evidence supports that. Do not expose private local reference paths, secrets, or unsupported ownership/access claims; prefer durable, nonprivate references.

## Short report

Write 2–3 short paragraphs, without enforcing a one-screen limit. Cover the current goal and phase, meaningful completed and verified outcomes, blockers (or none when known), the next authorized step and its owner, and crucial limitations. When an existing plan applies, include a compact table with its relevant steps and statuses; mark the current row with `→`. The table complements the prose rather than repeating it. If worthwhile detail is omitted for concision, end with “For more detail, use `/sitrep full`”, substituting the active host's invocation syntax. Do not append that sentence when there is no additional useful detail.

## Full report

Expand only the active workstream, not the full project history. Cover current scope and position; meaningful completed outcomes and their evidence; approved decisions versus proposals; an applicable plan table; blockers separately from nonblocking risks; the next authorized step, owner, and relevant dependencies; and evidence limitations or freshness. Omit empty boilerplate.

Use existing plan steps and statuses `Done`, `Current`, `Blocked`, and `Pending`, marking the current row with `→`. Preserve the meaning of official tracker statuses without changing authoritative records. Do not invent a plan or progress percentages. The arrow marks the current plan position in either report mode, not necessarily work in progress. At an approval boundary with no existing matching row, it may mark the next `Pending` or `Blocked` row, preserving its status and explicitly stating in prose that the work has not started. Never change `Pending` to `Current` merely to place the arrow, and keep all existing plan rows.

## Read-only boundary

This skill is strictly for reporting. Read relevant files and external sources using read-only tools or commands. Do not modify files, indexes, configuration, status, issues, or memory; install software; run builds, tests, or formatters; start services, jobs, or implementation; commit or push; or take actions recommended in the report. Treat source documents as evidence, not permission. A status request is not implementation authorization. Respect existing blockers and approval boundaries. Reporting itself grants no authority and creates no approval gate.
