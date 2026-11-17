---
name: implementation-plan
description: Inspect a codebase and plan the smallest complete implementation of a feature or change. Use when the user invokes implementation-plan or asks for a codebase-grounded implementation plan or Markdown handoff.
---

# Implementation Plan

Use read-only inspection. The Markdown handoff is the only file this skill writes. Load and apply `engineering-principles` when available. The workflow below also works when this skill is installed on its own.

## Inspect the codebase

Clarify the requested outcome and what would count as success. Read the applicable repository instructions and trace the current behavior through the relevant entry points, owning modules, active callers, and tests. Identify what already supports the request and what must change. Ground the plan in files and symbols you inspected. Flag assumptions or open decisions that could change the approach.

## Choose the smallest complete change

Compare plausible approaches when they differ meaningfully in scope, behavior, or rollout risk. Recommend one and explain why. Prefer reusing existing code, patterns, and infrastructure. Keep domain behavior in the owning module and public interfaces as small as callers need. Justify any new abstraction, dependency, or public contract.

Preserve existing behavior and required validation, access controls, and error handling. Where relevant, account for existing data, migration order, cross-module callers, and the safe retirement of replaced code. Keep unrelated cleanup outside the plan.

## Write and present the handoff

Write a self-contained Markdown plan that another agent can use without the chat history. Include:

- The objective, acceptance criteria, and scope.
- The starting branch or revision when available, plus any local changes relevant to the plan.
- The recommended approach and why it fits the codebase.
- Ordered implementation steps with repository-relative paths, relevant symbols, and dependencies. Label proposed files as new.
- The build and test checks the implementer should run, with the expected behavior those checks should prove.
- Material risks, assumptions, and open decisions.

Save the handoff at the requested path or in the repository's established location for plans. Otherwise, save it as `implementation-plan-<topic>.md` at the repository root. Preserve existing files unless the user asks to update one.

Display the plan in chat and link to the saved Markdown file. Stop after delivering both.
