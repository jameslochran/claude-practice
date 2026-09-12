---
description: Summarize what changed in this repo over the last day, based on recent git commits
---

Run `git log --since="24 hours ago" --oneline --all` (and `git log --since="24 hours ago" --stat --all` if you need more detail on which files changed) to gather commits from the last day across all branches.

Then produce a short standup-style summary:

- Group related commits together rather than listing them one by one.
- Call out anything notable: new features, bug fixes, docs-only changes, or database/config changes that need review (per this repo's `CLAUDE.md`).
- If there are no commits in the last 24 hours, say so plainly instead of padding the summary.

Keep the summary tight — a few bullet points, not a full commit-by-commit narration.
