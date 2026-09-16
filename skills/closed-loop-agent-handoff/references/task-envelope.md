# Task Envelope

Use this compact structure for a durable, agent-neutral assignment.

```markdown
# AGENT TASK — <short title>

TASK_ID: <entity-project-YYYYMMDD-sequence>
STATUS: READY_TO_DISPATCH | ACKNOWLEDGED | ACTIVE | PARTIAL | BLOCKED | COMPLETE | SUPERSEDED
SCOPE: <entity and project/matter>
OWNER: <receiving agent>
SUPERVISOR: <assigning agent or role>
CREATED: <ISO date-time and timezone>
SOURCE_VAULT: <exact path or URL>
RETURN_CHANNEL: <direct agent channel or monitored queue>

## Objective
<One measurable outcome.>

## Authoritative sources
- <exact source, path, ID, or URL>

## Known state
- <verified fact with source>

## Authorised actions
- <bounded action>

## Prohibited actions
- <external, destructive, confidential, or out-of-scope action>

## Acceptance tests
- [ ] <observable test>

## Required receipt
<Artifacts, evidence, status, next action, owner, and gate.>
```

## State transitions

`READY_TO_DISPATCH → ACKNOWLEDGED → ACTIVE → COMPLETE`

Use `PARTIAL` or `BLOCKED` from `ACTIVE` when work cannot finish. Use `SUPERSEDED` only when a newer task explicitly replaces the current task. Never reuse a completed task ID for new work.

## Acknowledgement

The receiver records:

- the same task ID;
- the objective in its own words;
- sources it can actually access;
- authorised and prohibited actions understood;
- any material conflict or missing dependency;
- the next action it will take.

## Receipt quality

A receipt must allow a fresh supervising agent to verify completion without chat history. Link evidence rather than copying secrets or large source contents. Record `NOT TESTED` rather than implying a check occurred.
