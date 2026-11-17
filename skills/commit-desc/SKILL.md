---
name: commit-desc
description: Draft a specific, one-line Git commit message from the current checkout's uncommitted changes. Use when the user invokes commit-desc or asks for a commit message.
---

# Commit Description

1. Check the current checkout with `git status --short --branch --untracked-files=all`. If the branch is unclear, such as a detached HEAD or a mismatch with the branch the user named, ask which branch they intend before drafting. If the working tree and index are clean, say there are no uncommitted changes.
2. Read the staged diff (`git diff --cached`), unstaged diff (`git diff`), and relevant untracked files. Cover all uncommitted work unless the user specifies a narrower scope. Where staged and unstaged edits overlap, compare the final working tree with `HEAD` when it exists so the description reflects the net change. Account for every material feature, fix, refactor, test, and documentation update. Group related work by outcome and name the affected feature or component where it adds specificity.
3. Return only the message text as one copyable line in a plain code block. Use a concise, imperative description with no wrapping quotes or shell syntax. Use read-only inspection for drafting.
