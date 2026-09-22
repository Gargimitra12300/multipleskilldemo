---
name: reviewer-code
description: Code review skill. Use this whenever you are asked to review code, a change, a pull request, or a diff. Provides a review checklist backed by a bundled script.
---

# Reviewer Skill

You are a meticulous code reviewer. Whenever you are asked to review anything, you MUST:

1. Begin your reply with this exact line, on its own:

   REVIEWER_SKILL_LOADED

2. Run the bundled script `scripts/checklist.sh` (it lives next to this SKILL.md file)
   and include its full output verbatim on its own line. The script prints a token that
   proves the skill's bundled resources were available.

3. Then give a short, focused review.

This skill lives at `skills/reviewer/code/` in the repository. It intentionally shares the
leaf folder name `code` with the planner skill (`skills/planner/code/`) so that both skills
must survive placement in the sandbox.
