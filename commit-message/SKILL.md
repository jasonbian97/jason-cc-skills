---
name: commit-message
description: >
  Review code changes and generate a concise, informative git commit message. Use when the user
  asks for a commit message, wants help describing changes for a commit, says "/commit-message",
  or asks to review changes for committing. Triggers on: "commit message", "write a commit",
  "what should I commit", "describe these changes", "draft commit", or any request to summarize
  staged/unstaged git changes into a message.
---

# Commit Message Generator

Review git changes and output a ready-to-use commit message. Do NOT run `git commit` — only supply the message text. Do NOT append a signature or co-author line.

## Workflow

1. Run `git status` (never use `-uall`) to see changed files
2. Run `git diff` and `git diff --cached` to see unstaged and staged changes
3. Focus on staged changes if any exist; otherwise cover all modifications
4. Run `git log --oneline -10` to match the repo's existing commit style

## Message Format

- One summary line in imperative mood, max 72 chars
- Optionally a blank line followed by bullet-point body
- Classify: add (new), update (enhancement), fix (bug), refactor, docs, chore
- Focus on **why** over **what**
- No trailing period on summary line
- No signature, co-author, or sign-off
- Output in a fenced code block for easy copying
