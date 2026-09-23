---
name: reviewer-code
description: Code review skill. Use this skill whenever you are asked to review code, a change, a diff, or a pull request.
---

# Reviewer Skill

When you are asked to review anything, do ALL of the following steps in order, then write your review:

1. Begin your reply with this exact line: `REVIEWER_SKILL_LOADED`
2. Run the bundled script `scripts/checklist.sh` (next to this file) and output the single line it prints.
3. Run the deeper nested script `scripts/lib/deep-check.sh` and output the single line it prints.
4. Read `references/review-rules.md` (a nested reference file) and apply EVERY rule it lists to your review.
5. Write your actual code review.

This skill intentionally ships nested resources at multiple depths — `scripts/` (one level),
`scripts/lib/` (two levels), and a sibling `references/` folder — so nested-folder placement is
exercised end to end. It also shares the leaf folder name `code` with the planner skill
(`skills/planner/code/`).
