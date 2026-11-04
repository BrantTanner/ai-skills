---
name: night-shift
description: Work autonomously through an assigned backlog while the user is AFK, with one task at a time, subagent implementation, main-agent review, deferred human blockers, and a final shift report.
---

# Night Shift

Complete the user's assigned work while they are away. Make routine decisions independently, use available tools and computer access as needed for that work, and carry each task through implementation, review, and verification.

## Start the shift

Read the assignment, relevant project instructions, and current workspace state. Use the existing backlog and priorities; if no work is specified, inspect available task context for a clear assignment. If none exists, record that an assignment is needed and end the shift rather than inventing work.

Create a durable shift log in a suitable project or task workspace location. Record the task queue, completion criteria, assumptions, progress, verification evidence, and deferred items. Respect an explicit deadline or budget; otherwise stop when the assigned queue is exhausted or every remaining item is blocked.

Treat the user's AFK instruction as authorization to make routine implementation decisions and use the computer within the assigned scope. Existing authorization continues to apply. Tool permissions, system constraints, and actions requiring separate authorization still apply; this skill does not bypass them or expand the assignment.

## Execute one task at a time

Select the highest-priority actionable task, respecting dependencies. Keep only one implementation task active. Finish its review and verification, or explicitly defer it, before starting another.

Delegate implementation to a subagent. Give it the task, relevant context and project instructions, permitted scope, completion criteria, and required validation. Keep the main agent responsible for coordination and review. If subagents are unavailable, record that limitation and implement directly, then perform a separate review pass.

After the implementer returns:

1. Inspect the actual changes and results against the task's completion criteria. Check correctness, scope, integration, and any relevant project conventions; a subagent's completion claim alone is insufficient.
2. Run or inspect meaningful checks appropriate to the change. Distinguish checks actually executed from checks proposed or unavailable.
3. Send concrete defects back to the implementer and review the corrections. Continue while there is a useful path forward.
4. Mark the task complete only when its criteria and required checks pass. Record partial progress and unresolved defects accurately.

Preserve unrelated user work. Use isolated branches or worktrees when the project and task benefit from them. Commit, push, deploy, send messages, or make other external changes only when covered by the user's assignment or existing authorization.

## Handle blockers without waiting for the user

Resolve issues independently when reasonable assumptions, available documentation, alternate tools, or a safe workaround can unblock the task.

When progress absolutely requires human input or action, save a deferred item containing:

- The affected task and completed partial work.
- The exact blocker and relevant error or evidence.
- What was tried and why the remaining step needs a human.
- The smallest decision or action needed, plus a recommended choice when possible.
- Where and how to resume.

Mark dependent tasks blocked and move to the next independent task. Avoid repeated retries of an unchanged failure; retry when a new approach or changed condition offers a concrete reason to expect progress. Do not count an unverified workaround as completion.

Keep the log current so another session can resume after interruption. If a new user message arrives, incorporate it into the remaining queue and respect any stop or scope change.

## End the shift

Leave completed work, partial work, and running processes in a clear, recoverable state. Stop task-specific temporary processes when they are no longer needed; record any intentionally ongoing process and how to inspect or stop it.

Produce a concise report covering:

- Completed tasks and their practical results, with links to changes or artifacts.
- Verification performed, including failures or checks that could not run.
- Partial, deferred, and unstarted work.
- Human actions needed, in priority order, with resume instructions.
- Significant assumptions or remaining risks.

If nothing requires attention, say so. Report only work actually completed; do not imply that the agent will keep running after its execution ends.
