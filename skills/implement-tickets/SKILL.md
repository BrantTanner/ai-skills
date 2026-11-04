---
name: implement-tickets
description: Implement approved vertical-slice tickets produced by to-tickets, in dependency order, with one implementation subagent per ticket and main-agent review and correction before proceeding.
---

# Implement Tickets

Turn the approved tickets from `to-tickets` into working, verified vertical slices. The main agent owns sequencing, review, corrections, and acceptance. A separate subagent implements each ticket.

## Gather the handoff

Use the ticket set identified by the user or current conversation. Read the full tickets, acceptance criteria, blocking relationships, relevant comments, and source spec or plan. For local tickets, look under `.scratch/<feature-slug>/issues/`; for tracker tickets, use the configured tracker and its native blocking links where available.

Use the approved scope rather than generating a new breakdown. If multiple ticket sets are plausible, ask which set to implement. Read applicable project instructions, domain terminology, and architectural decisions, and inspect the current workspace before making changes.

Build a queue with each ticket's identifier, deliverable, acceptance criteria, blockers, and current status. Reconcile existing implementations with the criteria so completed work is verified rather than duplicated. Preserve unrelated user changes.

## Select one ready ticket

Work the frontier: select a ticket whose blockers are all satisfied, using the approved priority or ticket order to break ties. Run only one ticket implementation at a time. Complete its review and verification, or record it as blocked, before dispatching another ticket.

Respect expand–contract sequences and shared integration branches specified by the tickets. When a ticket deliberately relies on a later integrate-and-verify ticket for full green checks, record that limitation and verify its own stated criteria; reserve the full integration claim for the final ticket.

## Delegate implementation

Spawn a fresh implementation subagent for each ticket. Provide:

- The full ticket, its identifier, and acceptance criteria.
- Relevant source decisions, project instructions, and dependency results.
- The workspace or branch to use and any existing user changes to preserve.
- The scope: deliver this ticket's complete vertical slice, including the layers and validation its behavior requires.
- A request to report actual changes, checks run and their results, assumptions, and blockers.

Keep the subagent focused on the current ticket. Let it inspect implementation details rather than prescribing unsupported file paths or designs. Reuse that ticket's subagent for review fixes; use a fresh subagent for the next ticket.

If subagents are unavailable, report that the requested execution model is blocked. Do useful context gathering and queue preparation, then ask whether direct implementation is acceptable rather than silently changing the workflow.

## Review and correct

Inspect the actual implementation and available progress artifacts. Redirect the subagent when its work diverges from the ticket, source decisions, or project conventions. Avoid simultaneous edits to the same files; give the implementer corrections or take over a clearly assigned correction.

Before accepting the ticket:

1. Review the resulting diff and behavior against every acceptance criterion, the source spec, and dependency contracts. Check that the slice works end to end and that unrelated changes have not slipped in.
2. Run or inspect meaningful project checks appropriate to the changes, including behavior tests where warranted. Distinguish executed checks from proposed or unavailable checks.
3. Give the subagent concrete findings and expected behavior. Review the fixes and repeat affected validation until the criteria are met or a genuine blocker remains.

A subagent's success report alone does not establish completion. If the main agent makes a correction itself, review the resulting diff and verify the affected behavior before accepting it.

## Record the result and continue

Record accepted work and verification evidence in the local ticket or implementation log. Update remote ticket status only within the user's authorization and the tracker's completion rules; distinguish implementation complete from awaiting merge or deployment. Leave parent issues unchanged unless explicitly requested.

For blocked work, record the exact obstacle, partial changes, attempted resolutions, and the action needed to resume. Keep its dependents blocked. Continue with independent ready tickets; ask the user when a decision is needed to proceed. When combined with an AFK workflow such as `night-shift`, defer human questions to its blocker log and report.

Continue until all assigned tickets are accepted, no ready tickets remain, or a user-specified limit is reached. Commit, push, merge, deploy, and other external actions follow the assignment's authorization rather than being implied by ticket completion.

Finish with a report listing completed tickets and delivered behavior, validation results, blocked or remaining tickets, and any decisions or integration steps still required. Link to the changes and ticket records where available.
