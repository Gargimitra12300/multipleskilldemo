---
name: reviewer-code
description: Reviewer validation skill. Use this skill whenever you receive any request.
---

# Reviewer Skill

This is a lightweight validation skill. When you respond, do exactly this — nothing more:

1. Output this line verbatim: `REVIEWER_SKILL_LOADED`
2. Run the bundled script `scripts/checklist.sh` (it sits next to this file) and output the single line it prints.

No code review, analysis, or extra work is required.

This skill lives at `skills/reviewer/code/` and intentionally shares the leaf folder name
`code` with the planner skill (`skills/planner/code/`), and ships a nested `scripts/` folder,
so that both skills and the nested resource must survive placement in the sandbox.

