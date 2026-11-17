---
name: engineering-principles
description: Apply project-neutral engineering principles when planning, implementing, or reviewing code changes that involve scope, module ownership, compatibility, or verification. Use when the user invokes engineering-principles or the task calls for these decisions.
---

# Engineering Principles

Strictly apply every relevant principle throughout the current task. Use these principles to choose an approach, evaluate tradeoffs, and check the result. Follow explicit user instructions and documented project requirements. Flag any conflict that materially affects the work.

1. **Start with the code that exists.** Follow the repository’s instructions and trace the relevant entry points, owning modules, active callers, and tests. When several approaches are viable, compare them by how much behavior, how many contracts, and how much operational complexity they would change.

2. **Choose the smallest complete change.** Prefer existing code and project patterns, then standard-library features or existing infrastructure, then a small direct implementation. Add abstractions, dependencies, or configuration only when they solve a concrete need. Preserve required validation, security, error handling, and verification.

3. **Put feature behavior in the module that owns it.** Keep public APIs small and expose complete operations. Keep validation, normalization, business rules, state transitions, and persistence details behind those APIs. Have other modules call the owning module’s API.

4. **Keep infrastructure generic.** Let transport adapters handle input and output, shared infrastructure provide reusable operations, and feature modules coordinate business workflows. Use the data store for schema, integrity constraints, indexes, and access controls. Follow the project’s established architecture when it deliberately assigns responsibilities differently.

5. **Establish identity at the trust boundary.** Verify identity through the existing authentication boundary and pass trusted context into feature operations. Enforce access through the project’s designated authorization mechanisms. Derive ownership and tenant scope from trusted context whenever those values determine access.

6. **Evolve data deliberately.** Add only the schema and permissions the feature needs. Prefer additive migrations for deployed systems, preserve applied migration history, and plan for existing data. When a change crosses module boundaries, identify affected callers, permissions, and rollout order so the full workflow keeps working through the transition.

7. **Retire replaced code once callers have moved.** When the task replaces a capability, account for active callers, old wiring, obsolete tests, and documentation. Keep temporary compatibility only when a real migration need warrants it, and give it a removal condition.

8. **Define done in observable terms.** Specify what users or callers should see and which checks will prove it. Cover the normal path and material failure, access-control, or state-transition cases through the relevant entry points. Name the build and test checks to run, and record what remains unverified.
