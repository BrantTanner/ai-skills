---
name: todo
description: Create and follow a fixed, evidence-based TODO list for the current task.
---

# TODO

Use this skill only when the user explicitly calls it. Turn the current assignment into a complete TODO list, then use that list as the source of truth for execution scope and progress until it is finished. The user's instructions and applicable system and project requirements remain authoritative.

## Build the list before executing

Identify the current task, requested outcome, constraints, and work already completed from the conversation and available artifacts. If the current assignment is unclear, ask the user rather than inventing one.

Inspect relevant files, requirements, dependencies, and existing behavior before planning. Think carefully through how the work will be implemented and verified: affected components, ordering, integration, necessary setup, likely failure cases, and completion evidence. Ground factual claims in inspected evidence and label assumptions. Resolve material unknowns before freezing the plan; include bounded investigation items when their answers are needed during execution.

Create one authoritative checklist in the existing task-planning tool or a suitable task-local file. Use an existing task list when one is already authoritative. Show the user the list and its location before implementation, then proceed within existing authorization.

Give each item a stable identifier and record:

- The concrete outcome and scope.
- The implementation approach at a useful level of detail.
- Dependencies or prerequisites.
- A checkable completion criterion and relevant validation.

Cover every requirement of the current assignment, including necessary integration and verification. Keep items actionable and sized for observable progress. Include only work needed for the requested outcome. Present the resulting plan and concise rationale rather than private deliberation.

## Freeze scope and execute

Once the checklist is established, freeze its items, scope, and completion criteria until every item is complete. Work only on listed items and the implementation steps directly necessary to satisfy them. Keep one item active at a time, respecting dependencies.

Before an action, connect it to the active item's outcome or validation. If it does not contribute to that item, leave it out. Record status and evidence as work progresses; status updates, implementation notes, and blocker records may change without expanding the list.

Complete an item only after its criterion is met and the required checks support that conclusion. Record failures and unverified results accurately. Re-read the authoritative list after interruptions or context changes, and resume from its recorded state.

## Handle discoveries and blockers

Record newly discovered optional work separately as observations outside the execution checklist. Keep those observations brief and explicitly unapproved; do not implement them or turn them into new TODO items while the frozen list is unfinished.

If an unexpected prerequisite is a necessary implementation detail within an existing item's scope, handle it under that item and document it. If it changes the promised outcome, adds scope, or invalidates a completion criterion, mark the affected item blocked and explain the evidence. Continue other unblocked listed items.

If completing the list requires changing its scope, ask the user to authorize a revision. Only an explicit user instruction may override the freeze; document the authorized change and preserve an accurate record of prior progress. Never fabricate completion to unlock additional work.

## Finish

When every item meets its completion criterion, report the completed checklist, validation evidence, and any remaining limitations. Separately mention relevant observations for the user to consider. Completing the list does not authorize new work: wait for a new assignment or explicit approval before creating and executing an expanded list.
