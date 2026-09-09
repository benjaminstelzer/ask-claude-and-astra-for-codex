---
format_version: 1
id: PLAN-0001
status: completed
created: 2026-09-09
updated: 2026-09-09
---

# Close completed Astra consultation agents

## Goal

Give every Astra consultation a bounded host lifecycle that preserves results and explicitly pending continuation state before verified agent closure, while exposing missing close capability and capacity blockers to the user.

## Non-goals

- Do not change Claude transport, models, effort, permissions, or answer synthesis.
- Do not raise global agent limits or treat interruption, archiving, or process termination as agent closure.
- Do not publish, install, release, or change repository remotes.

## Work items

### W-001 Add and validate the Astra agent lifecycle
Status: done
Depends on: []
Blocked by: []
Decisions: []
Outcome: Astra spawn, follow-up, collection, closure, status, and blocker paths preserve results without keeping completed agents open indefinitely.
Acceptance: The Skill checks spawn and close capability before dispatch; records result provenance and explicit continuation state before verified closure; protects needed active descendants; reports unavailable closure and capacity; never calls a new target a continuation; answers status questions before resuming an active wait; reports blockers immediately; the package validator and lifecycle scenarios pass without claiming a live close on a host that lacks close_agent.
Steps:
1. Add the bounded lifecycle to the existing dispatch, continuation, and result flow.
2. Inspect the scoped diff and run the repository tests and Skill validator.
3. Exercise close-unavailable, completed-open, pending-follow-up, closed-continuation, status-question, and blocker scenarios without spawning an agent.
Evidence: [23 repository tests passed; Skill quick validation passed; lifecycle contract scenarios passed without live close_agent execution, Native profile validation passed with zero diagnostics]
