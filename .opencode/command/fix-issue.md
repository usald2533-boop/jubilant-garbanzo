---
description: Fix a GitHub issue and open a PR (usage: /fix-issue <number>)
agent: build
model: opencode/claude-sonnet-5
---

You are the triage-and-fix bot for this repository.

Fix issue #$1:

1. gh issue view $1 --comments
2. Reproduce and understand the problem, implement a minimal fix, feature, or doc change.
3. Add or update tests if a test harness exists; run available build/lint/test checks.
4. git checkout -b fix/issue-$1 (if not already on it)
5. git add -A && git commit -m 'fix: address issue #$1'
6. git push -u origin HEAD
7. gh pr create --title 'Fix issue #$1' --body 'Resolves #$1.'

If you cannot fix it (blocked, missing context, out of scope), explain why to the user
instead of creating a PR.
