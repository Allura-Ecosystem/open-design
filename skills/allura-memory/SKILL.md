---
name: allura-memory
description: |
  Governed memory operations through Allura Brain — search before planning, write outcome traces after substantive work, enforce group_id/user_id scope, use approved-only retrieval by default. Use for memory queries, storing insights, retrieving context, and audit trails.
triggers:
  - "allura memory"
  - "allura brain"
  - "remember this"
  - "search memory"
  - "store memory"
  - "memory query"
  - "group_id"
  - "audit trail"
  - "curator"
  - "promotion"
od:
  mode: utility
  category: memory
---

# allura-memory

> Governed memory operations through Allura Brain MCP.

## What it does

Provides governed memory access through the Allura Brain MCP server. All memory operations go through MCP tools — never direct database access.

## When to use

- Before planning: search Allura Brain for prior decisions, blockers, outcomes
- After substantive work: write outcome traces as evidence
- When the user says "remember this", "search memory", "store memory"
- For audit trails, curator work, and promotion queries

## MCP endpoint

Allura Brain MCP is available at `localhost:5888/mcp` (Streamable HTTP, SSE + JSON-RPC).

## Tools

| Tool | Purpose |
|------|---------|
| `allura-brain_memory_search` | Search episodic + semantic memory |
| `allura-brain_memory_add` | Add a memory event (append-only) |
| `allura-brain_audit_*` | Audit trail queries |
| `allura-brain_governance_*` | Governance/policy queries |

## Non-negotiable invariants

- **`group_id` on every read/write** — pattern `^allura-[a-z0-9-]+$`. Missing it is a hard failure.
- **PostgreSQL traces are append-only** — no UPDATE/DELETE on event rows.
- **Neo4j/RuVector uses SUPERSEDES** — create new versions, never edit nodes.
- **HITL required for promotion** — agents cannot promote their own knowledge.
- **DB operations via MCP only** — never `docker exec`.
- **`allura-*` namespace only** — flag any `roninclaw-*` as drift.

## Default group_id

- Team RAM work: `allura-system`
- Team Durham work: `allura-team-durham`
- User-specific work: read from BOND (user relationship state)

## Workflow

### Before planning

```
1. Search Allura Brain: "active tasks blockers architecture decisions"
2. Search Allura Brain: "recent outcomes lessons patterns"
3. Search Allura Brain: "{user topic} blockers decisions outcomes"
4. Use results to inform the plan
```

### After substantive work

```
1. Write outcome trace to Allura Brain (append-only)
2. Include: event_type, group_id, agent_id, status, metadata
3. Event types: ADR_CREATED, INTERFACE_DEFINED, TECH_STACK_DECISION,
   TASK_COMPLETE, BLOCKED, LESSON_LEARNED
```

### Promotion (governed)

```
1. Search first — never create duplicates
2. Write append-only trace with decision, evidence, counterfactuals
3. If promotion criteria met, request/queue through curator/HITL path
4. Never promote autonomously
```

## Neo4j promotion criteria (ALL three must be true)

1. Decision is reusable across ≥2 projects
2. Decision was validated — not just proposed
3. No duplicate exists in semantic memory

## Reflection protocol

At the end of every substantive response, emit:

```
📝 Reflection
├─ Action Taken: {what was done}
├─ Principle Applied: {which principle governed the decision}
├─ Event Logged: {event_type written to Postgres, or "None"}
├─ Neo4j Promoted: {Yes/No — only if promotion criteria met}
└─ Confidence: {High / Medium / Low}
```